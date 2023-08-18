---
title: Levenscyclus van workflow
description: Meer informatie over de levenscyclus van een workflow
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
role: Data Architect
level: Beginner
exl-id: ba968add-25a3-4962-9e90-f0a06d9b74a8
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 3%

---

# Levenscyclus van workflow {#life-cycle}

De levenscyclus van een werkstroom omvat drie hoofdstappen en elke stap is gekoppeld aan een status en een kleur:

* **Bewerken** (grijs)

  Dit is de eerste ontwerpfase van een workflow (zie [Een workflow maken](../../automating/using/building-a-workflow.md#creating-a-workflow)). De workflow wordt nog niet door de server afgehandeld en kan zonder risico worden gewijzigd.

* **In uitvoering** (blauw)

  Zodra de eerste ontwerpfase is voltooid, kan de workflow worden gestart en door de server worden afgehandeld.

* **Voltooid** (groen)

  Een werkstroom wordt voltooid wanneer er geen taken meer worden uitgevoerd of wanneer een operator de instantie expliciet heeft gestopt.

Als de workflow eenmaal is gestart, kan deze ook twee andere statussen hebben:

* **Waarschuwing** (geel)

  De werkstroom kon niet worden voltooid of is gepauzeerd met de functie ![](assets/pause_darkgrey-24px.png) of ![](assets/check_pause_darkgrey-24px.png) knoppen.

* **Onjuist** (rood)

  Er is een fout opgetreden bij het uitvoeren van een workflow. De werkstroom is gestopt en de gebruiker moet een actie uitvoeren. Als u meer wilt weten over deze fout, gebruikt u de opdracht ![](assets/printpreview_darkgrey-24px.png) om toegang te krijgen tot het workflowlogboek (zie [Toezicht](../../automating/using/monitoring-workflow-execution.md)).

In de lijst met marketingactiviteiten kunt u alle workflows en de bijbehorende statussen weergeven. Zie voor meer informatie [Marketing beheren](../../start/using/marketing-activities.md#about-marketing-activities).

![](assets/wkf_execution_3.png)
