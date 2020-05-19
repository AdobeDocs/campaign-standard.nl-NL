---
title: Uitsluiting
description: Met de uitsluitingsactiviteit kunt u elementen op basis van bepaalde criteria uitsluiten van één populatie.
page-status-flag: never-activated
uuid: b79e7f73-37a0-4ec3-ac5a-5449dc1b1f22
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: d5312fcd-43ad-428e-bde9-90f062e9358c
context-tags: exclusion,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 21faea89b3b38f3e667ed6c4de0be6d07f0b7197
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 0%

---


# Uitsluiting{#exclusion}

## Beschrijving {#description}

![](assets/exclusion.png)

Met deze **[!UICONTROL Exclusion]** activiteit kunt u elementen op basis van bepaalde criteria uitsluiten van één populatie.

## Gebruikscontext {#context-of-use}

De **[!UICONTROL Exclusion]** activiteit wordt hoofdzakelijk gebruikt om extra filtreren op binnenkomende overgangspopulaties uit te voeren.

Een primaire set wordt gedefinieerd onder binnenkomende overgangen. Leden van andere binnenkomende overgangen worden uitgesloten van de primaire set. De uitgaande overgang van de uitsluitingsactiviteit bevat slechts de leden van de primaire reeks die niet in de andere binnenkomende overgangen werden ontmoet.

## Configuratie {#configuration}

1. Sleep een **[!UICONTROL Exclusion]** activiteit naar uw werkstroom.
1. Selecteer de activiteit, dan open het gebruikend de ![](assets/edit_darkgrey-24px.png) knoop van de snelle acties die verschijnen.
1. Selecteer de overgang **[!UICONTROL Primary set]** in de binnenkomende overgangen. Dit is de set waaruit elementen worden uitgesloten. De andere sets komen overeen met de elementen voordat deze worden uitgesloten van de primaire set.

   >[!NOTE]
   >
   >De binnenkomende overgangen moeten hetzelfde type populatie bevatten. Als de primaire set bijvoorbeeld testprofielen bevat, moeten de andere overgangen ook testprofielen bevatten.

1. Indien nodig, beheer de [Overgangen](../../automating/using/activity-properties.md) van de activiteit om tot de geavanceerde opties voor de uitgaande bevolking toegang te hebben.
1. Bevestig de configuratie van uw activiteit en sla uw werkschema op.

## Voorbeeld {#example}

In het volgende voorbeeld worden twee query-activiteiten getoond die zijn geconfigureerd om profielen te filteren uit de Adobe Campaign-database die tussen de 18 en 27 jaar oud zijn en een ongeldig e-mailadres hebben. De profielen met ongeldige e-mailadressen worden dan uitgesloten van de eerste reeks. Zo kunt u bijvoorbeeld een e-mail verzenden.

![](assets/wkf_exclusion_example.png)

