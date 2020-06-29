---
title: Profielen vanuit een bestand abonneren op een specifieke service
description: Met deze gebruiksaanwijzing kunt u zien hoe u een bestand met profielen importeert en deze abonneert op een bestaande service.
page-status-flag: never-activated
uuid: 56637024-15ab-4145-9c48-3fbd27ab8af8
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: 74a6df0e-fd85-4404-a42c-9a7406512717
context-tags: setOfService,workflow,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c3911232a3cce00c2b9a2e619f090a7520382dde
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 0%

---


# Profielen na het importeren van een bestand abonneren op een specifieke service {#subscribing-profiles-to-a-specific-service-after-importing-a-file}

In dit voorbeeld ziet u hoe u een bestand met profielen importeert en deze abonneert op een bestaande service. Na het importeren van het bestand moet een afstemming plaatsvinden, zodat de geïmporteerde gegevens kunnen worden geïdentificeerd als profielen. Om ervoor te zorgen dat het bestand geen duplicaten bevat, wordt een deduplicatieactiviteit uitgevoerd op de gegevens.

De workflow wordt als volgt weergegeven:

![](assets/subscription_activity_example1.png)

* Een [activiteit van het Dossier](../../automating/using/load-file.md) van de Lading laadt het profieldossier en bepaalt de structuur van de ingevoerde kolommen.

   In dit voorbeeld heeft het geladen bestand de .csv-indeling en bevat het de volgende gegevens:

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

* Bij een [afstemmingsactiviteit](../../automating/using/reconciliation.md) worden de gegevens uit het bestand geïdentificeerd als behorend tot de profieldimensie van de Adobe Campaign-database. Alleen het **[!UICONTROL Identification]** tabblad is geconfigureerd. De bestandsgegevens worden geïdentificeerd aan de hand van de e-mailadressen van de profielen.

   ![](assets/subscription_activity_example3.png)

* Bij een [deduplicatie](../../automating/using/deduplication.md) op basis van het **e-mailveld** van de tijdelijke bron (die het resultaat is van de afstemming) worden eventuele duplicaten geïdentificeerd. Als de gegevens die uit het bestand zijn geïmporteerd, duplicaten bevatten, mislukt het abonnement op een service voor alle gegevens.

   ![](assets/subscription_activity_example5.png)

* Met [Subscription Services](../../automating/using/subscription-services.md) kunt u de service selecteren waarop u een abonnement moet nemen op de profielen, het veld dat overeenkomt met de abonnementsdatum en de oorsprong van het abonnement.

   ![](assets/subscription_activity_example4.png)
