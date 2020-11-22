---
solution: Campaign Standard
product: campaign
title: De database bijwerken met externe data
description: In dit geval wordt beschreven hoe u profielen aan de Adobe Campaign-database kunt toevoegen of bijwerken met de gegevens uit het bestand.
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: writer,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '106'
ht-degree: 33%

---


# De database bijwerken met externe data {#update-database-file}

The following example shows the configuration of an **[!UICONTROL Update data]** activity following a **[!UICONTROL Load file]** activity. Het doel van deze workflow is om profielen aan de Adobe Campaign-database toe te voegen of bij te werken met de data uit het bestand.

In dit voorbeeld wordt het **e-mailadres** gebruikt als afstemmingssleutel. Het bestand dat wordt geladen in de activiteit [Bestand](../../automating/using/load-file.md) laden is een bestand met de indeling **.txt** dat de volgende voorbeeldgegevens bevat:

```
lastname;firstname;email;birthdate
jackman;megan;megan.jackman@testmail.com;07/08/1975
phillips;edward;phillips@testmail.com;09/03/1986
weaver;justin;justin_w@testmail.com;11/15/1990
martin;babeth;babeth_martin@testmail.net;11/25/1964
reese;richard;rreese@testmail.com;02/08/1987
cage;nathalie;cage.nathalie227@testmail.com;07/03/1989
xiuxiu;andrea;andrea.xiuxiu@testmail.com;09/12/1992
grimes;daryl;daryl_890@testmail.com;12/06/1979
tycoon;tyreese;tyreese_t@testmail.net;10/08/1971
```

The [Update data](../../automating/using/update-data.md) activity is configured as follows:

![](assets/deduplication_example2_writer1.png)

![](assets/deduplication_example2_writer2.png)
