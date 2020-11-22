---
solution: Campaign Standard
product: campaign
title: De activiteit Planner
description: Met de activiteit Planner kunt u plannen wanneer een workflow of activiteit wordt gestart.
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: schedule,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '555'
ht-degree: 97%

---


# Planner{#scheduler}

## Beschrijving {#description}

![](assets/scheduler.png)

Met de **[!UICONTROL Scheduler]**-activiteit kunt u plannen wanneer een workflow of activiteit wordt gestart.

## Gebruikscontext {#context-of-use}

De **[!UICONTROL Scheduler]**-activiteit kan dus worden beschouwd als een geplande start. De regels voor het positioneren van de activiteit in het diagram zijn hetzelfde als voor de **[!UICONTROL Start]**-activiteit. Deze activiteit mag geen binnenkomende overgang hebben.

Wanneer u een workflow samenstelt, kunt u slechts één **[!UICONTROL Scheduler]**-activiteit per tak gebruiken. Vergeet niet om een tijdzone in te stellen. Hierdoor kunt u uw workflow in een specifieke tijdzone starten, anders wordt de workflow uitgevoerd in de tijdzone die is gedefinieerd in de workfloweigenschappen (zie [Een workflow maken](../../automating/using/building-a-workflow.md)).

>[!CAUTION]
>
>De **[!UICONTROL Repetition frequency]** van de activiteit mag niet minder dan 10 minuten duren. Dit betekent dat een workflow niet automatisch meer dan eenmaal per 10 minuten kan worden uitgevoerd.

**Verwante onderwerpen:**

* [Hoofdlettergebruik: Leveringen maken op de aanmaakdatum van profielen](../../automating/using/workflow-creation-date-query.md)
* [Hoofdlettergebruik: Elke dinsdag een e-maillevering maken](../../automating/using/workflow-weekly-offer.md)

## Configuratie {#configuration}

1. Sleep een activiteit **[!UICONTROL Scheduler]** en zet deze neer in uw workflow.
1. Selecteer de activiteit en open deze met de knop ![](assets/edit_darkgrey-24px.png) vanuit de snelle acties die verschijnen.
1. Geef het volgend op **[!UICONTROL Execution frequency]**:

   * **[!UICONTROL Once]**: de workflow wordt één keer uitgevoerd.
   * **[!UICONTROL Several times a day]**: de workflow wordt regelmatig en meerdere keren per dag uitgevoerd. U kunt uitvoeringen instellen op specifieke tijdstippen of periodiek.
   * **[!UICONTROL Daily]**: de workflow wordt eenmaal per dag op een specifiek tijdstip uitgevoerd.
   * **[!UICONTROL Weekly]**: de workflow wordt op een specifiek moment uitgevoerd, één keer of meerdere keren per week.
   * **[!UICONTROL Monthly]**: de workflow wordt op een specifiek moment uitgevoerd, één keer of meerdere keren per maand. U kunt aangeven in welke maanden u de workflow wilt uitvoeren. U kunt uitvoeringen ook instellen op de opgegeven weekdag van de maand, zoals de tweede dinsdag van de maand.
   * **[!UICONTROL Yearly]**: de workflow wordt op een specifiek moment uitgevoerd, één keer of meerdere keren per jaar.

1. Definieer de details van de uitvoering op basis van de geselecteerde frequentie. De detailvelden variëren, afhankelijk van de gebruikte frequentie (tijd, herhalingsfrequentie, opgegeven dagen, enz.).

   >[!NOTE]
   >
   >In het veld **[!UICONTROL Repetition frequency]** kunt u de tijdstippen waarop de workflow wordt geactiveerd, verder uit elkaar leggen. Als u bijvoorbeeld een dagelijkse uitvoeringsperiode selecteert en de herhalingsfrequentie is ingesteld op **2** (dagen), dan wordt de workflow elke twee dagen geactiveerd. De tussenliggende periode mag niet minder dan 10 minuten zijn. Als de herhalingsfrequentie is ingesteld op **0** (de standaardwaarde), wordt deze optie niet in aanmerking genomen en wordt de workflow uitgevoerd volgens de opgegeven uitvoeringsfrequentie.

1. Geef aan wanneer de uitvoering verloopt:

   * **[!UICONTROL Never]**: de workflow wordt uitgevoerd volgens de opgegeven frequentie, zonder beperkingen voor het tijdsbestek of het aantal herhalingen.
   * **[!UICONTROL After a certain number of iterations]**: de workflow wordt uitgevoerd volgens de opgegeven frequentie, tot de limiet van **X** is bereikt. **[!UICONTROL Number of iterations]** zal dus nader moeten worden omschreven.
   * **[!UICONTROL On a specific date]**: de workflow wordt uitgevoerd volgens de opgegeven frequentie, tot een bepaalde datum. Hierbij moet dus de uitvoeringstermijn worden vastgesteld.

1. Controleer het schema voor de volgende tien uitvoeringen van de workflow door te klikken op **[!UICONTROL Preview next executions]**.

1. Op het tabblad **[!UICONTROL Execution options]** kunt u de tijdzone voor uw planner instellen in het veld **[!UICONTROL Time zone]**.

   Meer informatie over het instellen van leveringen op basis van de tijdzone van de ontvanger, vindt u in deze [sectie](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md) of in dit [voorbeeld](../../automating/using/recurring-push-notifications.md) van een terugkerende workflow.

1. Bevestig de configuratie van uw activiteit en sla de workflow op.

## Voorbeeld {#example}

In het volgende voorbeeld is de activiteit zo geconfigureerd dat de workflow wekelijks wordt gestart, elke maandag om 7 uur &#39;s ochtends, voor een onbepaalde duur.

![](assets/wkf_scheduler_example.png)

