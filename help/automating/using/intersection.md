---
solution: Campaign Standard
product: campaign
title: Doorsnede
description: Met de activiteit Doorsnede kunt u alleen de elementen behouden die de verschillende binnenkomende populaties in de activiteit gemeenschappelijk hebben.
audience: automating
content-type: reference
topic-tags: targeting-activities
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 100%

---


# Doorsnede{#intersection}

## Beschrijving {#description}

![](assets/intersection.png)

Met de activiteit **[!UICONTROL Intersection]** kunt u alleen de elementen behouden die de verschillende binnenkomende populaties in de activiteit gemeenschappelijk hebben.

## Gebruikscontext {#context-of-use}

De activiteit **[!UICONTROL Intersection]** wordt over het algemeen gebruikt om aanvullende filters toe te passen op populaties van binnenkomende overgangen.

## Configuratie {#configuration}

1. Sleep een activiteit **[!UICONTROL Intersection]** en zet deze neer in uw workflow.
1. Verbind de activiteit met de andere activiteiten die eraan voorafgaan, zoals query’s.
1. Selecteer de activiteit en open deze met de knop ![](assets/edit_darkgrey-24px.png) vanuit de snelle acties die verschijnen.
1. Selecteer het **[!UICONTROL Reconciliation type]**:

   * **[!UICONTROL Keys only]**: Standaardmodus. De activiteit behoudt slechts één element wanneer elementen van de verschillende binnenkomende overgangen dezelfde sleutel hebben.
   * **[!UICONTROL All shared columns]**: De data worden afgestemd op basis van kolommen die gemeenschappelijk zijn met de binnenkomende overgangen. Daarom moet u de primaire set selecteren die als basis voor de vergelijking zal dienen. Deze optie kan worden gebruikt als de doeldimensies van de binnenkomende populatie verschillend zijn.
   * **[!UICONTROL A selection of columns]**: Selecteer deze optie om de lijst met kolommen te definiëren waarop de data-afstemming wordt toegepast. U moet eerst de primaire set (de set met brondata) selecteren en vervolgens de velden opgeven die voor de samenvoeging moeten worden gebruikt.

1. Schakel het selectievakje **[!UICONTROL Use common additional data only]** in als u alleen de aanvullende data wilt behouden die in alle binnenkomende overgangen voorkomen.
1. Indien nodig beheert u de [Overgangen](../../automating/using/activity-properties.md) van de activiteit om toegang te krijgen tot de geavanceerde opties voor de uitgaande populatie.
1. Bevestig de configuratie van uw activiteit en sla de workflow op.

## Voorbeeld {#example}

Het volgende voorbeeld toont de doorsnede tussen twee queryactiviteiten. Dit voorbeeld wordt hier gebruikt om de Adobe Campaign-database te bekijken en profielen op te halen die tussen 18 en 27 jaar oud zijn en profielen waarvan het e-mailadres is opgegeven.

![](assets/wkf_intersection_example.png)

