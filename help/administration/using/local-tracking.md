---
title: Push tracking implementeren
description: In dit document kunt u controleren of pushmeldingen correct zijn geïmplementeerd op iOS en Android.
page-status-flag: never-activated
uuid: 961aaeb5-6948-4fd2-b8d7-de4510c10566
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: push-notifications
discoiquuid: 23b4212e-e878-4922-be20-50fb7fa88ae8
context-tags: mobileApp,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d0a0c59763af8babc9701206cc39fe41b98e0cd4
workflow-type: tm+mt
source-wordcount: '726'
ht-degree: 0%

---


# Lokale tracering implementeren {#local-tracking}

## Lokale tracering {#about-local-tracking}

Leer op deze pagina hoe u ervoor kunt zorgen dat het bijhouden van lokale meldingen correct is geïmplementeerd. Merk op dat dit impliceert dat het lokale bericht reeds is gevormd.

Het bijhouden van lokale meldingen kan in drie typen worden gesplitst:

* **Lokale indrukken** - Wanneer een lokale melding aan het apparaat is afgeleverd en op het kennisgevingscentrum zit, maar helemaal niet is aangeraakt. In de meeste gevallen zou het aantal indrukkingen gelijk moeten zijn, zo niet het zelfde als het geleverde aantal. Het zorgt ervoor dat het apparaat het bericht kreeg en dat de informatie terug naar de server.

* **Lokale klik** - wanneer een lokaal bericht aan het apparaat is geleverd en de gebruiker op het apparaat heeft geklikt. De gebruiker wilde het bericht bekijken (dat op zijn beurt naar het lokale open volgen zal bewegen) of het bericht sluiten.

* **Lokale open** - wanneer een lokaal bericht aan het apparaat is geleverd en de gebruiker op het bericht heeft geklikt dat de toepassing de open veroorzaakt. Dit is vergelijkbaar met de lokale klik, maar een lokaal geopend bericht wordt niet geactiveerd als het bericht is gesloten.

Voor het implementeren van tracering voor Adobe Campaign Standard moet de mobiele toepassing de Mobile SDK opnemen in de toepassing. Deze SDK&#39;s zijn beschikbaar in [!DNL Adobe Mobile Services].

Voor het verzenden van trackinggegevens zijn er drie variabelen die moeten worden verzonden: twee maken deel uit van de gegevens die van Adobe Campaign worden ontvangen, en de andere is een handelingsvariabele die bepaalt of het een indruk, een klik of een open is.

