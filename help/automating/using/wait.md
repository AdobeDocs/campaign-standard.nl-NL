---
title: Wachten
description: Met de wachtactiviteiten wordt het uitvoeren van een deel van een workflow tijdelijk opgeschort.
page-status-flag: never-activated
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: wait,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Wachten{#wait}

## Beschrijving {#description}

![](assets/wait.png)

De **[!UICONTROL Wait]** activiteit schort tijdelijk het uitvoeren van een deel van een werkschema op. Het activeert zijn uitgaande overgang na een vertraging die zich van een paar seconden tot verscheidene maanden kan uitstrekken, die de activiteiten uitvoert die daarna worden geplaatst.

## Gebruikscontext {#context-of-use}

De **[!UICONTROL Wait]** activiteit wordt gebruikt om een bepaalde hoeveelheid tijd toe te staan om tussen twee uit te voeren activiteiten over te gaan. Als u bijvoorbeeld meerdere dagen na een e-mailleveringsactiviteit wilt wachten, analyseert u de tijdens deze periode gegenereerde openen en klikken voordat u follow-upbewerkingen uitvoert (herinnerings-e-mail, een publiek maken, enz.).

## Configuratie {#configuration}

1. Sleep een **[!UICONTROL Wait]** activiteit naar uw werkstroom.
1. Selecteer de activiteit, dan open het gebruikend de ![](assets/edit_darkgrey-24px.png) knoop van de snelle acties die verschijnen.
1. Specificeer de **[!UICONTROL Duration]** wachttijd tussen wanneer de binnenkomende en uitgaande overgangen van de activiteit worden geactiveerd.

   U kunt de duur handmatig invoeren of de kiezer in het veld gebruiken.

   ![](assets/wait_duration.png)

1. Bevestig de configuratie van uw activiteit en sla uw werkschema op.

## Voorbeeld {#example}

Het volgende voorbeeld illustreert de **[!UICONTROL Wait]** activiteit in een typisch gebruiksgeval. Er wordt een e-mailuitnodiging voor een gebeurtenis verzonden. 24 uur nadat het bericht is verzonden, worden de logboeken voor e-mailbezorging geanalyseerd en wordt een herinneringsbericht verzonden naar de personen die het eerste e-mailbericht hebben ontvangen maar zich niet hebben aangemeld.

De workflow wordt als volgt weergegeven:

![](assets/wait_example_workflow.png)

* Een eerste **[!UICONTROL Query]** doel betreft de profielen die de e-mailuitnodiging zullen worden verzonden.
* Een **[!UICONTROL Email delivery]** verzendt de uitnodiging voor de eerste keer naar de geselecteerde profielen.
* Een **[!UICONTROL Wait]** activiteit van 24h plaatst een pauze tussen toen de uitnodiging werd verzonden en de rest van het werkschema.
* Een tweede **[!UICONTROL Query]** bestand heeft betrekking op de profielen die het eerste e-mailbericht hebben ontvangen maar niet op de koppeling met het abonnement hebben geklikt.
* Een tweede **[!UICONTROL Email delivery]** verzendt een herinnering van de uitnodiging aan de geselecteerde mensen.

