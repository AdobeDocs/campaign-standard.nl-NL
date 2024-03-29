---
title: De activiteit Planner
description: Met de activiteit Planner kunt u plannen wanneer een workflow of activiteit wordt gestart.
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: schedule,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 39f7b216-b3cd-4aa6-b5df-23e6805076df
source-git-commit: 6107f5e43b25037f7f5a7f130922a3a22d0047af
workflow-type: tm+mt
source-wordcount: '877'
ht-degree: 52%

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

Wanneer u een geplande workflow ontwerpt die meerdere activiteiten bevat, moet u ervoor zorgen dat de workflow niet opnieuw wordt gepland totdat deze is voltooid. Hiervoor moet u uw workflow configureren om te voorkomen dat deze wordt uitgevoerd als een of meer taken uit een eerdere uitvoering nog in behandeling zijn. Raadpleeg [deze pagina](../../automating/using/scheduled-workflows-execution.md) voor meer informatie.

**Verwante onderwerpen:**

* [Hoofdlettergebruik: leveringen maken op de aanmaakdatum van profielen](../../automating/using/workflow-creation-date-query.md)
* [Hoofdlettergebruik: elke dinsdag een e-maillevering maken](../../automating/using/workflow-weekly-offer.md)

## Configuratie {#configuration}

1. Sleep een activiteit **[!UICONTROL Scheduler]** en zet deze neer in uw workflow.
1. Selecteer de activiteit en open deze met de knop ![](assets/edit_darkgrey-24px.png) vanuit de snelle acties die verschijnen.
1. Geef het volgend op **[!UICONTROL Execution frequency]**:

   * **[!UICONTROL Once]**: de workflow wordt één keer uitgevoerd.
   * **[!UICONTROL Several times a day]**: de workflow wordt regelmatig meerdere keren per dag uitgevoerd.
   * **[!UICONTROL Daily]**: de workflow wordt eenmaal per dag op een specifiek tijdstip uitgevoerd.
   * **[!UICONTROL Weekly]**: de workflow wordt op een specifiek moment uitgevoerd, één keer of meerdere keren per week.
   * **[!UICONTROL Monthly]**: de workflow wordt op een specifiek moment uitgevoerd, één keer of meerdere keren per maand. U kunt aangeven in welke maanden u de workflow wilt uitvoeren. U kunt uitvoeringen ook instellen op de opgegeven weekdag van de maand, zoals de tweede dinsdag van de maand.
   * **[!UICONTROL Yearly]**: de workflow wordt op een specifiek moment uitgevoerd, één keer of meerdere keren per jaar.

1. Configureer de uitvoeringsinstellingen naar wens. Welke opties beschikbaar zijn, is afhankelijk van de geselecteerde uitvoerfrequentie (uitvoeringstijd of -dagen, herhalingsfrequentie, enz.).

   >[!NOTE]
   >
   >De **[!UICONTROL Repetition frequency]** in het veld voor de uitvoeringsfrequenties Dagelijks en Maandelijks kunt u de tijd vrijmaken waarop de workflow wordt geactiveerd. Als u bijvoorbeeld een dagelijkse uitvoeringsperiode selecteert en de herhalingsfrequentie is ingesteld op **2** (dagen), dan wordt de workflow elke twee dagen geactiveerd. De tussenliggende periode mag niet minder dan 10 minuten zijn. Als de herhalingsfrequentie is ingesteld op **0** (ook de standaardwaarde), wordt deze optie niet in aanmerking genomen en de workflow wordt uitgevoerd volgens de opgegeven uitvoeringsfrequentie.

   Wanneer u de uitvoeringsfrequentie instelt op **[!UICONTROL Several times a day]** hebt u de flexibiliteit om te kiezen tussen het uitvoeren van de workflow op specifieke tijdstippen van de dag of periodiek gedurende de dag.

+++ Leer hoe u een **[!UICONTROL "Several times a day"]** uitvoeringsfrequentie

   * Als u de workflow meerdere keren op bepaalde tijdstippen gedurende de dag wilt uitvoeren, schakelt u het **[!UICONTROL Specific times]** en klik vervolgens op **[!UICONTROL Add an element]** om de gewenste uitvoeringstijd op te geven. Voeg zo vaak als nodig is toe om aan uw vereisten te voldoen.

   * Als u de workflow gedurende de hele dag periodiek wilt uitvoeren, schakelt u het **[!UICONTROL Periodic]** en configureert u vervolgens de uitvoeringsfrequentie:

      1. In de **[!UICONTROL Repeat processing according to the following frequency (e.g. 2h)]** , geeft u het interval op waarmee de workflow moet worden uitgevoerd (bijvoorbeeld om de 30 minuten, om de 2 uur).

         >[!NOTE]
         >
         >Deze optie maakt het ook mogelijk dagelijkse, maandelijkse of jaarlijkse herhalingsfrequenties toe te passen. In dit geval wordt de workflow niet meerdere keren per dag uitgevoerd, maar volgens de frequentie die u in dit veld hebt opgegeven.
         >
         > Als u voor uw workflow geen meerdere uitvoeringen binnen een dag nodig hebt, maar deze in plaats daarvan dagelijks, maandelijks of jaarlijks moet uitvoeren, is het raadzaam de opdracht **[!UICONTROL Daily]**, **[!UICONTROL Monthly]** of **[!UICONTROL Yearly]** opties beschikbaar in het dialoogvenster **[!UICONTROL Execution frequency]** vervolgkeuzelijst.

      1. In de **[!UICONTROL Start]**/**[!UICONTROL End]** tijdvelden, definieert het tijdstip waarop de werkstroom moet worden gestart en beëindigd.

         Als geen eindtijd wordt gespecificeerd, eindigt de uitvoering bij middernacht 00:00:00 uur, en de volgende uitvoering begint de volgende dag bij de gespecificeerde begintijd.

      1. In de **[!UICONTROL Start]** datumveld, selecteert u de datum waarop de eerste uitvoering moet beginnen.

   In het onderstaande voorbeeld wordt de activiteit geconfigureerd om de workflow elke 2 uur tussen 8.00 uur en 5.00 uur uit te voeren, te beginnen op 1 maart.

   ![](assets/wkf_scheduler_day.png)

+++

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

