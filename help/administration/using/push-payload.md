---
title: Begrijpen met de Payload Structuur van Campaign Standard-pushberichten
description: Meer informatie over de structuur van de lading die in mobiele toepassingen wordt ontvangen
audience: channels
feature: Instance Settings
role: Admin
level: Experienced
exl-id: a6515795-1006-4f27-bc44-5ae8b8edc018
source-git-commit: bfba6b156d020e8d2656239e713d2d24625bda54
workflow-type: tm+mt
source-wordcount: '1137'
ht-degree: 3%

---

# De payloadstructuur voor pushmeldingen begrijpen {#push-payload}

Met Adobe Campaign kunt u persoonlijke en gesegmenteerde pushmeldingen op mobiele iOS- en Android-apparaten verzenden naar mobiele toepassingen (mobiele app).

Elke pushmelding die op een mobiele app wordt ontvangen, bevat informatie die door de app wordt gebruikt om de pushmelding weer te geven als een waarschuwingsbericht wordt verzonden. De pushmelding werkt hoogstwaarschijnlijk ook verder, vooral als een pushmelding wordt verzonden.

Deze informatie wordt ontvangen door de mobiele toepassingscode in een gebeurtenishandler die aangeeft dat een pushmelding is ontvangen. Wanneer u pushberichten van Adobe Campaign Standard verzendt, bevat de informatie die in de mobiele app is ontvangen mogelijk ook Campaign Standard-specifieke informatie die kan worden gebruikt om gebruik te maken van bepaalde functies van Campaign Standard. Bovendien kan de lading aangepaste gegevens bevatten die door de mobiele app kunnen worden verbruikt.

In dit document wordt de structuur beschreven van de payload die in een mobiele app is ontvangen wanneer een pushmelding naar een app van Adobe Campaign Standard is verzonden.

>[!NOTE]
>
>De payload-structuur is afhankelijk van het type mobiele app (bijvoorbeeld iOS-app, Android-app met FCM).

## Push-laadstructuur {#push-payload-structure}

Deze sectie beschrijft een structuur van een steekproeflading voor diverse mobiele platforms en beschrijft belangrijke attributen die in het bevat zijn. Dit is de structuur van de payload die in de code voor de mobiele app in de gebeurtenishandler wordt ontvangen, die aangeeft dat een pushmelding is ontvangen.

De attributen en hun waarden van de nuttige lading zullen variëren gebaseerd op de configuraties die in de Geavanceerde opties van het pushbericht worden verstrekt. Deze sectie verstrekt ook een afbeelding tussen deze configuraties in Campaign Standard UI en de attributen in de nuttige lading om te verduidelijken hoe de nuttige lading bij het vormen van een optie in Campaign Standard zal veranderen.

### Voor iOS Mobile-toepassing {#payload-structure-ios}

**Voorbeeld van Payload verzonden van Adobe Campaign naar iOS-app:**

```
{

    "aps":{

            "alert":{

                    "body":"This is the content of my push notification",

                    "title":"Push Notification Title"

            },

            "content-available":1,

            "category":"NEW_MESSAGE_CATEGORY",

            "badge":2,

            "mutable-content":1,

            "sound":"default"

        },

    "custom_field1":"custom_value1",

    "custom_field2":"custom_value2",

    "media-attachment-url":"https://2.img-dpreview.com/files/p/articles/9440145363/Creative_Cloud.jpeg",

    "uri":"https://mydeeplinkurl.com",

    "_dId":"56c4",

    "_mId":"h138a"} 
```

