---
title: Invoer van externe signalen en gegevens
description: Het volgende voorbeeld illustreert de Externe signaalactiviteit die met de invoer van gegevens wordt gebruikt.
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
source-git-commit: c3911232a3cce00c2b9a2e619f090a7520382dde
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 0%

---


# Invoer van externe signalen en gegevens {#external-signal-data-import}

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
* Een activiteit van het [Eind](../../automating/using/start-and-end.md) teweegbrengt het bestemmingswerkschema teweeg, dat wordt gebruikt om aggregaten bij te werken.

![](assets/signal_example_source1.png)

De doelworkflow wordt als volgt weergegeven:

* Een [Externe signaalactiviteit](../../automating/using/external-signal.md) wacht op een succesvolle bronwerkstroom.
* Een activiteit van de [Vraag](../../automating/using/query.md#enriching-data) richt profielen en verrijkt hen met een inzameling die wordt geplaatst om de laatste aankoopdatum terug te winnen.
* Met een [updategegevensactiviteit](../../automating/using/update-data.md) worden de aanvullende gegevens opgeslagen in een speciaal aangepast veld. Let op: de profielbron is uitgebreid om het veld **Laatste aankoopdatum** toe te voegen.

![](assets/signal_example_source2.png)
