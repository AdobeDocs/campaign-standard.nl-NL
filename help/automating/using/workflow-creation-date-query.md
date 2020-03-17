---
title: '"Gebruiksscenario voor workflow: Leveringen maken op de aanmaakdatum van het profiel"'
description: '"Gebruiksscenario voor workflow: Leveringen maken op de aanmaakdatum van het profiel"'
page-status-flag: never-activated
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: workflow,use-case,query
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: accc382ca1543d648e60d53cab338537fd9ea3ef

---


# Gebruiksscenario voor werkstroom: Leveringen maken op de aanmaakdatum van profielen {#creation-date-query}

U kunt een voorstel via e-mail verzenden op de verjaardag van het maken van het profiel van de klant.

1. Klik in **[!UICONTROL Marketing Activities]** en selecteer **[!UICONTROL Create]** de optie **[!UICONTROL Workflow]**.
1. Selecteer **[!UICONTROL New Workflow]** als workflowtype en klik op **[!UICONTROL Next]**.
1. Voer de eigenschappen van de workflow in en klik op **[!UICONTROL Create]**.

## Een planningsactiviteit maken {#creating-a-scheduler-activity}

1. In **[!UICONTROL Activities]** > **[!UICONTROL Execution]**, sleep en laat vallen een **[!UICONTROL Scheduler activity]**.
1. Dubbelklik op de activiteit.
1. Configureer de uitvoering van uw levering.
1. In **[!UICONTROL Execution frequency]** selecteert u **[!UICONTROL Daily]**.
1. Selecteer een **[!UICONTROL Time]** en de manier **[!UICONTROL Repetition frequency]** van uitvoering voor uw workflow.
1. Selecteer een **[!UICONTROL Start]** datum en **[!UICONTROL Expiration]** voor uw workflow.
1. Bevestig uw activiteit en sla uw werkschema op.

>[!NOTE]
>
>Om uw werkschema bij een specifieke tijdzone, op het **[!UICONTROL Execution options]** lusje te beginnen, opstelling de tijdzone voor uw planner op het **[!UICONTROL Time zone]** gebied. Standaard is de geselecteerde tijdzone de tijdzone die is gedefinieerd in de workfloweigenschappen (zie [Een workflow](../../automating/using/building-a-workflow.md)maken).

![](assets/time_zone.png)

## Query-activiteiten maken {#creating-a-query-activity}

1. Als u ontvangers wilt selecteren, sleept u een ontvanger **[!UICONTROL Query activity]** en dubbelklikt u erop.
1. Voeg toe **[!UICONTROL Profiles]** en selecteer **[!UICONTROL no longer contact by email]** met de waarde **[!UICONTROL no]**.

### Profielen ophalen die zijn gemaakt op dezelfde dag als de dag van uitvoering {#retriving-profiles-created-on-the-same-day}

1. Sleep **[!UICONTROL Profile]** het **[!UICONTROL Created]** veld in. en klik op **[!UICONTROL Advanced Mode]**.
   ![](assets/advanced_mode.png)
1. Dubbelklik in het **[!UICONTROL list of functions]** deelvenster op **[!UICONTROL Day]** het **[!UICONTROL Date]** knooppunt.
1. Voeg vervolgens het veld in **[!UICONTROL Created]** als argument.
1. Selecteren **[!UICONTROL equals to (=)]** als operator.
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

1. Sleep een e-maillevering en zet deze neer.
1. Klik op de activiteit en selecteer deze ![](assets/edit_darkgrey-24px.png) om te bewerken.
1. Selecteer **[!UICONTROL Recurring email]** en klik op **[!UICONTROL Next]**.
1. Selecteer een e-mailsjabloon en klik op **[!UICONTROL Next]**.
1. Voer de e-maileigenschappen in en klik op **[!UICONTROL Next]**.
1. Klik op om de lay-out van uw e-mail te maken **[!UICONTROL Email Designer]**.
1. Voeg elementen in of selecteer een bestaande sjabloon.
1. Pas uw e-mail aan met behulp van velden en koppelingen.
Raadpleeg voor meer informatie het [ontwerpen van een e-mail](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).
1. Klik **[!UICONTROL Preview]** om uw lay-out te controleren.
1. Klik op **[!UICONTROL Save]**.

**Verwante onderwerpen:**

* [Query](../../automating/using/query.md)
* [Planner](../../automating/using/scheduler.md)
* [E-maillevering](../../automating/using/email-delivery.md)
* [E-mailkanaal](../../channels/using/creating-an-email.md)