| Variabele | Waarde |
| :-: | :-: |
| deliveryId | &quot;deliveryId&quot; uit binnenkomende gegevens (vergelijkbaar met &#39;push tracking&#39; waar&#39;_dld&#39; wordt gebruikt) |
| broadlogId | &quot;broadlogId&quot; van binnenkomende gegevens (vergelijkbaar met &#39;push tracking&#39; wanneer &#39;_mld&#39; wordt gebruikt) |
| action | &quot;1&quot; voor Openen, &quot;2&quot; voor Klikken en &quot;7&quot; voor Impressie |

## Lokale interimtracering implementeren {#implement-local-impression-tracking}

Voor het bijhouden van de indruk moet u waarde &quot;7&quot; voor actie verzenden wanneer u de functies collectMessageInfo() of trackAction() aanroept.

### Voor Android {#implement-local-impression-tracking-android}

De Adobe Experience Platform Mobile SDK start de imitatie bijhouden voor lokale meldingen bij het activeren ervan.

### Voor iOS {#implement-local-impression-tracking-ios}

Als u wilt uitleggen hoe u importeert hoe u impressietracering toepast, moeten we de drie statussen van een toepassing begrijpen:

* **Voorgrond**: als de toepassing momenteel actief is en op het scherm op de voorgrond.

* **Achtergrond**: als de toepassing niet op het scherm wordt weergegeven, maar het proces ook niet wordt afgesloten. Wanneer u dubbelklikt op de knop Home, worden gewoonlijk alle toepassingen op de achtergrond weergegeven.

* **Uit/Gesloten**: wanneer het proces van de toepassing is gedood. Als een toepassing wordt gesloten, roept Apple deze pas aan nadat de toepassing opnieuw is gestart. Dit betekent dat u nooit echt kunt weten wanneer het bericht op iOS is ontvangen.

Als u wilt dat het bijhouden van de indruk nog steeds werkt terwijl de toepassing zich op de achtergrond bevindt, moet u &quot;Content-Available&quot; verzenden om de toepassing te laten weten dat het bijhouden van de inhoud moet worden uitgevoerd.

De Adobe Experience Platform Mobile SDK start de imitatie bijhouden voor lokale meldingen bij het activeren ervan.

>[!CAUTION]
>
>iOS-impressietracering is niet correct en moet niet betrouwbaar worden bekeken.

## Klikken bijhouden implementeren {#implementing-click-tracking}

Voor het volgen van klik, moet u waarde &quot;2&quot;voor actie verzenden wanneer het roepen van collectMessageInfo () of trackAction () functies.

### Voor Android {#implement-click-tracking-android}

Om te volgen klik, moeten twee scenario&#39;s worden behandeld:

* De gebruiker ziet het bericht maar wist het.

* De gebruiker ziet het bericht en klikt erop, dit zal aan open het volgen draaien.

Het eerste scenario van klik wordt gevolgd door Adobe Experience Platform Mobile SDK.

### Voor iOS {#implement-click-tracking-ios}

```
// AppDelegate.swift
...
import os.log
import UserNotifications
...
  
func registerForPushNotifications() {
        let center = UNUserNotificationCenter.current()
        center.delegate = notificationDelegate
        //Here we are creating a new Category that allows us to handle Dismiss Actions
        let defaultCategory = UNNotificationCategory(identifier: "DEFAULT", actions: [], intentIdentifiers: [], options: .customDismissAction)
        //Add it to our array of Category, in this case we only have one
        center.setNotificationCategories([defaultCategory])
        center.requestAuthorization(options: [.alert, .sound, .badge]) {
            (granted, error) in
            os_log("Permission granted: %{public}@", type:. debug, granted.description)
            if error != nil {
                return
            }
            if granted {
                os_log("Notifications allowed", type: .debug)
            }
            else {
                os_log("Notifications denied", type: .debug)
            }
  
            // 2. Attempt registration for remote notifications on the main thread
            DispatchQueue.main.async {
                UIApplication.shared.registerForRemoteNotifications()
            }
        }
    }
```

Vervolgens moet u het volgende toevoegen om het ontslag te verwerken en trackinggegevens te verzenden:

```
func userNotificationCenter(_ center: UNUserNotificationCenter, didReceive response: UNNotificationResponse, withCompletionHandler completionHandler: @escaping () -> Void) {
        let userInfo = response.notification.request.content.userInfo
        switch response.actionIdentifier {
        case UNNotificationDismissActionIdentifier:
            print("Dismiss Action")
            let deliveryId = userInfo["deliveryId"] as? String
            let broadlogId = userInfo["broadlogId"] as? String
            if (deliveryId != nil && broadlogId != nil) {
                // If you're using  ACPCore v2.3.0 or later, use the line below.
                ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
                // Else comment out the above line and uncomment the line below
                // ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
            }
        default:
            ////MORE CODE
        }
        completionHandler()
    }
```

## Openbare tracering implementeren {#implement-open-tracking}

U moet &quot;1&quot; en &quot;2&quot; verzenden omdat de gebruiker op het bericht moet klikken om de toepassing te openen. Als de toepassing niet via een lokale melding wordt gestart/geopend, vinden er geen gebeurtenissen tracking plaats.

### Voor Android {#implement-open-tracking-android}

Om open te volgen, moeten wij intent creëren. Met intentieobjecten kan het Android-besturingssysteem de methode aanroepen wanneer bepaalde handelingen zijn uitgevoerd. Klik in dit geval op het bericht om de toepassing te openen.

Deze code is gebaseerd op de implementatie van het bijhouden van de klikindruk. Als de intentie is ingesteld, moet u nu trackinggegevens terugsturen naar Adobe Campaign. In dit geval wordt Android View([!DNL Activity]) die de melding heeft geactiveerd, geopend of op voorgrond geplaatst als gevolg van de klik door de gebruiker. Het intent-object in [!DNL Activity] bevat de berichtgegevens die kunnen worden gebruikt om het openen bij te houden.

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
        //Looks it was opened based on the notification, lets get the tracking we passed on.
        Map<String, String> notificationData = (Map<String, Object>)data.getSerializableExtra("NOTIFICATION_USER_INFO");
        String deliveryId = (String)notificationData.get("deliveryId");
        String messageId = (String)notificationData.get("broadlogId");
  
  
  
        if (deliveryId != null && messageId != null) {
            HashMap<String, String> contextData = new HashMap<>();
            contextData.put("deliveryId", deliveryId);
            contextData.put("broadlogId", messageId);
  
            //Send Click Tracking since the user did click on the notification
            contextData.put("action", "2");
            // If you're using  ACPCore v1.4.0 or later, use the next line.
            MobileCore.collectMessageInfo(contextData);
            // Else comment out the above line and uncomment the line below
            // MobileCore.trackAction("tracking", contextData);
  
            //Send Open Tracking since the user opened the app
            contextData.put("action", "1");
            // If you're using  ACPCore v1.4.0 or later, use the next line.
            MobileCore.collectMessageInfo(contextData);
            // Else comment out the above line and uncomment the line below
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
  
    // Called when user clicks the local notification or also called from willPresent()
    func userNotificationCenter(_ center: UNUserNotificationCenter, didReceive response: UNNotificationResponse, withCompletionHandler completionHandler: @escaping () -> Void) {
  
        let userInfo = response.notification.request.content.userInfo
        os_log("App push data %{public}@, in userNotificationCenter:didReceive()", type: .debug, userInfo)
        switch response.actionIdentifier {
        case UNNotificationDismissActionIdentifier:
            //This is to handle the Dismiss Action
            let deliveryId = userInfo["deliveryId"] as? String
            let broadlogId = userInfo["broadlogId"] as? String
            if (deliveryId != nil && broadlogId != nil) {
            // If you're using  ACPCore v2.3.0 or later, use the line below.
                ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
            // Else comment out the above line and uncomment the line below
            // ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
            }
        default:
            //This is to handle the tracking when the app opens
            let deliveryId = userInfo["deliveryId"] as? String
            let broadlogId = userInfo["broadlogId"] as? String
            if (deliveryId != nil && broadlogId != nil) {
               // If you're using  ACPCore v2.3.0 or later, use the line below.
               ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
               ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"1"])
               // Else comment out the above line and uncomment the line below
               // ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
               // ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"1"])
            }
        }
        completionHandler()
    }
}
```
