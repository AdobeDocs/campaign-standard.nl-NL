---
title: Pushtracking implementeren
description: Leer hoe u ervoor kunt zorgen dat de functie voor het bijhouden van pushmeldingen correct is geïmplementeerd op iOS en Android
audience: channels
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 950d24e2-358f-44f8-98ea-643be61d4573
source-git-commit: acbe5f1990738f586e4310d13f0e19baab11d771
workflow-type: tm+mt
source-wordcount: '958'
ht-degree: 0%

---

# Pushtracking implementeren {#push-tracking}

## Over het bijhouden van push {#about-push-tracking}

Om ervoor te zorgen dat het pushbericht volledig is ontwikkeld, moet u ervoor zorgen dat het volgende gedeelte correct is geïmplementeerd, aangezien niet elke pushmelding tracking ingeschakeld heeft. Om dit mogelijk te maken, moeten ontwikkelaars weten welke leveringen &#39;tracking&#39; hebben ingeschakeld. Adobe Campaign Standard stuurt een markering met de naam `_acsDeliveryTracking` met twee waarden **op** of **uit**. De ontwikkelaar van de app moet alleen een aanvraag voor bijhouden verzenden bij leveringen waarvoor de variabele is ingesteld als **op**.

>[!IMPORTANT]
>
>Deze variabele is niet beschikbaar voor leveringen die zijn ingesteld vóór de release 21.1 of voor leveringen met aangepaste sjablonen.

De functie Push Tracking bestaat uit drie typen:

* **Push Impressions** - Wanneer een pushmelding aan het apparaat is afgeleverd en op het meldingscentrum zit, maar helemaal niet is aangeraakt.  Dit wordt als een indruk beschouwd.  In de meeste gevallen zouden de indrukkingsaantallen gelijkaardig moeten zijn als niet het zelfde als het geleverde aantal. Het zorgt ervoor dat het apparaat het bericht kreeg en die informatie terug naar de server terugbracht.

* **Klikken** - Wanneer een pushmelding naar het apparaat is gestuurd en de gebruiker op het apparaat heeft geklikt.  De gebruiker wilde de melding bekijken (die op zijn beurt weer naar Open Push-tracking gaat) of het bericht negeren.

* **Push Open** - Wanneer een pushmelding naar het apparaat is gestuurd en de gebruiker op het bericht heeft geklikt waardoor de app wordt geopend.  Dit is gelijkaardig aan de Duw klikt behalve zal een Duw Open niet teweeggebracht worden als het bericht werd verworpen.

Voor het implementeren van tracering voor Campaign Standard moet de mobiele app de SDK&#39;s van Adobe Experience Platform bevatten. Deze SDK&#39;s zijn beschikbaar in de [Adobe Experience Platform SDKs-documentatie](https://github.com/Adobe-Marketing-Cloud/acp-sdks).

Om het volgen informatie te verzenden zijn er drie variabelen die moeten worden verzonden. Twee die deel van de gegevens uitmaken van Campaign Standard en een actievariabele die dicteert of het een **Impressie**, **Klikken** of **Openen**.

| Variabele | Waarde |
|:-:|:-:|
| broadlogId | _mId van gegevens |
| deliveryId | _dId van gegevens |
| action | &quot;1&quot; voor Openen, &quot;2&quot; voor Klikken en &quot;7&quot; voor Impressie |

## Implementatie voor Android {#implementation-android}

### Hoe u push-tracking implementeert {#push-impression-tracking-android}

Voor het bijhouden van de indruk moet u de waarde &quot;7&quot; verzenden voor actie bij het aanroepen `collectMessageInfo()` of `trackAction()` functies.

