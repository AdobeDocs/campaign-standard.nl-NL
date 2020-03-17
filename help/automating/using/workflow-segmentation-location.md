---
title: '"Gebruiksscenario voor workflow: Segmentatie op locatie"'
description: '"Gebruiksscenario voor workflow: Segmentatie op locatie"'
page-status-flag: never-activated
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: workflow,use-case,query,segmentation,delivery
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Gebruiksscenario voor workflow: Segmentatie op locatie {#segmentation-on-location}

U kunt een e-mail sturen naar klanten met aanbiedingen in hun lokale winkels.

1. Klik in **[!UICONTROL Marketing Activities]** en selecteer **[!UICONTROL Create]** de optie **[!UICONTROL Workflow]**.
1. Selecteer **[!UICONTROL New Workflow]** als workflowtype en klik op **[!UICONTROL Next]**.
1. Voer de eigenschappen van de workflow in en klik op **[!UICONTROL Create]**.

## Ontvangers die via e-mail contact kunnen opnemen selecteren{#selecting-recipients-contactable-via-email}

1. In **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**, sleep en laat vallen een **[!UICONTROL Query activity]** ![](assets/query.png).
1. Dubbelklik op de activiteit.
1. Sleep **[!UICONTROL Shortcuts]** en zet het veld neer **[!UICONTROL Profiles]** en selecteer het veld **[!UICONTROL email]** met de operator **[!UICONTROL is not empty]**.
1. Sleep **[!UICONTROL Shortcuts]** en zet het veld neer **[!UICONTROL Profiles]** en selecteer het **[!UICONTROL no longer contact by email]** met de waarde **[!UICONTROL no]**.
1. Klik **[!UICONTROL Confirm]** tweemaal.

![](assets/wf-complement-query.png)

## Een segmentatieactiviteit maken{#creating-a-segmentation-activity}

1. Sleep een **[!UICONTROL Segmentation]** activiteit en zet deze neer en dubbelklik erop.
1. Klik op segment en open vervolgens de overgang naar de eerste stad. Hier Boston.
1. Sleep en zet de cursor neer **[!UICONTROL Location]** en selecteer **[!UICONTROL City]** deze met de operator **[!UICONTROL equals to]** en de waarde **[!UICONTROL Boston]**.
Opmerking: Om alle mensen te bereiken die boston zijn binnengekomen, maakt u, zonder rekening te houden met de zaak, de optie van de case sensitive uit.
1. Klik op **[!UICONTROL Confirm]**.
1. Klik **[!UICONTROL List of outbound segments]** in en klik op **[!UICONTROL Add an element]** ![](assets/edit_darkgrey-24px.png) om een segment te maken voor mensen in de tweede stad. Hier Chicago.
1. Sleep en zet de cursor neer **[!UICONTROL Location]** en selecteer **[!UICONTROL City]** deze met de operator **[!UICONTROL equals to]** en voer **[!UICONTROL Chicago]** de waarde in.
1. Om alle mensen te bereiken die chicago binnenkwamen, unheling van de zaak de case-sensitive optie.
1. Klik op **[!UICONTROL Confirm]**.

## Een e-maillevering maken{#creating-an-email-delivery}

1. Sleep in **[!UICONTROL Activities]** > **[!UICONTROL Channels]** een segment **[!UICONTROL Email Delivery]** na elk segment.
1. Klik op de activiteit en selecteer deze ![](assets/edit_darkgrey-24px.png) om te bewerken.
1. Selecteer **[!UICONTROL Simple email]** en klik op **[!UICONTROL Next]**.
1. Selecteer een e-mailsjabloon en klik op **[!UICONTROL Next]**.
1. Voer de e-maileigenschappen in en klik op **[!UICONTROL Next]**.
1. Klik op om de lay-out van uw e-mail te maken **[!UICONTROL Email Designer]**.
1. Voeg elementen in of selecteer een bestaande sjabloon.
1. Pas uw e-mail aan met aanbiedingen die specifiek zijn voor elke locatie.

Raadpleeg voor meer informatie het [ontwerpen van een e-mail](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).

1. Klik **[!UICONTROL Preview]** om uw lay-out te controleren.
1. Klik op **[!UICONTROL Save]**.

![](assets/wf-segmentation-location.png)

**Verwante onderwerpen:**

* [Query-activiteit](../../automating/using/query.md)
* [Segmenteringsactiviteit](../../automating/using/segmentation.md)
* [E-maillevering](../../automating/using/email-delivery.md)
