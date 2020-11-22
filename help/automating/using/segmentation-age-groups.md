---
solution: Campaign Standard
product: campaign
title: Segmentering volgens leeftijdsgroepen
description: Deze pagina bevat een segmentatie van databaseprofielen volgens hun leeftijdsgroep. Het doel van de workflow is om voor elke leeftijdsgroep een specifieke e-mail te verzenden.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: segmentation,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 66%

---


# Segmentering volgens leeftijdsgroepen {#segmentation-age-groups}

In het volgende voorbeeld wordt een segmentatie van databaseprofielen weergegeven op basis van de leeftijdsgroep.

Het doel van de workflow is om voor elke leeftijdsgroep een specifieke e-mail te verzenden. Aangezien deze workflow deel uitmaakt van een testcampagne, kan elk segment maximaal slechts 100 profielen bevatten die willekeurig zijn geselecteerd om een beperkte en representatieve doelgroep te gebruiken.

![](assets/wkf_segment_example_4.png)

De workflow bestaat uit de volgende elementen:

* A [Scheduler activity](../../automating/using/segmentation.md) to specify the workflow&#39;s execution date.
* A [Query](../../automating/using/query.md) activity to target profiles of people whose birthday and email address have been entered.
* A [Segmentation](../../automating/using/segmentation.md) activity to create 3 segments divided into different outbound transitions: 18-25-year old, 26-32-year old and profiles that are over 32 years old. De segmenten worden gedefinieerd volgens de volgende parameters:

   ![](assets/wkf_segment_example_3.png)

   * Een filter op de leeftijd om de leeftijdsgroep van het segment te bepalen

      ![](assets/wkf_segment_new_segment.png)

   * De typelimiet **[!UICONTROL Random sampling]**, gekoppeld aan een **[!UICONTROL Maximum size]** van 100

      ![](assets/wkf_segment_example_1.png)

* Een [e-mailleveringsactiviteit](../../automating/using/email-delivery.md) per segment.
