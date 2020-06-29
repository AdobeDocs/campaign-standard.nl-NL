---
title: Geboortedatum
description: Dit voorbeeld is een verjaardagsworkflow. Elke dag wordt een e-mail verzonden naar profielen waarvan het verjaart op die dag is.
page-status-flag: never-activated
uuid: 7de53431-84ae-4d21-8361-2775ad314ed2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: channel-activities
discoiquuid: 5f288cf6-f8ff-4ac9-9c1a-8010260554bb
context-tags: delivery,workflow,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7ffa48365875883a98904d6b344ac005afe26e18
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 0%

---


# Geboortedatum {#birthday-delivery}

![](assets/wkf_delivery_example_1.png)

Dit voorbeeld is een verjaardagsworkflow. Elke dag wordt een e-mail verzonden naar profielen waarvan het verjaart op die dag is.

Voer de volgende stappen uit om de workflow te maken:

* Met de [planner](../../automating/using/scheduler.md) kunt u de workflow elke dag om 8 uur starten.

   ![](assets/wkf_delivery_example_2.png)

* Met de activiteit [van de Vraag](../../automating/using/query.md) kunt u de profielen berekenen die een e-mail hebben verstrekt en waarvan verjaardag het op de huidige dag is, telkens als het werkschema wordt uitgevoerd. De verjaardagsberekening wordt uitgevoerd gebruikend een vooraf bepaald filter beschikbaar in het palet in het vraaguitgevende hulpmiddel.

   ![](assets/wkf_delivery_example_3.png)

* De [e-maillevering](../../automating/using/email-delivery.md) wordt opnieuw verzonden. De verzendingen worden samengevoegd per maand. Alle e-mails die in een maand worden verzonden, worden dus samengevoegd tot één weergave. In één jaar worden er dus 365 leveringen uitgevoerd, maar in de interface van Adobe Campaign worden deze gerangschikt in 12 weergaven (ook wel **terugkerende executies** genoemd). De geschiedenis en rapportdetails worden getoond elke maand en niet voor elke verzend.

   ![](assets/wkf_delivery_example_4.png)
