---
title: AND-join
description: Met de activiteit AND-join kunt u meerdere uitvoervertakkingen van een workflow synchroniseren.
page-status-flag: never-activated
uuid: 9b54fd4c-9915-400f-a494-74e52c329b8a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 4b55efa2-652e-4493-bfa7-eaee59b383ca
context-tags: andjoin,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# AND-join{#and-join}

## Beschrijving {#description}

![](assets/and_join.png)

Met deze **[!UICONTROL AND-join]** activiteit kunt u meerdere uitvoeringstakken van een workflow synchroniseren.

## Gebruikscontext {#context-of-use}

De **[!UICONTROL AND-join]** activiteit brengt slechts zijn uitgaande overgang teweeg zodra alle binnenkomende overgangen, met andere woorden, worden geactiveerd zodra alle voorafgaande activiteiten zijn geëindigd.

## Configuratie {#configuration}

1. U kunt meerdere activiteiten, zoals query&#39;s, in uw werkstroom neerzetten om minstens twee verschillende uitvoertakken te vormen.
1. Sleep een **[!UICONTROL AND-join]** activiteit naar uw werkstroom.
1. Verbind het na de twee verschillende takken die u zou willen synchroniseren.
1. Selecteer de activiteit, dan open het gebruikend de ![](assets/edit_darkgrey-24px.png) knoop van de snelle acties die verschijnen.
1. Selecteer de hoofdset die in de uitgaande overgang moet worden bewaard. Als u geen set selecteert, wordt een willekeurige populatie verzonden uit de activiteit.
1. Bevestig de configuratie van uw activiteit en sla uw werkschema op.

## Voorbeeld {#example}

In het volgende voorbeeld worden twee workflowvertakkingen getoond voordat er verbinding wordt gemaakt met de **[!UICONTROL AND-join]** activiteit. Het extraheren van bestanden kan alleen plaatsvinden wanneer de drie binnenkomende overgangen van de **[!UICONTROL AND-join]** activiteit zijn ingeschakeld.

![](assets/wkf_and-join_example.png)