Voor leveringen die zijn gemaakt vóór 21.1-release of leveringen met een aangepaste sjabloon, raadpleegt u deze [sectie](../../administration/using/push-tracking.md#about-push-tracking).

```
@Override
public void onMessageReceived(RemoteMessage remoteMessage) {
....{Handle push messages}....
  if (data.size() > 0) {
    String deliveryId = data.get("_dId");
    String messageId = data.get("_mId");
    String acsDeliveryTracking = data.get("_acsDeliveryTracking");
 
    /*
    This is to handle deliveries created before 21.1 release or deliveries with custom template
    where acsDeliveryTracking is not available.
    */
    if( acsDeliveryTracking == null ) {
        acsDeliveryTracking = "on";
    }
 
    HashMap<String, String> contextData = new HashMap<>();
    if( deliveryId != null && messageId != null && acsDeliveryTracking.equals("on")) {
      contextData.put("deliveryId", deliveryId);
      contextData.put("broadlogId", messageId);
      contextData.put("action", "7");

    //If you are using ACPCore v1.4.0 or later, use the next line.
      
      MobileCore.collectMessageInfo(contextData);
      
    //Else comment out the above line and uncomment the line below
        
    //MobileCore.trackAction("tracking", contextData) ;
    }
  }
}
```

### Klikspatiëring implementeren {#push-click-tracking-android}

Als u klikt op bijhouden, moet u waarde &quot;2&quot; verzenden voor actie bij het aanroepen `collectMessageInfo()` of `trackAction()` functies.
Om te volgen klik, moeten twee scenario&#39;s worden behandeld:

* De gebruiker ziet het bericht maar wist het.
* De gebruiker ziet de melding en klikt erop om deze om te zetten in een open tracking.

Om dit te behandelen, moet u twee Intenten gebruiken: voor het klikken van het bericht en een andere om het bericht te sluiten.

Voor leveringen die zijn gemaakt vóór 21.1-release of leveringen met een aangepaste sjabloon, raadpleegt u deze [sectie](../../administration/using/push-tracking.md#about-push-tracking).

**[!UICONTROL MyFirebaseMessagingService.java]**

```
private void sendNotification(Map<String, String> data) {
    Intent openIntent = new Intent(this, CollectPIIActivity.class);
    Intent dismissIntent = new Intent(this, NotificationDismissedReceiver.class);
    openIntent.addFlags(Intent.FLAG_ACTIVITY_CLEAR_TOP);
  
    //put the data map into the intent to track clickthroughs
    Bundle pushData = new Bundle();
    Set<String> keySet = data.keySet();
    for (String key : keySet) {
        pushData.putString(key, data.get(key));
    }
    openIntent.putExtras(pushData);
    dissmissIntent.putExtras(pushData);
  
  
    PendingIntent pendingIntent = PendingIntent.getActivity(this, 0, openIntent,
        PendingIntent.FLAG_UPDATE_CURRENT);
    PendingIntent onDismissPendingIntent = PendingIntent.getBroadcast(this.getApplicationContext(), 0, dismissIntent, 0);
  
    //<BUILD NOTIFICATION using notification builder>
    //Add both Intents to the notification
    notificationBuilder.setContentIntent(pendingIntent);
    notificationBuilder.setDeleteIntent(onDismissPendingIntent);
}
```

Om de **[!UICONTROL BroadcastReceiver]** om te kunnen werken, moet u het registreren bij **[!UICONTROL AndroidManifest.xml]**

```
<manifest>
    <application>
        <receiver android:name=".NotificationDismissedReceiver">
        </receiver>
    </application>
</manifest>
```

NotificationDismessedReceiver.java

```
public class NotificationDismissedReceiver extends BroadcastReceiver {
    private static final String TAG = NotificationDismissedReceiver.class.getSimpleName();
    @Override
    public void onReceive(Context context, Intent intent) {
        Bundle data = intent.getExtras();
        String deliveryId = data.getString("_dId");
        String messageId = data.getString("_mId");
        String acsDeliveryTracking = data.get("_acsDeliveryTracking");
         
        /*
        This is to handle deliveries created before 21.1 release or deliveries with custom template
        where acsDeliveryTracking is not available.
        */
        if( acsDeliveryTracking == null ) {
            acsDeliveryTracking = "on";
        }
 
        HashMap<String, Object> contextData = new HashMap<>();
 
        //We only send the click tracking since the user dismissed the notification
        if (deliveryId != null && messageId != null && acsDeliveryTracking.equals("on")) {
            contextData.put("deliveryId", deliveryId);
            contextData.put("broadlogId", messageId);
            contextData.put("action", "2");
            
        //If you are using ACPCore v1.4.0 or later, use the next line.
        
            MobileCore.collectMessageInfo(contextData);
            
        //Else comment out the above line and uncomment the line below
        
            //MobileCore.trackAction("tracking", contextData);
        }
    }
}
```

### Openbare tracering implementeren {#push-open-tracking-android}

U moet &quot;1&quot; en &quot;2&quot; verzenden omdat de gebruiker op een melding moet klikken om de app te openen. Als de app niet wordt gestart/geopend via pushberichten, vinden er geen gebeurtenissen voor het bijhouden van de app plaats.

Als u het openen wilt bijhouden, moet u Intent maken. Met Intentobjecten kan Android OS de methode aanroepen wanneer bepaalde handelingen zijn uitgevoerd. Klik in dit geval op het bericht om de app te openen.

Deze code is gebaseerd op de implementatie van het bijhouden van de klikindruk. Met **[!UICONTROL Intent]** Nu moet u trackinggegevens terugsturen naar Adobe Campaign Standard. In dit geval moet u de opdracht **[!UICONTROL Open Intent]** om voor een bepaalde mening in uw app te openen, zal dit de methode onResume met de berichtgegevens in roepen in **[!UICONTROL Intent Object]**.

Voor leveringen die zijn gemaakt vóór 21.1-release of leveringen met een aangepaste sjabloon, raadpleegt u deze [sectie](../../administration/using/push-tracking.md#about-push-tracking).

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
        //This was opened based on the notification, you need to get the tracking that was passed on.
        String deliveryId = data.getString("_dId");
        String messageId = data.getString("_mId");
        String acsDeliveryTracking = data.get("_acsDeliveryTracking");
        /*
        This is to handle deliveries created before 21.1 release or deliveries with custom template
        where acsDeliveryTracking is not available.
        */
        if( acsDeliveryTracking == null) {
            acsDeliveryTracking = "on";
        }
 
        HashMap<String, String> contextData = new HashMap<>();
 
        if (deliveryId != null && messageId != null && acsDeliveryTracking.equals("on")) {
            contextData.put("deliveryId", deliveryId);
            contextData.put("broadlogId", messageId);
            contextData.put("action", "2");
            
            //Send Click Tracking since the user did click on the notification
              
                //If you are using ACPCore v1.4.0 or later, use the next line.

                MobileCore.collectMessageInfo(contextData);
                  
                //Else comment out the above line and uncomment the line below
        
                //MobileCore.trackAction("tracking", contextData);
 
                //Send Open Tracking since the user opened the app
            
                contextData.put("action", "1");
                
                //If you are using ACPCore v1.4.0 or later, use the next line.

                MobileCore.collectMessageInfo(contextData);
                //Else comment out the above line and uncomment the line below
        
                //MobileCore.trackAction("tracking", contextData);
        }
    }
}
```

## Implementatie voor iOS {#implementation-iOS}

### Hoe u push-tracking implementeert {#push-impression-tracking-iOS}

Voor het bijhouden van de indruk moet u de waarde &quot;7&quot; verzenden voor actie bij het aanroepen `collectMessageInfo()` of `trackAction()` functies.

Om te begrijpen hoe iOS-meldingen werken, moeten de drie statussen van een app gedetailleerd zijn:

* **Voorgrond**: als de app momenteel actief is en momenteel op het scherm wordt weergegeven (op de voorgrond).
* **Achtergrond**: wanneer de app is niet op het scherm wordt weergegeven, maar het proces niet wordt gesloten. Wanneer u dubbelklikt op de knop Home, worden gewoonlijk alle apps op de achtergrond weergegeven.
* **Uit/gesloten**: een app waarvan het proces is gedood.

Om nog **[!UICONTROL Impression]** tracering werkt terwijl de app op de achtergrond is die we moeten verzenden **[!UICONTROL Content-Available]** om de app te laten weten , moet een tracering worden uitgevoerd .

>[!CAUTION]
>
> Als een app wordt gesloten, roept Apple de app pas aan nadat de app opnieuw is gestart. Dit betekent dat je niet weet wanneer de kennisgeving op iOS is ontvangen. </br> Daarom is het mogelijk dat de impressiemethode van iOS niet correct is en niet als betrouwbaar moet worden beschouwd.

Voor leveringen die zijn gemaakt vóór 21.1-release of leveringen met een aangepaste sjabloon, raadpleegt u deze [sectie](../../administration/using/push-tracking.md#about-push-tracking).

De volgende code is gericht op de achtergrond-app:

```
// In didReceiveRemoteNotification event handler in AppDelegate.m
 
//In order to handle push notification when only in background with content-available: 1
func application(_ application: UIApplication, didReceiveRemoteNotification userInfo: [AnyHashable : Any], fetchCompletionHandler completionHandler: @escaping (UIBackgroundFetchResult) -> Void) {
 
        //Check if the app is not in the foreground right now
        if(UIApplication.shared.applicationState != .active) {
            let deliveryId = userInfo["_dId"] as? String
            let broadlogId = userInfo["_mId"] as? String
            let acsDeliveryTracking = userInfo["_acsDeliveryTracking"] as? String
            /*
            This is to handle deliveries created before 21.1 release or deliveries with custom template where acsDeliveryTracking is not available.
            */
            if( acsDeliveryTracking == nil ) {
                acsDeliveryTracking = "on";
            }
            if (deliveryId != nil && broadlogId != nil && acsDeliveryTracking?.caseInsensitiveCompare("on") == ComparisonResult.orderedSame) {

            //If you are using ACPCore v2.3.0 or later, use the next line.

                ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"7"])
                
            //Else comment out the above line and uncomment the line below
        
                //ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"7"])
            }
        }
        completionHandler(UIBackgroundFetchResult.noData)
    }
