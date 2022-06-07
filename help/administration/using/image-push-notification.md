---
title: Een afbeelding weergeven vanuit een Adobe Campaign Standard-pushmelding
description: Leer hier hoe u een afbeelding kunt weergeven via een Adobe Campaign-pushmelding op een iOS-apparaat
audience: channels
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 474c8002-4263-4617-9480-6a9b603bde8e
source-git-commit: 7767b39a48502f97e2b3af9d21a3f49b9283ab2e
workflow-type: tm+mt
source-wordcount: '415'
ht-degree: 18%

---

# Afbeeldingen en video’s toevoegen in iOS {#image-push}

>[!NOTE]
>
>Dit document is alleen van toepassing op iOS-apparaten.

Leer in dit document hoe u een afbeelding weergeeft via een Adobe Campaign Standard iOS-pushmelding.

## Stap 1: Pushmelding instellen {#set-up-push}

Pushmelding wordt ondersteund door Experience Platform-SDK&#39;s.

De mobiele toepassingen die pushmeldingen ontvangen, moeten door een beheerder in de Adobe Campaign-interface zijn geconfigureerd.

Door zowel Adobe Campaign als Adobe Mobile Services te configureren, kunt u de gegevens van uw mobiele toepassing gebruiken voor uw campagnes. Raadpleeg [deze pagina](../../administration/using/configuring-a-mobile-application.md) voor meer informatie.

Als u pushberichten wilt verzenden met een Experience Cloud SDK-toepassing, moet een mobiele toepassing worden ingesteld in de gebruikersinterface voor gegevensverzameling en worden geconfigureerd in Adobe Campaign. Raadpleeg [deze pagina](../../administration/using/configuring-a-mobile-application.md#channel-specific-config) voor meer informatie.

## Stap 2: Je pushmelding aanpassen in Adobe Campaign {#customize-push}

Als u uw pushmelding wilt verfijnen, kunt u in Adobe Campaign een aantal geavanceerde opties gebruiken tijdens het ontwerpen van de melding.

1. Een pushmelding maken. Raadpleeg [deze pagina](../../channels/using/preparing-and-sending-a-push-notification.md) voor meer informatie.

1. Open vanaf de pagina met pushberichten de **[!UICONTROL Advanced options]** sectie.

1. Voer de URL van het bestand in het dialoogvenster **[!UICONTROL Rich media content URL]** veld.
Voor iOS 10 of hoger kunt u afbeeldings-, GIF-, audio- en videobestanden invoegen.

   ![](assets/push_notif_advanced_6.png)

1. Bekijk een voorbeeld van uw pushmelding en sla deze op.

## Stap 3: De mobiele toepassingscode aanpassen {#mobile-app-code}

Nadat u uw pushmelding in Adobe Campaign hebt aangepast, moet u uw mobiele toepassing configureren om de afbeelding op apparaten weer te geven.

>[!NOTE]
>
>Als uw toepassing in doelstelling-C is, verwijs naar het volgende [documentatie](https://experienceleague.adobe.com/docs/mobile-services/ios/messaging-ios/push-messaging/c-set-up-rich-push-notif-ios.html).

Als uw app in [!DNL Swift]volgt u de onderstaande stappen:

1. Open uw [!DNL Xcode] project.

1. In uw [!DNL Xcode] project selecteren **[!UICONTROL File]** > **[!UICONTROL New]** > **[!UICONTROL Target]**.

1. Selecteer **[!UICONTROL Notification Service Extension]**.

   ![](assets/push_notif_advanced_12.png)

1. Controleer of de **NotificationService.swift** File-klasse wordt gemaakt.

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

U kunt nu testen hoe u uw toepassing bouwt en hoe u de levering hebt gemaakt die u in stap 2 hierboven hebt gemaakt. Voor meer informatie over het voorbereiden en verzenden van uw pushmelding raadpleegt u deze [page](../../channels/using/preparing-and-sending-a-push-notification.md).

![](assets/push_notif_advanced_34.png)
