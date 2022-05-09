---
title: Use case for calling workflow
description: This section details how to call a workflow with external parameters.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 7a21f4f6-316f-4f3d-9d53-37d406a46aae
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '976'
ht-degree: 1%

---

# Gebruiksscenario {#use-case}

The use case below shows how to call workflow with parameters within your workflows.

The objective is to trigger a workflow from an API call with external parameters. Deze workflow laadt gegevens uit een bestand in uw database en maakt een gekoppeld publiek. Zodra het publiek is gecreeerd, zal een tweede werkschema worden teweeggebracht om een bericht te verzenden dat met de externe parameters wordt gepersonaliseerd die in de API vraag worden bepaald.

Voor dit gebruik moet u de volgende handelingen uitvoeren:

1. **Een API-aanroep maken** om Werkstroom 1 met externe parameters teweeg te brengen. Zie [Stap 1: De API-aanroep configureren](../../automating/using/use-case-calling-workflow.md#step-1--configuring-the-api-call).
1. **Workflow 1 samenstellen**: de workflow zal een bestand overbrengen en in de database laden . Vervolgens wordt getest of de gegevens leeg zijn of niet en worden de profielen uiteindelijk in een publiek opgeslagen. Tot slot zal het Werkschema 2 teweegbrengen. See [Step 2: Configuring Workflow 1](../../automating/using/use-case-calling-workflow.md#step-2--configuring-workflow-1).
1. **Workflow 2 samenstellen**: De workflow leest het publiek dat in Workflow 1 is gemaakt en stuurt vervolgens een gepersonaliseerd bericht naar de profielen, met een segmentcode die met de parameters is aangepast. Zie [Stap 3: Workflow 2 configureren](../../automating/using/use-case-calling-workflow.md#step-3--configuring-workflow-2).

![](assets/extsignal_uc_process.png)

## Vereisten {#prerequisites}

Voordat u de workflows configureert, moet u eerst de workflows 1 en 2 maken met een **[!UICONTROL External signal]** in elk van hen. Deze manier, zult u deze signaalactiviteiten kunnen richten wanneer het roepen van de werkschema&#39;s.

## Stap 1: De API-aanroep configureren {#step-1--configuring-the-api-call}

Maak een API vraag om Werkstroom 1 met parameters teweeg te brengen. Raadpleeg voor meer informatie over de syntaxis van de API-aanroep de [Campaign Standard REST API&#39;s-documentatie](../../api/using/triggering-a-signal-activity.md).

In our case, we want to call the workflow with the parameters below:

* **fileToTarget**: de naam van het bestand dat we in de database willen importeren.
* **discontoDesc**: de beschrijving die wij in de levering voor de korting willen tonen.

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/<TRIGGER_URL>
-H 'Authorization: Bearer <ACCESS_TOKEN>' 
-H 'Cache-Control: no-cache' 
-H 'X-Api-Key: <API_KEY>' 
-H 'Content-Type: application/json;charset=utf-8' 
-H 'Content-Length:79' 
-i
-d {
-d "source:":"API",
-d "parameters":{
-d "fileToTarget":"profile.txt",
-d "discountDesc":"Running shoes"
-d } 
```

## Stap 2: Workflow 1 configureren {#step-2--configuring-workflow-1}

Workflow 1 wordt als volgt samengesteld:

* **[!UICONTROL External signal]** activiteit: waar de externe parameters moeten worden gedeclareerd om binnen de werkstroom te worden gebruikt.
* **[!UICONTROL Transfer file]** activiteit: Hiermee importeert u het bestand met de naam die in de parameters is gedefinieerd.
* **[!UICONTROL Load file]** activity: loads data from the imported file into the database.
* **[!UICONTROL Update data]** activity: insert or update the database with data from the imported file.
* **[!UICONTROL Test]** activiteit: controleert of er gegevens zijn geïmporteerd.
* **[!UICONTROL Save audience]** activiteit: als het bestand gegevens bevat, worden de profielen in een publiek opgeslagen.
* **[!UICONTROL End activity]** activiteit: roept Werkschema 2 met de parameters die u binnen het wilt gebruiken.

![](assets/extsignal_uc_wkf1.png)

Voer de onderstaande stappen uit om de workflow te configureren:

1. Declareer de parameters die in de API vraag zijn bepaald. Om dit te doen, open **[!UICONTROL External signal]** en voeg vervolgens de namen en typen van de parameters toe.

   ![](assets/extsignal_uc1.png)

1. Add a **[!UICONTROL Transfer file]** activity to import data into the database.To do this, drag and drop the activity, open it, then select the **[!UICONTROL Protocol]** tab.
1. Selecteer **[!UICONTROL Use a dynamic file path]** en gebruikt u vervolgens de **fileToTarget** parameter als het over te dragen bestand:

   ```
   $(vars/@fileToTarget)
   ```

   ![](assets/extsignal_uc2.png)

1. Laad de gegevens uit het bestand in de database.

   Hiervoor sleept u een **[!UICONTROL Load file]** activiteit in het werkschema, dan vorm het op uw behoeften.

1. De database invoegen en bijwerken met gegevens uit het geïmporteerde bestand.

   U doet dit door een **[!UICONTROL Update data]** activiteit, dan selecteer **[!UICONTROL Identification]** tab om een verzoeningscriterium toe te voegen (in ons geval **email** veld).

   ![](assets/extsignal_uc3.png)

1. Selecteer **[!UICONTROL Fields to update]** en geeft u vervolgens de velden op die u wilt bijwerken in de database (in ons geval de **firstname** en **email** velden).

   ![](assets/extsignal_uc4.png)

1. Controleer of gegevens uit het bestand zijn opgehaald. Hiervoor sleept u een **[!UICONTROL Test]** in de workflow en klik vervolgens op de knop **[!UICONTROL Add an element]** om een voorwaarde toe te voegen.
1. Geef de voorwaarde een naam en definieer deze. In our case, we want to test if the outbound transition contains data with the syntax below:

   ```
   $long(vars/@recCount)>0
   ```

   ![](assets/extsignal_uc5.png)

1. Als gegevens worden opgehaald, slaat u deze op in een publiek. Hiervoor voegt u een **[!UICONTROL Save audience]** aan de **Doel is niet leeg** openen.
1. Selecteer **[!UICONTROL Use a dynamic label]** en gebruikt u vervolgens de **fileToTarget** parameter als label van het publiek:

   ```
   $(vars/@fileToTarget)
   ```

   ![](assets/extsignal_uc6.png)

1. Sleep een **[!UICONTROL End]** activiteit die Werkschema 2 met parameters zal roepen, dan het openen.
1. Select the **[!UICONTROL External signal]** tab, then specify the workflow to trigger and its associated signal activity.
1. Bepaal de parameters die u binnen Werkschema 2 en hun bijbehorende waarden wilt gebruiken.

   In ons geval willen we de parameters doorgeven die oorspronkelijk in de API-aanroep zijn gedefinieerd (**fileToTarget** en **discontoDesc**) en een aanvullende **segmentCode** parameter met een constante waarde (&quot;20% korting&quot;).

   ![](assets/extsignal_uc7.png)

Werkschema 1 wordt gevormd, kunt u Werkschema 2 nu bouwen. Raadpleeg [deze sectie](../../automating/using/use-case-calling-workflow.md#step-3--configuring-workflow-2) voor meer informatie.

## Stap 3: Workflow 2 configureren {#step-3--configuring-workflow-2}

Workflow 2 wordt als volgt samengesteld:

* **[!UICONTROL External signal]** activity: where the parameters must be declared in order to be used within the workflow.
* **[!UICONTROL Read audience]** activiteit: leest het publiek dat is opgeslagen in Workflow 1.
* **[!UICONTROL Email delivery]** activiteit: verzendt een terugkerend bericht naar het gerichte publiek, gepersonaliseerd met parameters.

![](assets/extsignal_uc_wkf2.png)

Follow the steps below to configure the workflow:

1. Declareer de parameters die in Werkschema 1 zijn bepaald.

   Om dit te doen, open **[!UICONTROL External signal]** activiteit, dan voeg de naam en het type van elke parameter toe die in **[!UICONTROL End]** activiteit van Workflow 1.

   ![](assets/extsignal_uc8.png)

1. Gebruik het publiek dat in Werkstroom 1 is opgeslagen. To do this, drag and drop a **[!UICONTROL Read audience]** activity into the workflow, then open it.
1. Selecteer **[!UICONTROL Use a dynamic audience]** en gebruikt u vervolgens de **fileToTarget** parameter als de naam van het publiek dat moet worden gelezen:

   ```
   $(vars/@fileToTarget)
   ```

   ![](assets/extsignal_uc9.png)

1. Geef de uitgaande overgang een naam op basis van de **segmentCode** parameter.

   Selecteer hiervoor de optie **[!UICONTROL Transition]** en vervolgens de **[!UICONTROL Use a dynamic segment code]** optie.

1. Gebruik de **segmentCode** parameter als naam van de uitgaande overgang:

   ```
   $(vars/@segmentCode)
   ```

   ![](assets/extsignal_uc10.png)

1. Sleep een **[!UICONTROL Email delivery]** activiteit om een bericht naar het publiek te verzenden.
1. Identificeer de parameters in het bericht te gebruiken om het met te personaliseren **discontoDesc** parameter. Hiervoor opent u de geavanceerde opties van de activiteit en voegt u vervolgens de parameternaam en -waarde toe.

   ![](assets/extsignal_uc10b.png)

1. U kunt het bericht nu vormen. Open de activiteit en selecteer **[!UICONTROL Recurring email]**.

   ![](assets/extsignal_uc11.png)

1. Selecteer de sjabloon die u wilt gebruiken en definieer de e-maileigenschappen naar wens.
1. Gebruik de **discontoDesc** parameter als een verpersoonlijkingsgebied. Selecteer dit in de lijst met personalisatievelden.

   ![](assets/extsignal_uc13.png)

1. U kunt nu klaar zijn met het configureren van het bericht en het vervolgens op de gebruikelijke manier verzenden.

   ![](assets/extsignal_uc14.png)

## Workflows uitvoeren {#executing-the-workflows}

Once the workflows has been built, you can execute them. Make sure the two workflows are started before performing the API call.
