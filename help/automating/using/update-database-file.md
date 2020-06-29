---
title: De database bijwerken met externe gegevens
description: In dit geval wordt beschreven hoe u profielen aan de Adobe Campaign-database kunt toevoegen of bijwerken met de gegevens uit het bestand.
page-status-flag: never-activated
uuid: 1dc55db5-affd-4688-b673-adfb8c1338b5
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: 4db83c95-4b75-4a16-8dbf-bd8940431fa9
context-tags: writer,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7ffa48365875883a98904d6b344ac005afe26e18
workflow-type: tm+mt
source-wordcount: '106'
ht-degree: 0%

---


# De database bijwerken met externe gegevens {#update-database-file}

Het volgende voorbeeld toont de configuratie van een **[!UICONTROL Update data]** activiteit na een **[!UICONTROL Load file]** activiteit. Het doel van deze workflow is om profielen toe te voegen aan of bij te werken naar de Adobe Campaign-database met de gegevens die uit het bestand zijn opgehaald.

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

De [activiteit van de Gegevens](../../automating/using/update-data.md) van de Update wordt gevormd als volgt:

![](assets/deduplication_example2_writer1.png)

![](assets/deduplication_example2_writer2.png)
