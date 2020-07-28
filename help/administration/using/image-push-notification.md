---
title: Een afbeelding weergeven op basis van een Adobe Campaign Standard-pushmelding
description: Leer hier hoe u een afbeelding kunt weergeven via een Adobe Campaign-pushmelding op een iOS-apparaat.
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
source-git-commit: cf43edcacbab9f1f33ce29e23c0957d8bfa64e7d
workflow-type: tm+mt
source-wordcount: '428'
ht-degree: 0%

---


# Afbeeldingen en video&#39;s toevoegen iOS {#image-push}

>[!NOTE]
>
>Dit document is alleen van toepassing op iOS-apparaten.

Leer in dit document hoe u een afbeelding weergeeft via een Adobe Campaign Standard iOS-pushmelding.

## Stap 1: Pushmelding instellen {#set-up-push}

Pushmelding wordt ondersteund door Experience Platform-SDK&#39;s.

De mobiele toepassingen die pushmeldingen ontvangen, moeten door een beheerder in de Adobe Campaign-interface zijn geconfigureerd.

Door zowel Adobe Campaign als Adobe Mobile Services te configureren, kunt u de gegevens van uw mobiele toepassing gebruiken voor uw campagnes. For more on this, refer to this [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html).

Als u pushmeldingen wilt verzenden met een Experience Cloud SDK-toepassing, moet u een mobiele app instellen in Adobe Experience Platform Launch en configureren in Adobe Campaign. For more on this, refer to this [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#ChannelspecificapplicationconfigurationinAdobeCampaign).

## Stap 2: Je pushmelding aanpassen in Adobe Campaign {#customize-push}

Als u uw pushmelding wilt verfijnen, kunt u in Adobe Campaign toegang krijgen tot een set geavanceerde opties terwijl u een pushmelding ontwerpt.

1. Maak een pushmelding. For more on this, refer to this [page](../../channels/using/preparing-and-sending-a-push-notification.md).

1. Open de **[!UICONTROL Advanced options]** sectie vanaf de pagina met inhoud voor pushmeldingen.

1. Voer in het **[!UICONTROL Rich media content URL]** veld de URL van het bestand in.
Voor iOS 10 of hoger kunt u afbeeldings-, gif-, audio- en videobestanden invoegen.

   ![](assets/push_notif_advanced_6.png)

1. Bekijk een voorbeeld van uw pushmelding en sla deze op.

## Stap 3: De mobiele toepassingscode aanpassen {#mobile-app-code}

Nadat u uw pushmelding in Adobe Campaign hebt aangepast, moet u uw mobiele toepassing configureren om de afbeelding op apparaten weer te geven.

>[!NOTE]
>
>Als uw toepassing in doelstelling-C is, verwijs naar de volgende [documentatie](https://docs.adobe.com/content/help/en/mobile-services/ios/messaging-ios/push-messaging/c-set-up-rich-push-notif-ios.html).

Voer de volgende stappen uit als uw app is ingeschakeld [!DNL Swift]:

1. Open uw [!DNL Xcode] project.

1. Selecteer in uw [!DNL Xcode] project **[!UICONTROL File]** > **[!UICONTROL New]** > **[!UICONTROL Target]**.

1. Selecteer **[!UICONTROL Notification Service Extension]**.

   ![](assets/push_notif_advanced_12.png)

1. Controleer of de **bestandsklasse NotificationService.swift** is gemaakt.

1. Bewerk deze klasse en vervang de standaardinhoud door het volgende.
Hierdoor kan de toepassing de binnenkomende parameter afhandelen met de afbeeldings-URL, deze parseren, lokaal kopiëren en vervolgens uit het pushbericht weergeven.

   ```
   import UserNotifications
   
   class NotificationService: UNNotificationServiceExtension {
   
   var contentHandler: ((UNNotificationContent) -> Void)?
   var bestAttemptContent: UNMutableNotificationContent?
   
   override func didReceive(_ request: UNNotificationRequest, withContentHandler contentHandler: @escaping (UNNotificationContent) -> Void) {
       self.contentHandler = contentHandler
       bestAttemptContent = (request.content.mutableCopy() as? UNMutableNotificationContent)
   
       if let bestAttemptContent = bestAttemptContent {
           var urlString:String? = nil
           if let urlImageString = request.content.userInfo["media-attachment-url"] as? String {
               urlString = urlImageString
           }
   
           if urlString != nil, let fileUrl = URL(string: urlString!) {
               print("fileUrl: \(fileUrl)")
   
               // Download the attachment
               URLSession.shared.downloadTask(with: fileUrl) { (location, response, error) in
                   if let location = location {
                       // Move temporary file to remove .tmp extension
                       if (error == nil) {
                           let tmpDirectory = NSTemporaryDirectory()
                           let tmpFile = "file://".appending(tmpDirectory).appending(fileUrl.lastPathComponent)
                           let tmpUrl = URL(string: tmpFile)!
                           try! FileManager.default.moveItem(at: location, to: tmpUrl)
   
                           // Add the attachment to the notification content
                           if let attachment = try? UNNotificationAttachment(identifier: fileUrl.lastPathComponent, url: tmpUrl) {
                               bestAttemptContent.attachments = [attachment]
                               }
                       }
                       if(error != nil) {
                           print("Failed to download attachment: \(error.debugDescription)")
                       }
                   }
                   // Serve the notification content
                   contentHandler(bestAttemptContent)
               }.resume()
           }
       }
   }
   
   override func serviceExtensionTimeWillExpire() {
       // Called just before the extension will be terminated by the system.
       // Use this as an opportunity to deliver your "best attempt" at modified content, otherwise the original push payload will be used.
       if let contentHandler = contentHandler, let bestAttemptContent = bestAttemptContent {
           contentHandler(bestAttemptContent)
       }
   }
   
   }
   ```

De mobiele telefoon moet de volgende lading ontvangen terwijl het bericht wordt verzonden.

De afbeeldings-URL wordt toegewezen met sleutel media-bijlage-url. Dit is het sleutelwaardepaar dat u vanuit het perspectief van de toepassingscode moet verwerken om de afbeelding te downloaden en weer te geven.

```
userInfo: [AnyHashable("media-attachment-url"): https://pbs.twimg.com/profile_images/876737835314950144/zPTs9b7o.jpg, AnyHashable("_dId"): 1de3ef93, AnyHashable("_mId"): h280a5, AnyHashable("aps"): {
 
    alert =     {
 
        body = "Message Body here";
 
        title = "This a push from Campaign";
 
    };
 
    badge = 1;
 
    "mutable-content" = 1;
 
}]
```

## Stap 4: Test het verzenden van de push {#test-send-push}

U kunt nu testen hoe u uw toepassing bouwt en hoe u de levering hebt gemaakt die u in stap 2 hierboven hebt gemaakt. Raadpleeg deze [pagina](../../channels/using/preparing-and-sending-a-push-notification.md)voor meer informatie over het voorbereiden en verzenden van uw pushmelding.

![](assets/push_notif_advanced_34.png)

