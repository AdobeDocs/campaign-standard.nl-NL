---
title: Over doelactiviteiten
description: De gerichte activiteiten kunnen van de linkerkant van het scherm worden betreden.
page-status-flag: never-activated
uuid: a6cbc431-1ae3-428e-b2c9-893454b32ae2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 5f7607a1-5f71-4d66-9688-3e5a1774f1b4
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 44d6126023e9411477ccd7ffc07ecde806e7976d
workflow-type: tm+mt
source-wordcount: '458'
ht-degree: 0%

---


# Over doelactiviteiten{#about-targeting-activities}

Vouw de **[!UICONTROL Targeting]** sectie uit het palet, links op het scherm.

Deze activiteiten zijn specifiek gericht op, het manipuleren van bevolkingsgegevens, en het filtreren activiteiten. Met deze instructies kunt u een of meer doelen maken door sets te definiëren en deze sets te splitsen of te combineren met een doorsnede, samenvoeging of uitsluitingsbewerking.

![](assets/wkf_targeting_activities.png)

Het **[!UICONTROL Targeting]** gedeelte bevat de volgende activiteiten:

* [Query](../../automating/using/query.md)
* [Incrementele query](../../automating/using/incremental-query.md)
* [Unie](../../automating/using/union.md)
* [Intersectie](../../automating/using/intersection.md)
* [Uitsluiting](../../automating/using/exclusion.md)
* [Segmentering](../../automating/using/segmentation.md)
* [Lees publiek](../../automating/using/read-audience.md)
* [Adviezen opslaan](../../automating/using/save-audience.md)
* [Deduplicatie](../../automating/using/deduplication.md)
* [Verrijking](../../automating/using/enrichment.md)

**[!UICONTROL Targeting]** De activiteiten staan u toe om **segmentcodes** voor hun uitgaande overgangen te bepalen. Vervolgens kunt u rapporten maken op basis van deze segmentcodes om de efficiëntie van uw marketingcampagnes te meten. For more on this, refer to [this section](../../reporting/using/creating-a-report-workflow-segment.md).

## Gegevens selecteren {#selecting-data}

U kunt gegevens selecteren met de volgende activiteiten:

* Met deze **[!UICONTROL Query]** activiteit kunt u een aantal elementen filteren en extraheren uit de Adobe Campagne-database. Zie de sectie [Query](../../automating/using/query.md) .
* Met deze **[!UICONTROL Incremental query]** activiteit kunt u een aantal elementen filteren en extraheren uit de Adobe Campagne-database. Telkens wanneer deze activiteit wordt uitgevoerd, worden de resultaten van de vorige uitvoeringen uitgesloten. Hierdoor kunt u alleen nieuwe elementen als doel instellen. Zie de koppeling. [Incrementele query](../../automating/using/incremental-query.md) -sectie.
* De **[!UICONTROL Read audience]** activiteit staat u toe om een bestaand publiek terug te winnen en het te verfijnen door extra het filtreren voorwaarden toe te passen.Zie de [Gelezen publiekssectie](../../automating/using/read-audience.md) .

## Gegevens segmenteren {#segmenting-data}

Met Adobe Campaign kunt u sets met binnenkomende gegevens verwerken. U kunt dus meerdere populaties combineren, een deel ervan uitsluiten of gegevens alleen gemeenschappelijk houden voor verschillende doelen.

* De **[!UICONTROL Union]** activiteit staat u toe om het resultaat van veelvoudige activiteiten in één enkel doel te hergroeperen. Zie de sectie [Vereniging](../../automating/using/union.md) .
* Met de **[!UICONTROL Intersection]** activiteit kunt u alleen de elementen behouden die de verschillende binnenkomende populaties in de activiteit gemeen hebben. Zie de sectie [Intersectie](../../automating/using/intersection.md) .
* Met deze **[!UICONTROL Exclusion]** activiteit kunt u elementen op basis van bepaalde criteria uitsluiten van één populatie. Zie de sectie [Uitsluiting](../../automating/using/exclusion.md) .
* Met de **[!UICONTROL Segmentation]** activiteit kunt u een of meerdere segmenten maken van een populatie die wordt berekend door activiteiten die eerder in de workflow zijn geplaatst. Aan het eind van de activiteit, kunnen zij in één enkele overgang of verschillende overgangen worden verwerkt. Zie de sectie [Segmentatie](../../automating/using/segmentation.md) .

## Gegevens worden verrijkt {#enriching-data}

De geïdentificeerde en verzamelde gegevens kunnen worden verrijkt, geaggregeerd en gemanipuleerd om de doelconstructie te optimaliseren. U kunt doelprocessen vereenvoudigen en optimaliseren door gegevens op te nemen die niet in de datamarkt zijn gemodelleerd.

Op het **[!UICONTROL Additional data]** tabblad van de **[!UICONTROL Query]** en **[!UICONTROL Incremental query]** activiteiten kunt u de gegevens waarop de query betrekking heeft verrijken en deze gegevens overdragen naar de volgende workflowactiviteiten, waar deze kunnen worden gebruikt. U kunt met name het volgende toevoegen:

* Eenvoudige gegevens
* Aggregaten
* Verzamelingen

**Verwante onderwerpen**

* [Hoofdlettergebruik: Eenmaal per week een e-maillevering maken](../../automating/using/workflow-weekly-offer.md)
* [Hoofdlettergebruik: Een levering maken die op een locatie is gesegmenteerd](../../automating/using/workflow-segmentation-location.md)
* [Hoofdlettergebruik: Leveringen maken met een aanvulling](../../automating/using/workflow-created-query-with-complement.md)
* [Hoofdlettergebruik: Werkstroom opnieuw toewijzen om een nieuwe levering naar niet-openers te verzenden](../../automating/using/workflow-cross-channel-retargeting.md)
