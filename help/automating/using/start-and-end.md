---
solution: Campaign Standard
product: campaign
title: Start- en Einde-activiteiten
description: Met de activiteiten Start en Einde kunt u duidelijk markeren waar uw workflow begint en eindigt.
audience: automating
content-type: reference
topic-tags: execution-activities
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 100%

---


# Start- en Einde-activiteiten{#start-and-end}

## Beschrijving {#description}

![](assets/start.png)

![](assets/end.png)

Met de activiteiten **[!UICONTROL Start]** en **[!UICONTROL End]** kunt u duidelijk aangeven waar uw workflow begint en eindigt.

## Gebruikscontext {#context-of-use}

Een workflow start als er activiteiten zijn zonder binnenkomende overgang, en stopt wanneer er geen taken meer worden uitgevoerd. Desondanks kunt u **[!UICONTROL Start]**- en **[!UICONTROL End]**-activiteiten toevoegen om duidelijk aan te geven wat de begin- en eindpunten van een workflow zijn. Dit is vooral handig voor relatief complexe workflows.

Als best practice geldt dat u beter een **[!UICONTROL End]**-activiteit kunt gebruiken om de laatste overgang van een workflow altijd duidelijk aan te geven. Zo weet u zeker dat de workflow op de juiste manier wordt beëindigd.

## Configuratie {#configuration}

1. Sleep een activiteit **[!UICONTROL Start]** of **[!UICONTROL End]** en zet deze neer in uw workflow.
1. Plaats de **[!UICONTROL Start]**-activiteit vóór andere activiteiten zoals query&#39;s en plaats de **[!UICONTROL End]**-activiteit na een reeks activiteiten.
1. Selecteer de activiteit en open deze met de knop ![](assets/edit_darkgrey-24px.png) vanuit de snelle acties die verschijnen.
1. U kunt het **End**-object zo configureren dat alle lopende taken van de workflow worden onderbroken, inclusief de taken die niet zijn afgerond. Selecteer de bijbehorende optie om dit te doen.
1. Bevestig de configuratie van uw activiteit en sla de workflow op.

## Een andere workflow activeren {#triggering-another-workflow}

Op het tabblad **[!UICONTROL External signal]** van een **[!UICONTROL End]**-activiteit kunt u een andere workflow activeren. Raadpleeg de sectie [Extern signaal](../../automating/using/external-signal.md).

## Voorbeeld {#example}

Het volgende voorbeeld toont hoe een complexe workflow wordt uitgevoerd met een **[!UICONTROL Start]**-activiteit en diverse **[!UICONTROL End]**-activiteiten. Het selectievakje **[!UICONTROL Stop all tasks in progress]** is ingeschakeld voor de eerste **[!UICONTROL End]**-activiteit. Zodra de overeenkomstige taak wordt beëindigd, wordt de volledige workflow gestopt: dit heeft hetzelfde effect als wanneer de knop ![](assets/stop_darkgrey-24px.png) was geselecteerd (zie de sectie [Actiebalk](../../automating/using/workflow-interface.md#action-bar)).

![](assets/wkf_start_end_example.png)