```

De volgende code is gericht op de voorgrond-app:

```
// This will get called when the app is in the foreground
 
func userNotificationCenter(_ center: UNUserNotificationCenter, willPresent notification: UNNotification, withCompletionHandler completionHandler: @escaping (UNNotificationPresentationOptions) -> Void) {
 
 
        let userInfo = notification.request.content.userInfo
        let deliveryId = userInfo["_dId"] as? String
        let broadlogId = userInfo["_mId"] as? String
        let acsDeliveryTracking = userInfo["_acsDeliveryTracking"] as? String
        /*
        This is to handle deliveries created before 21.1 release or deliveries with custom template where acsDeliveryTracking is not available.
        */
        if( acsDeliveryTracking == nil ) {
            acsDeliveryTracking = "on";
        }
        if (deliveryId != nil && broadlogId != nil && acsDeliveryTracking?.caseInsensitiveCompare("on") == ComparisonResult.orderedSame) {

            //If you are using ACPCore v2.3.0 or later, use the next line.

                ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"7"])
                
            //Else comment out the above line and uncomment the line below
        
                //ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"7"])        
            }
        completionHandler([.alert,.sound])
    }
```

### Klikspatiëring implementeren {#push-click-tracking-iOS}

Als u klikt op bijhouden, moet u waarde &quot;2&quot; verzenden voor actie bij het aanroepen `collectMessageInfo()` of `trackAction()` functies.
Voor leveringen die zijn gemaakt vóór 21.1-release of leveringen met een aangepaste sjabloon, raadpleegt u deze [sectie](../../administration/using/push-tracking.md#about-push-tracking).

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

Wanneer u pushberichten verzendt, moet u nu een categorie toevoegen. In dit geval noemden we het &quot;DEFAULT&quot;.

![](assets/tracking_push.png)

Vervolgens kunt u de knop **[!UICONTROL Dismiss]** en verzend een volgende informatie u het volgende moet toevoegen:

```
func userNotificationCenter(_ center: UNUserNotificationCenter, didReceive response: UNNotificationResponse, withCompletionHandler completionHandler: @escaping () -> Void) {
        let userInfo = response.notification.request.content.userInfo
        switch response.actionIdentifier {
        case UNNotificationDismissActionIdentifier:
            print("Dismiss Action")
            let deliveryId = userInfo["_dId"] as? String
            let broadlogId = userInfo["_mId"] as? String
            let acsDeliveryTracking = userInfo["_acsDeliveryTracking"] as? String
            /*
            This is to handle deliveries created before 21.1 release or deliveries with custom template where acsDeliveryTracking is not available.
            */
            if( acsDeliveryTracking == nil ) {
                acsDeliveryTracking = "on";
            }
            if (deliveryId != nil && broadlogId != nil && acsDeliveryTracking?.caseInsensitiveCompare("on") == ComparisonResult.orderedSame) {

            //If you are using ACPCore v2.3.0 or later, use the next line.

                ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
                
            //Else comment out the above line and uncomment the line below
        
                //ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])   
            }
        default:
            ////MORE CODE
        }
        completionHandler()
    }
