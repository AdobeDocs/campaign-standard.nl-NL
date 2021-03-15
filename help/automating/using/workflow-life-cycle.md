---
solution: Campaign Standard
product: campaign
title: Levenscyclus van workflow
description: Meer informatie over de levenscyclus van een workflow
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
role: Gegevensarchitect
level: Begin
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '204'
ht-degree: 3%

---


# Levenscyclus van workflow {#life-cycle}

De levenscyclus van een werkstroom omvat drie hoofdstappen en elke stap is gekoppeld aan een status en een kleur:

* **Bewerken**  (grijs)

   Dit is de eerste ontwerpfase van een workflow (zie [Een workflow maken](../../automating/using/building-a-workflow.md#creating-a-workflow)). De workflow wordt nog niet door de server afgehandeld en kan zonder risico worden gewijzigd.

* **Wordt uitgevoerd**  (blauw)

   Zodra de eerste ontwerpfase is voltooid, kan de workflow worden gestart en door de server worden afgehandeld.

* **Voltooid**  (groen)

   Een werkstroom wordt voltooid wanneer er geen taken meer worden uitgevoerd of wanneer een operator de instantie expliciet heeft gestopt.

Als de workflow eenmaal is gestart, kan deze ook twee andere statussen hebben:

* **Waarschuwing**  (geel)

   De workflow kon niet worden voltooid of werd gepauzeerd met de knoppen ![](assets/pause_darkgrey-24px.png) of ![](assets/check_pause_darkgrey-24px.png).

* **Onjuist**  (rood)

   Er is een fout opgetreden bij het uitvoeren van een workflow. De werkstroom is gestopt en de gebruiker moet een actie uitvoeren. Als u meer wilt weten over deze fout, gebruikt u de knop ![](assets/printpreview_darkgrey-24px.png) om toegang te krijgen tot het workflowlogboek (zie [Controle](../../automating/using/monitoring-workflow-execution.md)).

In de lijst met marketingactiviteiten kunt u alle workflows en de bijbehorende statussen weergeven. Zie [Commerciële activiteiten beheren](../../start/using/marketing-activities.md#about-marketing-activities) voor meer informatie.

![](assets/wkf_execution_3.png)
