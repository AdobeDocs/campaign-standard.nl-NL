---
title: Uitvoeringsopdrachten
description: Leer hoe u opdrachten voor het uitvoeren van workflows gebruikt.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
role: Data Architect
level: Beginner
exl-id: fddd88b1-603a-465b-b5e7-624632c0d5cd
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 1%

---

# Uitvoeringsopdrachten {#execution-commands}

Met de pictogrammen op de actiebalk kunt u de uitvoering van een werkstroom starten, bijhouden en wijzigen. Zie [Actiebalk](../../automating/using/workflow-interface.md#action-bar).

![](assets/wkf_execution_2.png)

De beschikbare acties zijn als volgt:

**Start**

De ![](assets/play_darkgrey-24px.png) start met het uitvoeren van een workflow die vervolgens de **In uitvoering** (blauw) status. Als de werkstroom is gepauzeerd, wordt deze hervat, anders wordt deze gestart en worden de initiële activiteiten geactiveerd.

>[!NOTE]
>
>De start is een asynchroon proces: de aanvraag wordt opgeslagen en wordt zo snel mogelijk verwerkt door de engine voor workflowuitvoering.

**Pauzeren**

De ![](assets/pause_darkgrey-24px.png) pauzeert de uitvoering. De workflow neemt de **Waarschuwing** (geel) status. Er zullen geen nieuwe activiteiten worden geactiveerd totdat de activiteiten worden hervat, maar de lopende activiteiten worden niet opgeschort.

**Stoppen**

De ![](assets/stop_darkgrey-24px.png) de knop stopt een workflow die wordt uitgevoerd en die vervolgens de **Voltooid** (groen) status. De actieve bewerkingen worden indien mogelijk onderbroken en de import of SQL-query&#39;s die worden uitgevoerd, worden onmiddellijk geannuleerd. U kunt de workflow niet hervatten vanaf de plaats waar deze is gestopt.

**Opnieuw starten**

De ![](assets/pauseplay_darkgrey-24px.png) de knop houdt in dat een workflow wordt gestopt en dat een workflow opnieuw wordt gestart. In de meeste gevallen kunt u de toepassing sneller opnieuw starten. Het kan ook nuttig zijn om opnieuw beginnen te automatiseren zodra het tegenhouden een bepaalde hoeveelheid tijd vergt, omdat ![](assets/play_darkgrey-24px.png) Deze knop is alleen beschikbaar wanneer de stop effectief is.

Wanneer een of meerdere activiteiten in een workflow zijn geselecteerd, kunt u andere handelingen uitvoeren, zoals:

**Onmiddellijke uitvoering**

De ![](assets/pending_darkgrey-24px.png) worden de geselecteerde lopende activiteiten zo snel mogelijk gestart.

**Normale uitvoering**

De ![](assets/check_darkgrey-24px.png) Hiermee activeert u gepauzeerde of gedeactiveerde activiteiten.

**Uitvoering opgeschort**

De ![](assets/check_pause_darkgrey-24px.png) pauzeert de werkstroom bij de geselecteerde activiteit: deze taak en alle taken die erop volgen (in dezelfde vertakking) worden niet uitgevoerd.

**Geen uitvoering**

De ![](assets/checkdisable.png) Hiermee deactiveert u geselecteerde activiteiten.

>[!NOTE]
>
>Met snelle handelingen hebt u toegang tot verschillende handelingen die betrekking hebben op een bepaalde activiteit en worden deze weergegeven wanneer een activiteit wordt geselecteerd.
