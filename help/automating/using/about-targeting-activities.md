---
solution: Campaign Standard
product: campaign
title: Targetingactiviteiten
description: De gerichte activiteiten kunnen van de linkerkant van het scherm worden betreden.
audience: automating
content-type: reference
topic-tags: targeting-activities
feature: Workflows
role: Gegevensarchitect
level: Intermediair
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 48%

---


# Targetingactiviteiten{#about-targeting-activities}

Ga naar het palet links op het scherm en vouw de sectie **[!UICONTROL Targeting]** uit.

Deze activiteiten zijn specifiek gericht op, het manipuleren van bevolkingsgegevens, en het filtreren activiteiten. Met deze instructies kunt u een of meer doelen maken door sets te definiëren en deze sets te splitsen of te combineren met een doorsnede, samenvoeging of uitsluitingsbewerking.

![](assets/wkf_targeting_activities.png)

De sectie **[!UICONTROL Targeting]** bevat de volgende activiteiten:

* [Query](../../automating/using/query.md)
* [Incrementele query](../../automating/using/incremental-query.md)
* [Samenvoeging](../../automating/using/union.md)
* [Doorsnede](../../automating/using/intersection.md)
* [Uitsluiting](../../automating/using/exclusion.md)
* [Segmentatie](../../automating/using/segmentation.md)
* [Doelgroep lezen](../../automating/using/read-audience.md)
* [Doelgroep opslaan](../../automating/using/save-audience.md)
* [Deduplicatie](../../automating/using/deduplication.md)
* [Verrijking](../../automating/using/enrichment.md)

**[!UICONTROL Targeting]** Met activiteiten kunt u  **segmentcodes** voor hun uitgaande overgangen definiëren. Vervolgens kunt u rapporten maken op basis van deze segmentcodes om de efficiëntie van uw marketingcampagnes te meten. Raadpleeg [deze sectie](../../reporting/using/creating-a-report-workflow-segment.md) voor meer informatie.

## Gegevens {#selecting-data} selecteren

U kunt gegevens selecteren met de volgende activiteiten:

* Met de activiteit **[!UICONTROL Query]** kunt u een populatie van elementen filteren en extraheren uit de Adobe Campaign-database. Zie de sectie [Query](../../automating/using/query.md).
* Met de activiteit **[!UICONTROL Incremental query]** kunt u een populatie van elementen filteren en extraheren uit de Adobe Campaign-database. Telkens wanneer deze activiteit wordt uitgevoerd, worden de resultaten van de vorige uitvoeringen uitgesloten. Hierdoor kunt u alleen nieuwe elementen als doel instellen. Zie de koppeling. [Incrementele ](../../automating/using/incremental-query.md) querysectie.
* Met de activiteit **[!UICONTROL Read audience]** kunt u een bestaand publiek ophalen en verfijnen door aanvullende filtervoorwaarden toe te passen.Zie de sectie [Leespubliek](../../automating/using/read-audience.md).

## Gegevens segmenteren {#segmenting-data}

Met Adobe Campaign kunt u sets van binnenkomende gegevens verwerken. U kunt dus meerdere populaties combineren, een deel ervan uitsluiten of gegevens alleen gemeenschappelijk houden voor verschillende doelen.

* Met de activiteit **[!UICONTROL Union]** kunt u het resultaat van meerdere activiteiten hergroeperen in één doel. Zie de sectie [Union](../../automating/using/union.md).
* Met de activiteit **[!UICONTROL Intersection]** kunt u alleen de elementen behouden die de verschillende binnenkomende populaties in de activiteit gemeenschappelijk hebben. Zie de sectie [Intersection](../../automating/using/intersection.md).
* Met de activiteit **[!UICONTROL Exclusion]** kunt u elementen uit één populatie uitsluiten op basis van bepaalde criteria. Zie de sectie [Uitsluiting](../../automating/using/exclusion.md).
* Met de activiteit **[!UICONTROL Segmentation]** kunt u een of meer segmenten maken van een populatie die wordt berekend door activiteiten die eerder in de workflow zijn geplaatst. Aan het eind van de activiteit kunnen zij in één enkele overgang of verschillende overgangen worden verwerkt. Zie de sectie [Segmentatie](../../automating/using/segmentation.md).

## Data verrijken {#enriching-data}

De geïdentificeerde en verzamelde gegevens kunnen worden verrijkt, geaggregeerd en gemanipuleerd om de doelconstructie te optimaliseren. U kunt doelprocessen vereenvoudigen en optimaliseren door gegevens op te nemen die niet in de datamarkt zijn gemodelleerd.

Op het tabblad **[!UICONTROL Additional data]** van de **[!UICONTROL Query]**- en **[!UICONTROL Incremental query]**-activiteiten kunt u de gegevens waarop de query betrekking heeft, verrijken en deze gegevens overdragen naar de volgende workflowactiviteiten, waar deze kunnen worden gebruikt. U kunt met name het volgende toevoegen:

* Eenvoudige data
* Aggregaten
* Verzamelingen

**Verwante onderwerpen:**

* [Hoofdlettergebruik: Een e-mail aanpassen met aanvullende gegevens](../../automating/using/personalizing-email-with-additional-data.md)
