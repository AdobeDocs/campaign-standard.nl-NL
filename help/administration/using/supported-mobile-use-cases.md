---
title: Kwesties voor mobiel gebruik die in Adobe Campaign Standard worden ondersteund met de SDK van Adobe Experience Platform
description: In dit document wordt informatie gegeven over de ondersteuning van gevallen van mobiel gebruik.
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
source-git-commit: 08513f960eb28f50e89e86e3130cf40c38e9a63e
workflow-type: tm+mt
source-wordcount: '953'
ht-degree: 0%

---


# Mobiele gebruiksscenario’s die worden ondersteund in Adobe Campaign Standard {#mobile-use-cases}

Op deze pagina vindt u de lijst met alle gevallen voor mobiel gebruik die worden ondersteund in [!DNL Adobe Campaign Standard] het [!DNL Adobe Experience Platform SDKs]dialoogvenster. Let op: het ondersteunen van deze gebruiksgevallen omvat het installeren en configureren van de [!DNL Adobe Experience Platform SDKs], [!DNL Adobe Experience Platform Launch]en [!DNL Adobe Campaign Standard]. For more information on this, refer to this [page](../../administration/using/configuring-a-mobile-application.md).

Adobe Campaign Standard ondersteunt de volgende gebruiksgevallen:

* [Een mobiel profiel registreren in Campaign Standard](../../administration/using/supported-mobile-use-cases.md#register-mobile-profile)
* [Een pushtoken verzenden naar Campaign Standard](../../administration/using/supported-mobile-use-cases.md#send-push-token)
* [Een mobiel profiel verrijken met aangepaste gegevens uit uw toepassing](../../administration/using/supported-mobile-use-cases.md#enrich-mobile-profile-custom)
* [Een mobiel profiel verrijken met levenscyclusgegevens van uw toepassing](../../administration/using/supported-mobile-use-cases.md#enrich-mobile-profile-lifecycle)
* [Gebruikersinteractie bijhouden met pushmeldingen](../../administration/using/supported-mobile-use-cases.md#track-user-push)
* [Een aangepaste gebeurtenis implementeren in uw mobiele app om In-App-berichten te activeren](../../administration/using/supported-mobile-use-cases.md#custom-event-inapp)
* [Koppelingsvelden instellen voor extra verificatie voor de profielsjabloon die is gebaseerd op In-App-berichten](../../administration/using/supported-mobile-use-cases.md#linkage-fields-inapp)

Om deze gebruiksgevallen te vormen, hebt u de volgende uitbreidingen van nodig [!DNL Experience Platform Launch]:

* **[!DNL Adobe Campaign Standard]** <br>Om de uitbreiding van de Campaign Standard te installeren en te vormen, zie de uitbreiding van de Campaign Standard in Experience Platform Launch [](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard#configure-the-campaign-standard-extension-in-experience-platform-launch)vormen.
* **[!DNL Mobile Core]**, die automatisch wordt geïnstalleerd. <br>Zie [Mobile Core](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core)voor meer informatie over de Mobile Core-extensie.
* **[!DNL Profile]**, die automatisch wordt geïnstalleerd. <br>Zie [Profiel](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/profile)voor meer informatie over de profielextensie.

## Een mobiel profiel registreren in Campaign Standard {#register-mobile-profile}

### Met iOS {#register-mobile-profile-ios}

In iOS is het volgende [!DNL Experience Platform APIs] vereist:

* **[!UICONTROL Lifecycle Start]**, wanneer de app wordt gestart en wanneer de app op de voorgrond staat.
* **[!UICONTROL Lifecycle Pause]**, als de toepassing op de achtergrond wordt uitgevoerd.

Zie [Levenscyclusextensie in iOS](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/lifecycle/lifecycle-extension-in-ios)voor meer informatie.

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

In Android is het volgende [!DNL Experience Platform APIs] vereist:

* **[!UICONTROL OnResume]**
* **[!UICONTROL OnPause]**

Zie [Levenscyclusextensie in Android](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/lifecycle/lifecycle-extension-in-android)voor meer informatie.

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

In iOS [!DNL Experience Platform SDK] is het volgende vereist:

* **[!UICONTROL setPushIdentifier]** <br>Zie [setPushIdentifier](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference#setpushidentifier)voor meer informatie.

Hier volgt een voorbeeld van de implementatie voor dit gebruiksgeval met iOS:

```
func application(_ application: UIApplication, didRegisterForRemoteNotificationsWithDeviceToken deviceToken: Data) {
  
 // Register Device Token
 ACPCore.setPushIdentifier(deviceToken)
```

### Met Android {#send-push-token-android}

In Android [!DNL Experience Platform SDK] is het volgende vereist:

* **[!UICONTROL setPushIdentifier]** <br>Zie [setPushIdentifier](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference#setpushidentifier)voor meer informatie.

Hier volgt een voorbeeldimplementatie voor dit geval van gebruik met Android:

```
@Override
public void onNewToken(String token) {
    Log.d(TAG, "Refreshed token: " + token);
    MobileCore.setPushIdentifier(token);
}
```

## Een mobiel profiel verrijken met aangepaste gegevens uit uw toepassing {#enrich-mobile-profile-custom}

Voor dit gebruiksgeval aan het werk, moet u regels voor PII postbacks tot stand brengen. Zie [PII Postbacks](../../administration/using/configuring-rules-launch.md#pii-postback)voor meer informatie.

### Met iOS {#enrich-mobile-profile-custom-ios}

In iOS [!DNL Experience Platform API] is het volgende vereist:

* collectionPII <br> Zie collectionPII voor meer informatie.

Hier volgt een voorbeeldimplementatie van dit gebruiksgeval met iOS:

```
ACPCore.collectPii(["email":email, "firstName":firstName, "lastName":lastName])
```

### Met Android {#enrich-mobile-profile-custom-android}

In Android [!DNL Experience Platform API] is het volgende vereist:

* collectionPII <br> Zie collectionPII voor meer informatie.

Hier volgt een voorbeeldimplementatie voor dit gebruiksgeval met Android:

```
HashMap<String, String> data = new HashMap<>();
data.put("firstName", firstNameText);
data.put("lastName", lastNameText);
data.put("email", emailText);
MobileCore.collectPii(data);
```

## Een mobiel profiel verrijken met levenscyclusgegevens van uw toepassing {#enrich-mobile-profile-lifecycle}

Voor dit gebruiksgeval aan het werk, moet u regels voor PII postbacks tot stand brengen. Zie [PII Postbacks](../../administration/using/configuring-rules-launch.md#pii-postback)voor meer informatie.

>[!NOTE]
>
>Adobe Campaign maakt geen onderscheid tussen aangepaste gegevens of levenscyclusgegevens en de mobiele app. Beide gegevenstypen kunnen naar de server worden verzonden met behulp van de terugzendregel collectPii als reactie op een gebeurtenis in de mobiele app.

### Met iOS {#enrich-mobile-profile-lifecycle-ios}

In iOS is het volgende [!DNL Experience Platform APIs] vereist:

* **[!UICONTROL Lifecycle Start]**, wanneer de app wordt gestart en wanneer de app op de voorgrond staat.
* **[!UICONTROL Lifecycle Pause]**, als de toepassing op de achtergrond wordt uitgevoerd.

Zie [Levenscyclusextensie in iOS](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/lifecycle/lifecycle-extension-in-ios)voor meer informatie.

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

In Android is het volgende [!DNL Experience Platform APIs] vereist:

* **[!UICONTROL OnResume]**
* **[!UICONTROL OnPause]**

Zie [Levenscyclusextensie in Android](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/lifecycle/lifecycle-extension-in-android)voor meer informatie.

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

U moet regels maken voor het bijhouden van teruggestuurde pushberichten. Voor meer informatie, zie [Push berichten die postback](../../administration/using/configuring-rules-launch.md#push-tracking-postback)volgen.

### Met iOS {#track-user-push-ios}

In iOS [!DNL Experience Platform SDK] is het volgende vereist:

* **[!UICONTROL trackAction]**. Zie Toepassingsacties [](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions)bijhouden voor meer informatie.

Hier volgt een voorbeeldimplementatie van dit gebruiksgeval met iOS:

```
let deliveryId = userInfo["_dId"] as? String
let broadlogId = userInfo["_mId"] as? String
if (deliveryId != nil && broadlogId != nil) {
    ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
}
```

### Met Android {#track-user-push-android}

In Android [!DNL Experience Platform SDK] is het volgende vereist:

* **[!UICONTROL trackAction]**
Zie Toepassingsacties [](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions)bijhouden voor meer informatie.

Hier volgt een voorbeeldimplementatie voor dit gebruiksgeval met Android:

```
contextData.put("deliveryId", deliveryId);
contextData.put("broadlogId", messageId);
contextData.put("action", "2");
MobileCore.trackAction("tracking", contextData);
```

## Een aangepaste gebeurtenis in uw toepassing implementeren om in-app-berichten te activeren {#custom-event-inapp}

### Met iOS {#custom-event-inapp-ios}

In iOS [!DNL Experience Platform SDK] is het volgende vereist:

* **[!UICONTROL trackAction]**. Zie Toepassingsacties [](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions)bijhouden voor meer informatie.

Hier volgt een voorbeeldimplementatie van dit gebruiksgeval met iOS:

```
ACPCore.trackAction(mobileEventName, data: [:] )
```

### Met Android {#custom-event-inapp-android}

In Android [!DNL Experience Platform SDK] is het volgende vereist:

* **[!UICONTROL trackAction]**
Zie Toepassingsacties [](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions)bijhouden voor meer informatie.

Hier volgt een voorbeeldimplementatie voor dit gebruiksgeval met Android:

```
MobileCore.trackAction(mobileEventText, new HashMap<String,String>());
```

## Koppelingsvelden instellen voor extra verificatie {#linkage-fields-inapp}

### Met iOS {#linkage-fields-inapp-ios}

Als u koppelingsvelden wilt instellen voor extra verificatie voor de profielsjabloon die is gebaseerd op In-App-berichten in iOS, [!DNL Experience Platform SDK] is het volgende vereist:

* Stel koppelingsvelden in <br>Zie Koppelingsvelden [](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference#set-linkage-fields)instellen voor meer informatie.
* Koppelingsvelden opnieuw instellen <br>Zie Koppelingsvelden [opnieuw instellen voor meer informatie](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference#reset-linkage-fields).

Hier volgen voorbeelden van implementaties van dit gebruiksscenario met iOS.

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

* Stel koppelingsvelden in <br>Zie Koppelingsvelden [](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference#set-linkage-fields)instellen voor meer informatie.
* Koppelingsvelden opnieuw instellen <br>Zie Koppelingsvelden [opnieuw instellen voor meer informatie](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference#reset-linkage-fields).

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
