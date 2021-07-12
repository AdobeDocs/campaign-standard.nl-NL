---
solution: Campaign Standard
product: campaign
title: Pushtracking implementeren
description: In dit document kunt u controleren of pushmeldingen correct zijn geïmplementeerd op iOS en Android.
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
feature: Instantie-instellingen
role: Admin
level: Experienced
exl-id: 950d24e2-358f-44f8-98ea-643be61d4573
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '951'
ht-degree: 1%

---

# Pushtracking implementeren {#push-tracking}

## Over het bijhouden van push {#about-push-tracking}

Om ervoor te zorgen dat het pushbericht volledig is ontwikkeld, moet u ervoor zorgen dat het volgende gedeelte correct is geïmplementeerd, aangezien niet elke pushmelding tracking ingeschakeld heeft. Om dit in te schakelen, moeten ontwikkelaars identificeren welke leveringen tracering ingeschakeld hebben, verzendt Adobe Campaign Standard een markering met de naam `_acsDeliveryTracking` met twee waarden **on** of **off**. De ontwikkelaar van de app dient alleen een aanvraag voor bijhouden te verzenden bij leveringen waarvoor de variabele is ingesteld op **on**.

>[!IMPORTANT]
>
>Deze variabele is niet beschikbaar voor leveringen die zijn ingesteld vóór de release 21.1 of voor leveringen met aangepaste sjablonen.

De functie Push Tracking bestaat uit drie typen:

* **Push Impressions**  - Wanneer een pushmelding aan het apparaat is afgeleverd en op het meldingscentrum zit, maar helemaal niet is aangeraakt.  Dit wordt als een indruk beschouwd.  In de meeste gevallen zouden de indrukkingsaantallen gelijkaardig moeten zijn als niet het zelfde als het geleverde aantal. Het zorgt ervoor dat het apparaat het bericht kreeg en die informatie terug naar de server terugbracht.

* **Druk op Klikken**  - wanneer een pushmelding aan het apparaat is bezorgd en de gebruiker op het apparaat heeft geklikt.  De gebruiker wilde de melding bekijken (die op zijn beurt weer naar Open Push-tracking gaat) of het bericht negeren.

* **Push Open**  - Als een pushmelding aan het apparaat is afgeleverd en de gebruiker op het bericht heeft geklikt dat de app moet worden geopend.  Dit is gelijkaardig aan de Duw klikt behalve zal een Duw Open niet teweeggebracht worden als het bericht werd verworpen.

Voor het implementeren van tracering voor Campaign Standard moet de mobiele app de Mobile SDK bevatten. Deze SDK is beschikbaar op Adobe Mobile Services. Raadpleeg [deze pagina](../../administration/using/configuring-a-mobile-application.md) voor meer informatie.

Om het volgen informatie te verzenden zijn er drie variabelen die moeten worden verzonden. Twee die deel van de gegevens uitmaken die van Campaign Standard en een actievariabele worden ontvangen die of het **Indrukking**, **Click** of **Open** dicteren.

| Variabele | Waarde |
|:-:|:-:|
| broadlogId | _mId van gegevens |
| deliveryId | _dId van gegevens |
| action | 1 voor Openen, 2 voor Klikken en 7 voor Impressie |

## Implementatie voor Android {#implementation-android}

### Hoe u push-tracking implementeert {#push-impression-tracking-android}

Voor het volgen van de indruk, zult u waarde &quot;7&quot;voor actie moeten verzenden wanneer het roepen van **[!UICONTROL trackAction()]** functie.

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
    if (deliveryId != null && messageId != null && acsDeliveryTracking.equals("on")) {
                contextData.put("deliveryId", deliveryId);
                contextData.put("broadlogId", messageId);
                contextData.put("action", "7");
                MobileCore.trackAction("tracking", contextData);
    }
  }
}
```

### Klikspatiëring implementeren {#push-click-tracking-android}

Voor klik het volgen, zult u waarde &quot;2&quot;voor actie moeten verzenden wanneer het roepen van **[!UICONTROL trackAction()]** functie.

Om te volgen klik, moeten twee scenario&#39;s worden behandeld:

* De gebruiker ziet het bericht maar wist het.
* De gebruiker ziet de melding en klikt erop om deze om te zetten in een open tracking.

Om dit te behandelen, moet u twee Intenten gebruiken: een voor het klikken op de melding en een andere voor het negeren van de melding.

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

Als u de **[!UICONTROL BroadcastReceiver]** wilt laten werken, moet u deze registreren bij **[!UICONTROL AndroidManifest.xml]**

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
            MobileCore.trackAction("tracking", contextData);
        }
    }
}
```

