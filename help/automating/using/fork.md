---
title: Vork
description: Met de vorkactiviteit kunt u uitgaande overgangen maken om meerdere activiteiten tegelijk te starten.
page-status-flag: never-activated
uuid: e4eaf69b-84ee-4f79-8b80-99284697cd2c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: f8ffe7af-e18c-4599-8fd0-fcd192565323
context-tags: fork,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Vork{#fork}

## Beschrijving {#description}

![](assets/fork.png)

De **[!UICONTROL Fork]** activiteit staat u toe om uitgaande overgangen tot stand te brengen om verscheidene activiteiten tezelfdertijd te beginnen.

## Gebruikscontext {#context-of-use}

Met deze **[!UICONTROL Fork]** activiteit kunt u verschillende activiteiten onafhankelijk binnen dezelfde workflow uitvoeren.

## Configuratie {#configuration}

1. Sleep een **[!UICONTROL Fork]** activiteit naar uw werkstroom.
1. Sluit het aan de andere activiteiten aan die voor het komen, zoals vragen.
1. Selecteer de activiteit, dan open het gebruikend de ![](assets/edit_darkgrey-24px.png) knoop van de snelle acties die verschijnen.
1. Geef het aantal uitgaande overgangen op door deze te maken, te verwijderen of te dupliceren. U kunt er ook een naam en een label aan toewijzen.
1. Bevestig de configuratie van uw activiteit en sla uw werkschema op.

## Voorbeeld {#example}

In het volgende voorbeeld ziet u een doorsnede van twee query-activiteiten die zich richten op profielen uit de Adobe Campaign-database, in dit geval vrouwen die in Parijs wonen. Met de vorkactiviteit kunt u dus verschillende activiteiten tegelijk gebruiken: één die het publiek bespaart om de berekende bevolking te herinneren, en een andere die de bevolking segmenteert om twee verschillende e-mails met een gerichte inhoud voor elk segment te verzenden. De eerste e-mail wordt gestuurd naar vrouwen in de leeftijd tussen 18 en 40 jaar die in de leeftijd van 19 jaar zijn, en een andere e-mail naar vrouwen in de leeftijd van 40 jaar.

![](assets/wkf_fork_example.png)

