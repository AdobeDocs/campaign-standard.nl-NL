---
title: Uitvoeropdrachten
description: Leer hoe u opdrachten voor het uitvoeren van workflows gebruikt.
page-status-flag: never-activated
uuid: ff02b74e-53e8-49c6-bf8e-0c729eaa7d25
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: 906c85ea-83b7-4268-86da-cd353f1dc591
context-tags: workflow,overview;workflow,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 3ed78fd610b0d134cd1e60f34c93161cb1e5c50f
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 0%

---


# Uitvoeropdrachten {#execution-commands}

Met de pictogrammen op de actiebalk kunt u de uitvoering van een werkstroom starten, bijhouden en wijzigen. Zie [Actiebalk](../../automating/using/workflow-interface.md#action-bar).

![](assets/wkf_execution_2.png)

De beschikbare acties zijn als volgt:

**Start**

Met de ![](assets/play_darkgrey-24px.png) knop wordt een workflow uitgevoerd die vervolgens de status **In uitvoering** (blauw) krijgt. Als de werkstroom is gepauzeerd, wordt deze hervat, anders wordt deze gestart en worden de initiële activiteiten geactiveerd.

>[!NOTE]
>
>De aanvang is een asynchroon proces: het verzoek wordt opgeslagen en zal zo spoedig mogelijk door de werkschemauitvoeringsmotor worden verwerkt.

**Pauzeren**

De ![](assets/pause_darkgrey-24px.png) knop pauzeert de uitvoering. De workflow neemt de status **Waarschuwing** (geel) over. Er zullen geen nieuwe activiteiten worden geactiveerd totdat de activiteiten worden hervat, maar de lopende activiteiten worden niet opgeschort.

**Stoppen**

Met de ![](assets/stop_darkgrey-24px.png) knop wordt een workflow gestopt die wordt uitgevoerd en die vervolgens de status **Voltooid** (groen) krijgt. De bewerkingen die worden uitgevoerd, worden indien mogelijk onderbroken en de import of SQL-query&#39;s die worden uitgevoerd, worden onmiddellijk geannuleerd. U kunt de workflow niet hervatten vanaf de plaats waar deze is gestopt.

**Opnieuw starten**

De ![](assets/pauseplay_darkgrey-24px.png) knop bestaat uit stoppen en een workflow opnieuw starten. In de meeste gevallen kunt u de toepassing sneller opnieuw starten. Het kan ook handig zijn om opnieuw starten te automatiseren wanneer het stoppen een bepaalde hoeveelheid tijd in beslag neemt, omdat de ![](assets/play_darkgrey-24px.png) knop alleen beschikbaar is wanneer de stop effectief is.

Wanneer een of meerdere activiteiten in een workflow zijn geselecteerd, kunt u andere handelingen uitvoeren, zoals:

**Onmiddellijke uitvoering**

Met de ![](assets/pending_darkgrey-24px.png) knop worden alle lopende activiteiten zo snel mogelijk gestart.

**Normale uitvoering**

Met de ![](assets/check_darkgrey-24px.png) knop activeert u gepauzeerde of gedeactiveerde activiteiten.

**Uitvoering opgeschort**

Met de ![](assets/check_pause_darkgrey-24px.png) knop wordt de workflow bij de geselecteerde activiteit onderbroken: deze taak en alle taken die erop volgen (in dezelfde vertakking) worden niet uitgevoerd.

**Geen uitvoering**

Met de ![](assets/checkdisable.png) knop worden geselecteerde activiteiten gedeactiveerd.

>[!NOTE]
>
>Met snelle handelingen hebt u toegang tot verschillende handelingen die betrekking hebben op een bepaalde activiteit en worden deze weergegeven wanneer een activiteit wordt geselecteerd.
