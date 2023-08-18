---
title: Leveringen maken met een aanvulling
description: In dit gebruiksgeval ziet u hoe u leveringen met een aanvulling kunt maken.
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: workflow,use-case,segmentation
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 5cd71e07-f955-4c15-bdfb-14b0daccec1a
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 41%

---

# Leveringen maken met een aanvulling {#deliveries-with-complement}

U kunt een e-mail naar klanten sturen: één voor klanten die minder dan een jaar geleden zijn gemaakt, één voor klanten die meer dan een jaar geleden zijn gemaakt.

1. Klik in **[!UICONTROL Marketing Activities]** op **[!UICONTROL Create]** en selecteer **[!UICONTROL Workflow]**.
1. Selecteer **[!UICONTROL New Workflow]** als workflowtype en klik op **[!UICONTROL Next]**.
1. Voer eigenschappen van de workflow in en klik op **[!UICONTROL Create]**.

## Een query-activiteit maken {#create-a-query-activity}

1. Sleep in **[!UICONTROL Activities]** > **[!UICONTROL Targeting]** een [Query](../../automating/using/query.md)-activiteit en zet deze neer.
1. Dubbelklik op de activiteit.
1. In **[!UICONTROL Shortcuts]**, slepen en neerzetten **[!UICONTROL Profiles]** en selecteert u **[!UICONTROL email]** met de exploitant **[!UICONTROL is not empty]**.
1. In **[!UICONTROL Shortcuts]**, slepen en neerzetten **[!UICONTROL Profiles]** en selecteert u **[!UICONTROL no longer contact by email]** met de waarde **[!UICONTROL no]**.
1. Klik op **[!UICONTROL Confirm]**.

![](assets/wf-complement-query.png)

## Een segmentatieactiviteit maken {#create-a-segmentation-activity}

1. In **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**, een [Segmentering](../../automating/using/segmentation.md) en dubbelklik erop.
1. Houd de cursor boven het segment en klik vervolgens op ![](assets/edit_darkgrey-24px.png) om klanten te richten voegde dit jaar in het gegevensbestand toe.
1. Slepen en slepen **[!UICONTROL Profiles]** en selecteert u **[!UICONTROL Created]** met het filtertype **[!UICONTROL Relative]**.
1. Wijzig de **[!UICONTROL Level of precision]** tot **[!UICONTROL Year]** en selecteert u **[!UICONTROL This year]**.
1. Klik twee keer op **[!UICONTROL Confirm]**.
1. In **[!UICONTROL Advanced Options]**, controle **[!UICONTROL Generate complement]** om een segment tot stand te brengen richtend de resterende ontvangers.
1. Klik op **[!UICONTROL Confirm]**.
1. Klik op **[!UICONTROL Save]**.

![](assets/wf-complement-segmentation.png)

>[!NOTE]
>
>Klik op **[!UICONTROL Advanced Mode]**.

## Een e-maillevering maken {#create-an-email-delivery}

1. In **[!UICONTROL Activities]** > **[!UICONTROL Channels]**, slepen en neerzetten [E-maillevering](../../automating/using/email-delivery.md) activiteit na elk segment.
1. Klik op de activiteit en selecteer ![](assets/edit_darkgrey-24px.png) om te bewerken.
1. Selecteer **[!UICONTROL Single send email]** en klik op **[!UICONTROL Next]**.
1. Selecteer een e-mailsjabloon en klik op **[!UICONTROL Next]**.
1. Voer de e-maileigenschappen in en klik op **[!UICONTROL Next]**.
1. Klik op **[!UICONTROL Email Designer]** om de lay-out van uw e-mail te bepalen.
1. Voeg elementen in of selecteer een bestaande sjabloon.
1. Pas uw e-mail aan met aanbiedingen die specifiek zijn voor elke levering.
1. Klik op **[!UICONTROL Preview]** om uw lay-out te controleren.
1. Klik op **[!UICONTROL Save]**.

Raadpleeg [Een e-mail ontwerpen](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch) voor meer informatie.

![](assets/wf-deliveries-with-a-complement.png)
