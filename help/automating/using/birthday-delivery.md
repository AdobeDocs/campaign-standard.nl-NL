---
title: Verjaardagslevering
description: Dit voorbeeld is een verjaardagsworkflow. Elke dag wordt er een e-mail gestuurd naar profielen die op die dag jarig zijn.
page-status-flag: never-activated
uuid: 7de53431-84ae-4d21-8361-2775ad314ed2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: channel-activities
discoiquuid: 5f288cf6-f8ff-4ac9-9c1a-8010260554bb
context-tags: delivery,workflow,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 69%

---


# Verjaardagslevering {#birthday-delivery}

![](assets/wkf_delivery_example_1.png)

Dit voorbeeld is een verjaardagsworkflow. Elke dag wordt er een e-mail gestuurd naar profielen die op die dag jarig zijn.

Voer de volgende stappen uit om de workflow te maken:

* The [Scheduler](../../automating/using/scheduler.md) allows you to start the workflow every day at 8am.

   ![](assets/wkf_delivery_example_2.png)

* The [Query](../../automating/using/query.md) activity allows you to calculate the profiles who have provided an email and whose birthday it is on the current day, every time the workflow is executed. De verjaardagsberekening wordt uitgevoerd met behulp van een vooraf gedefinieerd filter dat beschikbaar is in het palet in de query-editor.

   ![](assets/wkf_delivery_example_3.png)

* De [e-maillevering](../../automating/using/email-delivery.md) wordt opnieuw verzonden. De verzendingen worden samengevoegd per maand. Alle e-mails die in een maand worden verzonden, worden dus samengevoegd tot één weergave. In één jaar worden er dus 365 leveringen uitgevoerd, maar deze worden in de interface van Adobe Campaign gegroepeerd in 12 weergaven (ook wel **periodieke uitvoeringen** genoemd). De geschiedenis en rapportdetails worden elke maand weergegeven en niet voor elke verzending.

   ![](assets/wkf_delivery_example_4.png)
