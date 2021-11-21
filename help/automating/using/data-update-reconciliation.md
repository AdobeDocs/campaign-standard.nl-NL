---
title: Gegevensupdate met afstemming
description: In het volgende voorbeeld ziet u een workflow die een doelgroep van profielen rechtstreeks maakt op basis van een geïmporteerd bestand dat nieuwe klanten bevat.
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: reconciliation,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: cfca6202-791d-4baf-b5ed-677d2480cf06
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '128'
ht-degree: 67%

---

# Gegevensupdate met afstemming {#data-update-reconciliation}

In het volgende voorbeeld ziet u een workflow die een doelgroep van profielen rechtstreeks maakt op basis van een geïmporteerd bestand dat nieuwe klanten bevat. De workflow bestaat uit de volgende activiteiten:

![](assets/identification_example2.png)

* A [Bestand laden](../../automating/using/load-file.md) activiteit, die de gegevens van het te importeren bestand laadt en detecteert. Het geïmporteerde bestand bevat de volgende data:

   ```
   lastname;firstname;email;dateofbirth
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

* A [Verzoening](../../automating/using/reconciliation.md) activiteit, die elke kolom van het geladen dossier aan een kolom van de profielafmeting verbindt. De bestandsrecords die niet kunnen worden geïdentificeerd (wegens ontbrekende data, incompatibel datatype, enz.), worden genegeerd om de integriteit van de uiteindelijke doelgroepsdata te handhaven.

   ![](assets/identification_example1.png)

* A [Adviezen opslaan](../../automating/using/save-audience.md) activiteit, die het publiek van profielen bewaart.

   ![](assets/identification_example3.png)
