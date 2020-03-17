---
title: Begin en einde
description: Met de activiteiten Start en End kunt u duidelijk markeren waar uw workflow begint en eindigt.
page-status-flag: never-activated
uuid: 146b6337-122c-453d-8ffd-5c157db29217
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: a0a8a725-8ede-4626-9798-b86924b58beb
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Begin en einde{#start-and-end}

## Beschrijving {#description}

![](assets/start.png)

![](assets/end.png)

Met de **[!UICONTROL Start]** en **[!UICONTROL End]** activiteiten kunt u duidelijk aangeven waar de workflow begint en eindigt.

## Gebruikscontext {#context-of-use}

Het uitvoeren van een werkschema begint met activiteiten zonder een binnenkomende overgang, en houdt op wanneer er niet meer om het even welke lopende taken zijn. Desalniettemin kunt u **[!UICONTROL Start]** en **[!UICONTROL End]** activiteiten toevoegen om de begin- en eindpunten van een workflow duidelijk te markeren. Dit is vooral handig voor relatief complexe workflows.

Het is aan te raden om een **[!UICONTROL End]** activiteit te gebruiken in plaats van de laatste overgang van een workflow afzonderlijk te laten, zodat de workflow op de juiste manier wordt beëindigd.

## Configuratie {#configuration}

1. Sleep een **[!UICONTROL Start]** of **[!UICONTROL End]** activiteit naar uw werkstroom.
1. Plaats de **[!UICONTROL Start]** activiteit vóór andere activiteiten zoals query&#39;s en de **[!UICONTROL End]** activiteit na een reeks activiteiten.
1. Selecteer de activiteit, dan open het gebruikend de ![](assets/edit_darkgrey-24px.png) knoop van de snelle acties die verschijnen.
1. U kunt het **voorwerp van het Eind** vormen zodat het alle aan de gang zijnde taken van het werkschema onderbreekt, met inbegrip van die die niet hebben gebeëindigd. Selecteer de bijbehorende optie om dit te doen.
1. Bevestig de configuratie van uw activiteit en sla uw werkschema op.

## Een andere workflow activeren {#triggering-another-workflow}

Op het **[!UICONTROL External signal]** tabblad van een **[!UICONTROL End]** activiteit kunt u een andere workflow activeren. Raadpleeg de sectie [Extern signaal](../../automating/using/external-signal.md) .

## Voorbeeld {#example}

In het volgende voorbeeld wordt getoond hoe een complexe workflow wordt uitgevoerd met een **[!UICONTROL Start]** activiteit en diverse **[!UICONTROL End]** activiteiten. Het **[!UICONTROL Stop all tasks in progress]** vakje is gecontroleerd op de eerste **[!UICONTROL End]** activiteit. Zodra de overeenkomstige taak wordt gebeëindigd, zal het volledige werkschema worden tegengehouden: het heeft hetzelfde effect als wanneer de ![](assets/stop_darkgrey-24px.png) knop was geselecteerd (zie de sectie [Actiebalk](../../automating/using/workflow-interface.md#action-bar) ).

![](assets/wkf_start_end_example.png)

