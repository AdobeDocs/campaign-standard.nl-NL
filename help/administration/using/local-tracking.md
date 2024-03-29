---
title: Lokale tracering implementeren
description: Leer hoe u ervoor kunt zorgen dat de functie voor het bijhouden van pushmeldingen correct is geïmplementeerd op iOS en Android
audience: channels
feature: Instance Settings
role: Admin
level: Experienced
exl-id: b983d0a3-c345-44d4-bc82-202bf6ed26ab
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '574'
ht-degree: 0%

---

# Lokale tracering implementeren {#local-tracking}

## Lokale tracering {#about-local-tracking}

Leer op deze pagina hoe u ervoor kunt zorgen dat het bijhouden van lokale meldingen correct is geïmplementeerd. Merk op dat dit impliceert dat het lokale bericht reeds is gevormd.

Het bijhouden van lokale meldingen kan in drie typen worden gesplitst:

* **Lokale indrukken** - Wanneer een lokale melding aan het apparaat is afgeleverd en in het meldingscentrum zit, maar helemaal niet is aangeraakt. In de meeste gevallen zou het aantal indrukkingen gelijk moeten zijn, zo niet het zelfde als het geleverde aantal. Het zorgt ervoor dat het apparaat het bericht kreeg en dat de informatie terug naar de server.

* **Lokale klik** - Wanneer een lokaal bericht aan het apparaat is afgeleverd en de gebruiker op het bericht heeft geklikt. De gebruiker wilde het bericht bekijken (dat op zijn beurt naar het lokale open volgen zal bewegen) of het bericht sluiten.

* **Lokale open** - Wanneer een lokaal bericht aan het apparaat is afgeleverd en de gebruiker op het bericht heeft geklikt dat de toepassing het openen veroorzaakt. Dit is vergelijkbaar met de lokale klik, maar een lokaal geopend bericht wordt niet geactiveerd als het bericht is gesloten.

Voor het implementeren van tracering voor Adobe Campaign Standard moet de mobiele toepassing de Mobile SDK opnemen in de toepassing. Deze SDK&#39;s zijn beschikbaar in [!DNL Adobe Mobile Services].

Om het volgen informatie te verzenden, zijn er drie variabelen die moeten worden verzonden: twee maken deel uit van de gegevens die van Adobe Campaign worden ontvangen en het andere is een actievariabele die of het een indruk, een klik of een open dicteert.

