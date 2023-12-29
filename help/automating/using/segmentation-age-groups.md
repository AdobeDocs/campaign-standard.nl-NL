---
title: Segmentatie volgens leeftijdsgroepen
description: Deze pagina bevat een segmentatie van databaseprofielen volgens hun leeftijdsgroep. Het doel van de workflow is om voor elke leeftijdsgroep een specifieke e-mail te verzenden.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: segmentation,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: dab7ef86-4776-48f4-be9a-37de316e0dd9
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '204'
ht-degree: 51%

---

# Segmentatie volgens leeftijdsgroepen {#segmentation-age-groups}

In het volgende voorbeeld wordt een segmentatie van databaseprofielen weergegeven op basis van hun leeftijdsgroep.

Het doel van de workflow is om voor elke leeftijdsgroep een specifieke e-mail te verzenden. Aangezien deze workflow deel uitmaakt van een testcampagne, kan elk segment maximaal slechts 100 profielen bevatten die willekeurig zijn geselecteerd om een beperkte en representatieve doelgroep te gebruiken.

![](assets/wkf_segment_example_4.png)

De workflow bestaat uit de volgende elementen:

* A [Planningsactiviteit](../../automating/using/segmentation.md) om de uitvoeringsdatum van de workflow te bepalen.
* A [Query](../../automating/using/query.md) activiteit aan doelprofielen van mensen van wie verjaardag en e-mailadres zijn ingegaan.
* A [Segmentering](../../automating/using/segmentation.md) activiteit om 3 segmenten te creëren verdeeld in verschillende uitgaande overgangen: 18-25 jaar oud, 26-32 jaar oud en profielen ouder dan 32 jaar. De segmenten worden gedefinieerd volgens de volgende parameters:

  ![](assets/wkf_segment_example_3.png)

   * Een filter op de leeftijd om de leeftijdsgroep van het segment te bepalen

     ![](assets/wkf_segment_new_segment.png)

   * De typelimiet **[!UICONTROL Random sampling]**, gekoppeld aan een **[!UICONTROL Maximum size]** van 100

     ![](assets/wkf_segment_example_1.png)

* An [E-maillevering](../../automating/using/email-delivery.md) activiteit per segment.
