---
title: De database bijwerken met externe gegevens
description: In dit geval wordt beschreven hoe u profielen aan de Adobe Campaign-database kunt toevoegen of bijwerken met de gegevens uit het bestand.
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: writer,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 2df7fbed-b979-4706-bd56-83f712cc3070
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '106'
ht-degree: 11%

---

# De database bijwerken met externe gegevens {#update-database-file}

In het volgende voorbeeld wordt de configuratie van een **[!UICONTROL Update data]** activiteit na een **[!UICONTROL Load file]** activiteit. Het doel van deze workflow is om profielen toe te voegen aan of bij te werken naar de Adobe Campaign-database met de gegevens die uit het bestand zijn opgehaald.

In dit voorbeeld wordt de verzoeningssleutel gebruikt: **mailadres**. Het bestand dat in het dialoogvenster [Bestand laden](../../automating/using/load-file.md) activiteit is **.txt** opmaakbestand met de volgende voorbeeldgegevens:

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

De [Gegevens bijwerken](../../automating/using/update-data.md) activiteit is als volgt geconfigureerd:

![](assets/deduplication_example2_writer1.png)

![](assets/deduplication_example2_writer2.png)
