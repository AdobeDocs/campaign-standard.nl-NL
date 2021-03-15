---
solution: Campaign Standard
product: campaign
title: Uitvoeringsopdrachten
description: Leer hoe u opdrachten voor het uitvoeren van workflows gebruikt.
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
source-wordcount: '321'
ht-degree: 2%

---


# Uitvoeringsopdrachten {#execution-commands}

Met de pictogrammen op de actiebalk kunt u de uitvoering van een werkstroom starten, bijhouden en wijzigen. Zie [Actiebalk](../../automating/using/workflow-interface.md#action-bar).

![](assets/wkf_execution_2.png)

De beschikbare acties zijn als volgt:

**Starten**

Met de knop ![](assets/play_darkgrey-24px.png) wordt een workflow uitgevoerd die vervolgens de status **In progress** (blauw) krijgt. Als de werkstroom is gepauzeerd, wordt deze hervat, anders wordt deze gestart en worden de initiële activiteiten geactiveerd.

>[!NOTE]
>
>De aanvang is een asynchroon proces: het verzoek wordt opgeslagen en zal zo spoedig mogelijk door de werkschemauitvoeringsmotor worden verwerkt.

**Pauzeren**

Met de knop ![](assets/pause_darkgrey-24px.png) wordt de uitvoering gepauzeerd. De workflow neemt de status **Waarschuwing** (geel) over. Er zullen geen nieuwe activiteiten worden geactiveerd totdat de activiteiten worden hervat, maar de lopende activiteiten worden niet opgeschort.

**Stoppen**

De ![](assets/stop_darkgrey-24px.png) knoop houdt een werkschema tegen dat wordt uitgevoerd, die dan **voltooide** (groene) status zal nemen. De bewerkingen die worden uitgevoerd, worden indien mogelijk onderbroken en de import of SQL-query&#39;s die worden uitgevoerd, worden onmiddellijk geannuleerd. U kunt de workflow niet hervatten vanaf de plaats waar deze is gestopt.

**Opnieuw starten**

De ![](assets/pauseplay_darkgrey-24px.png) knoop impliceert het tegenhouden, dan het opnieuw beginnen van een werkschema. In de meeste gevallen kunt u de toepassing sneller opnieuw starten. Het kan ook nuttig zijn om opnieuw beginnen te automatiseren zodra het tegenhouden een bepaalde hoeveelheid tijd vergt, omdat ![](assets/play_darkgrey-24px.png) knoop slechts beschikbaar is wanneer de stop effectief is.

Wanneer een of meerdere activiteiten in een workflow zijn geselecteerd, kunt u andere handelingen uitvoeren, zoals:

**Onmiddellijke uitvoering**

Met de knop ![](assets/pending_darkgrey-24px.png) worden eventuele lopende activiteiten die zijn geselecteerd zo snel mogelijk gestart.

**Normale uitvoering**

Met de knop ![](assets/check_darkgrey-24px.png) activeert u gepauzeerde of gedeactiveerde activiteiten.

**Uitvoering opgeschort**

Met de knop ![](assets/check_pause_darkgrey-24px.png) wordt de workflow bij de geselecteerde activiteit gepauzeerd: deze taak en alle taken die erop volgen (in dezelfde vertakking) worden niet uitgevoerd.

**Geen uitvoering**

Met de knop ![](assets/checkdisable.png) worden geselecteerde activiteiten gedeactiveerd.

>[!NOTE]
>
>Met snelle handelingen hebt u toegang tot verschillende handelingen die betrekking hebben op een bepaalde activiteit en worden deze weergegeven wanneer een activiteit wordt geselecteerd.
