---
title: '"Gebruiksscenario voor workflow: wekelijkse levering maken"'
description: '"Gebruiksscenario voor workflow: wekelijkse levering maken"'
page-status-flag: never-activated
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: workflow,use-case,query,delivery,scheduler
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: accc382ca1543d648e60d53cab338537fd9ea3ef

---


# Gebruiksscenario voor werkstroom: Elke dinsdag een e-maillevering maken{#creating-email-every-tuesday}

U kunt elke dinsdag een e-mail naar alle klanten sturen voor speciale aanbiedingen.

1. Klik in **[!UICONTROL Marketing Activities]** en selecteer **[!UICONTROL Create]** de optie **[!UICONTROL Workflow]**.
1. Selecteer **[!UICONTROL New Workflow]** als workflowtype en klik op **[!UICONTROL Next]**.
1. Voer eigenschappen van de workflow in en klik op **[!UICONTROL Create]**.

## Een planningsactiviteit maken{#creating-a-scheduler-activity}

1. In **[!UICONTROL Activities]** > **[!UICONTROL Execution]**, sleep en laat vallen een **[!UICONTROL Scheduler activity]**.
1. Dubbelklik op de activiteit.
1. Configureer de uitvoering van uw levering.
1. In **[!UICONTROL Execution frequency]** selecteert u **[!UICONTROL Weekly]**.
1. Selecteer een **[!UICONTROL Time]** en een **[!UICONTROL Repetition frequency]** voor uw leveringen.
1. In **[!UICONTROL Days of the week]** selecteert u **[!UICONTROL Tuesday]**.
1. Geef een **[!UICONTROL Start]** en een **[!UICONTROL Expiration]** parameter voor de workflow op.
1. Bevestig uw activiteit en sla uw werkschema op.

![](assets/scheduler_properties.png)

>[!NOTE]
>
>Om uw werkschema bij een specifiek **[!UICONTROL Time Zone]**, op het **[!UICONTROL Execution options]** lusje te beginnen, opstelling de tijdzone voor uw planner op het gebied van de tijdzone. Standaard is de geselecteerde tijdzone de tijdzone die is gedefinieerd in de workfloweigenschappen (zie [Een workflow](../../automating/using/building-a-workflow.md)maken).

## Query-activiteiten maken{#creating-a-query-activity}

1. Als u in **[!UICONTROL Activities]** > **[!UICONTROL Targeting]** ontvangers wilt selecteren, sleept u een **[!UICONTROL query]** activiteit en dubbelklikt u erop.
1. In **[!UICONTROL Shortcuts]** > **[!UICONTROL Profile]**, belemmering en daling **[!UICONTROL Email]**.
1. Selecteren **[!UICONTROL is not empty]** als een operator.
1. Voeg in **[!UICONTROL Shortcuts]** > **[!UICONTROL General]** profielen toe en selecteer deze **[!UICONTROL no longer contact by email]** met de waarde **[!UICONTROL No]**.
1. Klik op **[!UICONTROL Confirm]**.

![](assets/wf-complement-query.png)

## Een e-maillevering maken{#creating-an-email-delivery}

1. In **[!UICONTROL Activities]** > **[!UICONTROL Channels]**, sleep en laat vallen een **[!UICONTROL Email delivery]**.
1. Klik op de activiteit en selecteer deze ![](assets/edit_darkgrey-24px.png) om te bewerken.
1. Selecteer **[!UICONTROL Recurring email]** en klik op **[!UICONTROL Next]**.
1. Selecteer een e-mailsjabloon en klik op **[!UICONTROL Next]**.
1. Voer de e-maileigenschappen in en klik op **[!UICONTROL Next]**.
1. Klik op om de lay-out van uw e-mail te maken **[!UICONTROL Use Email Designer]**.
1. Voeg elementen in of selecteer een bestaande sjabloon.
1. Pas uw e-mail aan met behulp van velden en koppelingen.
1. Klik op **[!UICONTROL Save]**.

Raadpleeg voor meer informatie het [ontwerpen van een e-mail](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).

**Verwante onderwerpen:**

* [Query-activiteit](../..//automating/using/query.md)
* [Planningsactiviteit](../..//automating/using/scheduler.md)
* [E-maillevering](../..//automating/using/email-delivery.md)
* [E-mailkanaal](../..//channels/using/creating-an-email.md)
