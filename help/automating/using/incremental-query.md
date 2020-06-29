---
title: Incrementele query
description: Met de incrementele query-activiteit kunt u een groep elementen filteren en extraheren uit de Adobe Campaign-database.
page-status-flag: never-activated
uuid: 73b42422-e815-43ef-84c0-97c4433ccc98
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 80961e73-42ec-463a-8496-cff69fab0475
context-tags: incremental,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 87e0611fae0560aca276caa3c4cf793e9c095d72
workflow-type: tm+mt
source-wordcount: '614'
ht-degree: 0%

---


# Incrementele query{#incremental-query}

## Beschrijving {#description}

![](assets/incremental.png)

Met deze **[!UICONTROL Incremental query]** activiteit kunt u een reeks elementen filteren en extraheren uit de Adobe Campaign-database. Telkens wanneer deze activiteit wordt uitgevoerd, worden de resultaten van de vorige uitvoeringen uitgesloten. Hierdoor kunt u alleen nieuwe elementen als doel instellen.

U kunt **[!UICONTROL Additional data]** voor de doelpopulatie definiëren via een toegewezen tabblad. Deze gegevens worden opgeslagen in extra kolommen en kunnen alleen worden gebruikt voor de actieve workflow.

De activiteit gebruikt het hulpmiddel van de vraagredacteur. Dit hulpmiddel wordt gedetailleerd in een [specifieke sectie](../../automating/using/editing-queries.md#about-query-editor).

## Gebruikscontext {#context-of-use}

Er **[!UICONTROL Incremental query]** moet een koppeling zijn naar een query **[!UICONTROL Scheduler]** om de uitvoeringsfrequentie van de workflow te definiëren, en dus ook naar de query.

Op het **[!UICONTROL Processed data]** tabblad, dat specifiek is voor deze activiteit, kunt u, indien nodig, alle resultaten bekijken van de vorige uitvoeringen van de activiteit.

De **[!UICONTROL Incremental query]** activiteit kan voor diverse soorten gebruik worden gebruikt:

* Individuen segmenteren om het doel van een bericht, publiek, enz. te bepalen.

* Gegevens exporteren.

   U kunt een **[!UICONTROL Incremental query]** activiteit gebruiken om nieuwe login dossiers regelmatig uit te voeren. Het kan bijvoorbeeld nuttig zijn als u uw logboekgegevens in externe rapportering of hulpmiddelen van BI wilt gebruiken. Een volledig voorbeeld is beschikbaar in de sectie Logbestanden [exporteren](../../automating/using/exporting-logs.md) .

**Verwante onderwerpen**

* [Hoofdlettergebruik: Incrementele query op abonnees van een service](../../automating/using/incremental-query-on-subscribers.md)

## Configuratie {#configuration}

1. Sleep een **[!UICONTROL Incremental query]** activiteit naar uw werkstroom.
1. Selecteer de activiteit, dan open het gebruikend de ![](assets/edit_darkgrey-24px.png) knoop van de snelle acties die verschijnen.
1. Als u een vraag op een middel buiten het profielmiddel zou willen in werking stellen, ga naar het **[!UICONTROL Properties]** lusje van de activiteit en selecteer **[!UICONTROL Resource]** en **[!UICONTROL Targeting dimension]**.

   Met de optie **[!UICONTROL Resource]** kunt u de filters verfijnen die in het palet worden weergegeven, terwijl de **[!UICONTROL Targeting dimension]** context met betrekking tot de geselecteerde bron overeenkomt met het type populatie dat u wilt verkrijgen (geïdentificeerde profielen, leveringen, gegevens die zijn gekoppeld aan de geselecteerde bron, enz.).

1. Voer op het **[!UICONTROL Target]** tabblad uw query uit door regels te definiëren en te combineren.
1. Kies op het **[!UICONTROL Processed data]** tabblad de incrementele modus die u wilt gebruiken voor de volgende uitvoeringen van de workflow:

   * **[!UICONTROL Use the exclusion of the results of previous executions]**: de resultaten van eerdere uitvoeringen voor elke nieuwe uitvoering zijn uitgesloten .
   * **[!UICONTROL Use a date field]**: bij de volgende uitvoeringen wordt alleen rekening gehouden met de resultaten waarbij het geselecteerde datumveld groter of gelijk is aan de laatste uitvoeringsdatum van de **[!UICONTROL Incremental query]** activiteit. U kunt elk datumveld selecteren dat betrekking heeft op de bron die op het **[!UICONTROL Properties]** tabblad is geselecteerd. Deze modus biedt betere prestaties bij het opvragen van grote bronnen, zoals loggegevens.

      Na de eerste uitvoering van de workflow ziet u op dit tabblad de laatste uitvoeringsdatum die wordt gebruikt voor de volgende uitvoering. Deze wordt automatisch bijgewerkt wanneer de workflow wordt uitgevoerd. U kunt deze waarde nog steeds overschrijven door handmatig een nieuwe waarde in te voeren zodat deze aan uw behoeften voldoet.
   >[!NOTE]
   >
   >In de **[!UICONTROL Use a date field]** modus is meer flexibiliteit mogelijk, afhankelijk van het datumveld dat is geselecteerd. Als het geselecteerde veld bijvoorbeeld overeenkomt met een wijzigingsdatum, kunt u in de modus Datumveld gegevens ophalen die onlangs zijn bijgewerkt, terwijl in de andere modus alleen opnamen worden uitgesloten die in een vorige uitvoering al als doel waren ingesteld, zelfs als deze zijn gewijzigd sinds de laatste uitvoering van de workflow.

   ![](assets/incremental_query_usedatefield.png)

1. U kunt **[!UICONTROL Additional data]** voor de doelpopulatie definiëren via een toegewezen tabblad. Deze gegevens worden opgeslagen in extra kolommen en kunnen alleen worden gebruikt voor de actieve workflow. Met name kunt u gegevens uit de Adobe Campaign-databasetabellen toevoegen die zijn gekoppeld aan de doeldimensie van de query. Raadpleeg de sectie [Verrijkende gegevens](../../automating/using/query.md#enriching-data) .
1. Bevestig de configuratie van uw activiteit en sla uw werkschema op.

## Gegevens worden verrijkt {#enriching-data}

Enkel zoals voor een vraag, kunt u de gegevens van een verrijken **[!UICONTROL Incremental query]**. Raadpleeg de sectie [Verrijkende gegevens](../../automating/using/query.md#enriching-data) .
