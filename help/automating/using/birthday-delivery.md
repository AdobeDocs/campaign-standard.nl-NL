---
title: Verjaardagslevering
description: Dit voorbeeld is een verjaardagsworkflow. Elke dag wordt een e-mail verzonden naar profielen waarvan het verjaart op die dag is.
audience: automating
content-type: reference
topic-tags: channel-activities
context-tags: delivery,workflow,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 535ddbce-d8ba-4578-9e37-10604291c95d
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 52%

---

# Verjaardagslevering {#birthday-delivery}

![](assets/wkf_delivery_example_1.png)

Dit voorbeeld is een verjaardagsworkflow. Elke dag wordt een e-mail verzonden naar profielen waarvan het verjaart op die dag is.

Voer de volgende stappen uit om de workflow te maken:

* De [ Planner ](../../automating/using/scheduler.md) staat u toe om het werkschema elke dag bij 8am te beginnen.

  ![](assets/wkf_delivery_example_2.png)

* De [ activiteit van de Vraag ](../../automating/using/query.md) staat u toe om de profielen te berekenen die een e-mail hebben verstrekt en van wie verjaardag het op de huidige dag is, telkens als het werkschema wordt uitgevoerd. De verjaardagsberekening wordt uitgevoerd met behulp van een vooraf gedefinieerd filter dat beschikbaar is in het palet in de query-editor.

  ![](assets/wkf_delivery_example_3.png)

* De [ E-maillevering ](../../automating/using/email-delivery.md) herhaalt. De verzendingen worden samengevoegd per maand. Alle e-mails die in een maand worden verzonden, worden dus samengevoegd tot één weergave. In één jaar worden er dus 365 leveringen uitgevoerd, maar deze worden in de interface van Adobe Campaign gegroepeerd in 12 weergaven (ook wel **periodieke uitvoeringen** genoemd). De geschiedenis en rapportdetails worden elke maand weergegeven en niet voor elke verzending.

  ![](assets/wkf_delivery_example_4.png)
