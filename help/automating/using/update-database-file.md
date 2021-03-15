---
solution: Campaign Standard
product: campaign
title: De database bijwerken met externe data
description: In dit geval wordt beschreven hoe u profielen aan de Adobe Campaign-database kunt toevoegen of bijwerken met de gegevens uit het bestand.
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: writer,main
feature: Workflows
role: Gegevensarchitect
level: Intermediair
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 32%

---


# De database bijwerken met externe data {#update-database-file}

Het volgende voorbeeld toont de configuratie van een **[!UICONTROL Update data]** activiteit na een **[!UICONTROL Load file]** activiteit. Het doel van deze workflow is om profielen aan de Adobe Campaign-database toe te voegen of bij te werken met de data uit het bestand.

In dit voorbeeld wordt de afstemmingssleutel gebruikt met het **e-mailadres**. Het bestand dat wordt geladen in de [Load file](../../automating/using/load-file.md) activiteit is een **.txt** formaat dossier dat de volgende voorbeeldgegevens bevat:

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

De [Update data](../../automating/using/update-data.md) activiteit wordt gevormd als volgt:

![](assets/deduplication_example2_writer1.png)

![](assets/deduplication_example2_writer2.png)
