---
title: Doelgroep lezen
description: Met de activiteit Doelgroep lezen kunt u een bestaande doelgroep ophalen en verfijnen door aanvullende filtervoorwaarden toe te passen.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: readAudience,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 9a77a2c7-cc1c-416f-8103-bb7d5c84a373
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 87%

---

# Doelgroep lezen{#read-audience}

## Beschrijving {#description}

![](assets/prefill.png)

Met de activiteit **[!UICONTROL Read audience]** kunt u een bestaande doelgroep ophalen en verfijnen door aanvullende filtervoorwaarden toe te passen.

## Gebruikscontext {#context-of-use}

De activiteit **[!UICONTROL Read audience]** is een vereenvoudigde versie van de activiteit **[!UICONTROL Query]** die is ontworpen voor gevallen waarbij u slechts een bestaande doelgroep moet selecteren.

**Verwante onderwerpen**

* [Hoofdlettergebruik: Unie op twee verfijnde doelgroepen](../../automating/using/union-on-two-refined-audiences.md)
* [Hoofdlettergebruik: Een bestandspubliek in overeenstemming brengen met de database](../../automating/using/reconcile-file-audience-with-database.md)

## Configuratie {#configuration}

1. Zet een activiteit **[!UICONTROL Read audience]** neer in uw workflow.
1. Selecteer de activiteit en open deze met de knop ![](assets/edit_darkgrey-24px.png) vanuit de snelle acties die verschijnen.
1. Selecteer de doelgroep die u wilt ophalen van het tabblad **[!UICONTROL Properties]**.

   U kunt doelgroepen van de volgende typen ophalen: **[!UICONTROL List]**, **[!UICONTROL Query]**, **[!UICONTROL File]** en **[!UICONTROL Experience Cloud]**. Raadpleeg de documentatie bij [Doelgroepen](../../audiences/using/about-audiences.md) voor meer informatie over typen doelgroepen.

   Met de optie **[!UICONTROL Use a dynamic audience]** kunt u de naam van de doelgroep definiëren die u doelgericht wilt benaderen op basis van de gebeurtenisvariabelen van de workflow. Zie [deze pagina](../../automating/using/customizing-workflow-external-parameters.md) sectie voor meer informatie.

   ![](assets/readaudience_activity1.png)

1. Als u aanvullende filters op de geselecteerde doelgroep wilt toepassen, voegt u voorwaarden toe via het tabblad **[!UICONTROL Source filtering]** van de activiteit.

   Voor meer informatie over het maken van filtervoorwaarden raadpleegt u de documentatie bij [Query’s maken](../../automating/using/editing-queries.md#creating-queries).

1. Bevestig de configuratie van uw activiteit en sla de workflow op.
