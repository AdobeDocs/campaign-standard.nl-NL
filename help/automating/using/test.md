---
solution: Campaign Standard
product: campaign
title: Test
description: De testactiviteit maakt een overgang mogelijk die is gebaseerd op een testresultaat.
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: jstest,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 90%

---


# Test{#test}

## Beschrijving {#description}

![](assets/test.png)

De **[!UICONTROL Test]**-activiteit maakt een overgang mogelijk die is gebaseerd op een testresultaat.

## Gebruikscontext {#context-of-use}

Een **testactiviteit** activeert de eerste overgang die aan de gekoppelde voorwaarde voldoet.

Als aan geen voorwaarde is voldaan en als de optie **Use default transition** (Standaardovergang gebruiken) is geactiveerd, wordt een standaardovergang geactiveerd.

![](assets/wkf_test_activity_example.png)

Voorwaarden zijn gebaseerd op **functies** of op **variabelen**, zoals gebeurtenisvariabelen die in de **[!UICONTROL External signal]**-activiteit van de workflow zijn opgegeven.

**Verwante onderwerpen:**

* [Lijst met functies](../../automating/using/list-of-functions.md)
* [Een workflow aanroepen met externe parameters](../../automating/using/calling-a-workflow-with-external-parameters.md)

## Configuratie {#configuration}

1. Sleep een **[!UICONTROL Test]**-activiteit en plaats deze in de workflow.
1. Selecteer de activiteit en open deze met de knop ![](assets/edit_darkgrey-24px.png) vanuit de snelle acties die verschijnen.
1. Kenmerken van elke voorwaarde definiëren:

   Bij het bewerken van het veld **[!UICONTROL Condition]** krijgt u via twee knoppen hulp bij het aanroepen van gebeurtenisvariabelen en bij het bewerken van expressies waarin variabelen en functies worden gecombineerd:

   * ![](assets/extsignal_picker.png): Selecteer de gebeurtenisvariabele onder alle variabelen die beschikbaar zijn in de workflow (zie [deze pagina](../../automating/using/customizing-workflow-external-parameters.md))

      ![](assets/wkf_test_activity_variables.png)

   * ![](assets/extsignal_expression_editor.png): bewerk expressies waarin variabelen en functies worden gecombineerd. Raadpleeg [deze sectie](../../automating/using/advanced-expression-editing.md) voor meer informatie over de expressie-editor.

      ![](assets/wkf_test_activity_variables_expression.png)
