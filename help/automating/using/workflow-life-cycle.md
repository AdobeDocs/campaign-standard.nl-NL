---
title: Levenscyclus van workflow
description: Meer informatie over de levenscyclus van een workflow
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Beginner
exl-id: ba968add-25a3-4962-9e90-f0a06d9b74a8
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 3%

---

# Levenscyclus van workflow {#life-cycle}

De levenscyclus van een werkstroom omvat drie hoofdstappen en elke stap is gekoppeld aan een status en een kleur:

* **het Uitgeven** (grijs)

  Dit is de aanvankelijke ontwerpfase van een werkschema (verwijs naar [&#x200B; Creërend een werkschema &#x200B;](../../automating/using/building-a-workflow.md#creating-a-workflow)). De workflow wordt nog niet door de server afgehandeld en kan zonder risico worden gewijzigd.

* **lopend** (blauw)

  Zodra de eerste ontwerpfase is voltooid, kan de workflow worden gestart en door de server worden afgehandeld.

* **Voltooid** (groen)

  Een werkstroom wordt voltooid wanneer er geen taken meer worden uitgevoerd of wanneer een operator de instantie expliciet heeft gestopt.

Als de workflow eenmaal is gestart, kan deze ook twee andere statussen hebben:

* **Waarschuwing** (geel)

  De workflow kon niet worden voltooid of was gepauzeerd met de knoppen ![](assets/pause_darkgrey-24px.png) of ![](assets/check_pause_darkgrey-24px.png) .

* **Onjuiste** (rood)

  Er is een fout opgetreden bij het uitvoeren van een workflow. De werkstroom is gestopt en de gebruiker moet een actie uitvoeren. Om meer over deze fout te weten te komen, gebruik de ![](assets/printpreview_darkgrey-24px.png) knoop om tot het werkschemalogboek toegang te hebben (verwijs naar [&#x200B; Controle &#x200B;](../../automating/using/monitoring-workflow-execution.md)).

In de lijst met marketingactiviteiten kunt u alle workflows en de bijbehorende statussen weergeven. Voor meer op dit, zie [&#x200B; het Leiden marketing activiteiten &#x200B;](../../start/using/marketing-activities.md#about-marketing-activities).

![](assets/wkf_execution_3.png)