```

### Openbare tracering implementeren {#push-open-tracking-iOS}

U moet &quot;1&quot; en &quot;2&quot; verzenden omdat de gebruiker op een melding moet klikken om de app te openen. Als de app niet wordt gestart/geopend via pushberichten, vinden er geen gebeurtenissen voor het bijhouden van de app plaats.

Voor leveringen die zijn gemaakt vóór 21.1-release of leveringen met een aangepaste sjabloon, raadpleegt u deze [sectie](../../administration/using/push-tracking.md#about-push-tracking).

```
import Foundation
import UserNotifications
import UserNotificationsUI
 
class NotificationDelegate: NSObject, UNUserNotificationCenterDelegate {
 
    // Called when user clicks the push notification or also called from willPresent()
    func userNotificationCenter(_ center: UNUserNotificationCenter, didReceive response: UNNotificationResponse, withCompletionHandler completionHandler: @escaping () -> Void) {
 
        let userInfo = response.notification.request.content.userInfo
        os_log("App push data %{public}@, in userNotificationCenter:didReceive()", type: .debug, userInfo)
        switch response.actionIdentifier {
        case UNNotificationDismissActionIdentifier:
            //This is to handle the Dismiss Action
            let deliveryId = userInfo["_dId"] as? String
            let broadlogId = userInfo["_mId"] as? String
            let acsDeliveryTracking = userInfo["_acsDeliveryTracking"] as? String
            /*
            This is to handle deliveries created before 21.1 release or deliveries with custom template where acsDeliveryTracking is not available.
            */
            if( acsDeliveryTracking == nil ) {
                acsDeliveryTracking = "on";
            }
            if (deliveryId != nil && broadlogId != nil && acsDeliveryTracking?.caseInsensitiveCompare("on") == ComparisonResult.orderedSame) {

            //If you are using ACPCore v2.3.0 or later, use the next line.

                ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
                
            //Else comment out the above line and uncomment the line below
        
                //ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])

            }
        default:
            //This is to handle the tracking when the app opens
            let deliveryId = userInfo["_dId"] as? String
            let broadlogId = userInfo["_mId"] as? String
            let acsDeliveryTracking = userInfo["_acsDeliveryTracking"] as? String
            /*
            This is to handle deliveries created before 21.1 release or deliveries with custom template where acsDeliveryTracking is not available.
            */
            if( acsDeliveryTracking == nil ) {
                acsDeliveryTracking = "on";
            }
            if (deliveryId != nil && broadlogId != nil && acsDeliveryTracking?.caseInsensitiveCompare("on") == ComparisonResult.orderedSame) {
            //If you are using ACPCore v2.3.0 or later, use the next line.

                ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
                
            //Else comment out the above line and uncomment the line below
        
                //ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])                
                
            //If you are using ACPCore v2.3.0 or later, use the next line.

                ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"1"])
                
            //Else comment out the above line and uncomment the line below
        
                //ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"1"])
                
            }
        }
        completionHandler()
    }
}
```
