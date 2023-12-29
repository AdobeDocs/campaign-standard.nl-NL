---
title: Tagregels configureren om Adobe Campaign Standard-gebruiksscenario's te ondersteunen
description: Leer hoe u labelregels configureert ter ondersteuning van Adobe Campaign Standard-gebruiksgevallen
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
feature: Instance Settings
role: Admin
level: Experienced
exl-id: b5f4f612-ea23-4007-b427-069777ecdd58
source-git-commit: 597ece8d833a216f0540f801461b08fdc9865024
workflow-type: tm+mt
source-wordcount: '983'
ht-degree: 2%

---

# Tagregels configureren om Adobe Campaign Standard-gebruiksscenario&#39;s te ondersteunen {#configuring-rules-launch}

In de UI van de Inzameling van Gegevens, creeer gegevenselementen en regels om PII en andere gegevens van mobiele toepassingen naar te verzenden [!DNL Adobe Campaign Standard].

Om ervoor te zorgen dat alle configuratieveranderingen in UI van de Inzameling van Gegevens van kracht worden, moet u deze veranderingen publiceren. Zie voor meer informatie [Publiceren](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/#publish-the-configuration).

Ga als volgt te werk om regels te maken in de gebruikersinterface voor gegevensverzameling:

1. [Gegevenselementen maken](../../administration/using/configuring-rules-launch.md#create-data-elements)
2. [Regels maken](../../administration/using/configuring-rules-launch.md#create-data-elements) voor gebruiksgevallen die u wilt ondersteunen:
   * [PII-postback](../../administration/using/configuring-rules-launch.md#pii-postback)
   * [Postback bijhouden in de app](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback)
   * [Postback-up van pushberichten](../../administration/using/configuring-rules-launch.md#push-tracking-postback)
   * [Locatie na terugzetten](../../administration/using/configuring-rules-launch.md#location-postback)

## Gegevenselementen maken {#create-data-elements}

Hier zijn de gegevenselementen wij adviseren dat u in de UI van de Inzameling van Gegevens creeert.
U kunt naar wens aanvullende gegevenselementen maken.

* **[!UICONTROL Experience Cloud ID]**
* **[!UICONTROL Pkey]**
* **[!UICONTROL Campaign server]**

U kunt als volgt deze gegevenselementen maken:

1. Klik in de gebruikersinterface voor gegevensverzameling op het dashboard voor mobiele toepassingen op de knop **[!UICONTROL Data Elements]** tab.

1. Als u de opdracht **[!UICONTROL Experience Cloud ID]** gegevenselement, klik **[!UICONTROL Create New Data Element]**.

1. In de **[!UICONTROL Name]** veld, bijvoorbeeld intypen **mcid**.

1. Van de **[!UICONTROL Extension]** vervolgkeuzelijst, selecteert u **[!UICONTROL Mobile Core]**. Vervolgens **[!UICONTROL Experience Cloud ID]** in de **[!UICONTROL Data element]** type drop-down.

   ![](assets/do-not-localize/rules_1.png)

1. Klik op **[!UICONTROL Add data element]**.

1. In de **[!UICONTROL Name]** veld, bijvoorbeeld intypen **pkey**.

1. Van de **[!UICONTROL Extension]** vervolgkeuzelijst, selecteert u **[!UICONTROL Adobe Campaign Standard]**. Vervolgens **[!UICONTROL pkey]** in de **[!UICONTROL Data element]** type drop-down.

1. Als u het gegevenselement Campagneserver wilt maken, klikt u op **[!UICONTROL Add data element]**.

1. In de **[!UICONTROL Name]** veld, typ een naam, bijvoorbeeld **kampeerserver**.

1. Van de **[!UICONTROL Extension]** vervolgkeuzelijst, selecteert u **[!UICONTROL Adobe Campaign Standard]**. Dan, **[!UICONTROL Campaign Server]** in de **[!UICONTROL Data element]** type drop-down.

## Regels maken {#creating-rules}

U moet regels maken voor het volgende:

* [PII-postback](../../administration/using/configuring-rules-launch.md#pii-postback)
* [Postback bijhouden in de app](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback)
* [Postback-up van pushberichten](../../administration/using/configuring-rules-launch.md#push-tracking-postback)
* [Locatie na terugzetten](../../administration/using/configuring-rules-launch.md#location-postback)

### PII-postback {#pii-postback}

>[!NOTE]
>
>Als u PII-gegevens van een mobiele app naar Adobe Campaign wilt verzenden, moet u een SDK-API implementeren. Ga voor meer informatie naar [CollectPII](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference/#collectpii).

PII-gegevens verzenden naar [!DNL Adobe Campaign Standard], maakt u een regel in de gebruikersinterface voor gegevensverzameling:

1. Klik in de gebruikersinterface voor gegevensverzameling op het dashboard voor mobiele toepassingen op de knop **[!UICONTROL Rules]** dan op **[!UICONTROL Create New Rule]**.

1. Typ bijvoorbeeld een naam, **Mobile Core - Collect PII**.

1. In de **[!UICONTROL Events]** sectie, klikken **[!UICONTROL Add]**.

1. Van de **[!UICONTROL Extension]** vervolgkeuzelijst, selecteert u **[!UICONTROL Mobile Core]**. Dan, **[!UICONTROL Collect PII]** in de **[!UICONTROL Event type]** vervolgkeuzelijst.

1. Klik op **[!UICONTROL Keep changes]**.

1. In de **[!UICONTROL Actions]** sectie, klikken **[!UICONTROL Add]**.

1. Van de **[!UICONTROL Extension]** vervolgkeuzelijst, selecteert u **[!UICONTROL Mobile Core]**. Dan, **[!UICONTROL Send PII]** in de **[!UICONTROL Action type]** vervolgkeuzelijst.

1. In **[!UICONTROL URL]** Voer de volgende URL in:

   ```
   https://{%%camp-server%%}/rest/head/mobileAppV5/{%%pkey%%}/subscriptions/{%%mcid%%}
   ```

1. Selecteer de **[!UICONTROL Add Post Body]** selectievakje.

1. In **[!UICONTROL Post Body]**, typt u het volgende:

   ```
   {
   "marketingCloudId":
   "{%%mcid%%}",
   "pushPlatform":
   "{%contextdata.pushPlatform%}",
   "cusEmail":
   "{%contextdata.email%}",
   "cusFirstName":
   "{%contextdata.firstName%}",
   "cusLastName":
   "{%contextdata.lastName%}" }
   ```

   Met de marketingCloudId kunt u uw app-abonnees in overeenstemming brengen met de ontvangers in de database en is het daarom vereist. U kunt andere sleutel-waardeparen specificeren zoals op uw bedrijfsbehoeften. In het bovenstaande voorbeeld worden E-mail, Voornaam en Achternaam doorgegeven vanuit de app.

   De sleutels (bijvoorbeeld cusEmail, cusFirstName, en cusLastName) zouden de gebied IDs moeten aanpassen die in uw douanemiddel in de instantie van Adobe Campaign Standard worden bepaald. De waardevariabelen (bijvoorbeeld e-mail, firstName en LastName) moeten overeenkomen met de sleutels in de JSON-gegevens die vanuit de mobiele app worden verzonden, terwijl de API voor het verzamelen van AMS vanuit de toepassingscode wordt aangeroepen.

   U kunt levenscyclusgegevens ook doorgeven in de PII-nabewerking verzamelen of een andere nabewerking, afhankelijk van de gebeurtenistriggers. Hier is een voorbeeld van de Lifecycle Data JSON:

   ```
   {
   "marketingCloudId":"{%%mcid%%}",
   "pushPlatform":"{%contextdata.pushPlatform%}",
   "cusDayslastlaunch": "{%%DaysSinceLastUse%%}", 
   "cusDaysfirstlaunch": "{%%DaysSinceFirstUse%%}", 
   "cusLaunches": "{%%Launches%%}"
   }
   ```

   De gegevenselementen die in UI van de Inzameling van Gegevens worden bepaald zouden in dubbele percentages, bijvoorbeeld moeten worden ingesloten `%%mcid%%`en contextvariabelen van de app moeten worden opgenomen in enkele percentages, bijvoorbeeld %contextdata.email%.

1. In **[!UICONTROL Content Type]**, type **application/json**.

1. In **[!UICONTROL Timeout]** selecteert u 0.

   ![](assets/do-not-localize/rules_2.png)

Uw gebruikersgegevens zijn nu geconfigureerd om naar Campagne te worden verzonden.

### Postback bijhouden in de app {#inapp-tracking-postback}

>[!NOTE]
>
>Als u Android ACPCore v1.4.0 of later/ iOS ACPCore v2.3.0 of later gebruikt, is het niet nodig om trackingpostbacks te configureren.

Trackinggegevens verzenden naar [!DNL Adobe Campaign Standard] voor het melden van hoe uw gebruikers met In-App berichten in uw mobiele toepassing interactie aangaan, creeer de volgende regel in de UI van de Inzameling van Gegevens:

1. Selecteer in de gebruikersinterface voor gegevensverzameling op het dashboard voor mobiele toepassingen de optie **[!UICONTROL Rules]** en klik op **[!UICONTROL Add Rule]**.

1. Typ bijvoorbeeld een naam, **Adobe Campaign - In-app klikken op bijhouden**.

1. In de **[!UICONTROL Events]** sectie, klikken **[!UICONTROL Add]**.

1. Van de **[!UICONTROL Extension]** vervolgkeuzelijst, selecteert u **[!UICONTROL Adobe Campaign Standard]**. Dan, **[!UICONTROL In-App click tracking]** in de **[!UICONTROL Event type]** vervolgkeuzelijst.

1. Klik op **[!UICONTROL Keep changes]**.

1. In de **[!UICONTROL Actions]** sectie, klikken **[!UICONTROL Add]**.

1. Van de **[!UICONTROL Extension]** vervolgkeuzelijst, selecteert u **[!UICONTROL Mobile Core]**. Dan, **[!UICONTROL Send postback]** in de **[!UICONTROL Event type]** vervolgkeuzelijst.

1. In **[!UICONTROL URL]** Typ de volgende URL:

   ```
   https://{%%camp-server%%}/r/?id={%id%}&mcid={%%mcid%%}
   ```

1. Selecteer de **[!UICONTROL Add post body]** selectievakje.

1. In **[!UICONTROL Post Body]**, type **{}**.

1. In **[!UICONTROL Content Type]**, type **application/json**.

1. In **[!UICONTROL Timeout]** selecteert u 0.

   ![](assets/do-not-localize/rules_3.png)

### Postback-up van pushberichten {#push-tracking-postback}

>[!NOTE]
>
>Als u Android ACPCore v1.4.0 of later/ iOS ACPCore v2.3.0 of later gebruikt, is het niet nodig om trackingpostbacks te configureren.

Trackinggegevens verzenden naar [!DNL Adobe Campaign Standard], die u helpt bij het bijhouden van uw pushberichten en de interactie van uw gebruikers met uw mobiele toepassing, moet u een regel maken in de gebruikersinterface voor gegevensverzameling.

Voor meer informatie over het bijhouden van push-berichten raadpleegt u [Push Tracking](../../administration/using/push-tracking.md).

Gebruik de trackAction-API om de handelingen van de app bij te houden. Zie voor meer informatie [Toepassingsacties bijhouden](https://app.gitbook.com/@aep-sdks/s/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions).

1. Klik in de gebruikersinterface voor gegevensverzameling op het dashboard voor mobiele toepassingen op de knop **[!UICONTROL Rules]** en klik op **[!UICONTROL Add Rule]**.

1. Typ bijvoorbeeld een naam, **Adobe Campaign - bijhouden van klikken met push**.

1. In de **[!UICONTROL Events]** sectie, klikken **[!UICONTROL Add]**.

1. Van de **[!UICONTROL Extension]** vervolgkeuzelijst, selecteert u **[!UICONTROL Mobile Core]**. Dan, **[!UICONTROL Track Action]** in de **[!UICONTROL Event type]** vervolgkeuzelijst.

1. Van de **[!UICONTROL Action]** vervolgkeuzelijst, selecteert u **[!UICONTROL Action]**, selecteert u **[!UICONTROL equals]**, en type **bijhouden**.

1. Klik op **[!UICONTROL Keep changes]**. Dan, in **[!UICONTROL Actions]** sectie, klikken **[!UICONTROL Add]**.

1. Van de **[!UICONTROL Extension]** vervolgkeuzelijst, selecteert u **[!UICONTROL Mobile Core]**. Dan, **[!UICONTROL Send postback]** in de **[!UICONTROL Action type]** vervolgkeuzelijst.

1. In **[!UICONTROL URL]** Voer de volgende URL in:

   ```
   https://{%%camp-server%%}/r/?id={%contextdata.broadlogId%},{%contextdata.deliveryId%},{%contextdata.action%}&mcId={%%mcid%%}
   ```

1. Selecteer de **[!UICONTROL Add post body]** selectievakje.

1. Voeg bijvoorbeeld de tekst { } toe.

1. In **[!UICONTROL Content Type]**, type **application/json**.

1. In **[!UICONTROL Timeout]** selecteert u 0.

### Locatie na terugzetten {#location-postback}

1. Klik in de gebruikersinterface voor gegevensverzameling op het dashboard voor mobiele toepassingen op de knop **[!UICONTROL Rules]** en klik op **[!UICONTROL Add Rule]**.

1. Typ bijvoorbeeld een naam, **Locatie na terugzetten**.

1. In de **[!UICONTROL Events]** sectie, klikken **[!UICONTROL Add]**.

1. Maak een gebeurtenis, bijvoorbeeld, Enter POI of Exit POI. Van de **[!UICONTROL Extension]** vervolgkeuzelijst, selecteert u **Plaatsen - bèta**. Dan, **POI invoeren** of **POI afsluiten** in de **[!UICONTROL Event type]** vervolgkeuzelijst.

1. Voer bijvoorbeeld een naam in **Plaatsen - bèta - ga POI in** of **POI afsluiten**.

1. In de **[!UICONTROL Actions]** sectie, klikken **[!UICONTROL Add]**.

1. Van de **[!UICONTROL Extension]** vervolgkeuzelijst, selecteert u **[!UICONTROL Mobile Core]**. Dan, **[!UICONTROL Send postback]** van de **[!UICONTROL Action type]** vervolgkeuzelijst.

1. Voer bijvoorbeeld een naam in **Mobiele kern - Locatiepostback verzenden**.

1. In **[!UICONTROL URL]** Voer de volgende URL in:

   ```
   https://{%%camp-server%%}/rest/head/mobileAppV5/{%%pkey%%}/locations/
   ```

1. Selecteer de **[!UICONTROL Add post body]** selectievakje en voeg je berichttekst toe, bijvoorbeeld:

   ```
   {
   "locationData": {
       "distances": "{%%Distance%%}",
       "poiLabel": "{%%POILabel%%}",
       "latitude": "{%%Latitude%%}",
       "longitude": "{%%Longitude%%}",
       "appId": "{%%AppId%%}",
       "marketingCloudId": "{%%ECID%%}"
   }
   }
   ```

   >[!NOTE]
   >
   >In het bovenstaande voorbeeld moeten de gegevenselementen aan de rechterkant worden geconfigureerd in de interface voor gegevensverzameling door de stappen in [Gegevenselementen maken](../../administration/using/configuring-rules-launch.md#create-data-elements). De gegevenselementen aan de linkerkant worden ondersteund in [!DNL Adobe Campaign Standard] en hebt geen configuratie nodig. Als u aanvullende gegevens nodig hebt, moet u de uitbreidingen van aangepaste bronnen uitvoeren in [!DNL Adobe Campaign Standard].

1. In **[!UICONTROL Content Type]**, type **application/json**.

1. In **[!UICONTROL Timeout]** selecteert u 5.

   ![](assets/do-not-localize/rules_4.png)
