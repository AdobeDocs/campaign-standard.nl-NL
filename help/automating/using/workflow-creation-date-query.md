---
title: Leveringen maken op de aanmaakdatum van het profiel
description: In dit geval kunt u zien hoe u leveringen maakt op de aanmaakdatum van het profiel.
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: workflow,use-case,query
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: f611e023-f74c-476e-83b9-aff451f68c81
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 32%

---

# Leveringen maken op de maakdatum van profielen {#creation-date-query}

U kunt een voorstel via e-mail verzenden op de dag dat de klant het profiel heeft gemaakt.

1. Klik in **[!UICONTROL Marketing Activities]** op **[!UICONTROL Create]** en selecteer **[!UICONTROL Workflow]**.
1. Selecteer **[!UICONTROL New Workflow]** als workflowtype en klik op **[!UICONTROL Next]**.
1. Voer de eigenschappen van de workflow in en klik op **[!UICONTROL Create]**.

## Een planningsactiviteit maken {#creating-a-scheduler-activity}

1. In **[!UICONTROL Activities]** > **[!UICONTROL Execution]**, een [Planner](../../automating/using/scheduler.md) activiteit.
1. Dubbelklik op de activiteit.
1. Configureer de uitvoering van uw levering.
1. In **[!UICONTROL Execution frequency]** selecteert u **[!UICONTROL Daily]**.
1. Selecteer een **[!UICONTROL Time]** en de **[!UICONTROL Repetition frequency]** van uitvoering voor uw workflow.
1. Selecteer een **[!UICONTROL Start]** datum en **[!UICONTROL Expiration]** voor uw workflow.
1. Bevestig uw activiteit en sla de workflow op.

>[!NOTE]
>
>Om uw werkschema bij een specifieke tijdzone te beginnen, in **[!UICONTROL Execution options]** lusje, opstelling de tijdzone voor uw planner in **[!UICONTROL Time zone]** veld. Standaard is de geselecteerde tijdzone de tijdzone die is gedefinieerd in de workfloweigenschappen (zie [Een workflow maken](../../automating/using/building-a-workflow.md)).

![](assets/time_zone.png)

## Query-activiteiten maken {#creating-a-query-activity}

1. Als u ontvangers wilt selecteren, sleept u een [Query](../../automating/using/query.md) en dubbelklik erop.
1. Toevoegen **[!UICONTROL Profiles]** en selecteert u **[!UICONTROL no longer contact by email]** met de waarde **[!UICONTROL no]**.

### Profielen ophalen die zijn gemaakt op dezelfde dag als de dag van uitvoering {#retrieving-profiles-created-on-the-same-day}

1. In **[!UICONTROL Profile]**, slepen en neerzetten **[!UICONTROL Created]** veld. en klik op **[!UICONTROL Advanced Mode]**.
   ![](assets/advanced_mode.png)
1. In de **[!UICONTROL list of functions]**, dubbelklikken **[!UICONTROL Day]** van de **[!UICONTROL Date]** knooppunt.
1. Voeg vervolgens het veld in **[!UICONTROL Created]** als argument.
1. Selecteren **[!UICONTROL equals to (=)]** als de operator.
1. Selecteer bij Waarde **[!UICONTROL Day]** van de **[!UICONTROL Date]** knooppunt in de **[!UICONTROL List of functions]**.
1. Voeg de **[!UICONTROL GetDate()]** functie als argument.

U hebt de profielen opgehaald die op de aanmaakdag gelijk zijn aan de huidige dag.

U zou moeten eindigen met:

```Day(@created) = Day(GetDate())```

![](assets/day_creation_query.png)

Klik op **[!UICONTROL Confirm]**.

### Profielen ophalen die zijn gemaakt op dezelfde maand als de maand van uitvoering{#retrieving-profiles-created-on-the-same-month}

1. Op de **[!UICONTROL Query]** editor, selecteert u de eerste query en dupliceert deze.
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

1. Sleep een [E-maillevering](../../automating/using/email-delivery.md) activiteit.
1. Klik op de activiteit en selecteer ![](assets/edit_darkgrey-24px.png) om te bewerken.
1. Selecteer **[!UICONTROL Recurring email]** en klik op **[!UICONTROL Next]**.
1. Selecteer een e-mailsjabloon en klik op **[!UICONTROL Next]**.
1. Voer de e-maileigenschappen in en klik op **[!UICONTROL Next]**.
1. Klik op **[!UICONTROL Email Designer]** om de lay-out van uw e-mail te bepalen.
1. Voeg elementen in of selecteer een bestaande sjabloon.
1. Pas uw e-mail aan met behulp van velden en koppelingen.
Zie [Een e-mail ontwerpen](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch) voor meer informatie.
1. Klik op **[!UICONTROL Preview]** om uw lay-out te controleren.
1. Klik op **[!UICONTROL Save]**.

**Verwante onderwerpen:**

* [Email channel](../../channels/using/creating-an-email.md)
