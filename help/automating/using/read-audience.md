---
title: Lees publiek
description: Met de activiteit van het leespubliek kunt u een bestaand publiek ophalen en verfijnen door aanvullende filtervoorwaarden toe te passen.
page-status-flag: never-activated
uuid: 58c54e71-f4a7-4ae9-80a3-33c379ab1db9
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 674684e5-8830-4d2f-ba97-59ed4ba7422f
context-tags: readAudience,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c3911232a3cce00c2b9a2e619f090a7520382dde
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 0%

---


# Lees publiek{#read-audience}

## Beschrijving {#description}

![](assets/prefill.png)

De **[!UICONTROL Read audience]** activiteit staat u toe om een bestaand publiek terug te winnen en het te verfijnen door extra het filtreren voorwaarden toe te passen.

## Gebruikscontext {#context-of-use}

De **[!UICONTROL Read audience]** activiteit is een eenvoudigere versie van de **[!UICONTROL Query]** activiteit die voor gevallen wordt ontworpen waar u slechts een bestaand publiek hoeft te selecteren.

**Verwante onderwerpen**

* [Hoofdlettergebruik: Unie op twee verfijnde doelgroepen](../../automating/using/union-on-two-refined-audiences.md)
* [Hoofdlettergebruik: Een bestandspubliek in overeenstemming brengen met de database](../../automating/using/reconcile-file-audience-with-database.md)

## Configuratie {#configuration}

1. Zet een **[!UICONTROL Read audience]** activiteit neer in uw werkschema.
1. Selecteer de activiteit, dan open het gebruikend de ![](assets/edit_darkgrey-24px.png) knoop van de snelle acties die verschijnen.
1. Selecteer het publiek dat u wilt ophalen van het **[!UICONTROL Properties]** tabblad.

   U kunt het publiek van de volgende typen ophalen: **[!UICONTROL List]**, **[!UICONTROL Query]**, **[!UICONTROL File]** en **[!UICONTROL Experience Cloud]**. Raadpleeg de documentatie bij [Soorten publiek](../../audiences/using/about-audiences.md) voor meer informatie over publiekstypen.

   Met de **[!UICONTROL Use a dynamic audience]** optie kunt u de naam definiëren van het publiek waarop u zich wilt richten op basis van de gebeurtenisvariabelen van de workflow. Raadpleeg voor meer informatie de sectie [Activiteiten aanpassen met gebeurtenisvariabelen](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables) .

   ![](assets/readaudience_activity1.png)

1. Als u extra filtreren op het geselecteerde publiek wilt toepassen, voeg voorwaarden via het **[!UICONTROL Source filtering]** lusje van de activiteit toe.

   Voor meer informatie over het creëren van het filtreren voorwaarden, verwijs naar de [Creërende vragen](../../automating/using/editing-queries.md#creating-queries) documentatie.

1. Bevestig de configuratie van uw activiteit en sla uw werkschema op.
