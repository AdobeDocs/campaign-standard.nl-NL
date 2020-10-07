---
title: Leveringen maken op de aanmaakdatum van het profiel
description: In dit geval kunt u zien hoe u leveringen maakt op de aanmaakdatum van het profiel.
page-status-flag: never-activated
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: workflow,use-case,query
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 38%

---


# Leveringen maken op de aanmaakdatum van profielen {#creation-date-query}

U kunt een voorstel via e-mail verzenden op de verjaardag van het maken van het profiel van de klant.

1. Klik in **[!UICONTROL Marketing Activities]** op **[!UICONTROL Create]** en selecteer **[!UICONTROL Workflow]**.
1. Selecteer **[!UICONTROL New Workflow]** als workflowtype en klik op **[!UICONTROL Next]**.
1. Voer de eigenschappen van de workflow in en klik op **[!UICONTROL Create]**.

## Een activiteit Planner maken {#creating-a-scheduler-activity}

1. In **[!UICONTROL Activities]** > **[!UICONTROL Execution]**, drag and drop a [Scheduler](../../automating/using/scheduler.md) activity.
1. Dubbelklik op de activiteit.
1. Configureer de uitvoering van uw levering.
1. In **[!UICONTROL Execution frequency]** selecteert u **[!UICONTROL Daily]**.
1. Selecteer een **[!UICONTROL Time]** en de manier **[!UICONTROL Repetition frequency]** van uitvoering voor uw workflow.
1. Selecteer een **[!UICONTROL Start]** datum en **[!UICONTROL Expiration]** voor uw workflow.
1. Bevestig uw activiteit en sla de workflow op.

>[!NOTE]
>
>To start your workflow at a specific time zone, in the **[!UICONTROL Execution options]** tab, set up the time zone for your scheduler in the **[!UICONTROL Time zone]** field. Standaard is de geselecteerde tijdzone de tijdzone die is gedefinieerd in de workfloweigenschappen (zie [Een workflow maken](../../automating/using/building-a-workflow.md)).

![](assets/time_zone.png)

## Een queryactiviteit maken {#creating-a-query-activity}

1. To select recipients, drag and drop a [Query](../../automating/using/query.md) activity and double-click it.
1. Voeg toe **[!UICONTROL Profiles]** en selecteer **[!UICONTROL no longer contact by email]** met de waarde **[!UICONTROL no]**.

### Profielen ophalen die zijn gemaakt op dezelfde dag als de dag van uitvoering {#retriving-profiles-created-on-the-same-day}

1. Sleep **[!UICONTROL Profile]** het **[!UICONTROL Created]** veld in. en klik op **[!UICONTROL Advanced Mode]**.
   ![](assets/advanced_mode.png)
1. Dubbelklik in het **[!UICONTROL list of functions]** deelvenster op **[!UICONTROL Day]** het **[!UICONTROL Date]** knooppunt.
1. Voeg vervolgens het veld in **[!UICONTROL Created]** als argument.
1. Select **[!UICONTROL equals to (=)]** as the operator.
1. Selecteer bij Waarde de optie **[!UICONTROL Day]** in het **[!UICONTROL Date]** knooppunt **[!UICONTROL List of functions]**.
1. Voeg de **[!UICONTROL GetDate()]** functie in als argument.

U hebt de profielen opgehaald die op de aanmaakdag gelijk zijn aan de huidige dag.

U zou moeten eindigen met:

```Day(@created) = Day(GetDate())```

![](assets/day_creation_query.png)

Klik op **[!UICONTROL Confirm]**.

### Profielen ophalen die zijn gemaakt op dezelfde maand als de maand van uitvoering{#retriving-profiles-created-on-the-same-month}

1. Selecteer in de **[!UICONTROL Query]** editor de eerste query en dupliceer deze.
1. Open het duplicaat.
1. Vervangen **[!UICONTROL Day]** door **[!UICONTROL Month]** in de query.
1. Klik op **[!UICONTROL Confirm]**.

![](assets/month_rule.png)

U zou met dit moeten eindigen:

``` Month(@created) = Month(GetDate()) ```

De uiteindelijke query wordt weergegeven:

```Day(@created) = Day(GetDate()) AND Month(@created) = Month(GetDate())```

![](assets/expression_editor_1.png)

## Een e-maillevering maken{#creating-an-email-delivery}

1. Sleep een [e-mailleveringsactiviteit](../../automating/using/email-delivery.md) en zet deze neer.
1. Klik op de activiteit en selecteer ![](assets/edit_darkgrey-24px.png) om te bewerken.
1. Selecteer **[!UICONTROL Recurring email]** en klik op **[!UICONTROL Next]**.
1. Selecteer een e-mailsjabloon en klik op **[!UICONTROL Next]**.
1. Voer de e-maileigenschappen in en klik op **[!UICONTROL Next]**.
1. Klik op **[!UICONTROL Email Designer]** om de lay-out van uw e-mail te bepalen.
1. Voeg elementen in of selecteer een bestaande sjabloon.
1. Personaliseer uw e-mail met velden en koppelingen.
Zie [Een e-mail ontwerpen](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch) voor meer informatie.
1. Klik op **[!UICONTROL Preview]** om uw lay-out te controleren.
1. Klik op **[!UICONTROL Save]**.

**Verwante onderwerpen:**

* [E-mailkanaal](../../channels/using/creating-an-email.md)
