---
title: Incrementele query
description: Met de incrementele queryactiviteit kunt u een populatie van elementen filteren en extraheren uit de Adobe Campaign-database.
page-status-flag: never-activated
uuid: 73b42422-e815-43ef-84c0-97c4433ccc98
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 80961e73-42ec-463a-8496-cff69fab0475
context-tags: incremental,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '614'
ht-degree: 98%

---


# Incrementele query{#incremental-query}

## Beschrijving {#description}

![](assets/incremental.png)

Met de activiteit **[!UICONTROL Incremental query]** kunt u een populatie van elementen filteren en extraheren uit de Adobe Campaign-database. Telkens wanneer deze activiteit wordt uitgevoerd, worden de resultaten van de vorige uitvoeringen uitgesloten. Zo kunt u doelgericht alleen nieuwe elementen benaderen.

Via een toegewezen tabblad kunt u **[!UICONTROL Additional data]** voor de doelpopulatie definiëren. Deze data worden in extra kolommen opgeslagen en kunnen alleen worden gebruikt voor de actieve workflow.

Deze activiteit maakt gebruikt van de tool Query-editor. Deze tool wordt gedetailleerd beschreven in een [specifieke sectie](../../automating/using/editing-queries.md#about-query-editor).

## Gebruikscontext {#context-of-use}

Een **[!UICONTROL Incremental query]** moet gekoppeld worden aan een **[!UICONTROL Scheduler]** om de uitvoeringsfrequentie van de workflow, en dus de query te definiëren.

Op het tabblad **[!UICONTROL Processed data]** dat specifiek is bedoeld voor deze activiteit, kunt u indien nodig alle resultaten bekijken van de vorige uitvoeringen van de activiteit.

De activiteit **[!UICONTROL Incremental query]** kan voor diverse doeleinden worden gebruikt:

* Individuele gebruikers segmenteren om het doel van een bericht, doelgroep, enz te bepalen.

* Data exporteren.

   U kunt een activiteit **[!UICONTROL Incremental query]** gebruiken om regelmatig nieuwe logboeken in bestanden te exporteren. Dit kan bijvoorbeeld nuttig zijn als u uw loggegevens wilt gebruiken in externe rapporten of BI-tools. Een volledig voorbeeld is beschikbaar in de sectie [Logboeken exporteren](../../automating/using/exporting-logs.md).

**Verwante onderwerpen**

* [Hoofdlettergebruik: Incrementele query op abonnees van een service](../../automating/using/incremental-query-on-subscribers.md)

## Configuratie {#configuration}

1. Sleep een activiteit **[!UICONTROL Incremental query]** en zet deze neer in uw workflow.
1. Selecteer de activiteit en open deze met de knop ![](assets/edit_darkgrey-24px.png) vanuit de snelle acties die verschijnen.
1. Als u een query wilt uitvoeren op een andere bron dan een profielbron, gaat u naar het tabblad **[!UICONTROL Properties]** van de activiteit en selecteert u een **[!UICONTROL Resource]** en een **[!UICONTROL Targeting dimension]**.

   Met de optie **[!UICONTROL Resource]** kunt u de filters verfijnen die in het palet worden weergegeven, terwijl de optie **[!UICONTROL Targeting dimension]** (binnen de context van de geselecteerde bron) overeenkomt met het type populatie dat u wilt verkrijgen (geïdentificeerde profielen, leveringen, data die zijn gekoppeld aan de geselecteerde bron, enz.).

1. Voer op het tabblad **[!UICONTROL Target]** uw query uit door regels te definiëren en te combineren.
1. Kies op het tabblad **[!UICONTROL Processed data]** de incrementele modus die u wilt gebruiken voor de volgende uitvoeringen van de workflow:

   * **[!UICONTROL Use the exclusion of the results of previous executions]**: De resultaten van eerdere uitvoeringen zijn uitgesloten van elke nieuwe uitvoering.
   * **[!UICONTROL Use a date field]**: Bij de volgende uitvoeringen wordt alleen rekening gehouden met de resultaten waarvan het geselecteerde datumveld groter is dan of gelijk is aan de laatste uitvoeringsdatum van de activiteit **[!UICONTROL Incremental query]**. U kunt elk datumveld selecteren dat betrekking heeft op de bron die is geselecteerd op het tabblad **[!UICONTROL Properties]**. Deze modus biedt betere prestaties bij het uitvoeren van query&#39;s op grote bronnen, zoals loggegevens.

      Na de eerste uitvoering van de workflow ziet u op dit tabblad de laatste uitvoeringsdatum die wordt gebruikt voor de volgende uitvoering. Deze wordt automatisch steeds bijgewerkt wanneer de workflow wordt uitgevoerd. U kunt deze waarde ook overschrijven door handmatig een nieuwe waarde in te voeren die beter aan uw behoeften voldoet.
   >[!NOTE]
   >
   >In de modus **[!UICONTROL Use a date field]** is meer flexibiliteit mogelijk, afhankelijk van het datumveld dat is geselecteerd. Als het geselecteerde veld bijvoorbeeld overeenkomt met een wijzigingsdatum, kunt u in de datumveldmodus data opvragen die recentelijk zijn bijgewerkt. De andere modus sluit opnames echter gewoon uit die al in een eerdere uitvoering waren benaderd, zelfs als deze sinds de laatste uitvoering van de workflow zijn gewijzigd.

   ![](assets/incremental_query_usedatefield.png)

1. Via een toegewezen tabblad kunt u **[!UICONTROL Additional data]** voor de doelpopulatie definiëren. Deze data worden in extra kolommen opgeslagen en kunnen alleen worden gebruikt voor de actieve workflow. U kunt met name data toevoegen uit de Adobe Campaign-databasetabellen die zijn gekoppeld aan de doeldimensie van de query. Raadpleeg de sectie [Data verrijken](../../automating/using/query.md#enriching-data).
1. Bevestig de configuratie van uw activiteit en sla de workflow op.

## Data verrijken {#enriching-data}

Net als bij een query kunt u de data van een **[!UICONTROL Incremental query]** verrijken. Raadpleeg de sectie [Data verrijken](../../automating/using/query.md#enriching-data).
