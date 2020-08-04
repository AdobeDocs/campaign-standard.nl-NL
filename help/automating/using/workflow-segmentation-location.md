---
title: Segmentatie op locatie"
description: Dit gebruiksgeval toont hoe te om segmentatie op plaats uit te voeren.
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
source-git-commit: c3911232a3cce00c2b9a2e619f090a7520382dde
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 83%

---


# Segmentatie op locatie {#segmentation-on-location}

U kunt een e-mail sturen naar klanten met aanbiedingen in hun lokale winkels.

1. Klik in **[!UICONTROL Marketing Activities]** op **[!UICONTROL Create]** en selecteer **[!UICONTROL Workflow]**.
1. Selecteer **[!UICONTROL New Workflow]** als workflowtype en klik op **[!UICONTROL Next]**.
1. Voer de eigenschappen van de workflow in en klik op **[!UICONTROL Create]**.

## Ontvangers selecteren met wie via e-mail{#selecting-recipients-contactable-via-email}contact kan worden opgenomen

1. In **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**, sleep en laat vallen een activiteit van de [Vraag](../../automating/using/query.md) ![](assets/query.png).
1. Dubbelklik op de activiteit.
1. In **[!UICONTROL Shortcuts]** sleept u het veld **[!UICONTROL Profiles]** en selecteert u het veld **[!UICONTROL email]** met de operator **[!UICONTROL is not empty]**.
1. In **[!UICONTROL Shortcuts]** sleept u het veld **[!UICONTROL Profiles]** en selecteert u het veld **[!UICONTROL no longer contact by email]** met de waarde **[!UICONTROL no]**.
1. Klik twee keer op **[!UICONTROL Confirm]**.

![](assets/wf-complement-query.png)

## Een segmentatie-activiteit maken{#creating-a-segmentation-activity}

1. Drag and drop a [Segmentation](../../automating/using/segmentation.md) activity and double-click it.
1. Klik op het segment en open vervolgens de overgang met als target de mensen in de eerste stad. In dit geval Boston.
1. Sleep **[!UICONTROL Location]** en selecteer **[!UICONTROL City]** met de operator **[!UICONTROL equals to]** en de waarde **[!UICONTROL Boston]**.
Opmerking: om alle mensen die Boston zijn binnengekomen te bereiken, ongeacht hoofdlettergebruik, schakelt u de hoofdlettergevoelige optie uit.
1. Klik op **[!UICONTROL Confirm]**.
1. In **[!UICONTROL List of outbound segments]** klikt u achtereenvolgens op **[!UICONTROL Add an element]** en op ![](assets/edit_darkgrey-24px.png) om een segment te maken dat is gericht op mensen in de tweede stad. In dit geval Chicago.
1. Sleep **[!UICONTROL Location]** en selecteer **[!UICONTROL City]** met de operator **[!UICONTROL equals to]** en voer **[!UICONTROL Chicago]** in als waarde.
1. Om alle mensen die Chicago zijn binnengekomen te bereiken, ongeacht hoofdlettergebruik, schakelt u de hoofdlettergevoelige optie uit.
1. Klik op **[!UICONTROL Confirm]**.

## Een e-maillevering maken{#creating-an-email-delivery}

1. Sleep in **[!UICONTROL Activities]** > **[!UICONTROL Channels]** een activiteit voor het verzenden van [e-mail](../../automating/using/email-delivery.md) na elk segment.
1. Klik op de activiteit en selecteer ![](assets/edit_darkgrey-24px.png) om te bewerken.
1. Selecteer **[!UICONTROL Simple email]** en klik op **[!UICONTROL Next]**.
1. Selecteer een e-mailsjabloon en klik op **[!UICONTROL Next]**.
1. Voer de e-maileigenschappen in en klik op **[!UICONTROL Next]**.
1. Klik op **[!UICONTROL Email Designer]** om de lay-out van uw e-mail te bepalen.
1. Voeg elementen in of selecteer een bestaande sjabloon.
1. Pas uw e-mail aan met aanbiedingen specifiek voor elke locatie.

   Zie [Een e-mail ontwerpen](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch) voor meer informatie.

1. Klik op **[!UICONTROL Preview]** om uw lay-out te controleren.
1. Klik op **[!UICONTROL Save]**.

![](assets/wf-segmentation-location.png)

