---
solution: Campaign Standard
product: campaign
title: Leveringen maken met een aanvulling
description: In dit gebruiksgeval ziet u hoe u leveringen met een complement maakt.
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: workflow,use-case,segmentation
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 41%

---


# Leveringen maken met een aanvulling {#deliveries-with-complement}

U kunt een e-mail naar klanten sturen: een voor klanten die minder dan een jaar geleden zijn gemaakt, een voor klanten die meer dan een jaar geleden zijn gecreëerd.

1. Klik in **[!UICONTROL Marketing Activities]** op **[!UICONTROL Create]** en selecteer **[!UICONTROL Workflow]**.
1. Selecteer **[!UICONTROL New Workflow]** als workflowtype en klik op **[!UICONTROL Next]**.
1. Voer eigenschappen van de workflow in en klik op **[!UICONTROL Create]**.

## Creeer een activiteit van de Vraag {#create-a-query-activity}

1. Sleep in **[!UICONTROL Activities]** > **[!UICONTROL Targeting]** een [Query](../../automating/using/query.md)-activiteit en zet deze neer.
1. Dubbelklik op de activiteit.
1. Sleep **[!UICONTROL Profiles]** in **[!UICONTROL Shortcuts]** en selecteer **[!UICONTROL email]** met de operator **[!UICONTROL is not empty]**.
1. Sleep **[!UICONTROL Profiles]** in **[!UICONTROL Shortcuts]** en selecteer **[!UICONTROL no longer contact by email]** met de waarde **[!UICONTROL no]**.
1. Klik op **[!UICONTROL Confirm]**.

![](assets/wf-complement-query.png)

## Een segmentatieactiviteit {#create-a-segmentation-activity} maken

1. In **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**, belemmering en laat vallen een [Segmentatie](../../automating/using/segmentation.md) activiteit en klik het tweemaal.
1. Houd de muisaanwijzer boven het segment en klik op ![](assets/edit_darkgrey-24px.png) om klanten aan te wijzen die dit jaar in de database zijn toegevoegd.
1. Sleep en zet **[!UICONTROL Profiles]** neer en selecteer **[!UICONTROL Created]** met het filtertype **[!UICONTROL Relative]**.
1. Wijzig **[!UICONTROL Level of precision]** in **[!UICONTROL Year]** en selecteer **[!UICONTROL This year]**.
1. Klik twee keer op **[!UICONTROL Confirm]**.
1. Schakel **[!UICONTROL Advanced Options]** in om een segment te maken dat zich richt op de overige ontvangers.**[!UICONTROL Generate complement]**
1. Klik op **[!UICONTROL Confirm]**.
1. Klik op **[!UICONTROL Save]**.

![](assets/wf-complement-segmentation.png)

>[!NOTE]
>
>Klik op **[!UICONTROL Advanced Mode]** om de structuur van de regel waar te nemen.

## Een e-maillevering maken {#create-an-email-delivery}

1. In **[!UICONTROL Activities]** > **[!UICONTROL Channels]**, belemmering en laat vallen een [E-maillevering](../../automating/using/email-delivery.md) activiteit na elk segment.
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
