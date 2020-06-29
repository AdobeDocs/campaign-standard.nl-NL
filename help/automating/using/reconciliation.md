---
title: Verzoening
description: Met de afstemmingsactiviteit kunt u niet-geïdentificeerde gegevens koppelen aan bestaande bronnen.
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
source-git-commit: 87e0611fae0560aca276caa3c4cf793e9c095d72
workflow-type: tm+mt
source-wordcount: '482'
ht-degree: 0%

---


# Verzoening{#reconciliation}

## Beschrijving {#description}

![](assets/reconciliation.png)

Met deze **[!UICONTROL Reconciliation]** activiteit kunt u niet-geïdentificeerde gegevens koppelen aan bestaande bronnen.

## Gebruikscontext {#context-of-use}

De **[!UICONTROL Reconciliation]** activiteit wordt hoofdzakelijk gebruikt voor gegevensbeheerdoeleinden en houdt twee verschillende gebruiksgevallen in:

* Relaties toevoegen: op een **[!UICONTROL Links]** tabblad kunt u koppelingen toevoegen tussen de binnenkomende gegevens en verschillende andere Adobe Campaign-databaseafmetingen.

   Een bestand met aankoopgegevens kan bijvoorbeeld ook informatie bevatten om de aangekochte producten en de koper te identificeren. De bestandsgegevens hebben derhalve betrekking op twee extra dimensies (naast die van **aankopen**): de afmetingen van de **producten** en **profielen** . Vervolgens moeten er relaties worden aangelegd tussen deze en de **inkoopdimensie** (zie het volgende voorbeeld).

   Bij het definiëren van een relatie wordt een kolom toegevoegd aan de binnenkomende gegevens om te verwijzen naar de externe sleutel van de gekoppelde dimensie.

   >[!NOTE]
   >
   >Deze bewerking houdt in dat de gegevens van de gekoppelde afmetingen al in de database staan. Als u bijvoorbeeld een aankoopbestand importeert waarin wordt aangegeven welk product op welk moment, door welke client enzovoort is aangeschaft, moeten het product en de client al in de database aanwezig zijn.

* Gegevensidentificatie: Met een **[!UICONTROL Identification]** tabblad kunt u eenvoudig binnenkomende gegevens koppelen aan kolommen van een bestaande dimensie in de Adobe Campaign-database. Na de activiteit, worden de gegevens geïdentificeerd als behorend tot de bepaalde dimensie.

   U kunt dan bijvoorbeeld een publiek opslaan, de database bijwerken, enzovoort.

De **[!UICONTROL Reconciliation]** activiteit kan bijvoorbeeld worden geplaatst na het laden van gegevens met als doel niet-standaardgegevens in de database te importeren.

**Verwante onderwerpen:**

* [Hoofdlettergebruik: Afstemming van gegevens met behulp van relaties](../../automating/using/reconciliation-using-relations.md)
* [Hoofdlettergebruik: Gegevensupdate met afstemming](../../automating/using/data-update-reconciliation.md)
* [Hoofdlettergebruik: Een bestandspubliek in overeenstemming brengen met de database](../../automating/using/reconcile-file-audience-with-database.md)

## Configuratie {#configuration}

1. Sleep een **[!UICONTROL Reconciliation]** activiteit naar uw werkstroom, na een overgang die een populatie bevat waarvan de doeldimensie niet rechtstreeks uit Adobe Campaign komt. Raadpleeg [Doeldimensies en bronnen](../../automating/using/query.md#targeting-dimensions-and-resources)voor meer informatie hierover.
1. Selecteer de activiteit, dan open het gebruikend de ![](assets/edit_darkgrey-24px.png) knoop van de snelle acties die verschijnen.
1. Ga naar het **[!UICONTROL Links]** tabblad als u koppelingen wilt definiëren tussen de binnenkomende gegevens en andere databaseafmetingen.

   Voeg zoveel relaties toe als nodig is. Selecteer eerst voor elke relatie de gekoppelde dimensie en geef vervolgens in de koppelingsdetails de bijbehorende velden op.

1. Als u eenvoudig de binnenkomende gegevens wilt identificeren, ga naar het **[!UICONTROL Identification]** lusje en controleer het **[!UICONTROL Identify the document from the working data]** vakje.

   Selecteer de doeldimensie waarmee u de binnenkomende gegevens wilt afstemmen.

   Voeg verzoeningscriteria toe om een binnenkomende overgangsverslag aan een geselecteerd gericht afmetingsverslag te verbinden. Als er meerdere criteria zijn opgegeven, moeten deze allemaal worden geverifieerd voordat het verband tussen al hun gegevens kan worden gecontroleerd.

   Kies de **[!UICONTROL Processing unidentified source lines]** modus:

   * **[!UICONTROL Ignore them]**: alleen de identificeerbare gegevens worden bewaard in de uitgaande overgang van de activiteit.
   * **[!UICONTROL Keep in the outbound population]**: alle gegevens van de binnenkomende overgang worden gehouden in de uitgaande overgang van de activiteit.

1. Bevestig de configuratie van uw activiteit en sla uw werkschema op.
