---
title: Segmentering volgens leeftijdsgroepen
description: Deze pagina bevat een segmentatie van databaseprofielen volgens hun leeftijdsgroep. Het doel van de workflow is om voor elke leeftijdsgroep een specifieke e-mail te verzenden.
page-status-flag: never-activated
uuid: 77796f18-cad5-4e7a-9d7b-4ed0dd8943bf
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 0ccd9d02-772e-406b-874a-5381dd0c8709
context-tags: segmentation,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7ffa48365875883a98904d6b344ac005afe26e18
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 0%

---


# Segmentering volgens leeftijdsgroepen {#segmentation-age-groups}

In het volgende voorbeeld wordt een segmentatie van databaseprofielen weergegeven op basis van hun leeftijdsgroep.

Het doel van de workflow is om voor elke leeftijdsgroep een specifieke e-mail te verzenden. Gezien het feit dat deze workflow deel uitmaakt van een testcampagne, kan elk segment slechts maximaal 100 profielen bevatten die willekeurig zijn geselecteerd om een beperkt en representatief publiek te gebruiken.

![](assets/wkf_segment_example_4.png)

De workflow bestaat uit de volgende elementen:

* Een [planneractiviteit](../../automating/using/segmentation.md) om de de uitvoeringsdatum van het werkschema te specificeren.
* Een activiteit van de [Vraag](../../automating/using/query.md) aan doelprofielen van mensen van wie verjaardag en e-mailadres zijn ingegaan.
* Een [Segmenteringsactiviteit](../../automating/using/segmentation.md) om 3 segmenten te creëren die in verschillende uitgaande overgangen worden verdeeld: 18-25 jaar oud, 26-32 jaar oud en profielen ouder dan 32 jaar. De segmenten worden gedefinieerd volgens de volgende parameters:

   ![](assets/wkf_segment_example_3.png)

   * Een filter op de leeftijd om de leeftijdsgroep van het segment te bepalen

      ![](assets/wkf_segment_new_segment.png)

   * Een **[!UICONTROL Random sampling]** typelimiet die is gekoppeld aan een **[!UICONTROL Maximum size]** limiet van 100

      ![](assets/wkf_segment_example_1.png)

* Een [e-mailleveringsactiviteit](../../automating/using/email-delivery.md) per segment.
