---
title: Personen die een bericht niet openen, doelgericht opnieuw benaderen
description: Dit gebruiksgeval laat zien hoe u zich opnieuw richt op niet-openers.
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: workflow,use-case,query,wait,delivery
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: cba4e5c6-8acd-47a1-824e-14415e90d451
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 36%

---

# Werkstroom opnieuw toewijzen om een nieuwe levering naar niet-openers te verzenden{#retargeting-delivery-to-non-openers}

U kunt een e-mail naar klanten en dan een sms naar hen verzenden die niet de post hebben geopend.

1. Klik in **[!UICONTROL Marketing Activities]** op **[!UICONTROL Create]** en selecteer **[!UICONTROL Workflow]**.
1. Selecteer **[!UICONTROL New Workflow]** als workflowtype en klik op **[!UICONTROL Next]**.
1. Voer de eigenschappen van de workflow in en klik op **[!UICONTROL Create]**.

## Query-activiteiten maken{#creating-a-query-activity}

1. Sleep in **[!UICONTROL Activities]** > **[!UICONTROL Targeting]** een [Query](../../automating/using/query.md)-activiteit en zet deze neer.
1. Dubbelklik op de activiteit.
1. In **[!UICONTROL Shortcuts]** sleept u **[!UICONTROL Profiles]** en selecteert u **[!UICONTROL email]** met de operator **[!UICONTROL is not empty]** .
1. Sleep in **[!UICONTROL Shortcuts]** en zet **[!UICONTROL Profiles]** neer en selecteer **[!UICONTROL no longer contact by email]** met de waarde **[!UICONTROL no]** .
1. Klik op **[!UICONTROL Confirm]**.

![](assets/wf-complement-query.png)

## Een e-maillevering maken{#creating-an-email-delivery}

1. De belemmering en laat vallen een [&#x200B; E-maillevering &#x200B;](../../automating/using/email-delivery.md) na elk segment.
1. Klik op de activiteit en selecteer ![](assets/edit_darkgrey-24px.png) om te bewerken.
1. Selecteer **[!UICONTROL Simple email]** en klik op **[!UICONTROL Next]**.
1. Selecteer **[!UICONTROL Add an outbound transition without the population]** en klik op **[!UICONTROL Next]**.
1. Selecteer een e-mailsjabloon en klik op **[!UICONTROL Next]**.
1. Voer de e-maileigenschappen in en klik op **[!UICONTROL Next]**.
1. Klik op **[!UICONTROL Using the Email Designer]** om de lay-out van uw e-mail te bepalen.
1. Voeg elementen in of selecteer een bestaande sjabloon.
1. Personaliseer uw e-mail met aanbiedingen specifiek voor elke plaats.Voor meer informatie, verwijs naar [&#x200B; het ontwerpen van e-mail &#x200B;](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).
1. Klik op **[!UICONTROL Preview]** om uw lay-out te controleren.
1. Klik op **[!UICONTROL Save]**.

## Het richten van niet-openers in een vraagactiviteit{#targeting-non-openers-in-a-query-activity}

1. In **[!UICONTROL Activities]** > **[!UICONTROL Execution]**, belemmering en laat vallen a [&#x200B; wacht &#x200B;](../../automating/using/wait.md) activiteit.
1. Klik in **[!UICONTROL Duration]** op ![](assets/duration-icon.png) en selecteer een dag.
1. In **[!UICONTROL Activities]** > **[!UICONTROL Targeting]** sleept u een **[!UICONTROL Query activity]** en zet u deze neer.
1. Dubbelklik op de activiteit.
1. Sleep in **[!UICONTROL Shortcuts]** en zet de cursor neer **[!UICONTROL Tracking Logs]** en met de operator **[!UICONTROL exists]** .
1. In **[!UICONTROL Shortcuts]**> **[!UICONTROL Delivery]** sleept en zet u **[!UICONTROL delivery]** neer met de operator **[!UICONTROL is equal to]** en selecteert u de levering als waarde.
1. Ga naar **[!UICONTROL Shortcuts]** > **[!UICONTROL Delivery]** en sleep **[!UICONTROL type]** en controleer **[!UICONTROL Open]** als waarde.
1. Selecteer de operator tussen regels als **[!UICONTROL except]** .
1. Klik op **[!UICONTROL Confirm]**.

## Een sms-levering maken{#creating-a-sms-delivery}

1. Sleep een sms-levering na elk segment.
1. Klik op de activiteit en selecteer ![](assets/edit_darkgrey-24px.png) om te bewerken.
1. Selecteer **[!UICONTROL Simple sms]** en klik op **[!UICONTROL Next]**.
1. Selecteer een sms-sjabloon en klik op **[!UICONTROL Next]** .
1. Voer de sms-eigenschappen in en klik op **[!UICONTROL Next]** .
1. Klik op **[!UICONTROL Email Designer]** om de lay-out van uw sms te maken.
1. Voeg elementen in of selecteer een bestaande sjabloon.
1. Pas uw SMS-berichten aan met specifieke aanbiedingen voor elke locatie.
Voor meer informatie, verwijs naar [&#x200B; het Ontwerpen van een sms &#x200B;](../../channels/using/creating-an-sms-message.md) sectie.
1. Klik op **[!UICONTROL Preview]** om uw lay-out te controleren.
1. Klik op **[!UICONTROL Save]**.

![](assets/wf-retargeting-non-openers.png)

**Verwante onderwerpen:**

* [Email channel](../../channels/using/creating-an-email.md)