**JSON-voorbeeldlading voor gebruik met [iOS APNS-tester](https://pushtry.com/)**

```
{

  "aps": {

    "alert": {

      "title": "Push Notification Title",

      "body": "body of push"

    },

    "badge": 33,

    "sound": "default"

  },

  "custom_field1": "custom_value1",

  "uri": "https://mydeeplinkurl.com"

}
```

Het belangrijkste gedeelte van de lading is het aps-woordenboek, dat Apple-bepaalde sleutels bevat en wordt gebruikt om te bepalen hoe het systeem dat het bericht ontvangt de gebruiker zou moeten waarschuwen, als bij allen. Deze sectie bevat vooraf gedefinieerde toetsen die door de mobiele app worden gebruikt om het gedrag van de pushmelding te formuleren.

Meer informatie over de kenmerken binnen de aps vindt u in de documenten voor Apple-ontwikkelaars: [De taakbelasting voor externe berichten maken](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CreatingtheNotificationPayload.html#//apple_ref/doc/uid/TP40008194-CH10-SW1).

### Voor Android-toepassing {#payload-structure-android}

**Voorbeeld van Payload verzenden van Adobe Campaign naar Android-app**

```
{

  "collapseKey": "1476005",

  "priority": "high",

  "data": {

    "_dId": "d57fd6",

    "_mId": "h1685a5",

    "body": "adobe body 123",

    "category": "adobe category 123",

    "custom key 1": "value 1",

    "custom key 2": "test value 2",

    "custom key 3": "foo bar android",

    "media-attachment-url": "http://adobegiphy.com?test=123",

    "sound": "http://testcampaign.instance.com/r/?id=s1685a5,d57fd6,d57ff5",

    "title": "adobe title 123",

    "uri": "http://testcampaign.instance.com/r/?id=d1685a5,d57fd6,d57ff6",

    "badge": 1817

  }

}
```

**Te gebruiken JSON-voorbeeldlading [Google FCM tester](https://pushtry.com/)**

```
{

  "to": "<==========ENTER your device token==============>",

  "collapseKey": "1476005",

  "priority": "high",

  "data": {

    "_dId": "d57fd6",

    "_mId": "h1685a5",

    "title": "adobe title 123",

    "body": "adobe body 123",

    "category": "adobe category 123",

    "custom key 1": "value 1",

    "custom key 2": "test value 2",

    "custom key 3": "foo bar android",

    "media-attachment-url": "http://adobegiphy.com?test=123",

    "sound": "http://testcampaign.instance.com/r/?id=s1685a5,d57fd6,d57ff5",

    "uri": "http://testcampaign.instance.com/r/?id=d1685a5,d57fd6,d57ff6",

    "badge": 1817

  }

}
```

De payload bevat een gegevensbericht dat alle inhoud van het pushbericht bevat, inclusief de aangepaste sleutel-/waardeparen, en de client-app moet het bericht verwerken om pushmelding te maken en weer te geven, indien nodig of om andere bedrijfslogica toe te voegen.

Om aspecten van een android lading te begrijpen verwijs naar [Concepten en opties voor berichten (fcm)](https://firebase.google.com/docs/cloud-messaging/concept-options).

>[!NOTE]
>
>De ondersteuning voor berichtberichten in Android-payload is met ingang van januari 2018 verwijderd om het wakker worden van de app en het doorgeven van de besturing aan de mobiele app mogelijk te maken zonder dat de gebruiker met de app moet communiceren.

### Toewijzing tussen Campaign Standard-configuraties en Payload-kenmerken {#mapping-payload}

| Campagneconfiguratie | Betrokken kenmerk in iOS | Betrokken kenmerk in Android | Beschrijving |
|:-:|:-:|:-:|:-:|
| Berichttitel <br>Bericht | alert → titel <br> waarschuwing → | titel <br>lichaam | Deze gegevens bevatten specifieke gegevens van het waarschuwingsbericht.<br>De titel en de lichaamstoetsen verstrekken de inhoud van de alarm. |
| Geluid afspelen | geluid | geluid | Een aangepast geluid dat met de waarschuwing moet worden afgespeeld. |
| Waarde van de badge | badge | badge | Een geheel-getalwaarde die moet worden gebruikt om het pictogram van de app aan te geven. |
| Een deeplink toevoegen | uri | NA | Met een deeplink kunt u gebruikers rechtstreeks naar de content in de applicatie brengen (in plaats van een webbrowserpagina te openen). |
| Categorie | categorie | categorie | Aangepaste handelingen weergeven met een extern bericht. <br>Met de categorietoets kan het systeem de handelingen voor die categorie weergeven als knoppen in de waarschuwingsinterface. |
| Aangepaste velden | custom_field1, custom_field2.. | custom_field1, custom_field2.. | Alle aangepaste gegevens die u naar uw app wilt verzenden. |
| URL met rijke media-inhoud (afbeeldings-, gif-, audio- en videobestanden)<br>(Alleen van toepassing voor iOS 10 of hoger) | media-gehechtheid-url | NA | URL van uw mediabestanden om rijke inhoud aan uw melding toe te voegen. <br>Wanneer u een waarde voor deze URL opgeeft, wordt de markering voor gemuteerde inhoud automatisch naar de payload verzonden. <br> (Alleen van toepassing voor iOS 10 of hoger) |
| Mabelinhoud <br> (Alleen van toepassing voor iOS 10 of hoger) | muteerbaar | NA | De uitbreiding van de Dienst van het Bericht in uw app zal &quot;onderscheppen&quot;alle verre berichten met veranderbaar-inhoudssleutel en zal u toestaan om de inhoud van de verzoeklading te behandelen/te manipuleren, die dan kan worden gebruikt om het bericht aan te passen. De gevallen van deze functie omvatten het downloaden en weergeven van meerdere media, het decoderen van gecodeerde gegevens die aanwezig zijn in de pushlading. Meer informatie vindt u in [Wijzig de lading van een Verre Bericht](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/ModifyingNotifications.html). <br>(Alleen van toepassing voor iOS 10 of hoger) |
| Inhoud beschikbaar | content-available | NA | Als u deze optie selecteert, kan een iOS-app in de achtergrond of stilgezet worden weergegeven. Het wakker worden impliceert dat de app op de achtergrond en de aangewezen gebeurtenismanager verantwoordelijk voor het ontvangen van de lading van de dupmelding gegevens een controle krijgt en de gegevens kan gebruiken om het even welke berekening te doen, met inbegrip van maar niet beperkt tot het bouwen van douanepijpbericht en het tonen van het zelfde. Meer informatie vindt u in [Wachten op app met levering van berichten](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CreatingtheNotificationPayload.html). |
| URL met rijke media-inhoud (afbeeldingsbestanden)<br>(Alleen van toepassing op Android) | NA | media-gehechtheid-url | URL van de afbeeldingsbestanden om rijke inhoud aan uw melding toe te voegen. |
| NA | _mId<br>_dId | _mId <br>_dId | Waarden van broadlogId en deliveryId.<br>Deze kenmerken zijn vereist als uw app een trackingpostback wil aanroepen om bij te houden wanneer op de pushmelding is geklikt of deze is geopend. Deze informatie wordt berekend en intern verzonden door de toepassingsserver zonder tussenkomst van de gebruiker.<br>Informatie over postbacks vindt u in deze [page](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback). |

### Informatie over de payload ophalen in mobiele app-code {#payload-information}

De payload-informatie die door de toepassingsserver wordt verzonden, wordt ontvangen door de mobiele toepassingscode in een gebeurtenishandler die aangeeft dat een pushmelding is ontvangen. Deze gebeurtenis varieert op basis van het mobiele platform waaraan wordt gewerkt en ook op basis van het feit of de app op de voor- of achtergrond wordt uitgevoerd. De volgende documentatie helpt u de gebeurtenismanager identificeren u wenst om te behandelen gebaseerd op uw gebruiksgeval.

* iOS-toepassingen: **Externe berichten verwerken** sectie in [Externe meldingen](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/HandlingRemoteNotifications.html).
* Android-toepassingen: [Berichten ontvangen op een Android-clienttoepassing](https://firebase.google.com/docs/cloud-messaging/android/receive)

**Voorbeeld voor iOS Mobile-app**

```
 - (void)application:(UIApplication *)application

didReceiveRemoteNotification:(NSDictionary *)userInfo {

    

    NSDictionary *apsDict = [userInfo objectForKey:@"aps"];

    NSDictionary *alertDict = [apsDict objectForKey:@"alert"];

    NSString *title = [alertDict objectForKey:@"title"];

    NSString *body = [alertDict objectForKey:@"body"];

    NSString *category = [apsDict objectForKey:@"category"];

    NSString *deliveryId = userInfo[@"_dId"];

    NSString *broadlogId = userInfo[@"_mId"];

    NSString *mediaAttachmentURL = userInfo[@"media-attachment-url"];

    NSString *deeplinkURL = userInfo[@"uri"];

    NSString *customValue1 = userInfo[@"custom_field1"];   

}
```

**Voorbeeld voor FCM-app voor Android Mobile**

```
public void onMessageReceived(RemoteMessage message) {

    Map<String, String> dataMap = message.getData();

     

    String title = dataMap.get("title");

    String body = dataMap.get("body");

    String category = dataMap.get("category");

    String deliveryId = dataMap.get("_dId");

    String broadlogId = dataMap.get("_mId");

    String mediaAttachmentURL = dataMap.get("media-attachment-url");

    String deeplinkURL = dataMap.get("uri");

    String customValue1 = dataMap.get("custom_field1");

}
```
