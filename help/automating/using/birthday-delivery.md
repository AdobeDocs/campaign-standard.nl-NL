---
solution: Campaign Standard
product: campaign
title: Verjaardagslevering
description: Dit voorbeeld is een verjaardagsworkflow. Elke dag wordt er een e-mail gestuurd naar profielen die op die dag jarig zijn.
audience: automating
content-type: reference
topic-tags: channel-activities
context-tags: delivery,workflow,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 69%

---


# Verjaardagslevering {#birthday-delivery}

![](assets/wkf_delivery_example_1.png)

Dit voorbeeld is een verjaardagsworkflow. Elke dag wordt er een e-mail gestuurd naar profielen die op die dag jarig zijn.

Voer de volgende stappen uit om de workflow te maken:

* Met [Scheduler](../../automating/using/scheduler.md) kunt u de workflow elke dag om 8 uur starten.

   ![](assets/wkf_delivery_example_2.png)

* Met de activiteit [Query](../../automating/using/query.md) kunt u de profielen berekenen die een e-mail hebben verstrekt en waarvan de verjaardag op de huidige dag is, telkens als de werkstroom wordt uitgevoerd. De verjaardagsberekening wordt uitgevoerd met behulp van een vooraf gedefinieerd filter dat beschikbaar is in het palet in de query-editor.

   ![](assets/wkf_delivery_example_3.png)

* De [E-maillevering](../../automating/using/email-delivery.md) komt steeds opnieuw voor. De verzendingen worden samengevoegd per maand. Alle e-mails die in een maand worden verzonden, worden dus samengevoegd tot één weergave. In één jaar worden er dus 365 leveringen uitgevoerd, maar deze worden in de interface van Adobe Campaign gegroepeerd in 12 weergaven (ook wel **periodieke uitvoeringen** genoemd). De geschiedenis en rapportdetails worden elke maand weergegeven en niet voor elke verzending.

   ![](assets/wkf_delivery_example_4.png)
