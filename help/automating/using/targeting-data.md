---
title: Doelgegevens
description: Leer de verschillende manieren om de gegevens te richten en te selecteren u wenst.
page-status-flag: never-activated
uuid: 0645d6e5-6a7e-4917-874a-7e7725f06abd
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: 382ea74e-1662-4c64-96d7-676040586913
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Doelgegevens{#targeting-data}

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
