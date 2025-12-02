---
title: Uitvoeringsopdrachten
description: Leer hoe u opdrachten voor het uitvoeren van workflows gebruikt.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Beginner
exl-id: fddd88b1-603a-465b-b5e7-624632c0d5cd
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 1%

---

# Uitvoeringsopdrachten {#execution-commands}

Met de pictogrammen op de actiebalk kunt u de uitvoering van een werkstroom starten, bijhouden en wijzigen. Zie [&#x200B; bar van de Actie &#x200B;](../../automating/using/workflow-interface.md#action-bar).

![](assets/wkf_execution_2.png)

De beschikbare acties zijn als volgt:

**Begin**

De ![](assets/play_darkgrey-24px.png) knoop begint een werkschema uit te voeren, dat dan de **Bezig** (blauw) status neemt. Als de werkstroom is gepauzeerd, wordt deze hervat, anders wordt deze gestart en worden de initiële activiteiten geactiveerd.

>[!NOTE]
>
>De start is een asynchroon proces: de aanvraag wordt opgeslagen en wordt zo snel mogelijk verwerkt door de engine voor workflowuitvoering.

**Pauze**

De knop ![](assets/pause_darkgrey-24px.png) pauzeert de uitvoering. Het werkschema neemt de **Waarschuwing** (geel) status over. Er zullen geen nieuwe activiteiten worden geactiveerd totdat de activiteiten worden hervat, maar de lopende activiteiten worden niet opgeschort.

**Einde**

De ![](assets/stop_darkgrey-24px.png) knoop houdt een werkschema tegen dat wordt uitgevoerd, die dan de **Voltooide** (groene) status zal nemen. De actieve bewerkingen worden indien mogelijk onderbroken en de import of SQL-query&#39;s die worden uitgevoerd, worden onmiddellijk geannuleerd. U kunt de workflow niet hervatten vanaf de plaats waar deze is gestopt.

**Begin** opnieuw

Met de knop ![](assets/pauseplay_darkgrey-24px.png) wordt gestopt en wordt vervolgens een workflow opnieuw gestart. In de meeste gevallen kunt u de toepassing sneller opnieuw starten. Het kan ook handig zijn om opnieuw starten te automatiseren nadat het stoppen een bepaalde hoeveelheid tijd in beslag neemt, omdat de knop ![](assets/play_darkgrey-24px.png) alleen beschikbaar is wanneer de stop effectief is.

Wanneer een of meerdere activiteiten in een workflow zijn geselecteerd, kunt u andere handelingen uitvoeren, zoals:

**Onmiddellijke uitvoering**

Met de knop ![](assets/pending_darkgrey-24px.png) kunt u activiteiten in behandeling starten die zo snel mogelijk zijn geselecteerd.

**Normale uitvoering**

Met de knop ![](assets/check_darkgrey-24px.png) activeert u gepauzeerde of gedeactiveerde activiteiten.

**Uitgestelde Uitvoering**

Met de knop ![](assets/check_pause_darkgrey-24px.png) wordt de workflow bij de geselecteerde activiteit gepauzeerd: deze taak en alle volgende taken (in dezelfde vertakking) worden niet uitgevoerd.

**Geen uitvoering**

Met de knop ![](assets/checkdisable.png) worden alle geselecteerde activiteiten gedeactiveerd.

>[!NOTE]
>
>Met snelle handelingen hebt u toegang tot verschillende handelingen die betrekking hebben op een bepaalde activiteit en worden deze weergegeven wanneer een activiteit wordt geselecteerd.