| Variabele | Waarde |
| :-: | :-: |
| deliveryId | `deliveryId` van binnenkomende gegevens (vergelijkbaar met &#39;push tracking&#39; waar `_dld` wordt gebruikt) |
| broadlogId | `broadlogId` van binnenkomende gegevens (vergelijkbaar met &#39;push tracking&#39; waar `_mld` wordt gebruikt) |
| action | &quot;1&quot; voor Openen, &quot;2&quot; voor Klikken en &quot;7&quot; voor Impressie |

## Lokale imitatie bijhouden {#implement-local-impression-tracking}

De Adobe Experience Platform Mobile SDK verzendt automatisch de impeilingsgebeurtenis voor zowel Android als iOS zonder extra configuratie.

## Klikken bijhouden implementeren {#implementing-click-tracking}

Voor klik het volgen moet u waarde &quot;2&quot;voor actie verzenden wanneer het roepen `collectMessageInfo()` of `trackAction()` functies.

### Voor Android {#implement-click-tracking-android}

Om kliks te volgen, moeten twee scenario&#39;s worden uitgevoerd:

* De gebruiker ziet het bericht maar wist het.

  Om te volgen klik in het geval van ontslagscenario, voeg de uitzendingsontvanger toe `NotificationDismissalHandler` in het AndroidManifest-bestand van uw toepassingsmodule.

  ```
  <receiver
  android:name="com.adobe.marketing.mobile.NotificationDismissalHandler">
  </receiver>
  ```

* De gebruiker ziet het bericht en klikt erop, dit zal aan open het volgen draaien.

  Dit scenario zou een klik en een open moeten veroorzaken. Het volgen van deze klik zal een deel van de implementatie nodig zijn om open te volgen. Zie [Openbare tracering implementeren](#implement-open-tracking).

### Voor iOS {#implement-click-tracking-ios}

Om de klik het volgen informatie te verzenden, moet u het volgende toevoegen:

```
class NotificationDelegate: NSObject, UNUserNotificationCenterDelegate {

   func userNotificationCenter(_ center: UNUserNotificationCenter, didReceive response: UNNotificationResponse, withCompletionHandler completionHandler: @escaping () -> Void) {
        let userInfo = response.notification.request.content.userInfo
        switch response.actionIdentifier {
        case UNNotificationDismissActionIdentifier:
            print("Dismiss Action")
            let deliveryId = userInfo["deliveryId"] as? String
            let broadlogId = userInfo["broadlogId"] as? String
            if (deliveryId != nil && broadlogId != nil) {
                
                //If you are using ACPCore v2.3.0 or later, use the next line.
                
                ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
                
                //Else comment out the above line and uncomment the line below
                
                // ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
            }
        default:
            
            ////MORE CODE
        }
        completionHandler()
    }
}
```

## Openstaande tracering implementeren {#implement-open-tracking}

U moet &quot;1&quot; en &quot;2&quot; verzenden omdat de gebruiker op het bericht moet klikken om de toepassing te openen. Als de toepassing niet via een lokale melding wordt gestart/geopend, vinden er geen gebeurtenissen tracking plaats.

### Voor Android {#implement-open-tracking-android}

Om open te houden, moeten we intent creëren. Met intentieobjecten kan het Android-besturingssysteem de methode aanroepen wanneer bepaalde handelingen zijn uitgevoerd. Klik in dit geval op het bericht om de toepassing te openen.

Deze code is gebaseerd op de implementatie van het bijhouden van de klikindruk. Als de intentie is ingesteld, moet je nu trackinggegevens terugsturen naar Adobe Campaign. In dit geval wordt Android View([!DNL Activity]) die de aanmelding heeft geactiveerd, wordt als gevolg van de klik door de gebruiker geopend of op voorgrond geplaatst. Het intentieobject in [!DNL Activity] bevat de berichtgegevens die kunnen worden gebruikt om open te volgen.

MainActivity.java (extends [!DNL Activity])

```
@Override
protected void onResume() {
    super.onResume();
    handleTracking();
}
 
 
private void handleTracking() {

    //Check to see if this view was opened based on a notification

    Intent intent = getIntent();
    Bundle data = intent.getExtras();
 
    if (data != null) {

        //Opened based on the notification, you must get the tracking that was passed on.

        Map<String, String> notificationData = (Map<String, Object>)data.getSerializableExtra("NOTIFICATION_USER_INFO");
        String deliveryId = (String)notificationData.get("deliveryId");
        String messageId = (String)notificationData.get("broadlogId");

        if (deliveryId != null && messageId != null) {
            HashMap<String, String> contextData = new HashMap<>();
            contextData.put("deliveryId", deliveryId);
            contextData.put("broadlogId", messageId);
 
            //Send click tracking since the user did click on the notification

            contextData.put("action", "2");

            //If you are using ACPCore v1.4.0 or later, use the next line.
    
            MobileCore.collectMessageInfo(contextData);

            //Else comment out the above line and uncomment the line below

            // MobileCore.trackAction("tracking", contextData);
 
            //Send open tracking since the user opened the app

            contextData.put("action", "1");

            //If you are using  ACPCore v1.4.0 or later, use the next line.

            MobileCore.collectMessageInfo(contextData);

            //Else comment out the above line and uncomment the line below

            // MobileCore.trackAction("tracking", contextData);
        }
    }
}
```

### Voor iOS {#implement-open-tracking-ios}

```
import os.log
import Foundation
import UserNotifications
import UserNotificationsUI
import ACPCore
 
class NotificationDelegate: NSObject, UNUserNotificationCenterDelegate {
 
    //Called when user clicks the local notification or also called from willPresent()

    func userNotificationCenter(_ center: UNUserNotificationCenter, didReceive response: UNNotificationResponse, withCompletionHandler completionHandler: @escaping () -> Void) {
 
        let userInfo = response.notification.request.content.userInfo
        os_log("App push data %{public}@, in userNotificationCenter:didReceive()", type: .debug, userInfo)
        switch response.actionIdentifier {
        case UNNotificationDismissActionIdentifier:

            //This is to handle the Dismiss action

            let deliveryId = userInfo["deliveryId"] as? String
            let broadlogId = userInfo["broadlogId"] as? String
            if (deliveryId != nil && broadlogId != nil) {

                //If you are using ACPCore v2.3.0 or later, use the next line.

                ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])

                //Else comment out the above line and uncomment the line below

                // ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
            }
        default:
            //This is to handle the tracking when the app opens
            let deliveryId = userInfo["deliveryId"] as? String
            let broadlogId = userInfo["broadlogId"] as? String
            if (deliveryId != nil && broadlogId != nil) {

               //If you are using ACPCore v2.3.0 or later, use the next line.

               ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
               ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"1"])

               //Else comment out the above line and uncomment the line below

               // ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
               // ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"1"])
            }
        }
        completionHandler()
    }
}
```
