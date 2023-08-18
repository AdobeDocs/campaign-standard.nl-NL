---
title: Verjaardagslevering
description: Dit voorbeeld is een verjaardagsworkflow. Elke dag wordt er een e-mail gestuurd naar profielen die op die dag jarig zijn.
audience: automating
content-type: reference
topic-tags: channel-activities
context-tags: delivery,workflow,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 535ddbce-d8ba-4578-9e37-10604291c95d
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 69%

---

# Verjaardagslevering {#birthday-delivery}

![](assets/wkf_delivery_example_1.png)

Dit voorbeeld is een verjaardagsworkflow. Elke dag wordt er een e-mail gestuurd naar profielen die op die dag jarig zijn.

Voer de volgende stappen uit om de workflow te maken:

* De [Planner](../../automating/using/scheduler.md) kunt u de workflow elke dag om 8.00 uur starten.

  ![](assets/wkf_delivery_example_2.png)

* De [Query](../../automating/using/query.md) Met activiteit kunt u de profielen berekenen die een e-mail hebben verzonden en waarvan de verjaardag op de huidige dag is, telkens wanneer de werkstroom wordt uitgevoerd. De verjaardagsberekening wordt uitgevoerd met behulp van een vooraf gedefinieerd filter dat beschikbaar is in het palet in de query-editor.

  ![](assets/wkf_delivery_example_3.png)

* De [E-maillevering](../../automating/using/email-delivery.md) is terugkerend. De verzendingen worden samengevoegd per maand. Alle e-mails die in een maand worden verzonden, worden dus samengevoegd tot één weergave. In één jaar worden er dus 365 leveringen uitgevoerd, maar deze worden in de interface van Adobe Campaign gegroepeerd in 12 weergaven (ook wel **periodieke uitvoeringen** genoemd). De geschiedenis en rapportdetails worden elke maand weergegeven en niet voor elke verzending.

  ![](assets/wkf_delivery_example_4.png)
