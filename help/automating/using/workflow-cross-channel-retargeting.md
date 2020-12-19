---
solution: Campaign Standard
product: campaign
title: Personen die een bericht niet openen doelgericht opnieuw benaderen
description: Dit gebruiksgeval laat zien hoe u niet-openers opnieuw kunt richten.
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: workflow,use-case,query,wait,delivery
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 38%

---


# Opnieuw toewijzen van workflow voor het verzenden van een nieuwe levering aan niet-openers{#retargeting-delivery-to-non-openers}

U kunt een e-mail naar klanten en dan een sms naar hen verzenden die niet de post hebben geopend.

1. Klik in **[!UICONTROL Marketing Activities]** op **[!UICONTROL Create]** en selecteer **[!UICONTROL Workflow]**.
1. Selecteer **[!UICONTROL New Workflow]** als workflowtype en klik op **[!UICONTROL Next]**.
1. Voer de eigenschappen van de workflow in en klik op **[!UICONTROL Create]**.

## Het creëren van een vraagactiviteit{#creating-a-query-activity}

1. Sleep in **[!UICONTROL Activities]** > **[!UICONTROL Targeting]** een [Query](../../automating/using/query.md)-activiteit en zet deze neer.
1. Dubbelklik op de activiteit.
1. Sleep **[!UICONTROL Profiles]** in **[!UICONTROL Shortcuts]** en selecteer **[!UICONTROL email]** met de operator **[!UICONTROL is not empty]**.
1. Sleep **[!UICONTROL Profiles]** in **[!UICONTROL Shortcuts]** en selecteer **[!UICONTROL no longer contact by email]** met de waarde **[!UICONTROL no ]**.
1. Klik op **[!UICONTROL Confirm]**.

![](assets/wf-complement-query.png)

## Een e-maillevering maken{#creating-an-email-delivery}

1. Sleep een [E-maillevering](../../automating/using/email-delivery.md) na elk segment.
1. Klik op de activiteit en selecteer ![](assets/edit_darkgrey-24px.png) om te bewerken.
1. Selecteer **[!UICONTROL Simple email]** en klik op **[!UICONTROL Next]**.
1. Selecteer **[!UICONTROL Add an outbound transition without the population]** en klik op **[!UICONTROL Next]**.
1. Selecteer een e-mailsjabloon en klik op **[!UICONTROL Next]**.
1. Voer de e-maileigenschappen in en klik op **[!UICONTROL Next]**.
1. Klik op **[!UICONTROL Using the Email Designer]** om de lay-out van uw e-mail te bepalen.
1. Voeg elementen in of selecteer een bestaande sjabloon.
1. Pas uw e-mail aan met aanbiedingen specifiek voor elke plaats.Raadpleeg [Een e-mail ontwerpen](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch) voor meer informatie.
1. Klik op **[!UICONTROL Preview]** om uw lay-out te controleren.
1. Klik op **[!UICONTROL Save]**.

## Het richten van niet-openers in een vraagactiviteit{#targeting-non-openers-in-a-query-activity}

1. In **[!UICONTROL Activities]** > **[!UICONTROL Execution]**, belemmering en laat vallen een [Wacht](../../automating/using/wait.md) activiteit.
1. Klik in **[!UICONTROL Duration]** op ![](assets/duration-icon.png) en selecteer één dag.
1. In **[!UICONTROL Activities]** > **[!UICONTROL Targeting]** sleept u een **[!UICONTROL Query activity]** en zet u deze neer.
1. Dubbelklik op de activiteit.
1. In **[!UICONTROL Shortcuts]**, belemmering en daling **[!UICONTROL Tracking Logs]** en met de exploitant **[!UICONTROL exists]**.
1. In **[!UICONTROL Shortcuts]** **[!UICONTROL Delivery]**, belemmering en daling **[!UICONTROL delivery]** met de exploitant **[!UICONTROL is equal to]** en selecteer de levering als waarde.
1. **[!UICONTROL Shortcuts]**> **[!UICONTROL Delivery]**, belemmering en daling **[!UICONTROL type]** en controleer **[!UICONTROL Open]** als waarde.
1. Selecteer de operator tussen regels als **[!UICONTROL except]**.
1. Klik op **[!UICONTROL Confirm]**.

## Een sms-levering maken{#creating-a-sms-delivery}

1. Sleep een sms-levering na elk segment.
1. Klik op de activiteit en selecteer ![](assets/edit_darkgrey-24px.png) om te bewerken.
1. Selecteer **[!UICONTROL Simple sms]** en klik op **[!UICONTROL Next]**.
1. Selecteer een sms-sjabloon en klik op **[!UICONTROL Next]**.
1. Voer de sms-eigenschappen in en klik op **[!UICONTROL Next]**.
1. Als u de lay-out van uw sms wilt maken, klikt u op **[!UICONTROL Email Designer]**.
1. Voeg elementen in of selecteer een bestaande sjabloon.
1. Pas uw SMS-berichten aan met specifieke aanbiedingen voor elke locatie.
Raadpleeg de sectie [Een sms](../../channels/using/creating-an-sms-message.md) ontwerpen voor meer informatie.
1. Klik op **[!UICONTROL Preview]** om uw lay-out te controleren.
1. Klik op **[!UICONTROL Save]**.

![](assets/wf-retargeting-non-openers.png)

**Verwante onderwerpen:**

* [E-mailkanaal](../../channels/using/creating-an-email.md)
