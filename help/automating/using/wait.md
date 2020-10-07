---
title: De activiteit Wachten
description: Met de activiteit Wachten wordt de uitvoering van een deel van de workflow tijdelijk opgeschort.
page-status-flag: never-activated
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: wait,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 100%

---


# Wait{#wait}

## Beschrijving {#description}

![](assets/wait.png)

Met de activiteit **[!UICONTROL Wait]** wordt de uitvoering van een deel van de workflow tijdelijk opgeschort. De uitgaande overgang wordt na een vertraging (van een paar seconden tot meerdere maanden) weer geactiveerd, zodat de later geplaatste activiteiten worden uitgevoerd.

## Gebruikscontext {#context-of-use}

Met de activiteit **[!UICONTROL Wait]** kunt u een bepaalde tijd instellen tussen twee activiteiten die worden uitgevoerd. Bijvoorbeeld als u een aantal dagen wilt wachten na een e-mailleveringsactiviteit om het aantal open- en klikacties tijdens die periode te analyseren voordat u follow-upbewerkingen gaat uitvoeren (herinneringsmail, doelgroep maken, enz.).

## Configuratie {#configuration}

1. Sleep een activiteit **[!UICONTROL Wait]** en zet deze neer in uw workflow.
1. Selecteer de activiteit en open deze met de knop ![](assets/edit_darkgrey-24px.png) vanuit de snelle acties die verschijnen.
1. Specificeer de **[!UICONTROL Duration]** van de wachttijd tussen het tijdstip waarop de binnenkomende en uitgaande overgangen van de activiteit worden geactiveerd.

   U kunt de tijdsduur handmatig of met de selectietool in het veld invoeren.

   ![](assets/wait_duration.png)

1. Bevestig de configuratie van uw activiteit en sla de workflow op.

## Voorbeeld {#example}

Het volgende voorbeeld illustreert de activiteit **[!UICONTROL Wait]** in een typisch gebruiksscenario. U stuurt een e-mailuitnodiging voor een evenement. Na 24 uur analyseert u de logboeken voor e-maillevering en stuurt u een herinneringsbericht naar iedereen die het eerste e-mailbericht wel heeft ontvangen maar zich niet heeft aangemeld.

De workflow wordt als volgt weergegeven:

![](assets/wait_example_workflow.png)

* Een eerste **[!UICONTROL Query]** is gericht op de profielen waarnaar de e-mailuitnodiging wordt verzonden.
* Een **[!UICONTROL Email delivery]** verzendt de uitnodiging voor de eerste keer naar de geselecteerde profielen.
* Een **[!UICONTROL Wait]**-activiteit van 24 uur plaatst een pauze tussen het tijdstip waarop de uitnodiging is verzonden en de rest van de workflow.
* Een tweede **[!UICONTROL Query]** is gericht op de profielen die het eerste e-mailbericht wel hebben ontvangen, maar niet op de koppeling met de uitnodiging hebben geklikt.
* Een tweede **[!UICONTROL Email delivery]** stuurt een herinnering naar de geselecteerde personen.

