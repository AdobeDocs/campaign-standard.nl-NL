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
source-git-commit: efb1f14e0094e200d186423f98bfad65d25cfab2

---


# Push tracking implementeren {#push-tracking}

## Over het bijhouden van push {#about-push-tracking}

Om ervoor te zorgen dat het pushbericht volledig is ontwikkeld, moet u ervoor zorgen dat het trackinggedeelte correct is geïmplementeerd.

Met de volgende stappen kunt u controleren of de functie voor het bijhouden van pushmeldingen correct is geïmplementeerd. Hierbij wordt ervan uitgegaan dat u de eerste onderdelen van de implementatie van pushberichten al hebt geïmplementeerd: De gebruiker van de app registreren en een pushmelding afhandelen.

De functie Push Tracking bestaat uit drie typen:

* **Push Impressions** - Wanneer een pushmelding is afgeleverd aan het apparaat en op het meldingscentrum zit, maar helemaal niet is aangeraakt.  Dit wordt als een indruk beschouwd.  In de meeste gevallen zouden de indrukkingsaantallen gelijkaardig moeten zijn als niet het zelfde als het geleverde aantal. Het zorgt ervoor dat het apparaat het bericht kreeg en die informatie terug naar de server terugbracht.

* **Push Click** - Wanneer een pushmelding aan het apparaat is afgeleverd en de gebruiker op het apparaat heeft geklikt.  De gebruiker wilde de melding bekijken (die op zijn beurt weer naar Open Push-tracking gaat) of het bericht negeren.

* **Push Open** - Wanneer een pushmelding aan het apparaat is geleverd en de gebruiker op het bericht heeft geklikt dat de app moet worden geopend.  Dit is gelijkaardig aan de Duw klikt behalve zal een Duw Open niet teweeggebracht worden als het bericht werd verworpen.

Voor het implementeren van tracering voor Campagnestandaard moet de mobiele app de Mobile SDK bevatten. Deze SDK is beschikbaar op Adobe Mobile Services.

Om het volgen informatie te verzenden zijn er drie variabelen die moeten worden verzonden. Twee die deel van de gegevens uitmaken die van de Norm van de Campagne en een actievariabele worden ontvangen die of het een **Indrukking**, **Klik** of **Open** dicteert.

| Variabele | Waarde |
|:-:|:-:|
| broadlogId | _mId van gegevens |
| deliveryId | _dId van gegevens |
| action | 1 voor Openen, 2 voor Klikken en 7 voor Impressie |

## Implementatie voor Android {#implementation-android}

### Hoe u push-tracking implementeert {#push-impression-tracking-android}

Voor het bijhouden van de indruk moet u waarde &quot;7&quot; verzenden voor actie wanneer u de functie trackAction() aanroept.

```
@Override
public void onMessageReceived(RemoteMessage remoteMessage) {
....{Handle push messages}....
  if (data.size() > 0) {
    String deliveryId = data.get("_dId");
    String messageId = data.get("_mId");
    HashMap<String, String> contextData = new HashMap<>();
    if (deliveryId != null && messageId != null) {
                contextData.put("deliveryId", deliveryId);
                contextData.put("broadlogId", messageId);
                contextData.put("action", "7");
                MobileCore.trackAction("tracking", contextData);
    }
  }
}
```

### Klikspatiëring implementeren {#push-click-tracking-android}

Als u op &#39;tracking&#39; klikt, moet u de waarde &#39;2&#39; verzenden voor de handeling wanneer u de functie trackAction() aanroept.

Om te volgen klik, moeten twee scenario&#39;s worden behandeld:

* De gebruiker ziet het bericht maar wist het.
* De gebruiker ziet de melding en klikt erop om deze om te zetten in een open tracking.

Om dit te behandelen, moet u twee Intenten gebruiken: een voor het klikken op de melding en een andere voor het negeren van de melding.

MyFirebaseMessagingService.java

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

