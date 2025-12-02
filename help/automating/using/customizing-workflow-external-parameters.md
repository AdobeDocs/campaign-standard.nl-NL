---
title: Een workflow aanpassen met externe parameters
description: In deze sectie wordt beschreven hoe u een workflow met externe parameters kunt aanroepen.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 8c1a47ed-3467-4fcd-8747-86f0e8f15cec
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '810'
ht-degree: 0%

---

# Een workflow aanpassen met externe parameters {#customizing-a-workflow-with-external-parameters}

Nadat de workflow is geactiveerd, worden de parameters opgenomen in de gebeurtenisvariabelen en kunnen deze worden gebruikt om de activiteiten van de workflow aan te passen.

Ze kunnen bijvoorbeeld worden gebruikt om te definiëren welk publiek wordt gelezen in de **[!UICONTROL Read audience]** -activiteit, de naam van het bestand dat wordt overgebracht in de **[!UICONTROL Transfer file]** -activiteit, enzovoort. (zie [ deze pagina ](../../automating/using/customizing-workflow-external-parameters.md)).

## Gebeurtenisvariabelen gebruiken {#using-events-variables}

De variabelen van gebeurtenissen worden gebruikt binnen een uitdrukking die de [ Standaardsyntaxis ](../../automating/using/advanced-expression-editing.md#standard-syntax) moet respecteren.

De syntaxis om gebeurtenisvariabelen te gebruiken moet hieronder het formaat volgen, en de naam van de parameter gebruiken die in de **[!UICONTROL External signal]** activiteit (zie [ die de parameters in de Externe signaalactiviteit ](../../automating/using/declaring-parameters-external-signal.md) verklaart) is bepaald:

```
$(vars/@parameterName)
```

In deze syntaxis, keert de **$** functie **koord** gegevenstype terug. Als u een ander type gegevens wilt opgeven, gebruikt u de volgende functies:

* **$long**: geheel getal.
* **$float**: decimaal getal.
* **$boolean**: true/false.
* **$datetime**: timestamp.

Wanneer het gebruiken van een variabele in een activiteit, verstrekt de interface hulp om het te roepen.

![](assets/extsignal_callparameter.png)

* ![](assets/extsignal_picker.png) : selecteer de gebeurtenisvariabele onder alle variabelen die beschikbaar zijn in de workflow.

  ![](assets/wkf_test_activity_variables.png)

* ![](assets/extsignal_expression_editor.png): geef uitdrukkingen uit die variabelen en functies combineren (zie [ deze pagina ](../../automating/using/advanced-expression-editing.md)).

  ![](assets/wkf_test_activity_variables_expression.png)

  Deze lijst verstrekt functies die u toestaan om het complexe filtreren uit te voeren. Deze functies zijn gedetailleerd in [ deze sectie ](../../automating/using/list-of-functions.md).

  Bovendien, kunt u de functies hieronder gebruiken, die in alle activiteiten beschikbaar zijn die u toestaan om gebeurtenisvariabelen na het roepen van een werkschema met externe parameters (zie [ dit sectie ](../../automating/using/customizing-workflow-external-parameters.md#customizing-activities-with-events-variables)) te gebruiken:

  | Naam | Beschrijving | Syntaxis |
  | ---------|----------|---------|
  | EndWith | Geeft aan of een tekenreeks (eerste parameter) eindigt met een specifieke tekenreeks (tweede parameter). | EndWith(&lt;String>,&lt;String>) |
  | startWith | Geeft aan of een tekenreeks (eerste parameter) begint met een specifieke tekenreeks (tweede parameter). | startWith(&lt;String>,&lt;String>) |
  | Extraheren | Retourneert de eerste tekens van een tekenreeks met een scheidingsteken. | Extraheren(&lt;String>,&lt;Separator>) |
  | ExtractRight | Retourneert de laatste tekens van een tekenreeks met een scheidingsteken. | ExtractRight(&lt;String>,&lt;Separator>) |
  | DateFormat | Hiermee wordt een datum opgemaakt in de notatie die is opgegeven in de tweede parameter (bijvoorbeeld: &#39;%4Y%2M%2D&#39;) | DateFormat(&lt;Date>,&lt;Format>) |
  | FileName | Retourneert de naam van een bestandspad. | FileName(&lt;String>) |
  | FileExt | Retourneert de extensie van een bestandspad. | FileExt(&lt;String>) |
  | GetOption | Retourneert de waarde van de opgegeven functie. | GetOption(&lt;optionName>) |
  | IsNull | Geeft aan of een tekenreeks of datum null is. | IsNull(&lt;String/date>) |
  | UrlUtf8Encode | Codeert een URL in UTF8. | UrlUtf8Encode(&lt;String>) |

## Activiteiten aanpassen met gebeurtenisvariabelen {#customizing-activities-with-events-variables}

Gebeurtenisvariabelen kunnen worden gebruikt om verschillende activiteiten aan te passen die in de onderstaande sectie worden vermeld. Voor meer op hoe te om een variabele van een activiteit te roepen, verwijs naar [ deze sectie ](../../automating/using/customizing-workflow-external-parameters.md#using-events-variables).

**[!UICONTROL Read audience]** -activiteit: definieer het doelpubliek op basis van gebeurtenisvariabelen. Voor meer op hoe te om de activiteit te gebruiken, verwijs naar [ deze sectie ](../../automating/using/read-audience.md).

![](assets/extsignal_activities_audience.png)

**[!UICONTROL Test]** activity: bouwvoorwaarden op basis van gebeurtenisvariabelen. Voor meer op hoe te om de activiteit te gebruiken, verwijs naar [ deze sectie ](../../automating/using/test.md).

![](assets/extsignal_activities_test.png)

**[!UICONTROL Transfer file]** -activiteit: pas het over te dragen bestand aan op basis van gebeurtenisvariabelen. Voor meer op hoe te om de activiteit te gebruiken, verwijs naar [ deze sectie ](../../automating/using/transfer-file.md).

![](assets/extsignal_activities_transfer.png)

**[!UICONTROL Query]** activity: in een query kan naar parameters worden verwezen door expressies te gebruiken die gebeurtenisvariabelen en -functies combineren. Om dit te doen, voeg een regel dan de **[!UICONTROL Advanced mode]** verbinding toe om tot de uitdrukking toegang te hebben die venster uitgeeft (zie [ Geavanceerde uitdrukking die ](../../automating/using/advanced-expression-editing.md) uitgeeft).

Voor meer op hoe te om de activiteit te gebruiken, verwijs naar [ deze sectie ](../../automating/using/query.md).

![](assets/extsignal_activities_query.png)

**[!UICONTROL Channels]** -activiteiten: geef leveringen een persoonlijk tintje op basis van gebeurtenisvariabelen.

>[!NOTE]
>
>De waarden van de leveringsparameters worden teruggewonnen telkens als de levering wordt voorbereid.
>
>Het terugkomen van leveringsvoorbereiding is gebaseerd op de levering **samenvoegingsperiode**. Als de samenvoegingsperiode bijvoorbeeld &quot;op dag&quot; is, wordt de levering slechts eenmaal per dag opnieuw voorbereid. Als de waarde van een leveringsparameter tijdens de dag wordt gewijzigd, zal het niet in de levering worden bijgewerkt, aangezien het reeds eens is voorbereid.
>
>Als u de workflow meerdere keren per dag wilt aanroepen, gebruikt u de optie [!UICONTROL No aggregation] , zodat de leveringsparameters elke keer worden bijgewerkt. Voor meer bij terugkomende leveringsconfiguratie, verwijs naar [ deze sectie ](/help/automating/using/email-delivery.md#configuration).

Om een levering te personaliseren die op gebeurtenisvariabelen wordt gebaseerd, moet u eerst in de leveringsactiviteit de variabelen verklaren die u wilt gebruiken:

1. Selecteer de activiteit, dan klik de ![](assets/dlv_activity_params-24px.png) knoop om tot de montages toegang te hebben.
1. Selecteer het tabblad **[!UICONTROL General]** en voeg vervolgens de gebeurtenisvariabelen toe die beschikbaar zijn als aanpassingsvelden in de levering.

   ![](assets/extsignal_activities_delivery.png)

1. Klik op de knop **[!UICONTROL Confirm]**.

De gedeclareerde gebeurtenisvariabelen zijn nu beschikbaar in de lijst met verpersoonlijkingsvelden. U kunt ze in de levering gebruiken om de onderstaande handelingen uit te voeren:

* Definieer de naam van de sjabloon die voor de levering moet worden gebruikt.

  >[!NOTE]
  >
  >Deze actie is beschikbaar voor **terugkomende** slechts leveringen.

  ![](assets/extsignal_activities_template.png)

* Personaliseer de levering: wanneer het selecteren van een verpersoonlijkingsgebied om een levering te vormen, zijn de gebeurtenisvariabelen beschikbaar in het **[!UICONTROL Workflow parameters]** element. U kunt ze als een willekeurig verpersoonlijkingsveld gebruiken, bijvoorbeeld om het leveringsonderwerp, de afzender enzovoort te definiëren.

  De verpersoonlijking van de levering wordt gedetailleerd in [ deze sectie ](../../designing/using/personalization.md).

  ![](assets/extsignal_activities_perso.png)

**codes van het Segment**: bepaal de segmentcode die op gebeurtenisvariabelen wordt gebaseerd.

>[!NOTE]
>
>Deze handeling kan worden uitgevoerd vanuit elke activiteit waarmee u een segmentcode kunt definiëren, zoals **[!UICONTROL Query]** - of **[!UICONTROL Segmentation]** -activiteiten.

![](assets/extsignal_activities_segment.png)

**Etiket van de Levering**: bepaal het leveringsetiket dat op gebeurtenisvariabelen wordt gebaseerd.

![](assets/extsignal_activities_label.png)
