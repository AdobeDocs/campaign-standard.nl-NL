---
title: Targetingactiviteiten
description: De gerichte activiteiten kunnen van de linkerkant van het scherm worden betreden.
audience: automating
content-type: reference
topic-tags: targeting-activities
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 1cd471e3-5332-4119-b342-2c3c8503fdd1
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 48%

---

# Targetingactiviteiten{#about-targeting-activities}

Ga naar het palet links op het scherm en vouw de sectie **[!UICONTROL Targeting]** uit.

Deze activiteiten zijn specifiek gericht op, het manipuleren van bevolkingsgegevens, en het filtreren activiteiten. Met deze instructies kunt u een of meer doelen maken door sets te definiëren en deze sets te splitsen of te combineren met een doorsnede, samenvoeging of uitsluitingsbewerking.

![](assets/wkf_targeting_activities.png)

De sectie **[!UICONTROL Targeting]** bevat de volgende activiteiten:

* [Query](../../automating/using/query.md)
* [Incrementele query](../../automating/using/incremental-query.md)
* [Samenvoegen](../../automating/using/union.md)
* [Doorsnede](../../automating/using/intersection.md)
* [Uitsluiting](../../automating/using/exclusion.md)
* [Segmentatie](../../automating/using/segmentation.md)
* [Doelgroep lezen](../../automating/using/read-audience.md)
* [Doelgroep opslaan](../../automating/using/save-audience.md)
* [Deduplicatie](../../automating/using/deduplication.md)
* [Verrijking](../../automating/using/enrichment.md)

**[!UICONTROL Targeting]** activiteiten kunt u definiëren **segmentcodes** voor hun uitgaande overgangen. Vervolgens kunt u rapporten maken op basis van deze segmentcodes om de efficiëntie van uw marketingcampagnes te meten. Raadpleeg [deze sectie](../../reporting/using/creating-a-report-workflow-segment.md) voor meer informatie.

## Gegevens selecteren {#selecting-data}

U kunt gegevens selecteren met behulp van de volgende activiteiten:

* Met de activiteit **[!UICONTROL Query]** kunt u een populatie van elementen filteren en extraheren uit de Adobe Campaign-database. Zie de [Query](../../automating/using/query.md) sectie.
* Met de activiteit **[!UICONTROL Incremental query]** kunt u een populatie van elementen filteren en extraheren uit de Adobe Campaign-database. Telkens wanneer deze activiteit wordt uitgevoerd, worden de resultaten van de vorige uitvoeringen uitgesloten. Hierdoor kunt u alleen nieuwe elementen als doel instellen. Zie de koppeling. [Incrementele query](../../automating/using/incremental-query.md) sectie.
* De **[!UICONTROL Read audience]** De activiteit staat u toe om een bestaand publiek terug te winnen en het te verfijnen door extra het filtreren voorwaarden toe te passen.Zie [Lees publiek](../../automating/using/read-audience.md) sectie.

## Gegevens segmenteren {#segmenting-data}

Met Adobe Campaign kunt u sets van binnenkomende gegevens verwerken. U kunt dus meerdere populaties combineren, een deel ervan uitsluiten of gegevens alleen gemeenschappelijk houden voor verschillende doelen.

* Met de activiteit **[!UICONTROL Union]** kunt u het resultaat van meerdere activiteiten hergroeperen in één doel. Zie de [Unie](../../automating/using/union.md) sectie.
* Met de activiteit **[!UICONTROL Intersection]** kunt u alleen de elementen behouden die de verschillende binnenkomende populaties in de activiteit gemeenschappelijk hebben. Zie de [Intersectie](../../automating/using/intersection.md) sectie.
* Met de activiteit **[!UICONTROL Exclusion]** kunt u elementen uit één populatie uitsluiten op basis van bepaalde criteria. Zie de [Uitsluiting](../../automating/using/exclusion.md) sectie.
* Met de activiteit **[!UICONTROL Segmentation]** kunt u een of meer segmenten maken van een populatie die wordt berekend door activiteiten die eerder in de workflow zijn geplaatst. Aan het eind van de activiteit kunnen zij in één enkele overgang of verschillende overgangen worden verwerkt. Zie de [Segmentering](../../automating/using/segmentation.md) sectie.

## Data verrijken {#enriching-data}

De geïdentificeerde en verzamelde gegevens kunnen worden verrijkt, geaggregeerd en gemanipuleerd om de doelconstructie te optimaliseren. U kunt doelprocessen vereenvoudigen en optimaliseren door gegevens op te nemen die niet in de datamarkt zijn gemodelleerd.

De **[!UICONTROL Additional data]** tabblad van het **[!UICONTROL Query]** en **[!UICONTROL Incremental query]** De activiteiten staan u toe om de gegevens te verrijken die door de vraag worden gericht en deze gegevens over te brengen naar de volgende werkschemaactiviteiten, waar het kan worden gebruikt. U kunt met name het volgende toevoegen:

* Eenvoudige data
* Aggregaten
* Verzamelingen

**Verwante onderwerpen:**

* [Hoofdlettergebruik: een e-mailadres aanpassen met aanvullende gegevens](../../automating/using/personalizing-email-with-additional-data.md)