De BroadcastReceiver werkt alleen als u deze registreert bij AndroidManifest.xml

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
  
        HashMap<String, Object> contextData = new HashMap<>();
  
        //We only send the click tracking since the user dismissed the notification
        if (deliveryId != null && messageId != null) {
            contextData.put("deliveryId", deliveryId);
            contextData.put("broadlogId", messageId);
            contextData.put("action", "1");
            MobileCore.trackAction("tracking", contextData);
        }
    }
}
```

### Openbare tracering implementeren {#push-open-tracking-android}

U moet &quot;1&quot; en &quot;2&quot; verzenden omdat de gebruiker op een melding moet klikken om de app te openen. Als de app niet wordt gestart/geopend via pushberichten, vinden er geen gebeurtenissen voor het bijhouden van de app plaats.

Als u het openen wilt bijhouden, moet u Intent maken. Met Intentobjecten kan Android OS de methode aanroepen wanneer bepaalde handelingen zijn uitgevoerd. Klik in dit geval op het bericht om de app te openen.

Deze code is gebaseerd op de implementatie van het bijhouden van de klikindruk. Als Intentie is ingesteld, moet u de trackinggegevens nu terugsturen naar Campagne. In dit geval wordt de methode onResume MET DE meldingsgegevens in het Intent-object aangeroepen als u de Open Intent zo moet instellen dat deze voor een bepaalde weergave in uw app wordt geopend.

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
        String deliveryId = data.getString("_dId");
        String messageId = data.getString("_mId");
  
        HashMap<String, Object> contextData = new HashMap<>();
  
        if (deliveryId != null && messageId != null) {
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

Voor het bijhouden van de indruk moet u waarde &quot;7&quot; verzenden voor actie wanneer u de functie trackAction() aanroept.

Als u wilt weten hoe iOS-meldingen werken, moeten de drie statussen van een app gedetailleerd zijn:

* **Voorgrond**: als de app momenteel actief is en momenteel op het scherm wordt weergegeven (op de voorgrond).
* **Achtergrond**: wanneer de app is niet op het scherm wordt weergegeven, maar het proces niet wordt gesloten. Wanneer u dubbelklikt op de knop Home, worden gewoonlijk alle apps op de achtergrond weergegeven.
* **Uit/gesloten**: een app waarvan het proces is gedood.

Als een app wordt gesloten, roept Apple de app pas aan nadat de app opnieuw is gestart. Dit betekent dat u niet kunt weten wanneer de melding is ontvangen op iOS.

Om ervoor te zorgen dat het bijhouden van indrukken nog steeds werkt terwijl de app op de achtergrond wordt uitgevoerd, moeten we **Content-Available** verzenden om de app te laten weten dat het bijhouden van de inhoud moet worden uitgevoerd.

>[!CAUTION]
>
>iOS Impression Tracking is niet correct en moet niet als betrouwbaar worden beschouwd.

De volgende code is gericht op de achtergrond-app:

```
// In didReceiveRemoteNotification event handler in AppDelegate.m
  
//In order to handle push notification when only in background with content-available: 1
func application(_ application: UIApplication, didReceiveRemoteNotification userInfo: [AnyHashable : Any], fetchCompletionHandler completionHandler: @escaping (UIBackgroundFetchResult) -> Void) {
  
        //Check if the app is not in the foreground right now
        if(UIApplication.shared.applicationState != .active) {
            let deliveryId = userInfo["_dId"] as? String
            let broadlogId = userInfo["_mId"] as? String
            if (deliveryId != nil && broadlogId != nil) {
               ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"7"])
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
        if (deliveryId != nil && broadlogId != nil) {
             ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"7"])
        }
        completionHandler([.alert,.sound])
    }
```

### Klikspatiëring implementeren {#push-click-tracking-iOS}

Als u op &#39;tracking&#39; klikt, moet u de waarde &#39;2&#39; verzenden voor de handeling wanneer u de functie trackAction() aanroept.

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

Dan om de Ontslag te behandelen en een het volgen info te verzenden moet u het volgende toevoegen:

```
func userNotificationCenter(_ center: UNUserNotificationCenter, didReceive response: UNNotificationResponse, withCompletionHandler completionHandler: @escaping () -> Void) {
        let userInfo = response.notification.request.content.userInfo
        switch response.actionIdentifier {
        case UNNotificationDismissActionIdentifier:
            print("Dismiss Action")
            let deliveryId = userInfo["_dId"] as? String
            let broadlogId = userInfo["_mId"] as? String
            if (deliveryId != nil && broadlogId != nil) {
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
            if (deliveryId != nil && broadlogId != nil) {
                ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
            }
        default:
            //This is to handle the tracking when the app opens
            let deliveryId = userInfo["_dId"] as? String
            let broadlogId = userInfo["_mId"] as? String
            if (deliveryId != nil && broadlogId != nil) {
                ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
                ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"1"])
            }
        }
        completionHandler()
    }
}
```
