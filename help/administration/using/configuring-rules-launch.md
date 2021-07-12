---
solution: Campaign Standard
product: campaign
title: Adobe Experience Platform Launch-regels configureren ter ondersteuning van Adobe Campaign Standard-gebruiksgevallen
description: Adobe Experience Platform Launch-regels configureren ter ondersteuning van Adobe Campaign Standard-gebruiksgevallen
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
feature: Instantie-instellingen
role: Admin
level: Experienced
exl-id: b5f4f612-ea23-4007-b427-069777ecdd58
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '956'
ht-degree: 1%

---

# Launch-regels configureren voor ondersteuning van Adobe Campaign Standard-gebruiksscenario’s {#configuring-rules-launch}

In [!DNL Adobe Experience Platform Launch], moet u gegevenselementen en regels tot stand brengen om PII en andere gegevens van mobiele toepassingen naar [!DNL Adobe Campaign Standard] te verzenden.

Om ervoor te zorgen dat alle configuratieveranderingen in [!DNL Adobe Experience Platform Launch] van kracht worden, moet u deze veranderingen publiceren. Zie [Publiceren](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#publish-the-configuration) voor meer informatie.

Ga als volgt te werk om regels te maken in [!DNL Experience Platform Launch]:

1. [Gegevenselementen maken](../../administration/using/configuring-rules-launch.md#create-data-elements)
2. [Het creëren van ](../../administration/using/configuring-rules-launch.md#create-data-elements) regels voor gebruiksgevallen wilt u steunen:
   * [PII-postback](../../administration/using/configuring-rules-launch.md#pii-postback)
   * [Postback bijhouden in de app](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback)
   * [Postback-up van pushberichten](../../administration/using/configuring-rules-launch.md#push-tracking-postback)
   * [Locatie na terugzetten](../../administration/using/configuring-rules-launch.md#location-postback)

## Gegevenselementen maken {#create-data-elements}

Hier zijn de gegevenselementen wij adviseren dat u in [!DNL Experience Platform Launch] creeert.
U kunt naar wens aanvullende gegevenselementen maken.

* **[!UICONTROL Experience Cloud ID]**
* **[!UICONTROL Pkey]**
* **[!UICONTROL Campaign server]**

U kunt als volgt deze gegevenselementen maken:

1. Klik in [!DNL Experience Platform Launch] op het tabblad **[!UICONTROL Data Elements]** van het dashboard voor mobiele toepassingen.

1. Als u het gegevenselement **[!UICONTROL Experience Cloud ID]** wilt maken, klikt u op **[!UICONTROL Create New Data Element]**.

1. Typ in het veld **[!UICONTROL Name]** bijvoorbeeld **mcid**.

1. Selecteer **[!UICONTROL Mobile Core]** in de vervolgkeuzelijst **[!UICONTROL Extension]**. Vervolgens **[!UICONTROL Experience Cloud ID]** in de vervolgkeuzelijst **[!UICONTROL Data element]** typen.

   ![](assets/do-not-localize/rules_1.png)

1. Klik op **[!UICONTROL Add data element]** om het Pkey-gegevenselement te maken.

1. Typ in het veld **[!UICONTROL Name]** bijvoorbeeld **pkey**.

1. Selecteer **[!UICONTROL Adobe Campaign Standard]** in de vervolgkeuzelijst **[!UICONTROL Extension]**. Vervolgens **[!UICONTROL pkey]** in de vervolgkeuzelijst **[!UICONTROL Data element]** typen.

1. Klik op **[!UICONTROL Add data element]** om het gegevenselement Campagneserver te maken.

1. Typ in het veld **[!UICONTROL Name]** een naam, bijvoorbeeld **kampserver**.

1. Selecteer **[!UICONTROL Adobe Campaign Standard]** in de vervolgkeuzelijst **[!UICONTROL Extension]**. Vervolgens **[!UICONTROL Campaign Server]** in de vervolgkeuzelijst **[!UICONTROL Data element]** typen.

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

Als u PII-gegevens naar [!DNL Adobe Campaign Standard] wilt verzenden, maakt u een regel in [!DNL Experience Platform Launch]:

1. Klik in [!DNL Experience Platform Launch] vanaf het dashboard voor mobiele toepassingen op het tabblad **[!UICONTROL Rules]** en **[!UICONTROL Create New Rule]**.

1. Typ een naam, bijvoorbeeld **Mobile Core - Collect PII**.

1. Klik in de sectie **[!UICONTROL Events]** op **[!UICONTROL Add]**.

1. Selecteer **[!UICONTROL Mobile Core]** in de vervolgkeuzelijst **[!UICONTROL Extension]**. Vervolgens **[!UICONTROL Collect PII]** in de vervolgkeuzelijst **[!UICONTROL Event type]**.

1. Klik op **[!UICONTROL Keep changes]**.

1. Klik in de sectie **[!UICONTROL Actions]** op **[!UICONTROL Add]**.

1. Selecteer **[!UICONTROL Mobile Core]** in de vervolgkeuzelijst **[!UICONTROL Extension]**. Vervolgens **[!UICONTROL Send PII]** in de vervolgkeuzelijst **[!UICONTROL Action type]**.

1. Voer in **[!UICONTROL URL]** de volgende URL in:

   ```
   https://{%%camp-server%%}/rest/head/mobileAppV5/{%%pkey%%}/subscriptions/{%%mcid%%}
   ```

1. Schakel het selectievakje **[!UICONTROL Add Post Body]** in.

1. Typ in **[!UICONTROL Post Body]** het volgende:

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

   De gegevenselementen die in [!DNL Experience Platform Launch] worden gedefinieerd, moeten in dubbele percentages worden ingesloten, bijvoorbeeld %%mcid%%, en contextvariabelen van de app moeten in enkele percentages worden ingesloten, bijvoorbeeld %contextdata.email%.

1. Typ **application/json** in **[!UICONTROL Content Type]**.

1. Selecteer 0 in **[!UICONTROL Timeout]**.

   ![](assets/do-not-localize/rules_2.png)

Uw gebruikersgegevens zijn nu geconfigureerd om naar Campagne te worden verzonden.

### Postback bijhouden in de app {#inapp-tracking-postback}

>[!NOTE]
>
>Als u Android ACPCore v1.4.0 of later/ iOS ACPCore v2.3.0 of later gebruikt, is het configureren van teruggestuurde back-ups niet vereist.

Als u volggegevens naar [!DNL Adobe Campaign Standard] wilt verzenden voor rapportage over hoe uw gebruikers in uw mobiele toepassing communiceren met In-App-berichten, maakt u de volgende regel in [!DNL Experience Platform Launch]:

1. Selecteer in [!DNL Experience Platform Launch] op het dashboard voor mobiele toepassingen de tab **[!UICONTROL Rules]** en klik op **[!UICONTROL Add Rule]**.

1. Typ een naam, bijvoorbeeld **Adobe Campaign - In-app klik op tracking**.

1. Klik in de sectie **[!UICONTROL Events]** op **[!UICONTROL Add]**.

1. Selecteer **[!UICONTROL Adobe Campaign Standard]** in de vervolgkeuzelijst **[!UICONTROL Extension]**. Vervolgens **[!UICONTROL In-App click tracking]** in de vervolgkeuzelijst **[!UICONTROL Event type]**.

1. Klik op **[!UICONTROL Keep changes]**.

1. Klik in de sectie **[!UICONTROL Actions]** op **[!UICONTROL Add]**.

1. Selecteer **[!UICONTROL Mobile Core]** in de vervolgkeuzelijst **[!UICONTROL Extension]**. Vervolgens **[!UICONTROL Send postback]** in de vervolgkeuzelijst **[!UICONTROL Event type]**.

1. Typ de volgende URL in **[!UICONTROL URL]**:

   ```
   https://{%%camp-server%%}/r/?id={%id%}&mcid={%%mcid%%}
   ```

1. Schakel het selectievakje **[!UICONTROL Add post body]** in.

1. In **[!UICONTROL Post Body]** typt u **{}**.

1. Typ **application/json** in **[!UICONTROL Content Type]**.

1. Selecteer 0 in **[!UICONTROL Timeout]**.

   ![](assets/do-not-localize/rules_3.png)

### Postback-up van pushberichten {#push-tracking-postback}

>[!NOTE]
>
>Als u Android ACPCore v1.4.0 of later/ iOS ACPCore v2.3.0 of later gebruikt, is het configureren van teruggestuurde back-ups niet vereist.

Als u volggegevens wilt verzenden naar [!DNL Adobe Campaign Standard], waarmee u uw pushmeldingleveringen en de interactie van uw gebruikers met uw mobiele toepassing kunt bijhouden, moet u een regel maken in [!DNL Experience Platform Launch].

Zie [Push Tracking](../../administration/using/push-tracking.md) voor meer informatie over push-tracking.

Gebruik de trackAction-API om de handelingen van de app bij te houden. Zie [Toepassingsacties bijhouden](https://app.gitbook.com/@aep-sdks/s/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions) voor meer informatie.

1. Klik in [!DNL Experience Platform Launch] op het tabblad **[!UICONTROL Rules]** van het dashboard voor mobiele toepassingen en klik op **[!UICONTROL Add Rule]**.

1. Typ een naam, bijvoorbeeld **Adobe Campaign - duw klik het volgen**.

1. Klik in de sectie **[!UICONTROL Events]** op **[!UICONTROL Add]**.

1. Selecteer **[!UICONTROL Mobile Core]** in de vervolgkeuzelijst **[!UICONTROL Extension]**. Vervolgens **[!UICONTROL Track Action]** in de vervolgkeuzelijst **[!UICONTROL Event type]**.

1. Selecteer **[!UICONTROL Action]** in de vervolgkeuzelijst **[!UICONTROL Action]**, selecteer **[!UICONTROL equals]** en typ **tracking**.

1. Klik op **[!UICONTROL Keep changes]**. Klik vervolgens in de sectie **[!UICONTROL Actions]** op **[!UICONTROL Add]**.

1. Selecteer **[!UICONTROL Mobile Core]** in de vervolgkeuzelijst **[!UICONTROL Extension]**. Vervolgens **[!UICONTROL Send postback]** in de vervolgkeuzelijst **[!UICONTROL Action type]**.

1. Voer in **[!UICONTROL URL]** de volgende URL in:

   ```
   https://{%%camp-server%%}/r/?id={%contextdata.broadlogId%},{%contextdata.deliveryId%},{%contextdata.action%}&mcId={%%mcid%%}
   ```

1. Schakel het selectievakje **[!UICONTROL Add post body]** in.

1. Voeg je berichttekst toe, bijvoorbeeld { }.

1. Typ **application/json** in **[!UICONTROL Content Type]**.

1. Selecteer 0 in **[!UICONTROL Timeout]**.

### Locatie na terugzetten {#location-postback}

1. Klik in [!DNL Experience Platform Launch] op het tabblad **[!UICONTROL Rules]** van het dashboard voor mobiele toepassingen en klik op **[!UICONTROL Add Rule]**.

1. Typ een naam, bijvoorbeeld **Locatiepostback**.

1. Klik in de sectie **[!UICONTROL Events]** op **[!UICONTROL Add]**.

1. Maak een gebeurtenis, bijvoorbeeld, Enter POI of Exit POI. Selecteer **[!UICONTROL Extension]** Plaatsen - Bèta **in de vervolgkeuzelijst**. Vervolgens **Voer POI** of **Sluit POI** in de vervolgkeuzelijst **[!UICONTROL Event type]** in.

1. Voer een naam in, bijvoorbeeld **Plaatsen - Bèta - Enter POI** of **Sluit POI**.

1. Klik in de sectie **[!UICONTROL Actions]** op **[!UICONTROL Add]**.

1. Selecteer **[!UICONTROL Mobile Core]** in de vervolgkeuzelijst **[!UICONTROL Extension]**. Dan, **[!UICONTROL Send postback]** van **[!UICONTROL Action type]** drop-down.

1. Voer een naam in, bijvoorbeeld **Mobiele kern - Locatie achteraf verzenden**.

1. Voer in **[!UICONTROL URL]** de volgende URL in:

   ```
   https://{%%camp-server%%}/rest/head/mobileAppV5/{%%pkey%%}/locations/
   ```

1. Schakel het selectievakje **[!UICONTROL Add post body]** in en voeg bijvoorbeeld de tekst voor de post toe:

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
   >In het bovenstaande voorbeeld moeten de gegevenselementen aan de rechterkant worden geconfigureerd in [!DNL Experience Platform Launch] door de stappen in [Gegevenselementen maken](../../administration/using/configuring-rules-launch.md#create-data-elements) te benutten. De gegevenselementen aan de linkerkant worden ondersteund in [!DNL Adobe Campaign Standard] en hoeven niet te worden geconfigureerd. Als u extra gegevens vereist, moet u de uitbreidingen van het douanemiddel in [!DNL Adobe Campaign Standard] uitvoeren.

1. Typ **application/json** in **[!UICONTROL Content Type]**.

1. Selecteer in **[!UICONTROL Timeout]** 5.

   ![](assets/do-not-localize/rules_4.png)
