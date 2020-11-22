---
solution: Campaign Standard
product: campaign
title: Levenscyclus van workflow
description: Meer informatie over de levenscyclus van een workflow
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 3%

---


# Levenscyclus van workflow {#life-cycle}

De levenscyclus van een werkstroom omvat drie hoofdstappen en elke stap is gekoppeld aan een status en een kleur:

* **Bewerken** (grijs)

   Dit is de eerste ontwerpfase van een workflow (zie [Een workflow](../../automating/using/building-a-workflow.md#creating-a-workflow)maken). De workflow wordt nog niet door de server afgehandeld en kan zonder risico worden gewijzigd.

* **Bezig** (blauw)

   Zodra de eerste ontwerpfase is voltooid, kan de workflow worden gestart en door de server worden afgehandeld.

* **Voltooid** (groen)

   Een werkstroom wordt voltooid wanneer er geen taken meer worden uitgevoerd of wanneer een operator de instantie expliciet heeft gestopt.

Als de workflow eenmaal is gestart, kan deze ook twee andere statussen hebben:

* **Waarschuwing** (geel)

   De werkstroom kon niet worden voltooid of werd gepauzeerd met de ![](assets/pause_darkgrey-24px.png) knoppen of ![](assets/check_pause_darkgrey-24px.png) knoppen.

* **Onjuist** (rood)

   Er is een fout opgetreden bij het uitvoeren van een workflow. De werkstroom is gestopt en de gebruiker moet een actie uitvoeren. Als u meer wilt weten over deze fout, gebruikt u de ![](assets/printpreview_darkgrey-24px.png) knop om het workflowlogboek te openen (zie [Controle](../../automating/using/monitoring-workflow-execution.md)).

In de lijst met marketingactiviteiten kunt u alle workflows en de bijbehorende statussen weergeven. For more on this, see [Managing marketing activities](../../start/using/marketing-activities.md#about-marketing-activities).

![](assets/wkf_execution_3.png)
