---
solution: Campaign Standard
product: campaign
title: Overlappende uitvoering van geplande workflows
description: Leer hoe u overlappende uitvoering van geplande workflows voorkomt.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
translation-type: tm+mt
source-git-commit: 4a61c988f95dd84797e6e33707651304223045fb
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 0%

---


# Overlappende uitvoering van geplande workflows{#preventing-overlapping-execution-of-scheduled-workflows}

## Uitvoering van geplande workflows

In Campaign Standard garandeert de workflowengine dat een workflowinstantie slechts door één proces wordt uitgevoerd. Het blokkeren van activiteiten zoals invoer, lange lopende vragen of schrijft in het gegevensbestand verhindert de uitvoering van om het even welke andere taak wanneer het lopen.

Anderzijds blokkeren niet-blokkerende activiteiten niet de uitvoering van andere taken (gewoonlijk activiteiten die wachten op een gebeurtenis zoals de **[!UICONTROL Scheduler]** activiteit).

Dit kan leiden tot een scenario waarbij een op een planning gebaseerde workflow kan worden uitgevoerd, zelfs als de vorige uitvoering van dezelfde workflow nog niet is voltooid, wat kan leiden tot onverwachte gegevensproblemen.

Daarom moet u er bij het ontwerpen van een geplande workflow met meerdere activiteiten voor zorgen dat de workflow niet opnieuw wordt gepland totdat deze is voltooid. Hiervoor moet u uw workflow configureren om te voorkomen dat deze wordt uitgevoerd als een of meer taken uit een eerdere uitvoering nog in behandeling zijn.

## De workflow configureren

Om te controleren of een of meer taken uit een vorige werkstroomuitvoering nog in behandeling zijn, moet u een **[!UICONTROL Query]** en een **[!UICONTROL Test]** activiteit gebruiken.

1. Voeg een **[!UICONTROL Query]** activiteit na **[!UICONTROL Scheduler]** activiteit toe, dan vorm het als volgt.

1. Wijzig de bron van de activiteit in **[!UICONTROL WorkflowTaskDetail]**, wat betekent dat de huidige taken van de werkstroom erop gericht zullen zijn.

   ![](assets/scheduled-wkf-resource.png)

1. Configureer de query met de onderstaande regels:

   ![](assets/scheduled-wkf-query.png)

   * De eerste regelfilters uit de huidige taak (query2) evenals de volgende planningtaak (planning2) die tot het huidige werkschema behoort.

      >[!NOTE]
      >
      >Wanneer een **[!UICONTROL Scheduler]** activiteit begint, voegt het onmiddellijk een andere planningtaak toe om bij de volgende geplande tijd te lopen en het werkschema te beginnen. Daarom is het belangrijk om zowel de vraag als planningstaken te filtreren wanneer het zoeken naar hangende taken van een vorige uitvoering.

   * De tweede regel bepaalt of taken uit een vorige uitvoering van de workflow nog actief zijn (in behandeling), wat overeenkomt met de uitvoerstatus 0.

1. Voeg een **[!UICONTROL Test]** activiteit toe om het aantal hangende taken te controleren die door **[!UICONTROL Query]** activiteit zijn teruggekeerd. Om dit te doen, vorm twee uitgaande overgangen.

   ![](assets/scheduled-wkf-test.png)

   * De eerste overgang gaat door met de uitvoering van de workflow als er geen taken in behandeling zijn.
   * De tweede overgang annuleert de uitvoering van de workflow als er nog taken in behandeling zijn.

   ![](assets/scheduled-wkf-workflow.png)

U kunt nu de rest van uw workflow naar wens configureren. Als de uitvoering van de workflow wordt geannuleerd vanwege lopende taken, kan de workflow deze stappen doorlopen wanneer de workflow volgens het schema opnieuw wordt uitgevoerd. Hierdoor wordt ervoor gezorgd dat de workflow alleen wordt uitgevoerd als er geen actieve (hangende) taken uit een vorige uitvoering zijn.