---
title: Levenscyclus van workflow
description: Meer informatie over de levenscyclus van een workflow
page-status-flag: never-activated
uuid: ff02b74e-53e8-49c6-bf8e-0c729eaa7d25
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: 906c85ea-83b7-4268-86da-cd353f1dc591
context-tags: workflow,overview;workflow,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
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
