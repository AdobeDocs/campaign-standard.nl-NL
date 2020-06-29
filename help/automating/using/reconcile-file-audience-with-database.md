---
title: Een bestandspubliek in overeenstemming brengen met de database
description: In dit voorbeeld ziet u hoe u de publieksactiviteit Lezen gebruikt om een publiek te combineren dat rechtstreeks is gemaakt op basis van een geïmporteerd bestand.
page-status-flag: never-activated
uuid: 58c54e71-f4a7-4ae9-80a3-33c379ab1db9
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 674684e5-8830-4d2f-ba97-59ed4ba7422f
context-tags: readAudience,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7ffa48365875883a98904d6b344ac005afe26e18
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 0%

---


# Een bestandspubliek in overeenstemming brengen met de database {#example--reconcile-a-file-audience-with-the-database}

In dit voorbeeld wordt getoond hoe u de **[!UICONTROL Read audience]** activiteit kunt gebruiken om een publiek te verzoenen dat rechtstreeks is gemaakt van het importeren van een bestand.

Wanneer u een bestand importeert, kunt u de inhoud rechtstreeks in een publiek opslaan. Dit publiek is een publiek van het Dossier en zijn gegevens zijn niet verbonden met om het even welke gegevensbestandmiddelen.

De importworkflow is als volgt ontworpen:

![](assets/readaudience_activity_example3.png)

* Een [activiteit van het Laad dossier](../../automating/using/load-file.md) uploadt een dossier dat profielgegevens bevat die uit een extern hulpmiddel werden gehaald.

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

* Met de publieksactiviteit [Opslaan](../../automating/using/save-audience.md) worden de binnenkomende gegevens als een publiek opgeslagen. Aangezien de gegevens nog niet met elkaar in overeenstemming zijn gebracht, is het publiek een bestandspubliek en worden de gegevens ervan nog niet herkend als profielgegevens.

De afstemmingsworkflow is als volgt ontworpen:

![](assets/readaudience_activity_example2.png)

* Een [Lees publiek](../../automating/using/read-audience.md) activiteit uploadt het publiek van het Dossier dat in het de invoerwerkschema wordt gecreeerd. De publieksgegevens zijn nog niet in overeenstemming met de Adobe Campaign-database.
* Met een [afstemmingsactiviteit](../../automating/using/reconciliation.md) worden de inkomende gegevens via het **[!UICONTROL Identification]** tabblad aangeduid als profielen. Bijvoorbeeld door het veld **E-mail** te gebruiken als afstemmingscriteria.
* Een [updategegevensactiviteit](../../automating/using/update-data.md) neemt en werkt het profielmiddel van het gegevensbestand met de inkomende gegevens op. Aangezien de gegevens al als profielen worden geïdentificeerd, kunt u de **[!UICONTROL Directly using the targeting dimension]** optie selecteren en **[!UICONTROL Profiles]** op het **[!UICONTROL Identification]** tabblad van de activiteit selecteren. Vervolgens hoeft u alleen maar de lijst met velden toe te voegen die op het tabblad Afhankelijk moeten worden bijgewerkt.
