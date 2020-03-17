---
title: Testen
description: De activiteit van de Test laat een overgang toe die op een testresultaat wordt gebaseerd.
page-status-flag: never-activated
uuid: 1562ec7a-253a-4f4f-b66a-c2948b57775a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 2650bf1f-0bce-4049-a226-2369f6666b95
context-tags: jstest,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Testen{#test}

## Beschrijving {#description}

![](assets/test.png)

De **[!UICONTROL Test]** activiteit laat een overgang toe die op een testresultaat wordt gebaseerd.

## Gebruikscontext {#context-of-use}

Een **testactiviteit** activeert de eerste overgang die aan de voorwaarde verbonden aan het voldoet.

Als aan geen voorwaarde wordt voldaan en als de optie **Standaardovergang** gebruiken wordt geactiveerd, zal een standaardovergang worden geactiveerd.

![](assets/wkf_test_activity_example.png)

De voorwaarden kunnen op **functies**, of op **variabelen** worden gebaseerd, bijvoorbeeld gebeurtenisvariabelen die in de **[!UICONTROL External signal]** activiteit van de werkstroom zijn verklaard.

**Verwante onderwerpen:**

* [Lijst met functies](../../automating/using/list-of-functions.md)
* [Een workflow aanroepen met externe parameters](../../automating/using/calling-a-workflow-with-external-parameters.md)

## Configuratie {#configuration}

1. Sleep een **[!UICONTROL Test]** activiteit naar de werkstroom.
1. Selecteer de activiteit, dan open het gebruikend de ![](assets/edit_darkgrey-24px.png) knoop van de snelle acties die verschijnen.
1. De kenmerken van elke voorwaarde definiëren:

   Bij het bewerken van het **[!UICONTROL Condition]** veld bieden twee knoppen hulp bij het aanroepen van gebeurtenisvariabelen en het bewerken van expressies waarin variabelen en functies worden gecombineerd:

   * ![](assets/extsignal_picker.png): Selecteer de gebeurtenisvariabele onder alle variabelen die beschikbaar zijn in de workflow (zie Een workflow met externe parameters [](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-a-workflow-with-external-parameters)aanpassen)

      ![](assets/wkf_test_activity_variables.png)

   * ![](assets/extsignal_expression_editor.png): bewerkingsexpressies waarin variabelen en functies worden gecombineerd. Voor meer op de redacteur van de Uitdrukking, verwijs naar [deze sectie](../../automating/using/advanced-expression-editing.md).

      ![](assets/wkf_test_activity_variables_expression.png)

