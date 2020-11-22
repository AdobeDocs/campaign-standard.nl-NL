---
solution: Campaign Standard
product: campaign
title: Een workflow aanroepen met externe parameters
description: In deze sectie wordt beschreven hoe een workflow met externe parameters wordt aangeroepen.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '803'
ht-degree: 1%

---


# Customizing a workflow with external parameters {#customizing-a-workflow-with-external-parameters}

Nadat de workflow is geactiveerd, worden de parameters opgenomen in de gebeurtenisvariabelen en kunnen deze worden gebruikt om de activiteiten van de workflow aan te passen.

Ze kunnen bijvoorbeeld worden gebruikt om te definiëren welk publiek in de **[!UICONTROL Read audience]** activiteit moet worden gelezen, welke naam van het bestand in de **[!UICONTROL Transfer file]** activiteit moet worden overgebracht, enzovoort. (see [this page](../../automating/using/customizing-workflow-external-parameters.md)).

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

* ![](assets/extsignal_expression_editor.png): bewerkingsexpressies waarin variabelen en functies worden gecombineerd (zie [deze pagina](../../automating/using/advanced-expression-editing.md)).

   ![](assets/wkf_test_activity_variables_expression.png)

   Deze lijst verstrekt functies die u toestaan om het complexe filtreren uit te voeren. Deze functies worden beschreven in [deze sectie](../../automating/using/list-of-functions.md).

   Bovendien kunt u de functies hieronder gebruiken, die in alle activiteiten beschikbaar zijn die u toestaan om gebeurtenisvariabelen te gebruiken na het roepen van een werkschema met externe parameters (zie [deze sectie](../../automating/using/customizing-workflow-external-parameters.md#customizing-activities-with-events-variables)):

   | Naam | Beschrijving | Syntaxis |
   ---------|----------|---------
   | EndWith | Geeft aan of een tekenreeks (eerste parameter) eindigt met een specifieke tekenreeks (tweede parameter). | EndWith(&lt;String>,&lt;String>) |
   | startWith | Geeft aan of een tekenreeks (eerste parameter) begint met een specifieke tekenreeks (tweede parameter). | startWith(&lt;String>,&lt;String>) |
   | Extraheren | Retourneert de eerste tekens van een tekenreeks met een scheidingsteken. | Extraheren(&lt;String>,&lt;Separator>) |
   | ExtractRight | Retourneert de laatste tekens van een tekenreeks met een scheidingsteken. | ExtractRight(&lt;String>,&lt;Separator>) |
   | DateFormat | Maakt een datum op in de notatie die is opgegeven in de tweede parameter (voorbeeld:  &#39;%4Y%2M%2D&#39;) | DateFormat(&lt;Date>,&lt;Format>) |
   | FileName | Retourneert de naam van een bestandspad. | FileName(&lt;String>) |
   | FileExt | Retourneert de extensie van een bestandspad. | FileExt(&lt;String>) |
   | IsNull | Geeft aan of een tekenreeks of datum null is. | IsNull(&lt;String/date>) |
   | UrlUtf8Encode | Codeert een URL in UTF8. | UrlUtf8Encode(&lt;String>) |

## Activiteiten aanpassen met gebeurtenisvariabelen {#customizing-activities-with-events-variables}

Gebeurtenisvariabelen kunnen worden gebruikt om verschillende activiteiten aan te passen die in de onderstaande sectie worden vermeld. Voor meer op hoe te om een variabele van een activiteit te roepen, verwijs naar [deze sectie](../../automating/using/customizing-workflow-external-parameters.md#using-events-variables).

**[!UICONTROL Read audience]** activiteit: het publiek bepalen om te richten op basis van gebeurtenisvariabelen. Raadpleeg [deze sectie](../../automating/using/read-audience.md)voor meer informatie over het gebruik van de activiteit.

![](assets/extsignal_activities_audience.png)

**[!UICONTROL Test]** activiteit: voorwaarden bouwen die op gebeurtenisvariabelen worden gebaseerd. Raadpleeg [deze sectie](../../automating/using/test.md)voor meer informatie over het gebruik van de activiteit.

![](assets/extsignal_activities_test.png)

**[!UICONTROL Transfer file]** activiteit: Pas het bestand aan dat u wilt overbrengen op basis van gebeurtenisvariabelen. Raadpleeg [deze sectie](../../automating/using/transfer-file.md)voor meer informatie over het gebruik van de activiteit.

![](assets/extsignal_activities_transfer.png)

**[!UICONTROL Query]** activiteit: In een query kan naar parameters worden verwezen door expressies te gebruiken die gebeurtenisvariabelen en -functies combineren. Hiervoor voegt u een regel toe en klikt u op de **[!UICONTROL Advanced mode]** koppeling om het venster voor het bewerken van expressies te openen (zie [Geavanceerde bewerking](../../automating/using/advanced-expression-editing.md)van expressies).

Raadpleeg [deze sectie](../../automating/using/query.md)voor meer informatie over het gebruik van de activiteit.

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