### Openbare tracering implementeren {#push-open-tracking-android}

U moet &quot;1&quot; en &quot;2&quot; verzenden omdat de gebruiker op een melding moet klikken om de app te openen. Als de app niet wordt gestart/geopend via pushberichten, vinden er geen gebeurtenissen voor het bijhouden van de app plaats.

Als u het openen wilt bijhouden, moet u Intent maken. Met Intentobjecten kan Android OS de methode aanroepen wanneer bepaalde handelingen zijn uitgevoerd. Klik in dit geval op het bericht om de app te openen.

Deze code is gebaseerd op de implementatie van het bijhouden van de klikindruk. Als **[!UICONTROL Intent]** is ingesteld, moet u nu trackinggegevens terugsturen naar Adobe Campaign Standard. In dit geval moet u **[!UICONTROL Open Intent]** instellen om te worden geopend voor een bepaalde weergave in uw app. Hierbij wordt de methode onResume aangeroepen met de meldingsgegevens in **[!UICONTROL Intent Object]**.

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
 
            //Send Click Tracking since the user did click on the notification
            contextData.put("action", "2");
            MobileCore.trackAction("tracking", contextData);
 
            //Send Open Tracking since the user opened the app
            contextData.put("action", "1");
            MobileCore.trackAction("tracking", contextData);
        }
    }
}
```

## Implementatie voor iOS {#implementation-iOS}

### Hoe u push-tracking implementeert {#push-impression-tracking-iOS}

Voor het volgen van de indruk, zult u waarde &quot;7&quot;voor actie moeten verzenden wanneer het roepen van **[!UICONTROL trackAction()]** functie.

Als u wilt weten hoe iOS-meldingen werken, moeten de drie statussen van een app gedetailleerd zijn:

* **Voorgrond**: als de app momenteel actief is en momenteel op het scherm wordt weergegeven (op de voorgrond).
* **Achtergrond**: wanneer de app is niet op het scherm wordt weergegeven, maar het proces niet wordt gesloten. Wanneer u dubbelklikt op de knop Home, worden gewoonlijk alle apps op de achtergrond weergegeven.
* **Uit/gesloten**: een app waarvan het proces is gedood.

Als een app wordt gesloten, roept Apple de app pas aan nadat de app opnieuw is gestart. Dit betekent dat u niet kunt weten wanneer de melding is ontvangen op iOS.

Als u **[!UICONTROL Impression]** wilt bijhouden terwijl de app op de achtergrond wordt uitgevoerd, moeten we **[!UICONTROL Content-Available]** verzenden om de app te laten weten dat een tracering moet worden uitgevoerd.

>[!CAUTION]
>
>iOS-impressietracering is niet correct en moet niet als betrouwbaar worden beschouwd.

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
               ADBMobile.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"7"])
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
             ADBMobile.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"7"])
        }
        completionHandler([.alert,.sound])
    }
```

### Klikspatiëring implementeren {#push-click-tracking-iOS}

Voor klik het volgen, zult u waarde &quot;2&quot;voor actie moeten verzenden wanneer het roepen van **[!UICONTROL trackAction()]** functie.
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

Dan om **[!UICONTROL Dismiss]** te behandelen en een het volgen info te verzenden moet u het volgende toevoegen:

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
                ADBMobile.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
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
                ADBMobile.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
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
                ADBMobile.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
                ADBMobile.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"1"])
            }
        }
        completionHandler()
    }
}
```
