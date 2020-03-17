---
title: '"Gebruiksscenario voor workflow: Leveringen maken met een complement"'
description: '"Gebruiksscenario voor workflow: Leveringen maken met een complement"'
page-status-flag: never-activated
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: workflow,use-case,segmentation
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Gebruiksscenario voor workflow: Leveringen maken met een aanvulling {#deliveries-with-complement}

U kunt een e-mail naar klanten sturen: een voor klanten die minder dan een jaar geleden zijn gemaakt, een voor klanten die meer dan een jaar geleden zijn gecreëerd.

1. Klik in **[!UICONTROL Marketing Activities]** en selecteer **[!UICONTROL Create]** de optie **[!UICONTROL Workflow]**.
1. Selecteer **[!UICONTROL New Workflow]** als workflowtype en klik op **[!UICONTROL Next]**.
1. Voer eigenschappen van de workflow in en klik op **[!UICONTROL Create]**.

## Een query-activiteit maken {#create-a-query-activity}

1. In **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**, sleep en laat vallen een **[!UICONTROL Query activity]** ![](assets/query.png).
1. Dubbelklik op de activiteit.
1. In **[!UICONTROL Shortcuts]**, belemmering en daling **[!UICONTROL Profiles]** en selecteer **[!UICONTROL email]** met de exploitant **[!UICONTROL is not empty]**.
1. Sleep **[!UICONTROL Shortcuts]** en zet de cursor neer **[!UICONTROL Profiles]** en selecteer deze met de waarde **[!UICONTROL no longer contact by email]** **[!UICONTROL no]**.
1. Klik op **[!UICONTROL Confirm]**.

![](assets/wf-complement-query.png)

## Een segmentatieactiviteit maken {#create-a-segmentation-activity}

1. Sleep in **[!UICONTROL Activities]** > **[!UICONTROL Targeting]** een **[!UICONTROL Segmentation]** activiteit en dubbelklik erop.
1. Houd de muis boven het segment en klik vervolgens op ![](assets/edit_darkgrey-24px.png) om klanten aan te wijzen die dit jaar in de database zijn toegevoegd.
1. Sleep en zet **[!UICONTROL Profiles]** de cursor neer en selecteer **[!UICONTROL Created]** deze met het filtertype **[!UICONTROL Relative]**.
1. Wijzig de **[!UICONTROL Level of precision]** in **[!UICONTROL Year]** en selecteer **[!UICONTROL This year]**.
1. Klik **[!UICONTROL Confirm]** tweemaal.
1. In **[!UICONTROL Advanced Options]**, controleer **[!UICONTROL Generate complement]** om een segment tot stand te brengen richtend de resterende ontvangers.
1. Klik op **[!UICONTROL Confirm]**.
1. Klik op **[!UICONTROL Save]**.

![](assets/wf-complement-segmentation.png)

>[!NOTE]
>
>Klik op **[!UICONTROL Advanced Mode]**.

## Een e-maillevering maken {#create-an-email-delivery}

1. Sleep in **[!UICONTROL Activities]** > **[!UICONTROL Channels]** een e-maillevering na elk segment.
1. Klik op de activiteit en selecteer deze ![](assets/edit_darkgrey-24px.png) om te bewerken.
1. Selecteer **[!UICONTROL Single send email]** en klik op **[!UICONTROL Next]**.
1. Selecteer een e-mailsjabloon en klik op **[!UICONTROL Next]**.
1. Voer de e-maileigenschappen in en klik op **[!UICONTROL Next]**.
1. Klik op om de lay-out van uw e-mail te maken **[!UICONTROL Email Designer]**.
1. Voeg elementen in of selecteer een bestaande sjabloon.
1. Pas uw e-mail aan met aanbiedingen die specifiek zijn voor elke levering.
1. Klik **[!UICONTROL Preview]** om uw lay-out te controleren.
1. Klik op **[!UICONTROL Save]**.

Raadpleeg voor meer informatie het [ontwerpen van een e-mail](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).

![](assets/wf-deliveries-with-a-complement.png)

**Verwante onderwerpen:**

* [Query](../../automating/using/query.md)
* [Segmenteringsactiviteit](../../automating/using/segmentation.md)
* [E-maillevering](../../automating/using/email-delivery.md)
