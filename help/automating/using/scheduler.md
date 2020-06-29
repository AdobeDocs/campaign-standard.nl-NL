---
title: Planner
description: De activiteit van de Planner staat u toe om te plannen wanneer een werkschema of een activiteit is begonnen.
page-status-flag: never-activated
uuid: f5e50a11-8dc9-4d98-9531-024c0fb3f7da
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 0fb16cea-3941-404f-899c-33f81ced4ed5
context-tags: schedule,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2d994d85f126951215f1227301599c554c1f12c8
workflow-type: tm+mt
source-wordcount: '555'
ht-degree: 0%

---


# Planner{#scheduler}

## Beschrijving {#description}

![](assets/scheduler.png)

De **[!UICONTROL Scheduler]** activiteit staat u toe om te plannen wanneer een werkschema of een activiteit wordt begonnen.

## Gebruikscontext {#context-of-use}

De **[!UICONTROL Scheduler]** activiteit moet worden beschouwd als een geplande start. De regels voor het positioneren van de activiteit in het diagram zijn hetzelfde als voor de **[!UICONTROL Start]** activiteit. Deze activiteit moet geen binnenkomende overgang hebben.

Wanneer het bouwen van uw werkschema, gebruik slechts één **[!UICONTROL Scheduler]** activiteit per tak en herinner me om een tijdzone te plaatsen. Hierdoor kunt u uw workflow op een specifieke tijdzone starten, anders wordt de workflow uitgevoerd in de tijdzone die is gedefinieerd in de workfloweigenschappen (zie [Een workflow](../../automating/using/building-a-workflow.md)maken).

>[!CAUTION]
>
>De activiteit **[!UICONTROL Repetition frequency]** mag niet minder dan 10 minuten duren. Dit betekent dat een workflow niet automatisch meer dan eenmaal per 10 minuten kan worden uitgevoerd.

**Verwante onderwerpen:**

* [Hoofdlettergebruik: Leveringen maken op de aanmaakdatum van profielen](../../automating/using/workflow-creation-date-query.md)
* [Hoofdlettergebruik: Elke dinsdag een e-maillevering maken](../../automating/using/workflow-weekly-offer.md)

## Configuratie {#configuration}

1. Sleep een **[!UICONTROL Scheduler]** activiteit naar uw werkstroom.
1. Selecteer de activiteit, dan open het gebruikend de ![](assets/edit_darkgrey-24px.png) knoop van de snelle acties die verschijnen.
1. Geef de **[!UICONTROL Execution frequency]** volgende instellingen op:

   * **[!UICONTROL Once]**: de workflow wordt één keer uitgevoerd.
   * **[!UICONTROL Several times a day]**: de workflow wordt regelmatig verscheidene keren per dag uitgevoerd . U kunt uitvoeringen instellen op specifieke tijdstippen of periodiek.
   * **[!UICONTROL Daily]**: de workflow wordt op een bepaald tijdstip, eenmaal per dag, uitgevoerd.
   * **[!UICONTROL Weekly]**: de workflow wordt op een bepaald moment, één keer of meerdere keren per week uitgevoerd.
   * **[!UICONTROL Monthly]**: de workflow wordt op een bepaald moment, één keer of meerdere keren per maand uitgevoerd. U kunt maanden selecteren wanneer u de workflow moet uitvoeren. U kunt uitvoeringen ook instellen op de opgegeven weekdag van de maand, zoals de tweede dinsdag van de maand.
   * **[!UICONTROL Yearly]**: de workflow wordt op een bepaald moment, één keer of meerdere keren per jaar uitgevoerd.

1. Definieer de details van de uitvoering op basis van de geselecteerde frequentie. De detailvelden kunnen variëren afhankelijk van de gebruikte frequentie (tijd, herhalingsfrequentie, opgegeven dagen, enz.).

   >[!NOTE]
   >
   >In het **[!UICONTROL Repetition frequency]** veld kunt u de tijd vrijmaken waarop de workflow wordt geactiveerd. Als u bijvoorbeeld een dagelijkse uitvoeringsperiode selecteert en de herhalingsfrequentie is ingesteld op **2** (dagen), wordt de workflow elke twee dagen geactiveerd. Het mag niet minder dan 10 minuten zijn. Als de herhalingsfrequentie is ingesteld op **0** (ook de standaardwaarde), wordt deze optie niet in aanmerking genomen en wordt de workflow uitgevoerd volgens de opgegeven uitvoeringsfrequentie.

1. Geef op wanneer de uitvoering verloopt:

   * **[!UICONTROL Never]**: de werkstroom zal worden uitgevoerd volgens de opgegeven frequentie, zonder beperkingen aan het tijdsbestek of het aantal herhalingen.
   * **[!UICONTROL After a certain number of iterations]**: de workflow wordt uitgevoerd volgens de opgegeven frequentie, tot de limiet van **X** is bereikt. Het **[!UICONTROL Number of iterations]** zal dus nader moeten worden omschreven.
   * **[!UICONTROL On a specific date]**: de werkstroom zal worden uitgevoerd volgens de opgegeven frequentie, tot een bepaalde datum. Daarom moet de uitvoeringstermijn worden vastgesteld.

1. Controleer het schema van de volgende tien uitvoeringen van uw werkschema door te klikken **[!UICONTROL Preview next executions]**.

1. In het **[!UICONTROL Execution options]** lusje, opstelling de tijdzone voor uw planner op het **[!UICONTROL Time zone]** gebied.

   Voor meer informatie bij het verzenden van levering afhankelijk van de tijdzone van de ontvanger, verwijs naar deze [sectie](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md) of dit [voorbeeld](../../automating/using/recurring-push-notifications.md) van een terugkomende werkschema.

1. Bevestig de configuratie van uw activiteit en sla uw werkschema op.

## Voorbeeld {#example}

In het volgende voorbeeld is de activiteit zo geconfigureerd dat deze de workflow wekelijks start, elke andere maandag om 7 uur &#39;s nachts, voor een onbepaalde duur.

![](assets/wkf_scheduler_example.png)

