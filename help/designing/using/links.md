---
solution: Campaign Standard
product: campaign
title: Koppelingen toevoegen
description: Ontdek hoe u koppelingen kunt beheren met de e-mailontwerper.
audience: designing
content-type: reference
topic-tags: editing-email-content
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '592'
ht-degree: 2%

---


# Koppelingen {#links} toevoegen

## Een koppeling {#inserting-a-link} invoegen

Met de editor kunt u een e-mail- of landingspagina aanpassen door koppelingen in te voegen in de HTML-inhoudselementen.

U kunt een koppeling invoegen in elk pagina-element: afbeelding, woord, groep woorden, tekstblok, enz.

>[!NOTE]
>
>In de onderstaande afbeeldingen ziet u hoe u een koppeling invoegt met de [e-mailontwerper](../../designing/using/designing-content-in-adobe-campaign.md) in een e-mail.

1. Selecteer een element en klik **[!UICONTROL Insert link]** van de contextafhankelijke toolbar.

   ![](assets/des_insert_link.png)

1. Kies het type koppeling dat u wilt maken:

   * **Externe koppeling**: voegt een koppeling naar een externe URL in.

      U kunt personalisatie voor uw URLs bepalen. Zie [URL&#39;s aanpassen](../../designing/using/using-reusable-content.md#creating-a-content-fragment).

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

Wanneer u een e-mailbericht bewerkt met de [e-mailontwerper](../../designing/using/designing-content-in-adobe-campaign.md), kunt u eenvoudig de koppelingen openen en wijzigen die u hebt gemaakt in de tabel met alle URL&#39;s die in het e-mailbericht zijn opgenomen. In deze lijst kunt u een gecentraliseerde weergave gebruiken en elke URL in de e-mailinhoud opzoeken. Zie [Informatie over bijgehouden URL&#39;s](#about-tracked-urls) voor toegang tot deze URL.

![](assets/des_link_list.png)

>[!NOTE]
>
>Persoonlijke URL&#39;s, zoals de koppeling **Pagina-URL spiegelen** of **Abonnement** kan niet worden gewijzigd in deze lijst. Alle andere koppelingen kunnen worden bewerkt.

**Verwante onderwerpen**:

* [Een personalisatieveld invoegen](../../designing/using/personalization.md#inserting-a-personalization-field)
* [Inhoudsblokken toevoegen](../../designing/using/personalization.md#adding-a-content-block)
* [Dynamische inhoud definiëren](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)

## Informatie over bijgehouden URL&#39;s {#about-tracked-urls}

Met Adobe Campaign kunt u het gedrag van ontvangers bijhouden wanneer ze op een URL in een e-mail klikken. Zie [deze sectie](../../sending/using/tracking-messages.md#about-tracking)voor meer informatie over tracking.

Het pictogram **[!UICONTROL Links]** in de actiebalk geeft automatisch de lijst weer van alle URL&#39;s van de inhoud die wordt bijgehouden.

![](assets/des_links.png)

>[!NOTE]
>
>Tekstspatiëring wordt standaard geactiveerd. Deze functionaliteit is alleen beschikbaar voor e-mailberichten als tracering is geactiveerd in Adobe Campaign. Raadpleeg [deze sectie](../../administration/using/configuring-email-channel.md#tracking-parameters) voor meer informatie over de volgende parameters.

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
>Standaard worden in Adobe Campaign alle inhoud-URL&#39;s bijgehouden, behalve de koppeling **Pagina-URL spiegelen** en **Unsubscription**.

U kunt uw URL&#39;s opnieuw groeperen door het veld **[!UICONTROL Category]** te bewerken, afhankelijk van de URL&#39;s die in het bericht worden gebruikt. Deze categorieën kunnen rapporten, zoals bijvoorbeeld in [URLs worden getoond en stromen](../../reporting/using/urls-and-click-streams.md) klikken.

![](assets/des_link_tracking_category.png)

Wanneer het bouwen van een rapport, van **[!UICONTROL Components]** tabel, uitgezocht **[!UICONTROL Dimension]** en scroll onderaan de lijst om tot de volgende componenten toegang te hebben. Sleep bijvoorbeeld **[!UICONTROL Tracking URL Category]** naar de werkruimte om de resultaten weer te geven op basis van de categorie voor bijhouden van elke aangeklikte URL.

![](assets/des_link_tracking_report.png)

Zie [deze sectie](../../reporting/using/about-dynamic-reports.md) voor meer informatie over het samenstellen van aangepaste rapporten.
