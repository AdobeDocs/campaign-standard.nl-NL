---
title: Adobe Experience Platform Launch-regels configureren ter ondersteuning van Adobe Campaign Standard-gebruiksgevallen
description: Adobe Experience Platform Launch-regels configureren ter ondersteuning van Adobe Campaign Standard-gebruiksgevallen
page-status-flag: never-activated
uuid: 961aaeb5-6948-4fd2-b8d7-de4510c10566
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: push-notifications
discoiquuid: 23b4212e-e878-4922-be20-50fb7fa88ae8
context-tags: mobileApp,overview
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '914'
ht-degree: 1%

---


# Launch-regels configureren voor ondersteuning van Adobe Campaign Standard-gebruiksscenario’s {#configuring-rules-launch}

In [!DNL Adobe Experience Platform Launch], moet u gegevenselementen en regels tot stand brengen om PII en andere gegevens van mobiele toepassingen naar te verzenden [!DNL Adobe Campaign Standard].

Om ervoor te zorgen dat alle configuratieveranderingen in [!DNL Adobe Experience Platform Launch] werking treden, moet u deze veranderingen publiceren. Zie [Publiceren](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#publish-the-configuration)voor meer informatie.

Voer de volgende stappen uit om regels te maken in [!DNL Experience Platform Launch]:

1. [Gegevenselementen maken](../../administration/using/configuring-rules-launch.md#create-data-elements)
2. [Het creëren van regels](../../administration/using/configuring-rules-launch.md#create-data-elements) voor gebruiksgevallen wilt u steunen:
   * [PII-postback](../../administration/using/configuring-rules-launch.md#pii-postback)
   * [Postback bijhouden in de app](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback)
   * [Postback-up van pushberichten](../../administration/using/configuring-rules-launch.md#push-tracking-postback)
   * [Locatie na terugzetten](../../administration/using/configuring-rules-launch.md#location-postback)

## Gegevenselementen maken {#create-data-elements}

Hier zijn de gegevenselementen wij adviseren dat u binnen creeert [!DNL Experience Platform Launch].
U kunt naar wens aanvullende gegevenselementen maken.

* **[!UICONTROL Experience Cloud ID]**
* **[!UICONTROL Pkey]**
* **[!UICONTROL Campaign server]**

U kunt als volgt deze gegevenselementen maken:

1. Klik in [!DNL Experience Platform Launch]het dashboard van de mobiele toepassing op het **[!UICONTROL Data Elements]** tabblad.

1. Klik op het **[!UICONTROL Experience Cloud ID]** **[!UICONTROL Create New Data Element]** gegevenselement om het te maken.

1. Typ in het **[!UICONTROL Name]** veld bijvoorbeeld in **mcid**.

1. From the **[!UICONTROL Extension]** drop-down, select **[!UICONTROL Mobile Core]**. Dan **[!UICONTROL Experience Cloud ID]** in de **[!UICONTROL Data element]** typedrop-down.

   ![](assets/do-not-localize/rules_1.png)

1. Klik op Pkey-gegevenselement om het Pkey-gegevenselement te maken **[!UICONTROL Add data element]**.

1. Typ in het **[!UICONTROL Name]** veld bijvoorbeeld **pkey**.

1. From the **[!UICONTROL Extension]** drop-down, select **[!UICONTROL Adobe Campaign Standard]**. Dan **[!UICONTROL pkey]** in de **[!UICONTROL Data element]** typedrop-down.

1. Klik op het gegevenselement Campagneserver om dit te maken. **[!UICONTROL Add data element]**

1. Typ in het **[!UICONTROL Name]** veld een naam, bijvoorbeeld **kampserver**.

1. From the **[!UICONTROL Extension]** drop-down, select **[!UICONTROL Adobe Campaign Standard]**. Dan, **[!UICONTROL Campaign Server]** in de **[!UICONTROL Data element]** typedrop-down.

## Regels maken {#creating-rules}

U moet regels maken voor het volgende:

* [PII-postback](../../administration/using/configuring-rules-launch.md#pii-postback)
* [Postback bijhouden in de app](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback)
* [Postback-up van pushberichten](../../administration/using/configuring-rules-launch.md#push-tracking-postback)
* [Locatie na terugzetten](../../administration/using/configuring-rules-launch.md#location-postback)

### PII-postback {#pii-postback}

>[!NOTE]
>
>Als u PII-informatie van een mobiele app naar Adobe Campaign wilt verzenden, moet u een SDK API implementeren. Ga voor meer informatie naar [CollectPII](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#collect-pii).

Als u PII-gegevens wilt verzenden naar [!DNL Adobe Campaign Standard], maakt u een regel in [!DNL Experience Platform Launch]:

1. Klik in [!DNL Experience Platform Launch]het dashboard van de mobiele toepassing op het **[!UICONTROL Rules]** tabblad en vervolgens op **[!UICONTROL Create New Rule]**.

1. Typ een naam, bijvoorbeeld **Mobile Core - Collect PII**.

1. In the **[!UICONTROL Events]** section, click **[!UICONTROL Add]**.

1. From the **[!UICONTROL Extension]** drop-down, select **[!UICONTROL Mobile Core]**. Dan, **[!UICONTROL Collect PII]** in de **[!UICONTROL Event type]** drop-down.

1. Klik op **[!UICONTROL Keep changes]**.

1. In the **[!UICONTROL Actions]** section, click **[!UICONTROL Add]**.

1. From the **[!UICONTROL Extension]** drop-down, select **[!UICONTROL Mobile Core]**. Dan, **[!UICONTROL Send PII]** in de **[!UICONTROL Action type]** drop-down.

1. Voer in **[!UICONTROL URL]** de volgende URL in:

   ```
   https://{%%camp-server%%}/rest/head/mobileAppV5/{%%pkey%%}/subscriptions/{%%mcid%%}
   ```

1. Select the **[!UICONTROL Add Post Body]** check box.

1. Typ bij **[!UICONTROL Post Body]** deze optie het volgende:

   ```
   {
   "marketingCloudId":
   "{%%mcid%%}",
   "cusEmail":
   "{%contextdata.email%}",
   "cusFirstName":
   "{%contextdata.firstName%}",
   "cusLastName":
   "{%contextdata.lastName%}" }
   ```

   Met de marketingCloudId kunt u uw app-abonnees in overeenstemming brengen met de ontvangers in de database en is het daarom vereist. U kunt andere sleutel-waardeparen specificeren zoals uw bedrijfsbehoeften. In het bovenstaande voorbeeld worden E-mail, Voornaam en Achternaam doorgegeven vanuit de app.

   De sleutels (bijvoorbeeld cusEmail, cusFirstName, en cusLastName) zouden de gebied IDs moeten aanpassen die in uw douanemiddel in de instantie van Adobe Campaign Standard worden bepaald. De waardevariabelen (bijvoorbeeld email, firstName en LastName) moeten overeenkomen met de toetsen in de JSON-gegevens die vanuit de mobiele app worden verzonden, terwijl de API voor het verzamelen van AMS vanuit de toepassingscode wordt aangeroepen.

   U kunt levenscyclusgegevens ook doorgeven in de PII-nabewerking verzamelen of een andere nabewerking afhankelijk van de gebeurtenistriggers. Hier is een voorbeeld van de Lifecycle Data JSON:

   ```
   {
   "marketingCloudId":"{%%mcid%%}",
   "cusDayslastlaunch": "{%%DaysSinceLastUse%%}", 
   "cusDaysfirstlaunch": "{%%DaysSinceFirstUse%%}", 
   "cusLaunches": "{%%Launches%%}"
   }
   ```

   De gegevenselementen die in worden gedefinieerd, [!DNL Experience Platform Launch] moeten worden ingesloten in dubbele percentages, bijvoorbeeld %%mcid%%, en contextvariabelen van de app moeten worden ingesloten in enkele percentages, bijvoorbeeld %contextdata.email%.

1. Typ in **[!UICONTROL Content Type]** het tekstvak **application/json**.

1. In **[!UICONTROL Timeout]**, select 0.

   ![](assets/do-not-localize/rules_2.png)

Uw gebruikersgegevens zijn nu geconfigureerd om naar Campagne te worden verzonden.

### Postback bijhouden in de app {#inapp-tracking-postback}

Als u volggegevens wilt verzenden naar [!DNL Adobe Campaign Standard] voor rapportage over hoe uw gebruikers in uw mobiele toepassing communiceren met In-App-berichten, maakt u de volgende regel in [!DNL Experience Platform Launch]:

1. Selecteer in [!DNL Experience Platform Launch]het dashboard van de mobiele toepassing de **[!UICONTROL Rules]** tab en klik op **[!UICONTROL Add Rule]**.

1. Typ een naam, bijvoorbeeld **Adobe Campaign - In-app klik op bijhouden**.

1. In the **[!UICONTROL Events]** section, click **[!UICONTROL Add]**.

1. From the **[!UICONTROL Extension]** drop-down, select **[!UICONTROL Adobe Campaign Standard]**. Dan, **[!UICONTROL In-App click tracking]** in de **[!UICONTROL Event type]** drop-down.

1. Klik op **[!UICONTROL Keep changes]**.

1. In the **[!UICONTROL Actions]** section, click **[!UICONTROL Add]**.

1. From the **[!UICONTROL Extension]** drop-down, select **[!UICONTROL Mobile Core]**. Dan, **[!UICONTROL Send postback]** in de **[!UICONTROL Event type]** drop-down.

1. Typ in **[!UICONTROL URL]** dit vak de volgende URL:

   ```
   https://{%%camp-server%%}/r/?id={%id%}&mcid={%%mcid%%}
   ```

1. Select the **[!UICONTROL Add post body]** check box.

1. In **[!UICONTROL Post Body]** typt u **{}**.

1. Typ in **[!UICONTROL Content Type]** het tekstvak **application/json**.

1. In **[!UICONTROL Timeout]**, select 0.

   ![](assets/do-not-localize/rules_3.png)

### Postback-up van pushberichten {#push-tracking-postback}

Als u volggegevens wilt verzenden naar [!DNL Adobe Campaign Standard], waarmee u de pushberichten en de interactie van uw gebruikers met uw mobiele toepassing kunt bijhouden, moet u een regel maken in [!DNL Experience Platform Launch].

Zie [Push Tracking](../../administration/using/push-tracking.md)voor meer informatie over push-tracking.

Gebruik de trackAction-API om de handelingen van de app bij te houden. Zie Toepassingsacties [](https://app.gitbook.com/@aep-sdks/s/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions)bijhouden voor meer informatie.

1. Klik in [!DNL Experience Platform Launch]het dashboard van de mobiele toepassing op het **[!UICONTROL Rules]** tabblad en klik **[!UICONTROL Add Rule]**.

1. Typ een naam, bijvoorbeeld **Adobe Campaign - klik het volgen**.

1. In the **[!UICONTROL Events]** section, click **[!UICONTROL Add]**.

1. From the **[!UICONTROL Extension]** drop-down, select **[!UICONTROL Mobile Core]**. Dan, **[!UICONTROL Track Action]** in de **[!UICONTROL Event type]** drop-down.

1. Selecteer in de **[!UICONTROL Action]** vervolgkeuzelijst de optie **[!UICONTROL Action]**, selecteer **[!UICONTROL equals]** en typ **tekstspatiëring**.

1. Klik op **[!UICONTROL Keep changes]**. Klik vervolgens in de **[!UICONTROL Actions]** sectie op **[!UICONTROL Add]**.

1. From the **[!UICONTROL Extension]** drop-down, select **[!UICONTROL Mobile Core]**. Dan, **[!UICONTROL Send postback]** in de **[!UICONTROL Action type]** drop-down.

1. Voer in **[!UICONTROL URL]** de volgende URL in:

   ```
   https://{%%camp-server%%}/r/?id={%contextdata.broadlogId%},{%contextdata.deliveryId%},{%contextdata.action%}&mcId={%%mcid%%}
   ```

1. Select the **[!UICONTROL Add post body]** check box.

1. Voeg je berichttekst toe, bijvoorbeeld { }.

1. Typ in **[!UICONTROL Content Type]** het tekstvak **application/json**.

1. In **[!UICONTROL Timeout]**, select 0.

### Locatie na terugzetten {#location-postback}

1. Klik in [!DNL Experience Platform Launch]het dashboard van de mobiele toepassing op het **[!UICONTROL Rules]** tabblad en klik **[!UICONTROL Add Rule]**.

1. Typ een naam, bijvoorbeeld **Locatie na** terugsturen.

1. In the **[!UICONTROL Events]** section, click **[!UICONTROL Add]**.

1. Maak een gebeurtenis, bijvoorbeeld, Enter POI of Exit POI. Selecteer **[!UICONTROL Extension]** Plaatsen - bèta in het **keuzemenu**. Dan, **ga POI** of **Uitgang POI** in de **[!UICONTROL Event type]** drop-down in.

1. Voer een naam in, bijvoorbeeld **Plaatsen - Bèta - Voer de POI** in of **Sluit de POI** af.

1. In the **[!UICONTROL Actions]** section, click **[!UICONTROL Add]**.

1. From the **[!UICONTROL Extension]** drop-down, select **[!UICONTROL Mobile Core]**. Vervolgens **[!UICONTROL Send postback]** vanuit de **[!UICONTROL Action type]** vervolgkeuzelijst.

1. Voer een naam in, bijvoorbeeld **Mobile Core - Send Location Postback**.

1. Voer in **[!UICONTROL URL]** de volgende URL in:

   ```
   https://{%%camp-server%%}/rest/head/mobileAppV5/{%%pkey%%}/locations/
   ```

1. Schakel het **[!UICONTROL Add post body]** selectievakje in en voeg bijvoorbeeld de tekst van het bericht toe:

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
   >In het bovenstaande voorbeeld moeten de gegevenselementen aan de rechterkant worden geconfigureerd [!DNL Experience Platform Launch] door de stappen in het [maken van gegevenselementen](../../administration/using/configuring-rules-launch.md#create-data-elements)te benutten. De gegevenselementen aan de linkerkant worden ondersteund in [!DNL Adobe Campaign Standard] en hoeven niet te worden geconfigureerd. Als u aanvullende gegevens nodig hebt, moet u aangepaste bronextensies uitvoeren in [!DNL Adobe Campaign Standard].

1. Typ in **[!UICONTROL Content Type]** het tekstvak **application/json**.

1. In **[!UICONTROL Timeout]**, select 5.

   ![](assets/do-not-localize/rules_4.png)
