---
title: Koppelingen toevoegen
description: Ontdek hoe u koppelingen kunt beheren met de e-mailontwerper.
page-status-flag: never-activated
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: editing-email-content
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '592'
ht-degree: 1%

---


# Koppelingen toevoegen {#links}

## Inserting a link {#inserting-a-link}

Met de editor kunt u een e-mail- of landingspagina aanpassen door koppelingen in te voegen in de HTML-inhoudselementen.

U kunt een koppeling invoegen in elk pagina-element: afbeelding, woord, groep woorden, tekstblok, enz.

>[!NOTE]
>
>In de onderstaande afbeeldingen ziet u hoe u een koppeling invoegt met de [e-mailontwerper](../../designing/using/designing-content-in-adobe-campaign.md) .

1. Selecteer een element en klik op **[!UICONTROL Insert link]** de contextafhankelijke werkbalk.

   ![](assets/des_insert_link.png)

1. Kies het type koppeling dat u wilt maken:

   * **Externe koppeling**: voegt een koppeling naar een externe URL in.

      U kunt personalisatie voor uw URLs bepalen. Zie URL&#39;s [aanpassen](../../designing/using/using-reusable-content.md#creating-a-content-fragment).

   * **Openingspagina**: toegang geven tot een Adobe Campaign-landingspagina.
   * **Koppeling** met abonnement: voeg een koppeling in om u te abonneren op een Adobe Campaign-service.
   * **Koppeling** voor abonnement opzeggen: voeg een koppeling in om uw abonnement op een Adobe Campaign-service op te zeggen.
   * **Koppeling die een handeling** definieert: definieert een actie wanneer op een element in de landingspagina wordt geklikt.

      >[!NOTE]
      >
      >Dit type koppeling is alleen beschikbaar voor bestemmingspagina&#39;s.

1. U kunt de tekst wijzigen die aan de ontvanger wordt getoond.
1. U kunt het browsergedrag instellen wanneer de gebruiker op de koppeling klikt (bijvoorbeeld een nieuw venster openen).

   >[!NOTE]
   >
   >Het browsergedrag definiëren is alleen van toepassing op bestemmingspagina&#39;s.

1. Sla uw wijzigingen op.

Nadat de koppeling is gemaakt, kunt u deze nog steeds wijzigen in het deelvenster Instellingen. Klik op het potloodpictogram om de parameters ervan te bewerken.

![](assets/des_link_edit.png)

Wanneer u een e-mailbericht bewerkt met de [e-mailontwerper](../../designing/using/designing-content-in-adobe-campaign.md), kunt u gemakkelijk de koppelingen openen en wijzigen die u hebt gemaakt in de tabel met alle URL&#39;s die in de e-mail zijn opgenomen. In deze lijst kunt u een gecentraliseerde weergave gebruiken en elke URL in de e-mailinhoud opzoeken. Zie [Informatie over bijgehouden URL&#39;s](#about-tracked-urls)voor toegang tot deze URL.

![](assets/des_link_list.png)

>[!NOTE]
>
>Persoonlijke URL&#39;s, zoals de URL **van de** Mirror-pagina of de koppeling **Unsubscription** , kunnen niet in deze lijst worden gewijzigd. Alle andere koppelingen kunnen worden bewerkt.

**Verwante onderwerpen**:

* [Een personalisatieveld invoegen](../../designing/using/personalization.md#inserting-a-personalization-field)
* [Inhoudsblokken toevoegen](../../designing/using/personalization.md#adding-a-content-block)
* [Dynamische inhoud definiëren](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)

## Bijgehouden URL&#39;s {#about-tracked-urls}

Met Adobe Campaign kunt u het gedrag van ontvangers bijhouden wanneer ze op een URL in een e-mail klikken. For more on tracking, see [this section](../../sending/using/tracking-messages.md#about-tracking).

Het **[!UICONTROL Links]** pictogram op de actiebalk geeft automatisch de lijst weer van alle URL&#39;s van de inhoud die wordt bijgehouden.

![](assets/des_links.png)

>[!NOTE]
>
>Tekstspatiëring wordt standaard geactiveerd. Deze functionaliteit is alleen beschikbaar voor e-mailberichten als tracering is geactiveerd in Adobe Campaign. For more on the tracking parameters, refer to [this section](../../administration/using/configuring-email-channel.md#tracking-parameters).

Het URL-, categorie-, label- en tracatietype van elke koppeling kan in deze lijst worden gewijzigd. Als u een koppeling wilt bewerken, klikt u op het bijbehorende potloodpictogram.

![](assets/des_links_tracking.png)

Voor elke bijgehouden URL kunt u de modus Tekstspatiëring instellen op een van de volgende waarden:

* **Bijgehouden**: activeert tracking op deze URL.
* **Pagina** spiegelen: beschouwt deze URL als een URL van een spiegelpagina.
* **Nooit**: activeert het bijhouden van deze URL nooit. Deze gegevens worden opgeslagen: als de URL in een toekomstig bericht opnieuw verschijnt, wordt het volgen automatisch gedeactiveerd.
* **Uitschakelen**: beschouwt deze URL als een opt-out- of niet-abonnements-URL.

![](assets/des_link_tracking_type.png)

U kunt het bijhouden van wijzigingen ook uitschakelen of activeren voor elke URL.

>[!NOTE]
>
>Standaard worden in Adobe Campaign alle inhoud-URL&#39;s bijgehouden, behalve de URL **van de** Mirror-pagina en de koppeling **Unsubscription** .

U kunt uw URL&#39;s opnieuw groeperen door het **[!UICONTROL Category]** veld te bewerken, afhankelijk van de URL&#39;s die in het bericht worden gebruikt. Deze categorieën kunnen rapporten, zoals bijvoorbeeld in [URLs worden getoond en stromen](../../reporting/using/urls-and-click-streams.md)klikken.

![](assets/des_link_tracking_category.png)

Wanneer het bouwen van een rapport, van het **[!UICONTROL Components]** lusje, selecteer **[!UICONTROL Dimension]** en scrol onderaan de lijst om tot de volgende componenten toegang te hebben. Sleep bijvoorbeeld naar de werkruimte om de resultaten weer te geven op basis van de categorie voor bijhouden van elke aangeklikte URL. **[!UICONTROL Tracking URL Category]**

![](assets/des_link_tracking_report.png)

Zie [deze sectie](../../reporting/using/about-dynamic-reports.md)voor meer informatie over het samenstellen van aangepaste rapporten.
