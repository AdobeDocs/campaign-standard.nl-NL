---
solution: Campaign Standard
product: campaign
title: Een doelgroep Bestand afstemmen op de database
description: In dit voorbeeld ziet u hoe u de publieksactiviteit Lezen gebruikt om een publiek te combineren dat rechtstreeks is gemaakt op basis van een geïmporteerd bestand.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: readAudience,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 87%

---


# Een doelgroep Bestand afstemmen op de database {#example--reconcile-a-file-audience-with-the-database}

In dit voorbeeld wordt getoond hoe u de activiteit **[!UICONTROL Read audience]** kunt gebruiken om een doelgroep af te stemmen die rechtstreeks vanaf een bestandsimport is gemaakt.

Wanneer u een bestand importeert, kunt u de content ervan rechtstreeks in een doelgroep opslaan. Deze doelgroep is een doelgroep File en de data ervan zijn niet gekoppeld aan databaseresources.

De importworkflow is als volgt ontworpen:

![](assets/readaudience_activity_example3.png)

* Met een activiteit [Bestand laden](../../automating/using/load-file.md) uploadt u een bestand met profieldata die uit een extern hulpprogramma zijn geëxtraheerd.

   Bijvoorbeeld:

   ```
   lastname;firstname;birthdate;email;crmID
   Smith;Hayden;23/05/1989;hayden.smith@example.com;124365
   Mars;Daniel;17/11/1987;dannymars@example.com;123545
   Smith;Clara;08/02/1989;hayden.smith@example.com;124567
   Durance;Allison;15/12/1978;allison.durance@example.com;120987
   Lucassen;Jody;28/03/1988;jody.lucassen@example.com;127634
   Binder;Tom;19/01/1982;tombinder@example.com;128653
   Binder;Tommy;19/01/1915;tombinder@example.com;134576
   Connor;Jade;10/10/1979;connor.jade@example.com;132452
   Mack;Clarke;02/03/1985;clarke.mack@example.com;149876
   Ross;Timothy;04/07/1986;timross@example.com;157643
   ```

* Met de activiteit [Doelgroep opslaan](../../automating/using/save-audience.md) worden de binnenkomende data als een doelgroep opgeslagen. Aangezien de data nog niet zijn afgestemd, is de doelgroep een doelgroep File en worden de data ervan nog niet herkend als profieldata.

De afstemmingsworkflow is als volgt ontworpen:

![](assets/readaudience_activity_example2.png)

* A [Read audience](../../automating/using/read-audience.md) activity uploads the File audience created in the import workflow. De doelgroepsdata zijn nog niet afgestemd op de Adobe Campaign-database.
* Met een activiteit [Afstemming](../../automating/using/reconciliation.md) worden de binnenkomende data via het tabblad **[!UICONTROL Identification]** aangeduid als profielen. Bijvoorbeeld door het veld **email** te gebruiken als afstemmingscriteria.
* Met een activiteit [Data bijwerken](../../automating/using/update-data.md) wordt de resource met de profielen van de database ingevoegd en bijgewerkt met de binnenkomende data. Aangezien de data al als profielen zijn geïdentificeerd, kunt u de optie **[!UICONTROL Directly using the targeting dimension]** selecteren en **[!UICONTROL Profiles]** selecteren op het tabblad **[!UICONTROL Identification]** van de activiteit. Vervolgens hoeft u alleen maar de lijst met velden toe te voegen die op het overeenkomstige tabblad moeten worden bijgewerkt.
