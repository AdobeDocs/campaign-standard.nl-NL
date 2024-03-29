---
title: Invoer van externe signalen en gegevens
description: Het volgende voorbeeld illustreert de Externe signaalactiviteit die met de invoer van gegevens wordt gebruikt.
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: signal,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: e2997cf5-861b-4202-aeb7-3a47c4d55bef
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 79%

---

# Invoer van externe signalen en gegevens {#external-signal-data-import}

Het volgende voorbeeld illustreert de activiteit **[!UICONTROL External signal]** in een typisch gebruiksscenario. Er worden data geïmporteerd in een bronworkflow. Nadat het importeren is voltooid en de database is bijgewerkt, wordt een tweede workflow geactiveerd. Deze tweede workflow wordt gebruikt om een aggregaat van de geïmporteerde data bij te werken.

De bronworkflow wordt als volgt weergegeven:

* Een activiteit [Bestand laden](../../automating/using/load-file.md) uploadt een bestand met nieuwe aankoopdata. Merk op dat de [database dienovereenkomstig is uitgebreid](../../developing/using/data-model-concepts.md) aangezien aankoopdata niet standaard aanwezig zijn in de datamart.

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

* Bij een activiteit [Afstemming](../../automating/using/reconciliation.md) worden de koppelingen tussen de geïmporteerde data en de database tot stand gebracht, zodat de transactiedata correct aan profielen en producten worden gekoppeld.
* Bij een activiteit [Data bijwerken](../../automating/using/update-data.md) wordt de resource Transacties van de database ingevoegd en bijgewerkt met de binnenkomende data.
* An [Einde](../../automating/using/start-and-end.md) activiteit brengt de bestemmingswerkstroom teweeg, die wordt gebruikt om aggregaten bij te werken.

![](assets/signal_example_source1.png)

De bestemmingsworkflow wordt als volgt weergegeven:

* An [Extern signaal](../../automating/using/external-signal.md) activiteit wacht op een succesvolle bronwerkstroom.
* Een activiteit [Query](../../automating/using/query.md#enriching-data) benadert doelgericht profielen en verrijkt deze met een verzamelingsreeks om de laatste aankoopdatum op te halen.
* Met een activiteit [Data bijwerken](../../automating/using/update-data.md) worden de aanvullende data opgeslagen in een speciaal aangepast veld. Merk op dat de profielresource is uitgebreid om het veld **Last purchase date** toe te voegen.

![](assets/signal_example_source2.png)
