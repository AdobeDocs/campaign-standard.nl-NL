---
title: Profielen vanuit een bestand aanmelden voor een specifieke service
description: Met deze gebruiksaanwijzing kunt u zien hoe u een bestand met profielen importeert en deze abonneert op een bestaande service.
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: setOfService,workflow,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 06ae4a5c-f112-4aac-b776-437ac35a8f02
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 53%

---

# Profielen na het importeren van een bestand abonneren op een specifieke service {#subscribing-profiles-to-a-specific-service-after-importing-a-file}

In dit voorbeeld ziet u hoe u een bestand met profielen importeert en deze abonneert op een bestaande service. Nadat het bestand is geïmporteerd, moet een afstemming worden uitgevoerd, zodat de geïmporteerde data kunnen worden geïdentificeerd als profielen. Om ervoor te zorgen dat het bestand geen duplicaten bevat, wordt een ontdubbelingsactiviteit uitgevoerd op de data.

De workflow wordt als volgt weergegeven:

![](assets/subscription_activity_example1.png)

* A [Bestand laden](../../automating/using/load-file.md) Deze activiteit laadt het profieldossier en bepaalt de structuur van de ingevoerde kolommen.

  In dit voorbeeld heeft het geladen bestand de csv-indeling en bevat het de volgende data:

  ```
  lastname;firstname;email;birthdate;subdate
  jackman;megan;megan.jackman@testmail.com;07/08/1975;10/08/2017
  phillips;edward;phillips@testmail.com;09/03/1986;10/08/2017
  weaver;justin;justin_w@testmail.com;11/15/1990;10/08/2017
  martin;babeth;babeth_martin@testmail.net;11/25/1964;10/08/2017
  reese;richard;rreese@testmail.com;02/08/1987;11/08/2017
  cage;nathalie;cage.nathalie227@testmail.com;07/03/1989;11/08/2017
  xiuxiu;andrea;andrea.xiuxiu@testmail.com;09/12/1992;11/08/2017
  grimes;daryl;daryl_890@testmail.com;12/06/1979;12/08/2017
  tycoon;tyreese;tyreese_t@testmail.net;10/08/1971;12/08/2017
  ```

  ![](assets/subscription_activity_example2.png)

* A [Verzoening](../../automating/using/reconciliation.md) de activiteit identificeert de gegevens van het dossier als deel uitmakend van de profielafmeting van het gegevensbestand van Adobe Campaign. Alleen het tabblad **[!UICONTROL Identification]** is geconfigureerd. De bestandsdata worden geïdentificeerd aan de hand van de e-mailadressen van de profielen.

  ![](assets/subscription_activity_example3.png)

* A [Deduplicatie](../../automating/using/deduplication.md) op basis van de **email** in het veld van de tijdelijke bron (die voortvloeit uit de afstemming) worden eventuele duplicaten geïdentificeerd. Als de data die uit het bestand zijn geïmporteerd, duplicaten bevatten, mislukt de inschrijving op een service voor alle data.

  ![](assets/subscription_activity_example5.png)

* A [Abonnementsservices](../../automating/using/subscription-services.md) Met deze activiteit kunt u de service selecteren waarop de profielen moeten worden geabonneerd, het veld dat overeenkomt met de abonnementsdatum en de oorsprong van het abonnement.

  ![](assets/subscription_activity_example4.png)
