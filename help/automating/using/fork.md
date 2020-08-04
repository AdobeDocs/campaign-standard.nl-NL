---
title: Vertakking
description: Met de activiteit Vertakking kunt u uitgaande overgangen maken om verschillende activiteiten tegelijk te starten.
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
translation-type: ht
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e
workflow-type: ht
source-wordcount: '210'
ht-degree: 100%

---


# Vertakking{#fork}

## Beschrijving {#description}

![](assets/fork.png)

Met de activiteit **[!UICONTROL Fork]** kunt u uitgaande overgangen maken om verschillende activiteiten tegelijk te starten.

## Gebruikscontext {#context-of-use}

Met de activiteit **[!UICONTROL Fork]** kunt u verschillende activiteiten onafhankelijk van elkaar uitvoeren binnen dezelfde workflow.

## Configuratie {#configuration}

1. Sleep een activiteit **[!UICONTROL Fork]** en zet deze neer in uw workflow.
1. Verbind de activiteit met de andere activiteiten die eraan voorafgaan, zoals query’s.
1. Selecteer de activiteit en open deze met de knop ![](assets/edit_darkgrey-24px.png) vanuit de snelle acties die verschijnen.
1. Geef het aantal uitgaande overgangen op door deze te maken, te verwijderen of te dupliceren. U kunt ook een naam en een label aan de overgangen toewijzen.
1. Bevestig de configuratie van uw activiteit en sla de workflow op.

## Voorbeeld {#example}

In het volgende voorbeeld ziet u een doorsnede van twee queryactiviteiten die zich richten op profielen uit de Adobe Campaign-database, in dit geval vrouwen die in Parijs wonen. Met de activiteit Vertakking kunt u dus verschillende activiteiten tegelijk gebruiken: één activiteit die de doelgroep opslaat om de berekende populatie bij te houden, en een andere activiteit die de populatie segmenteert om twee verschillende e-mails met getargete content voor elk segment te verzenden. De eerste e-mail wordt verzonden naar Parijse vrouwen in de leeftijd tussen 18 en 40 jaar en een andere e-mail wordt verzonden naar Parijse vrouwen die ouder zijn dan 40 jaar.

![](assets/wkf_fork_example.png)

