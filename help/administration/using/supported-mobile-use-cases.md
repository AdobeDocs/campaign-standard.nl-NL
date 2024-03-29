---
title: Kwesties voor mobiel gebruik die in Adobe Campaign Standard worden ondersteund met de SDK van Adobe Experience Platform
description: Leer hoe u problemen met mobiel gebruik kunt ondersteunen
audience: channels
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 3cd8d756-a271-4e53-8ed0-984ce20298bc
source-git-commit: 597ece8d833a216f0540f801461b08fdc9865024
workflow-type: tm+mt
source-wordcount: '852'
ht-degree: 0%

---

# Mobiele gebruiksscenario’s die worden ondersteund in Adobe Campaign Standard {#mobile-use-cases}

Op deze pagina vindt u de lijst met alle gevallen voor mobiel gebruik die worden ondersteund in [!DNL Adobe Campaign Standard] met de [!DNL Adobe Experience Platform SDKs]. Let op: als u deze gebruiksgevallen ondersteunt, moet u de [!DNL Adobe Experience Platform SDKs], [!DNL tags in Adobe Experience Platform], en [!DNL Adobe Campaign Standard]. Raadpleeg voor meer informatie hierover [page](../../administration/using/configuring-a-mobile-application.md).

Adobe Campaign Standard ondersteunt de volgende gebruiksgevallen:

