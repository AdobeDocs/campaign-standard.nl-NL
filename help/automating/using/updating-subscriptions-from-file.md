---
title: Meerdere abonnementstatussen bijwerken vanuit een bestand
description: Met deze gebruiksaanwijzing kunt u zien hoe u een bestand met profielen importeert en uw abonnement bijwerkt naar verschillende services die in het bestand zijn opgegeven.
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
source-wordcount: '417'
ht-degree: 0%

---


# Meerdere abonnementstatussen bijwerken vanuit een bestand {#updating-multiple-subscription-statuses-from-a-file}

In dit voorbeeld wordt getoond hoe u een bestand met profielen kunt importeren en hun abonnement kunt bijwerken naar verschillende services die in het bestand zijn opgegeven. Na het importeren van het bestand moet een afstemming plaatsvinden, zodat de geïmporteerde gegevens kunnen worden geïdentificeerd als profielen met een koppeling naar services. Om ervoor te zorgen dat het bestand geen duplicaten bevat, wordt een deduplicatieactiviteit uitgevoerd op de gegevens.

De workflow wordt als volgt weergegeven:

![](assets/subscription_activity_example1.png)

* Een [activiteit van het Dossier](../../automating/using/load-file.md) van de Lading laadt het profieldossier en bepaalt de structuur van de ingevoerde kolommen.

   In dit voorbeeld heeft het geladen bestand de .csv-indeling en bevat het de volgende gegevens:

   ```
   lastname;firstname;email;birthdate;service;operation
   jackman;megan;megan.jackman@testmail.com;07/08/1975;SVC2;sub
   phillips;edward;phillips@testmail.com;09/03/1986;SVC3;unsub
   weaver;justin;justin_w@testmail.com;11/15/1990;SVC3;sub
   martin;babeth;babeth_martin@testmail.net;11/25/1964;SVC3;unsub
   reese;richard;rreese@testmail.com;02/08/1987;SVC3;sub
   cage;nathalie;cage.nathalie227@testmail.com;07/03/1989;SVC3;sub
   xiuxiu;andrea;andrea.xiuxiu@testmail.com;09/12/1992;SVC4;sub
   grimes;daryl;daryl_890@testmail.com;12/06/1979;SVC3;unsub
   tycoon;tyreese;tyreese_t@testmail.net;10/08/1971;SVC2;sub
   ```

   ![](assets/subscription_example_load_file.png)

   Zoals u misschien hebt opgemerkt, wordt de bewerking in het bestand opgegeven als &quot;sub&quot; of &quot;unsub&quot;. Het systeem verwacht dat een **Booleaanse** of **gehele** waarde de bewerking herkent die moet worden uitgevoerd: &quot;0&quot; voor afmelden en &quot;1&quot; voor abonneren. Om aan dit vereiste te voldoen, wordt een nieuwe toewijzing van waarden uitgevoerd in het detail van de &quot;verrichting&quot;kolom.

   ![](assets/subscription_example_remapping.png)

   Als in uw bestand al &quot;0&quot; en &quot;1&quot; worden gebruikt om de bewerking te identificeren, hoeft u deze waarden niet opnieuw toe te wijzen. Zorg alleen dat de kolom op het **tabblad als een** Booleaanse **of** gehele kolom **[!UICONTROL Column definition]** wordt verwerkt.

* Bij een [afstemmingsactiviteit](../../automating/using/reconciliation.md) worden de gegevens uit het bestand geïdentificeerd als behorend tot de profieldimensie van de Adobe Campaign-database. Via het **[!UICONTROL Identification]** tabblad komt het veld **E-mail** van het bestand overeen met het veld **E-mail** van de profielbron.

   ![](assets/subscription_activity_example3.png)

   Op het **[!UICONTROL Relations]** lusje, wordt een verbinding gecreeerd met het de dienstmiddel om het de **dienstgebied** van het dossier toe te laten om worden erkend. In dit voorbeeld, passen de waarden het **naamgebied** van het de dienstmiddel aan.

   ![](assets/subscription_example_service_relation.png)

* Bij een [deduplicatie](../../automating/using/deduplication.md) op basis van het **e-mailveld** van de tijdelijke bron (die het resultaat is van de afstemming) worden dubbele gegevens geïdentificeerd. Het is belangrijk om dubbele gegevens te elimineren aangezien het abonnement aan de dienst voor alle gegevens in het geval van duplicaten zal ontbreken.

   ![](assets/subscription_activity_example5.png)

* Een [activiteit van de Diensten](../../automating/using/subscription-services.md) van het Abonnement identificeert de diensten om als voortkomend uit de overgang, door de verbinding bij te werken die in de **[!UICONTROL Reconciliation]** activiteit wordt gecreeerd.

   Het **[!UICONTROL Operation type]** wordt geïdentificeerd als afkomstig van het **bewerkingsveld** van het bestand. U kunt hier alleen Booleaanse of gehele getallen selecteren. Als de kolom van het bestand dat de uit te voeren bewerking bevat, niet in de lijst voorkomt, moet u de kolomindeling correct instellen in de **[!UICONTROL Load file]** activiteit, zoals eerder in dit voorbeeld wordt uitgelegd.

   ![](assets/subscription_activity_example_from_file.png)
