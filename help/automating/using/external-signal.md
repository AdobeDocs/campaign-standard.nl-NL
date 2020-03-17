---
title: Extern signaal
description: De activiteit van het Externe signaal brengt een werkschema teweeg wanneer sommige voorwaarden met succes in een andere werkschema worden vervuld.
page-status-flag: never-activated
uuid: 884b6daf-bfd9-440b-8336-004b80c76def
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 911c71b5-da8b-4916-b645-13bba6d21715
context-tags: signal,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: aee0e0437cbfe578cb2f715a2433099c79dd1748

---


# Extern signaal{#external-signal}

## Beschrijving {#description}

![](assets/signal.png)

De **[!UICONTROL External signal]** activiteit brengt een werkschema teweeg wanneer sommige voorwaarden met succes in een andere werkschema of van een REST API vraag worden vervuld.

## Gebruikscontext {#context-of-use}

De **[!UICONTROL External signal]** activiteit wordt gebruikt om verschillende processen te organiseren en te ordenen die deel van de zelfde klantenreis in verschillende werkschema&#39;s uitmaken. Het staat toe om één werkschema van een andere te beginnen, toelatend om complexere klantenreizen te steunen, terwijl het kunnen beter controleren en reageren in geval van kwestie.

De **[!UICONTROL External signal]** activiteit wordt ontworpen om als eerste activiteit van een werkschema worden geplaatst. Deze kan worden geactiveerd door de **[!UICONTROL End]** activiteit van een andere workflow of door een REST API-aanroep (zie voor meer informatie de [API-documentatie](../../api/using/triggering-a-signal-activity.md)).

Wanneer dit wordt geactiveerd, kunnen externe parameters worden gedefinieerd en beschikbaar zijn in de variabelen voor workflowgebeurtenissen. Het proces om een werkschema met externe parameters te roepen is gedetailleerd in [deze sectie](../../automating/using/calling-a-workflow-with-external-parameters.md).

>[!NOTE]
>
>De activiteit kan niet vaker dan om de 10 minuten worden geactiveerd.

Merk op dat een **[!UICONTROL External signal]** activiteit van verscheidene verschillende gebeurtenissen kan worden teweeggebracht. In dat geval **[!UICONTROL External signal]** wordt de activering uitgevoerd zodra een van de bronworkflows of API-aanroepen wordt uitgevoerd. Het vereist niet dat alle bronwerkschema&#39;s worden gebeëindigd.

## Configuratie {#configuration}

Wanneer het vormen van een extern signaal, is het belangrijk om de **[!UICONTROL External signal]** activiteit in het bestemmingswerkschema eerst te vormen. Zodra deze configuratie wordt gedaan, wordt de **[!UICONTROL External signal]** activiteit van dit werkschema beschikbaar om de **[!UICONTROL End]** activiteit van het bronwerkschema te vormen.

