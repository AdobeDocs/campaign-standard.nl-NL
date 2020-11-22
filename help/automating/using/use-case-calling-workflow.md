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
source-wordcount: '977'
ht-degree: 1%

---


# Gebruiksscenario {#use-case}

Het onderstaande gebruiksgeval laat zien hoe u een workflow met parameters in uw workflows kunt aanroepen.

Het doel is een workflow te activeren vanaf een API-aanroep met externe parameters. Deze workflow laadt gegevens uit een bestand in uw database en maakt een gekoppeld publiek. Zodra het publiek is gecreeerd, zal een tweede werkschema worden teweeggebracht om een bericht te verzenden dat met de externe parameters wordt gepersonaliseerd die in de API vraag worden bepaald.

Voor dit gebruik moet u de volgende handelingen uitvoeren:

1. **Maak een API vraag** om Werkschema 1 met externe parameters teweeg te brengen. Zie [stap 1: De API-aanroep](../../automating/using/use-case-calling-workflow.md#step-1--configuring-the-api-call)configureren.
1. **Workflow 1** samenstellen: de workflow zal een bestand overbrengen en in de database laden . Vervolgens wordt getest of de gegevens leeg zijn of niet en worden de profielen uiteindelijk in een publiek opgeslagen. Tot slot zal het Werkschema 2 teweegbrengen. Zie [stap 2: Workflow 1](../../automating/using/use-case-calling-workflow.md#step-2--configuring-workflow-1)configureren.
1. **Workflow 2** samenstellen: De workflow leest het publiek dat in Workflow 1 is gemaakt en stuurt vervolgens een gepersonaliseerd bericht naar de profielen, met een segmentcode die met de parameters is aangepast. Zie [stap 3: Workflow 2](../../automating/using/use-case-calling-workflow.md#step-3--configuring-workflow-2)configureren.

![](assets/extsignal_uc_process.png)

## Vereisten {#prerequisites}

Alvorens de werkschema&#39;s te vormen, moet u Werkschema 1 en 2 met een **[!UICONTROL External signal]** activiteit in elk van hen tot stand brengen. Deze manier, zult u deze signaalactiviteiten kunnen richten wanneer het roepen van de werkschema&#39;s.

## Stap 1: De API-aanroep configureren {#step-1--configuring-the-api-call}

Maak een API vraag om Werkstroom 1 met parameters teweeg te brengen. Raadpleeg de documentatie [van de API&#39;s van](../../api/using/triggering-a-signal-activity.md)Campaign Standard REST voor meer informatie over de API-aanroepsyntaxis.

In ons geval willen we de workflow met de volgende parameters bellen:

* **fileToTarget**: de naam van het bestand dat we in de database willen importeren.
* **kortingDesc**: de beschrijving die wij in de levering voor de korting willen tonen.

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
* **[!UICONTROL Load file]** activiteit: laadt gegevens uit het geïmporteerde bestand in de database.
* **[!UICONTROL Update data]** activiteit: de database invoegen of bijwerken met gegevens uit het geïmporteerde bestand.
* **[!UICONTROL Test]** activiteit: controleert of er gegevens zijn geïmporteerd.
* **[!UICONTROL Save audience]** activiteit: als het bestand gegevens bevat, worden de profielen in een publiek opgeslagen.
* **[!UICONTROL End activity]** activiteit: roept Werkschema 2 met de parameters die u binnen het wilt gebruiken.

![](assets/extsignal_uc_wkf1.png)

Voer de onderstaande stappen uit om de workflow te configureren:

1. Declareer de parameters die in de API vraag zijn bepaald. Hiervoor opent u de **[!UICONTROL External signal]** activiteit en voegt u de namen en typen van de parameters toe.

   ![](assets/extsignal_uc1.png)

1. Voeg een **[!UICONTROL Transfer file]** activiteit toe om gegevens in het gegevensbestand in te voeren. Om dit te doen, sleep en laat vallen de activiteit, open het, dan selecteer het **[!UICONTROL Protocol]** lusje.
1. Selecteer de **[!UICONTROL Use a dynamic file path]** optie en gebruik vervolgens de parameter **fileToTarget** als het over te dragen bestand:

   ```
   $(vars/@fileToTarget)
   ```

   ![](assets/extsignal_uc2.png)

1. Laad de gegevens uit het bestand in de database.

   Om dit te doen, sleep en laat vallen een **[!UICONTROL Load file]** activiteit in het werkschema, dan vorm het op uw behoeften.

1. De database invoegen en bijwerken met gegevens uit het geïmporteerde bestand.

   U doet dit door een **[!UICONTROL Update data]** activiteit te slepen en neer te zetten en vervolgens het **[!UICONTROL Identification]** tabblad te selecteren om verzoeningscriteria toe te voegen (in ons geval het veld **E-mail** ).

   ![](assets/extsignal_uc3.png)

1. Selecteer het **[!UICONTROL Fields to update]** tabblad en geef vervolgens de velden op die u wilt bijwerken in de database (in ons geval de velden **firstname** en **email** ).

   ![](assets/extsignal_uc4.png)

1. Controleer of gegevens uit het bestand zijn opgehaald. U doet dit door een **[!UICONTROL Test]** activiteit naar de werkstroom te slepen en vervolgens op de **[!UICONTROL Add an element]** knop te klikken om een voorwaarde toe te voegen.
1. Geef de voorwaarde een naam en definieer deze. In ons geval, willen wij testen of bevat de uitgaande overgang gegevens met de syntaxis hieronder:

   ```
   $long(vars/@recCount)>0
   ```

   ![](assets/extsignal_uc5.png)

1. Als gegevens worden opgehaald, slaat u deze op in een publiek. Hiervoor voegt u een **[!UICONTROL Save audience]** activiteit toe aan het **doel en maakt u de overgang niet leeg** . Open vervolgens de bewerking.
1. Selecteer de **[!UICONTROL Use a dynamic label]** optie en gebruik vervolgens de parameter **fileToTarget** als label van het publiek:

   ```
   $(vars/@fileToTarget)
   ```

   ![](assets/extsignal_uc6.png)

1. Sleep en zet een **[!UICONTROL End]** activiteit neer die Werkschema 2 met parameters zal roepen, dan het openen.
1. Selecteer het **[!UICONTROL External signal]** tabblad en geef vervolgens de workflow op die u wilt activeren en de bijbehorende signaalactiviteit.
1. Bepaal de parameters die u binnen Werkschema 2 en hun bijbehorende waarden wilt gebruiken.

   In ons geval, willen wij de parameters die oorspronkelijk in de API vraag (**fileToTarget** en **discontoDesc**) werden bepaald, en een extra **segmentCode** parameter met een constante waarde (&quot;20% korting&quot;) overgaan.

   ![](assets/extsignal_uc7.png)

Werkschema 1 wordt gevormd, kunt u Werkschema 2 nu bouwen. Raadpleeg [deze sectie](../../automating/using/use-case-calling-workflow.md#step-3--configuring-workflow-2) voor meer informatie.

## Stap 3: Workflow 2 configureren {#step-3--configuring-workflow-2}

Workflow 2 wordt als volgt samengesteld:

* **[!UICONTROL External signal]** activiteit: waar de parameters moeten worden gedeclareerd om binnen de werkstroom te worden gebruikt.
* **[!UICONTROL Read audience]** activiteit: leest het publiek dat is opgeslagen in Workflow 1.
* **[!UICONTROL Email delivery]** activiteit: verzendt een terugkerend bericht naar het gerichte publiek, gepersonaliseerd met parameters.

![](assets/extsignal_uc_wkf2.png)

Voer de onderstaande stappen uit om de workflow te configureren:

1. Declareer de parameters die in Werkschema 1 zijn bepaald.

   Om dit te doen, open de **[!UICONTROL External signal]** activiteit, dan voeg de naam en het type van elke parameter toe die in de **[!UICONTROL End]** activiteit van Werkschema 1 wordt bepaald.

   ![](assets/extsignal_uc8.png)

1. Gebruik het publiek dat in Werkstroom 1 is opgeslagen. U doet dit door een **[!UICONTROL Read audience]** activiteit naar de werkstroom te slepen en vervolgens te openen.
1. Selecteer de **[!UICONTROL Use a dynamic audience]** optie en gebruik vervolgens de parameter **fileToTarget** als de naam van het publiek dat u wilt lezen:

   ```
   $(vars/@fileToTarget)
   ```

   ![](assets/extsignal_uc9.png)

1. Noem de uitgaande overgang volgens de **segmentCode** parameter.

   To do this, select the **[!UICONTROL Transition]** tab, then the **[!UICONTROL Use a dynamic segment code]** option.

1. Gebruik de **segmentCode** parameter als naam van de uitgaande overgang:

   ```
   $(vars/@segmentCode)
   ```

   ![](assets/extsignal_uc10.png)

1. Sleep een **[!UICONTROL Email delivery]** activiteit om een bericht naar het publiek te verzenden.
1. Identificeer de parameters in het bericht te gebruiken om het met de parameter **discontoDesc** te personaliseren. Hiervoor opent u de geavanceerde opties van de activiteit en voegt u vervolgens de parameternaam en -waarde toe.

   ![](assets/extsignal_uc10b.png)

1. U kunt het bericht nu vormen. Open de activiteit en selecteer vervolgens **[!UICONTROL Recurring email]**.

   ![](assets/extsignal_uc11.png)

1. Selecteer de sjabloon die u wilt gebruiken en definieer de e-maileigenschappen naar wens.
1. Gebruik de parameter **kortingDesc** als verpersoonlijkingsgebied. Selecteer dit in de lijst met personalisatievelden.

   ![](assets/extsignal_uc13.png)

1. U kunt nu klaar zijn met het configureren van het bericht en het vervolgens op de gebruikelijke manier verzenden.

   ![](assets/extsignal_uc14.png)

## Workflows uitvoeren {#executing-the-workflows}

Nadat de workflows zijn samengesteld, kunt u deze uitvoeren. Zorg ervoor dat de twee workflows zijn gestart voordat u de API-aanroep uitvoert.
