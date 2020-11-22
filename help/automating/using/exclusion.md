---
solution: Campaign Standard
product: campaign
title: Uitsluiting
description: Met de activiteit Uitsluiting kunt u elementen uit één populatie uitsluiten op basis van bepaalde criteria.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: exclusion,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 100%

---


# Uitsluiting{#exclusion}

## Beschrijving {#description}

![](assets/exclusion.png)

Met de activiteit **[!UICONTROL Exclusion]** kunt u elementen uit één populatie uitsluiten op basis van bepaalde criteria.

## Gebruikscontext {#context-of-use}

De activiteit **[!UICONTROL Exclusion]** wordt hoofdzakelijk gebruikt om extra filters op binnenkomende overgangspopulaties toe te passen.

Er wordt een primaire set van binnenkomende overgangen gedefinieerd. Leden van andere binnenkomende overgangen worden uitgesloten van de primaire set. De uitgaande overgang van de activiteit Uitsluiting bevat alleen de leden van de primaire set die niet in de andere binnenkomende overgangen zijn aangetroffen.

## Configuratie {#configuration}

1. Sleep een activiteit **[!UICONTROL Exclusion]** en zet deze neer in uw workflow.
1. Selecteer de activiteit en open deze met de knop ![](assets/edit_darkgrey-24px.png) vanuit de snelle acties die verschijnen.
1. Selecteer de **[!UICONTROL Primary set]** in de binnenkomende overgangen. Dit is de set waaruit elementen worden uitgesloten. De andere sets komen overeen met de elementen voordat deze worden uitgesloten van de primaire set.

   >[!NOTE]
   >
   >De binnenkomende overgangen moeten hetzelfde type populatie bevatten. Als de primaire set bijvoorbeeld testprofielen bevat, moeten de andere overgangen ook testprofielen bevatten.

1. Indien nodig beheert u de [Overgangen](../../automating/using/activity-properties.md) van de activiteit om toegang te krijgen tot de geavanceerde opties voor de uitgaande populatie.
1. Bevestig de configuratie van uw activiteit en sla de workflow op.

## Voorbeeld {#example}

In het volgende voorbeeld worden twee queryactiviteiten getoond die zijn geconfigureerd om profielen te filteren uit de Adobe Campaign-database die tussen de 18 en 27 jaar oud zijn en een ongeldig e-mailadres hebben. De profielen met ongeldige e-mailadressen worden dan uitgesloten van de eerste set. Zo kunt u bijvoorbeeld een e-mail verzenden.

![](assets/wkf_exclusion_example.png)

