---
title: Lees publiek
description: Met de activiteit van het leespubliek kunt u een bestaand publiek ophalen en verfijnen door aanvullende filtervoorwaarden toe te passen.
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
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Lees publiek{#read-audience}

## Beschrijving {#description}

![](assets/prefill.png)

De **[!UICONTROL Read audience]** activiteit staat u toe om een bestaand publiek terug te winnen en het te verfijnen door extra het filtreren voorwaarden toe te passen.

## Gebruikscontext {#context-of-use}

De **[!UICONTROL Read audience]** activiteit is een eenvoudigere versie van de **[!UICONTROL Query]** activiteit die voor gevallen wordt ontworpen waar u slechts een bestaand publiek hoeft te selecteren.

## Configuratie {#configuration}

1. Zet een **[!UICONTROL Read audience]** activiteit neer in uw werkschema.
1. Selecteer de activiteit, dan open het gebruikend de ![](assets/edit_darkgrey-24px.png) knoop van de snelle acties die verschijnen.
1. Selecteer het publiek dat u wilt ophalen van het **[!UICONTROL Properties]** tabblad.

   U kunt het publiek van de volgende typen ophalen: **[!UICONTROL List]**, **[!UICONTROL Query]**, **[!UICONTROL File]** en **[!UICONTROL Experience Cloud]**. Raadpleeg de documentatie bij [Soorten publiek](../../audiences/using/about-audiences.md) voor meer informatie over publiekstypen.

   Met de **[!UICONTROL Use a dynamic audience]** optie kunt u de naam definiëren van het publiek waarop u zich wilt richten op basis van de gebeurtenisvariabelen van de workflow. Raadpleeg voor meer informatie de sectie [Activiteiten aanpassen met gebeurtenisvariabelen](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables) .

   ![](assets/readaudience_activity1.png)

1. Als u extra filtreren op het geselecteerde publiek wilt toepassen, voeg voorwaarden via het **[!UICONTROL Source filtering]** lusje van de activiteit toe.

   Voor meer informatie over het creëren van het filtreren voorwaarden, verwijs naar de [Creërende vragen](../../automating/using/editing-queries.md#creating-queries) documentatie.

1. Bevestig de configuratie van uw activiteit en sla uw werkschema op.

## Voorbeeld: Een bestandspubliek in overeenstemming brengen met de database {#example--reconcile-a-file-audience-with-the-database}

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

* Een **[!UICONTROL Read audience]** activiteit uploadt het publiek van het Dossier dat in het de invoerwerkschema wordt gecreeerd. De publieksgegevens zijn nog niet in overeenstemming met de Adobe Campaign-database.
* Met een [afstemmingsactiviteit](../../automating/using/reconciliation.md) worden de inkomende gegevens via het **[!UICONTROL Identification]** tabblad aangeduid als profielen. Bijvoorbeeld door het veld **E-mail** te gebruiken als afstemmingscriteria.
* Een [updategegevensactiviteit](../../automating/using/update-data.md) neemt en werkt het profielmiddel van het gegevensbestand met de inkomende gegevens op. Aangezien de gegevens al als profielen worden geïdentificeerd, kunt u de **[!UICONTROL Directly using the targeting dimension]** optie selecteren en **[!UICONTROL Profiles]** op het **[!UICONTROL Identification]** tabblad van de activiteit selecteren. Vervolgens hoeft u alleen maar de lijst met velden toe te voegen die op het tabblad Afhankelijk moeten worden bijgewerkt.

## Voorbeeld: Unie op twee verfijnde doelgroepen {#example--union-on-two-refined-audiences}

De workflow die in dit voorbeeld wordt gedefinieerd, toont de samenvoeging van twee **[!UICONTROL Read audience]** activiteiten. Het doel van deze workflow is om een e-mail te sturen naar Gold- of Silver-leden van 18 tot 30 jaar oud.

Er zijn al specifieke doelgroepen in het systeem gecreëerd om de Gold- en Silver-leden bij te houden.

De workflow is als volgt ontworpen:

![](assets/readaudience_activity_example1.png)

* Een eerste **[!UICONTROL Read audience]** activiteit die het publiek van de Gouden leden terugwint en het door slechts profielen te selecteren die tussen 18 en 30 jaar oud zijn verfijnt.
* Een tweede **[!UICONTROL Read audience]** activiteit die het Silver ledenpubliek terugwint en het verfijnt door slechts profielen te selecteren die tussen 18 en 30 jaar oud zijn.
* Een **[!UICONTROL Union]** activiteit die populaties van beide **[!UICONTROL Read audiences]** activiteiten verenigt in één eindpopulatie.
* Een **[!UICONTROL Email delivery]** activiteit die e-mail naar de bevolking verzendt die uit de **[!UICONTROL Union]** activiteit komt.

