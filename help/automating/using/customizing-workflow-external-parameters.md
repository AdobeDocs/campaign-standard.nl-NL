---
title: Een workflow aanroepen met externe parameters
description: In deze sectie wordt beschreven hoe een workflow met externe parameters wordt aangeroepen.
page-status-flag: never-activated
uuid: beccd1b6-8e6d-4504-9152-9ff537459c4a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: 1676da91-55e3-414f-bcd3-bb0804b682bd
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 51e98bb6212ad96d9c11b848df9dcad25b3f1b61
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 5%

---


# Customizing a workflow with external parameters {#customizing-a-workflow-with-external-parameters}

Nadat de workflow is geactiveerd, worden de parameters opgenomen in de gebeurtenisvariabelen en kunnen deze worden gebruikt om de activiteiten van de workflow aan te passen.

Ze kunnen bijvoorbeeld worden gebruikt om te definiëren welk publiek in de **[!UICONTROL Read audience]** activiteit moet worden gelezen, welke naam van het bestand in de **[!UICONTROL Transfer file]** activiteit moet worden overgebracht, enzovoort. (see [](../../automating/using/customizing-workflow-external-parameters.md)).

## Gebeurtenisvariabelen gebruiken {#using-events-variables}

Gebeurtenisvariabelen worden gebruikt binnen een expressie die de [standaardsyntaxis](../../automating/using/advanced-expression-editing.md#standard-syntax)moet gebruiken.

De syntaxis voor het gebruik van gebeurtenisvariabelen moet de onderstaande indeling volgen en de naam van de parameter gebruiken die in de **[!UICONTROL External signal]** activiteit is gedefinieerd (zie [Parameters declareren in de externe signaalactiviteit](../../automating/using/declaring-parameters-external-signal.md)):

```
$(vars/@parameterName)
```

In deze syntaxis retourneert de functie **$** het gegevenstype van de **tekenreeks** . Als u een ander type gegevens wilt opgeven, gebruikt u de volgende functies:

* **$long**: geheel getal.
* **$float**: decimaal getal.
* **$boolean**: true/false.
* **$datetime**: tijdstempel.

Wanneer het gebruiken van een variabele in een activiteit, verstrekt de interface hulp om het te roepen.

![](assets/extsignal_callparameter.png)

* ![](assets/extsignal_picker.png): Selecteer de gebeurtenisvariabele onder alle variabelen die beschikbaar zijn in de workflow.

   ![](assets/wkf_test_activity_variables.png)

* ![](assets/extsignal_expression_editor.png): bewerk expressies waarin variabelen en functies worden gecombineerd. Raadpleeg [deze sectie](../../automating/using/advanced-expression-editing.md) voor meer informatie over de expressie-editor.

   ![](assets/wkf_test_activity_variables_expression.png)

**Verwante onderwerpen:**

* [Een expressie bewerken](../../automating/using/advanced-expression-editing.md#edit-an-expression)
* [Standaardsyntaxis](../../automating/using/advanced-expression-editing.md#standard-syntax)
* [Lijst met functies](../../automating/using/list-of-functions.md)

## Activiteiten aanpassen met gebeurtenisvariabelen {#customizing-activities-with-events-variables}

Gebeurtenisvariabelen kunnen worden gebruikt om verschillende activiteiten aan te passen die in de onderstaande sectie worden vermeld. Voor meer op hoe te om een variabele van een activiteit te roepen, verwijs naar [deze sectie](../../automating/using/customizing-workflow-external-parameters.md#using-events-variables).

**[!UICONTROL Read audience]** activiteit: het publiek bepalen om te richten op basis van gebeurtenisvariabelen.

Raadpleeg de [desbetreffende sectie](../../automating/using/read-audience.md)voor meer informatie over het gebruik van de activiteit.

![](assets/extsignal_activities_audience.png)

**[!UICONTROL Test]** activiteit: voorwaarden bouwen die op gebeurtenisvariabelen worden gebaseerd.

Raadpleeg de [desbetreffende sectie](../../automating/using/test.md)voor meer informatie over het gebruik van de activiteit.

![](assets/extsignal_activities_test.png)

**[!UICONTROL Transfer file]** activiteit: Pas het bestand aan dat u wilt overbrengen op basis van gebeurtenisvariabelen.

Raadpleeg de [desbetreffende sectie](../../automating/using/transfer-file.md)voor meer informatie over het gebruik van de activiteit.

![](assets/extsignal_activities_transfer.png)

**[!UICONTROL Query]** activiteit: In een query kan naar parameters worden verwezen door expressies te gebruiken die gebeurtenisvariabelen en -functies combineren. Hiervoor voegt u een regel toe en klikt u op de **[!UICONTROL Advanced mode]** koppeling om het venster voor het bewerken van expressies te openen (zie [Geavanceerde bewerking](../../automating/using/advanced-expression-editing.md)van expressies).

Raadpleeg de [desbetreffende sectie](../../automating/using/query.md)voor meer informatie over het gebruik van de activiteit.

![](assets/extsignal_activities_query.png)

**[!UICONTROL Channels]** activiteiten: leveringen personaliseren op basis van gebeurtenisvariabelen.

>[!NOTE]
>
>De waarden van de leveringsparameters worden teruggewonnen telkens als de levering wordt voorbereid.
>
>De voorbereiding van de terugkerende leveringen is gebaseerd op de **aggregatieperiode** van de levering. Als de samenvoegingsperiode bijvoorbeeld &quot;op dag&quot; is, wordt de levering slechts eenmaal per dag opnieuw voorbereid. Als de waarde van een leveringsparameter tijdens de dag wordt gewijzigd, zal het niet in de levering worden bijgewerkt, aangezien het reeds eens is voorbereid.
>
>Als u de workflow meerdere keren per dag wilt aanroepen, gebruikt u de [!UICONTROL No aggregation] optie, zodat de leveringsparameters elke keer worden bijgewerkt. Voor meer bij terugkomende leveringsconfiguratie, verwijs naar [deze sectie](/help/automating/using/email-delivery.md#configuration).

Om een levering te personaliseren die op gebeurtenisvariabelen wordt gebaseerd, moet u eerst in de leveringsactiviteit de variabelen verklaren die u wilt gebruiken:

1. Selecteer de activiteit, dan klik de ![](assets/dlv_activity_params-24px.png) knoop om tot de montages toegang te hebben.
1. Selecteer het **[!UICONTROL General]** tabblad en voeg vervolgens de gebeurtenisvariabelen toe die beschikbaar zijn als aanpassingsvelden in de levering.

   ![](assets/extsignal_activities_delivery.png)

1. Klik op de knop **[!UICONTROL Confirm]**.

De gedeclareerde gebeurtenisvariabelen zijn nu beschikbaar in de lijst met verpersoonlijkingsvelden. U kunt ze in de levering gebruiken om de onderstaande handelingen uit te voeren:

* Definieer de naam van de sjabloon die voor de levering moet worden gebruikt.

   >[!NOTE]
   >
   >Deze actie is alleen beschikbaar voor **terugkerende** leveringen.

   ![](assets/extsignal_activities_template.png)

* De levering personaliseren: wanneer het selecteren van een verpersoonlijkingsgebied om een levering te vormen, zijn de gebeurtenisvariabelen beschikbaar in het **[!UICONTROL Workflow parameters]** element. U kunt ze als een willekeurig verpersoonlijkingsveld gebruiken, bijvoorbeeld om het leveringsonderwerp, de afzender enzovoort te definiëren.

   De personalisatie van de levering wordt gedetailleerd in [deze sectie](../../designing/using/personalization.md).

   ![](assets/extsignal_activities_perso.png)

**Segmentcodes**: definieert de segmentcode op basis van gebeurtenisvariabelen.

>[!NOTE]
>
>Deze actie kan van om het even welke activiteit worden uitgevoerd die u een segmentcode zoals, bijvoorbeeld, **[!UICONTROL Query]** of **[!UICONTROL Segmentation]** activiteiten laat bepalen.

![](assets/extsignal_activities_segment.png)

**Leveringslabel**: het leveringslabel definiëren op basis van gebeurtenisvariabelen.

![](assets/extsignal_activities_label.png)
