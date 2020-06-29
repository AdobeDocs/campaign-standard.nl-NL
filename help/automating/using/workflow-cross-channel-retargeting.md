---
title: Niet-openers opnieuw rangschikken
description: Dit gebruiksgeval laat zien hoe u niet-openers opnieuw kunt richten.
page-status-flag: never-activated
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: workflow,use-case,query,wait,delivery
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 87e0611fae0560aca276caa3c4cf793e9c095d72
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 1%

---


# Werkstroom opnieuw toewijzen om een nieuwe levering naar niet-openers te verzenden{#retargeting-delivery-to-non-openers}

U kunt een e-mail naar klanten en dan een sms naar hen verzenden die niet de post hebben geopend.

1. Klik in **[!UICONTROL Marketing Activities]** en selecteer **[!UICONTROL Create]** de optie **[!UICONTROL Workflow]**.
1. Selecteer **[!UICONTROL New Workflow]** als workflowtype en klik op **[!UICONTROL Next]**.
1. Voer de eigenschappen van de workflow in en klik op **[!UICONTROL Create]**.

## Query-activiteiten maken{#creating-a-query-activity}

1. In **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**, sleep en laat vallen een activiteit van de [Vraag](../../automating/using/query.md) .
1. Dubbelklik op de activiteit.
1. In **[!UICONTROL Shortcuts]**, belemmering en daling **[!UICONTROL Profiles]** en selecteer **[!UICONTROL email]** met de exploitant **[!UICONTROL is not empty]**.
1. Sleep **[!UICONTROL Shortcuts]** en zet de cursor neer **[!UICONTROL Profiles]** en selecteer deze met de waarde **[!UICONTROL no longer contact by email]** **[!UICONTROL no ]**.
1. Klik op **[!UICONTROL Confirm]**.

![](assets/wf-complement-query.png)

## Een e-maillevering maken{#creating-an-email-delivery}

1. Sleep een [e-maillevering](../../automating/using/email-delivery.md) na elk segment.
1. Klik op de activiteit en selecteer deze ![](assets/edit_darkgrey-24px.png) om te bewerken.
1. Selecteer **[!UICONTROL Simple email]** en klik op **[!UICONTROL Next]**.
1. Selecteer **[!UICONTROL Add an outbound transition without the population]** en klik op **[!UICONTROL Next]**.
1. Selecteer een e-mailsjabloon en klik op **[!UICONTROL Next]**.
1. Voer de e-maileigenschappen in en klik op **[!UICONTROL Next]**.
1. Klik op om de lay-out van uw e-mail te maken **[!UICONTROL Using the Email Designer]**.
1. Voeg elementen in of selecteer een bestaande sjabloon.
1. Pas uw e-mail aan met aanbiedingen die specifiek zijn voor elke locatie.Raadpleeg [ontwerpen voor meer informatie](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).
1. Klik **[!UICONTROL Preview]** om uw lay-out te controleren.
1. Klik op **[!UICONTROL Save]**.

## Het richten van niet-openers in een vraagactiviteit{#targeting-non-openers-in-a-query-activity}

1. In **[!UICONTROL Activities]** > **[!UICONTROL Execution]**, sleep en laat vallen een activiteit van de [Wacht](../../automating/using/wait.md) .
1. Klik in **[!UICONTROL Duration]** op ![](assets/duration-icon.png) en selecteer een dag.
1. In **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**, sleep en laat vallen een **[!UICONTROL Query activity]**.
1. Dubbelklik op de activiteit.
1. In **[!UICONTROL Shortcuts]**, belemmering en daling **[!UICONTROL Tracking Logs]** en met de exploitant **[!UICONTROL exists]**.
1. In **[!UICONTROL Shortcuts]**> **[!UICONTROL Delivery]**, belemmering en daling **[!UICONTROL delivery]** met de exploitant **[!UICONTROL is equal to]** en selecteer de levering als waarde.
1. In **[!UICONTROL Shortcuts]**> **[!UICONTROL Delivery]**, belemmering en daling **[!UICONTROL type]** en controleer **[!UICONTROL Open]** als waarde.
1. Selecteer de operator tussen regels als **[!UICONTROL except]**.
1. Klik op **[!UICONTROL Confirm]**.

## Een sms-levering maken{#creating-a-sms-delivery}

1. Sleep een sms-levering na elk segment.
1. Klik op de activiteit en selecteer deze ![](assets/edit_darkgrey-24px.png) om te bewerken.
1. Selecteer **[!UICONTROL Simple sms]** en klik op **[!UICONTROL Next]**.
1. Selecteer een sms-sjabloon en klik op **[!UICONTROL Next]**.
1. Voer de sms-eigenschappen in en klik op **[!UICONTROL Next]**.
1. Klik op om de lay-out van uw sms te maken **[!UICONTROL Email Designer]**.
1. Voeg elementen in of selecteer een bestaande sjabloon.
1. Pas uw SMS-berichten aan met specifieke aanbiedingen voor elke locatie.
Raadpleeg de sectie [Een sms](../../channels/using/creating-an-sms-message.md) ontwerpen voor meer informatie.
1. Klik **[!UICONTROL Preview]** om uw lay-out te controleren.
1. Klik op **[!UICONTROL Save]**.

![](assets/wf-retargeting-non-openers.png)

**Verwante onderwerpen:**

* [E-mailkanaal](../../channels/using/creating-an-email.md)
