---
title: Gegevensupdate met afstemming
description: In het volgende voorbeeld ziet u een workflow die een publiek van profielen rechtstreeks maakt vanuit een geïmporteerd bestand dat nieuwe clients bevat.
page-status-flag: never-activated
uuid: 7884db8c-1717-4724-be15-3b0b32ccc071
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: cb8c43f4-9cdd-4e85-99a4-004b36b336aa
context-tags: reconciliation,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 175709a41607bb9d64da7fac77dd749fa84f7360
workflow-type: tm+mt
source-wordcount: '128'
ht-degree: 0%

---


# Gegevensupdate met afstemming {#data-update-reconciliation}

In het volgende voorbeeld ziet u een workflow die een publiek van profielen rechtstreeks maakt vanuit een geïmporteerd bestand dat nieuwe clients bevat. Het bestaat uit de volgende activiteiten:

![](assets/identification_example2.png)

* Een [activiteit van het Dossier](../../automating/using/load-file.md) van de Lading, die haar gegevens van het te importeren dossier laadt en ontdekt. Het geïmporteerde bestand bevat de volgende gegevens:

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

* Een [afstemmingsactiviteit](../../automating/using/reconciliation.md) die elke kolom van het geladen bestand koppelt aan een kolom met profielafmetingen. De bestandsrecords die niet kunnen worden geïdentificeerd (ontbrekende gegevens, incompatibel gegevenstype, enz.) worden genegeerd om de integriteit van de uiteindelijke publieksgegevens te behouden.

   ![](assets/identification_example1.png)

* Een publieksactiviteit [Opslaan](../../automating/using/save-audience.md) waarmee het publiek van profielen wordt opgeslagen.

   ![](assets/identification_example3.png)
