---
title: Afstemming
description: Met de activiteit Afstemming kunt u niet-geïdentificeerde data koppelen aan bestaande resources.
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
ht-degree: 95%

---


# Afstemming{#reconciliation}

## Beschrijving {#description}

![](assets/reconciliation.png)

Met de activiteit **[!UICONTROL Reconciliation]** kunt u niet-geïdentificeerde data koppelen aan bestaande resources.

## Gebruikscontext {#context-of-use}

De activiteit **[!UICONTROL Reconciliation]** wordt hoofdzakelijk gebruikt voor databeheerdoeleinden en houdt twee gebruikssituaties in:

* Relaties toevoegen: Op het tabblad **[!UICONTROL Links]** kunt u koppelingen toevoegen tussen de binnenkomende data en verschillende andere Adobe Campaign-databasedimensies.

   Een bestand met aankoopdata kan bijvoorbeeld ook informatie bevatten om de aangekochte producten en de koper te identificeren. De bestandsdata hebben derhalve betrekking op twee extra dimensies (naast **Purchases**): de dimensies **Products** en **Profiles**. Vervolgens moeten er relaties worden aangelegd tussen deze dimensies en de dimensie **Purchases** (zie het volgende voorbeeld).

   Bij het definiëren van een relatie wordt een kolom toegevoegd aan de binnenkomende data om te verwijzen naar de externe sleutel van de gekoppelde dimensie.

   >[!NOTE]
   >
   >Deze bewerking houdt in dat de data van de gekoppelde dimensies al in de database staan. Als u bijvoorbeeld een aankoopbestand importeert waarin wordt aangegeven welk product is gekocht, op welk moment, door welke klant, enzovoort, moeten het product en de klant al in de database aanwezig zijn.

* Data-identificatie: Op het tabblad **[!UICONTROL Identification]** kunt u binnenkomende data eenvoudig koppelen aan kolommen van een bestaande dimensie in de Adobe Campaign-database. Na de activiteit worden de data geïdentificeerd als behorend tot de gedefinieerde dimensie.

   U kunt dan bijvoorbeeld een doelgroep opslaan, de database bijwerken, enzovoort.

De activiteit **[!UICONTROL Reconciliation]** kan bijvoorbeeld na een activiteit voor het laden van data worden geplaatst met het doel om niet-standaarddata in de database te importeren.

**Verwante onderwerpen:**

* [Hoofdlettergebruik: Afstemming van gegevens met behulp van relaties](../../automating/using/reconciliation-using-relations.md)
* [Hoofdlettergebruik: Gegevensupdate met afstemming](../../automating/using/data-update-reconciliation.md)
* [Hoofdlettergebruik: Een bestandspubliek in overeenstemming brengen met de database](../../automating/using/reconcile-file-audience-with-database.md)

## Configuratie {#configuration}

1. Sleep een **[!UICONTROL Reconciliation]**-activiteit naar uw workflow en plaats deze na een overgang met een populatie waarvan de targetingdimensie niet rechtstreeks afkomstig is uit Adobe Campaign. Raadpleeg [Targetingdimensies en resources](../../automating/using/query.md#targeting-dimensions-and-resources) voor meer informatie.
1. Selecteer de activiteit en open deze met de knop ![](assets/edit_darkgrey-24px.png) vanuit de snelle acties die verschijnen.
1. Ga naar het tabblad **[!UICONTROL Links]** als u koppelingen wilt definiëren tussen de binnenkomende data en andere databasedimensies.

   Voeg zoveel relaties toe als nodig is. Selecteer eerst voor elke relatie de gekoppelde dimensie en geef vervolgens in de koppelingsdetails de bijbehorende velden op.

1. Als u de binnenkomende data eenvoudig wilt identificeren, gaat u naar het tabblad **[!UICONTROL Identification]** en schakelt u het vakje **[!UICONTROL Identify the document from the working data]** in.

   Selecteer de targetingdimensie waarop u de binnenkomende data wilt afstemmen.

   Voeg afstemmingscriteria toe om de record van een binnenkomende overgang aan een geselecteerde targetingdimensie-record te koppelen. Als er meerdere criteria zijn opgegeven, moeten deze allemaal worden geverifieerd om te zorgen dat de koppeling tussen alle betreffende data werkt.

   Kies de modus **[!UICONTROL Processing unidentified source lines]**:

   * **[!UICONTROL Ignore them]**: Alleen de identificeerbare data blijven behouden in de uitgaande overgang van de activiteit.
   * **[!UICONTROL Keep in the outbound population]**: Alle data van de binnenkomende overgang blijven behouden in de uitgaande overgang van de activiteit.

1. Bevestig de configuratie van uw activiteit en sla de workflow op.