1. Sleep een **[!UICONTROL External signal]** activiteit naar de doelworkflow.
1. Selecteer de activiteit, dan open het gebruikend de ![](assets/edit_darkgrey-24px.png) knoop van de snelle acties die verschijnen.
1. Bewerk het label van de activiteit. Dit etiket is nodig wanneer het vormen van het bronwerkschema dat het **[!UICONTROL External signal]** teweegbrengt.

   Als u de werkstroom met parameters wilt roepen, gebruik het **[!UICONTROL Parameters]** gebied om hen te verklaren. For more on this, refer to [this section](../../automating/using/calling-a-workflow-with-external-parameters.md#declaring-the-parameters-in-the-external-signal-activity).

   ![](assets/external_signal_configuration.png)

1. Bevestig de configuratie van uw activiteit, voeg om het even welke andere activiteit toe u wenst en sla uw werkschema op.

   >[!NOTE]
   >
   >Ga als volgt te werk als u de doelworkflow wilt activeren vanuit een andere workflow. Als u de doelworkflow wilt activeren via een REST API-aanroep, raadpleegt u de [API-documentatie](../../api/using/triggering-a-signal-activity.md) voor meer informatie.

1. Open de bronworkflow en selecteer een **[!UICONTROL End]** activiteit. Als er geen **[!UICONTROL End]** activiteit beschikbaar is, voeg na de laatste activiteit van een tak van het werkschema toe.

   Sommige activiteiten hebben geen uitgaande overgang door gebrek. Van het **[!UICONTROL Properties]** lusje van deze activiteiten, kunt u een uitgaande overgang toevoegen.

   Ga in een **[!UICONTROL Update data]** activiteit bijvoorbeeld naar het **[!UICONTROL Transitions]** tabblad en controleer de **[!UICONTROL Add an outbound transition without the population]** optie. Met deze optie kunt u een overgang toevoegen die geen gegevens bevat en geen overbodige ruimte inneemt op uw systeem. Het wordt enkel gebruikt om de extra **[!UICONTROL End]** activiteit te verbinden die het bestemmingswerkschema teweegbrengt.

   ![](assets/external_signal_empty_transition.png)

1. Selecteer op het **[!UICONTROL External signal]** tabblad van de **[!UICONTROL End]** activiteit de doelworkflow en de **[!UICONTROL External signal]** activiteit die binnen die workflow moet worden geactiveerd.

   Wanneer u een **[!UICONTROL End]** activiteit plaatst om een andere werkschema teweeg te brengen, wordt zijn pictogram bijgewerkt met een extra signaalsymbool.

   Als u de workflow met parameters wilt aanroepen, gebruikt u het **[!UICONTROL Parameters and values]** gebied. For more on this, refer to [this section](../../automating/using/calling-a-workflow-with-external-parameters.md#defining-the-parameters-when-calling-the-workflow).

   ![](assets/external_signal_end.png)

1. Sla de bronworkflow op.

Zodra de **[!UICONTROL End]** activiteit van het bronwerkschema of de REST API vraag wordt uitgevoerd, wordt het bestemmingswerkschema automatisch teweeggebracht van de **[!UICONTROL External signal]** activiteit.

>[!NOTE]
>
>De doelworkflow moet handmatig worden gestart voordat deze kan worden geactiveerd. Wanneer begonnen, **[!UICONTROL External activity]** wordt het geactiveerd en wacht op het signaal van het bronwerkschema.

## Voorbeeld {#example}

Het volgende voorbeeld illustreert de **[!UICONTROL External signal]** activiteit in een typisch gebruiksgeval. Er worden gegevens geïmporteerd in een bronwerkstroom. Nadat het importeren is voltooid en de database is bijgewerkt, wordt een tweede workflow geactiveerd. Deze tweede workflow wordt gebruikt om een aggregaat van de geïmporteerde gegevens bij te werken.

De bronworkflow wordt als volgt weergegeven:

* Een [activiteit van het Laad dossier](../../automating/using/load-file.md) uploadt een dossier dat nieuwe aankoopgegevens bevat. Merk op dat het [gegevensbestand dienovereenkomstig is uitgebreid](../../developing/using/data-model-concepts.md) aangezien de aankoopgegevens niet door gebrek in datamart aanwezig zijn.

   Bijvoorbeeld:

   ```
   tcode;tdate;customer;product;tamount
   aze123;21/05/2015;dannymars@example.com;A2;799
   aze124;28/05/2015;dannymars@example.com;A7;8
   aze125;31/07/2015;john.smith@example.com;A7;8
   aze126;14/12/2015;john.smith@example.com;A10;4
   aze127;02/01/2016;dannymars@example.com;A3;79
   aze128;04/03/2016;clara.smith@example.com;A8;149
   ```

* Bij een [afstemmingsactiviteit](../../automating/using/reconciliation.md) worden de koppelingen tussen de geïmporteerde gegevens en de database tot stand gebracht, zodat de transactiegegevens correct zijn gekoppeld aan profielen en producten.
* Een de gegevensactiviteit van de [Update](../../automating/using/update-data.md) neemt en werkt het middel van Transacties van het gegevensbestand met de inkomende gegevens op.
* Een **[!UICONTROL End]** activiteit activeert de bestemmingswerkstroom, die wordt gebruikt om aggregaten bij te werken.

![](assets/signal_example_source1.png)

De doelworkflow wordt als volgt weergegeven:

* Een **[!UICONTROL External signal]** activiteit wacht op een succesvolle bronwerkstroom.
* Een activiteit van de [Vraag](../../automating/using/query.md#enriching-data) richt profielen en verrijkt hen met een inzameling die wordt geplaatst om de laatste aankoopdatum terug te winnen.
* Met een [updategegevensactiviteit](../../automating/using/update-data.md) worden de aanvullende gegevens opgeslagen in een speciaal aangepast veld. Let op: de profielbron is uitgebreid om het veld **Laatste aankoopdatum** toe te voegen.

![](assets/signal_example_source2.png)