* [Een mobiel profiel registreren in Campaign Standard](../../administration/using/supported-mobile-use-cases.md#register-mobile-profile)
* [Een pushtoken naar het Campaign Standard verzenden](../../administration/using/supported-mobile-use-cases.md#send-push-token)
* [Een mobiel profiel verrijken met aangepaste gegevens uit uw toepassing](../../administration/using/supported-mobile-use-cases.md#enrich-mobile-profile-custom)
* [Een mobiel profiel verrijken met levenscyclusgegevens van uw toepassing](../../administration/using/supported-mobile-use-cases.md#enrich-mobile-profile-lifecycle)
* [Gebruikersinteractie bijhouden met pushmeldingen](../../administration/using/supported-mobile-use-cases.md#track-user-push)
* [Een aangepaste gebeurtenis implementeren in uw mobiele app om In-App-berichten te activeren](../../administration/using/supported-mobile-use-cases.md#custom-event-inapp)
* [Koppelingsvelden instellen voor extra verificatie voor de profielsjabloon die is gebaseerd op In-App-berichten](../../administration/using/supported-mobile-use-cases.md#linkage-fields-inapp)

Voor het configureren van deze gebruiksgevallen hebt u de volgende extensies nodig:

* **[!DNL Adobe Campaign Standard]** <br>Om de uitbreiding van het Campaign Standard te installeren en te vormen, zie [Vorm de uitbreiding van het Campaign Standard in de Inzameling UI van Gegevens](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/#configure-the-campaign-standard-extension).
* **[!DNL Mobile Core]**, die automatisch wordt geïnstalleerd. <br>Voor meer informatie over de Mobile Core-extensie raadpleegt u [Mobiele kern](https://developer.adobe.com/client-sdks/documentation/mobile-core/).
* **[!DNL Profile]**, die automatisch wordt geïnstalleerd. <br>Zie voor meer informatie over de profielextensie [Profiel](https://developer.adobe.com/client-sdks/documentation/profile/).

## Een mobiel profiel registreren in Campaign Standard {#register-mobile-profile}

### Met iOS {#register-mobile-profile-ios}

In iOS: [!DNL Experience Platform APIs] zijn vereist:

* **[!UICONTROL Lifecycle Start]**, wanneer de app wordt gestart en wanneer de app op de voorgrond staat.
* **[!UICONTROL Lifecycle Pause]**, als de toepassing op de achtergrond wordt uitgevoerd.

Zie voor meer informatie [Levenscyclusextensie in iOS](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/ios/).

Hier volgt een voorbeeldimplementatie van dit gebruiksgeval met iOS:

```
 func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?) -> Bool {
  
  
 ACPCore.setLogLevel(.debug)
 appId = SettingsBundle.getLaunchAppId()
   
 //===== START Set up Adobe SDK =====
 ACPCore.configure(withAppId: appId)
   
 ACPCampaign.registerExtension()
 ACPIdentity.registerExtension()
 ACPLifecycle.registerExtension()
 ACPUserProfile.registerExtension()
 ACPSignal.registerExtension()
 ACPCore.start()
 ACPCore.lifecycleStart(nil)
   
 return true
 }
  
func applicationDidEnterBackground(_ application: UIApplication) {
 ACPCore.lifecyclePause()
 }
   
 func applicationDidBecomeActive(_ application: UIApplication) {
 // Workaround until jira AMSDK-7411 is fixed.
 sleep(2)
 ACPCore.lifecycleStart(nil)
 }
```

### Met Android {#register-mobile-profile-android}

In Android: [!DNL Experience Platform APIs] zijn vereist:

* **[!UICONTROL OnResume]**
* **[!UICONTROL OnPause]**

Zie voor meer informatie [Levenscyclusextensie in Android](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/android/).

Hier volgt een voorbeeldimplementatie voor dit gebruiksgeval met Android:

```
@Override
  
public void onResume() {
 super.onResume();
 MobileCore.setApplication(getApplication());
 MobileCore.lifecycleStart(null);
 handleOpenTracking();
 }
  
 @Override
 public void onPause() {
 super.onPause();
 MobileCore.lifecyclePause();
 }
```

## Een pushtoken verzenden naar Adobe Campaign Standard {#send-push-token}

### Met iOS {#send-push-token-ios}

In iOS: [!DNL Experience Platform SDK] is vereist:

* **[!UICONTROL setPushIdentifier]** <br>Zie voor meer informatie [setPushIdentifier](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/).

Hier volgt een voorbeeld van de implementatie voor dit gebruiksgeval met iOS:

```
func application(_ application: UIApplication, didRegisterForRemoteNotificationsWithDeviceToken deviceToken: Data) {
  
 // Register Device Token
 ACPCore.setPushIdentifier(deviceToken)
```

### Met Android {#send-push-token-android}

In Android: [!DNL Experience Platform SDK] is vereist:

* **[!UICONTROL setPushIdentifier]** <br>Zie voor meer informatie [setPushIdentifier](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/).

Hier volgt een voorbeeldimplementatie voor dit geval van gebruik met Android:

```
@Override
public void onNewToken(String token) {
    Log.d(TAG, "Refreshed token: " + token);
    MobileCore.setPushIdentifier(token);
}
```

## Een mobiel profiel verrijken met aangepaste gegevens uit uw toepassing {#enrich-mobile-profile-custom}

Voor dit gebruiksgeval aan het werk, moet u regels voor PII postbacks tot stand brengen. Zie voor meer informatie [PII-postbacks](../../administration/using/configuring-rules-launch.md#pii-postback).

### Met iOS {#enrich-mobile-profile-custom-ios}

In iOS: [!DNL Experience Platform API] is vereist:

* collectionPII <br> Zie collectPII voor meer informatie.

Hier volgt een voorbeeldimplementatie van dit gebruiksgeval met iOS:

```
ACPCore.collectPii(["pushPlatform":"apns", "email":email, "firstName":firstName, "lastName":lastName])
```

### Met Android {#enrich-mobile-profile-custom-android}

In Android: [!DNL Experience Platform API] is vereist:

* collectionPII <br> Zie collectPII voor meer informatie.

Hier volgt een voorbeeldimplementatie voor dit gebruiksgeval met Android:

```
HashMap<String, String> data = new HashMap<>();
data.put("pushPlatform", "gcm");
data.put("firstName", firstNameText); 
data.put("lastName", lastNameText); 
data.put("email", emailText); 
MobileCore.collectPii(data);
```

## Een mobiel profiel verrijken met levenscyclusgegevens van uw toepassing {#enrich-mobile-profile-lifecycle}

Voor dit gebruiksgeval aan het werk, moet u regels voor PII postbacks tot stand brengen. Zie voor meer informatie [PII-postbacks](../../administration/using/configuring-rules-launch.md#pii-postback).

>[!NOTE]
>
>Adobe Campaign maakt geen onderscheid tussen aangepaste gegevens of levenscyclusgegevens en de mobiele app. Beide gegevenstypen kunnen naar de server worden verzonden met behulp van de terugzendregel collectPii als reactie op een gebeurtenis in de mobiele app.

### Met iOS {#enrich-mobile-profile-lifecycle-ios}

In iOS: [!DNL Experience Platform APIs] zijn vereist:

* **[!UICONTROL Lifecycle Start]**, wanneer de app wordt gestart en wanneer de app op de voorgrond staat.
* **[!UICONTROL Lifecycle Pause]**, als de toepassing op de achtergrond wordt uitgevoerd.

Zie voor meer informatie [Levenscyclusextensie in iOS](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/ios/).

Hier volgt een voorbeeldimplementatie van dit gebruiksgeval met iOS:

```
func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?) -> Bool {
  
  
 ACPCore.setLogLevel(.debug)
 appId = SettingsBundle.getLaunchAppId()
   
 //===== START Set up Adobe SDK =====
 ACPCore.configure(withAppId: appId)
   
 ACPCampaign.registerExtension()
 ACPIdentity.registerExtension()
 ACPLifecycle.registerExtension()
 ACPUserProfile.registerExtension()
 ACPSignal.registerExtension()
 ACPCore.start()
 ACPCore.lifecycleStart(nil)
   
 return true
 }
  
func applicationDidEnterBackground(_ application: UIApplication) {
 ACPCore.lifecyclePause()
 }
   
 func applicationDidBecomeActive(_ application: UIApplication) {
 // Workaround until jira AMSDK-7411 is fixed.
 sleep(2)
 ACPCore.lifecycleStart(nil)
 }
```

### Met Android {#enrich-mobile-profile-lifecycle-android}

In Android: [!DNL Experience Platform APIs] zijn vereist:

* **[!UICONTROL OnResume]**
* **[!UICONTROL OnPause]**

Zie voor meer informatie [Levenscyclusextensie in Android](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/android/).

Hier volgt een voorbeeldimplementatie voor dit gebruiksgeval met Android:

```
@Override
  
public void onResume() {
 super.onResume();
 MobileCore.setApplication(getApplication());
 MobileCore.lifecycleStart(null);
 handleOpenTracking();
 }
  
 @Override
 public void onPause() {
 super.onPause();
 MobileCore.lifecyclePause();
 }
```

## Gebruikersinteractie bijhouden met pushmeldingen {#track-user-push}

U moet regels maken voor het bijhouden van teruggestuurde pushberichten. Zie voor meer informatie [Postback-up van pushberichten](../../administration/using/configuring-rules-launch.md#push-tracking-postback).

### Met iOS {#track-user-push-ios}

In iOS: [!DNL Experience Platform SDK] is vereist:

* **[!UICONTROL trackAction]**. Zie voor meer informatie [Toepassingsacties bijhouden](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference/#trackaction).

Hier volgt een voorbeeldimplementatie van dit gebruiksgeval met iOS:

```
let deliveryId = userInfo["_dId"] as? String
let broadlogId = userInfo["_mId"] as? String
if (deliveryId != nil && broadlogId != nil) {
    ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
}
```

### Met Android {#track-user-push-android}

In Android: [!DNL Experience Platform SDK] is vereist:

* **[!UICONTROL trackAction]**
Zie voor meer informatie [Toepassingsacties bijhouden](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference/#trackaction).

Hier volgt een voorbeeldimplementatie voor dit gebruiksgeval met Android:

```
contextData.put("deliveryId", deliveryId);
contextData.put("broadlogId", messageId);
contextData.put("action", "2");
MobileCore.trackAction("tracking", contextData);
```

## Een aangepaste gebeurtenis in uw toepassing implementeren om in-app-berichten te activeren {#custom-event-inapp}

### Met iOS {#custom-event-inapp-ios}

In iOS: [!DNL Experience Platform SDK] is vereist:

* **[!UICONTROL trackAction]**. Zie voor meer informatie [Toepassingsacties bijhouden](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference/#trackaction).

Hier volgt een voorbeeldimplementatie van dit gebruiksgeval met iOS:

```
ACPCore.trackAction(mobileEventName, data: [:] )
```

### Met Android {#custom-event-inapp-android}

In Android: [!DNL Experience Platform SDK] is vereist:

* **[!UICONTROL trackAction]**
Zie voor meer informatie [Toepassingsacties bijhouden](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference/#trackaction).

Hier volgt een voorbeeldimplementatie voor dit gebruiksgeval met Android:

```
MobileCore.trackAction(mobileEventText, new HashMap<String,String>());
```

## Koppelingsvelden instellen voor extra verificatie {#linkage-fields-inapp}

### Met iOS {#linkage-fields-inapp-ios}

Als u koppelingsvelden wilt instellen voor extra verificatie voor de profielsjabloon die is gebaseerd op berichten in de app in iOS, gaat u als volgt te werk [!DNL Experience Platform SDK] is vereist:

* Koppelingsvelden instellen <br>Zie voor meer informatie [Koppelingsvelden instellen](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/#setlinkagefields).
* Koppelingsvelden opnieuw instellen <br>Zie voor meer informatie [Koppelingsvelden opnieuw instellen](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/#setlinkagefields).

Hier volgen voorbeelden van implementaties van dit gebruiksgeval met iOS.

Koppelingsvelden instellen:

```
var linkageFields = [String: String]()
linkageFields["cusEmail"] = "john.doe@email.com"
ACPCampaign.setLinkageFields(linkageFields)
```

Koppelingsvelden opnieuw instellen:

```
ACPCampaign.resetLinkageFields(linkageFields)
```

### Met Android {#linkage-fields-inapp-android}

Als u koppelingsvelden wilt instellen voor extra verificatie voor de profielsjabloon die is gebaseerd op In-App-berichten in Android, is de volgende Experience Platform-SDK vereist:

* Koppelingsvelden instellen <br>Zie voor meer informatie [Koppelingsvelden instellen](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/#setlinkagefields).
* Koppelingsvelden opnieuw instellen <br>Zie voor meer informatie [Koppelingsvelden opnieuw instellen](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/#resetlinkagefields).

Hier volgen voorbeelden van implementaties van dit gebruiksgeval met Android.

Koppelingsvelden instellen:

```
HashMap<String, String> linkageFields = new HashMap<String, String>();
linkageFields.put("cusEmail", "john.doe@email.com");
Campaign.setLinkageFields(linkageFields);
```

Koppelingsvelden opnieuw instellen:

```
Campaign.resetLinkageFields()
```
