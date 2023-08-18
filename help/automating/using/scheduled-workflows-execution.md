---
title: Overlappende uitvoering van geplande workflows
description: Leer hoe u overlappende uitvoering van geplande workflows voorkomt.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 8d9820a4-3c44-45f5-815e-4ed48a96276d
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 1%

---

# Overlappende uitvoering van geplande workflows{#preventing-overlapping-execution-of-scheduled-workflows}

## Uitvoering van geplande workflows

In Campaign Standard garandeert de workflowengine dat een workflowinstantie slechts door één proces wordt uitgevoerd. Het blokkeren van activiteiten zoals invoer, lange lopende vragen of schrijft in het gegevensbestand verhindert de uitvoering van een andere taak wanneer het lopen.

Anderzijds blokkeren niet-blokkerende activiteiten niet de uitvoering van andere taken (gewoonlijk activiteiten die wachten op een gebeurtenis zoals de **[!UICONTROL Scheduler]** activiteit).

Dit kan leiden tot een scenario waarbij een op een planning gebaseerde workflow kan worden uitgevoerd, zelfs als de vorige uitvoering van dezelfde workflow nog niet is voltooid, wat kan leiden tot onverwachte gegevensproblemen.

Daarom moet u er bij het ontwerpen van een geplande workflow met meerdere activiteiten voor zorgen dat de workflow niet opnieuw wordt gepland totdat deze is voltooid. Hiervoor moet u uw workflow configureren om te voorkomen dat deze wordt uitgevoerd als een of meer taken uit een eerdere uitvoering nog in behandeling zijn.

## De workflow configureren

Als u wilt controleren of een of meer taken uit een vorige werkstroom nog niet zijn uitgevoerd, moet u een **[!UICONTROL Query]** en **[!UICONTROL Test]** activiteit.

1. Voeg een **[!UICONTROL Query]** activiteit na de **[!UICONTROL Scheduler]** activiteit, dan vorm het als volgt.

1. De bron van de activiteit wijzigen in **[!UICONTROL WorkflowTaskDetail]**, wat betekent dat het zich richt op de huidige taken van de workflow.

   ![](assets/scheduled-wkf-resource.png)

1. Configureer de query met de onderstaande regels:

   ![](assets/scheduled-wkf-query.png)

   * De eerste regelfilters uit de huidige taak (query2) evenals de volgende planningtaak (planning2) die tot het huidige werkschema behoort.

     >[!NOTE]
     >
     >Wanneer een **[!UICONTROL Scheduler]** de activiteit begint, voegt het onmiddellijk een andere planningstaak toe om bij de volgende geplande tijd te lopen en het werkschema te beginnen. Daarom is het belangrijk om zowel de vraag als planningstaken te filtreren wanneer het zoeken naar hangende taken van een vorige uitvoering.

   * De tweede regel bepaalt of taken uit een vorige uitvoering van de workflow nog actief zijn (in behandeling), wat overeenkomt met de uitvoerstatus 0.

1. Voeg een **[!UICONTROL Test]** activiteit om te controleren op het aantal hangende taken die door de **[!UICONTROL Query]** activiteit. Hiertoe configureert u twee uitgaande overgangen.

   ![](assets/scheduled-wkf-test.png)

   * De eerste overgang gaat door met de uitvoering van de workflow als er geen taken in behandeling zijn.
   * De tweede overgang annuleert de uitvoering van de workflow als er nog taken in behandeling zijn.

   ![](assets/scheduled-wkf-workflow.png)

U kunt nu de rest van uw workflow naar wens configureren. Als de uitvoering van de workflow wordt geannuleerd vanwege lopende taken, kan de workflow deze stappen doorlopen wanneer de workflow volgens het schema opnieuw wordt uitgevoerd. Hierdoor wordt ervoor gezorgd dat de workflow alleen wordt uitgevoerd als er geen actieve (hangende) taken uit een vorige uitvoering zijn.
