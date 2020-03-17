---
title: Schermdefinitie configureren
description: Leer hoe u nieuwe Adobe Campagne-schermen definieert op basis van de gegevensstructuur van de bronnen.
page-status-flag: never-activated
uuid: 40848197-b1a0-4018-bfc3-7df64fb83307
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
discoiquuid: 9dabb328-ac0c-49fd-8996-8d56341ee7ac
context-tags: cusResource,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Schermdefinitie configureren{#configuring-the-screen-definition}

Wanneer u een bron maakt of wanneer u nieuwe velden toevoegt aan een bestaande bron, kunt u definiëren hoe deze moeten worden weergegeven in de interface.

Deze stap is niet verplicht omdat u uw bron nog steeds kunt vullen en toegang hebt tot de gegevens via workflows, publiek en REST API.

Op het **[!UICONTROL Screen definition]** tabblad kunt u:

* Voeg toegang tot het douanemiddel in de navigatieruit toe
* De manier aanpassen waarop de lijst met elementen waaruit de bron bestaat wordt weergegeven
* Bepaal de manier de detailmening van elk element van het middel wordt getoond

## Toegang inschakelen via het navigatiemenu {#enabling-access-from-the-navigation-menu}

Als u wilt dat uw bron een speciaal scherm heeft, kunt u dit beschikbaar stellen via het navigatiemenu.

1. Van het **[!UICONTROL Screen definition]** lusje van het middel, ontvouw de **[!UICONTROL Navigation]** sectie.
1. Controleer de **[!UICONTROL Add an entry in the 'Client data' section]** doos om toegang tot dit middel van de navigatieruit toe te staan.

   ![](assets/schema_extension_19.png)

De bron wordt weergegeven als een subitem binnen de **[!UICONTROL Client data]** sectie.

## De standaardlijstconfiguratie definiëren {#defining-the-default-list-configuration}

In het **[!UICONTROL List configuration]** gedeelte van de schermdefinitie kunt u de kolommen en informatie definiëren die standaard worden weergegeven in het overzicht van een bron.

1. Controleer de **[!UICONTROL Customize the list configuration]** doos om de manier te bepalen de kolommen van het middel worden getoond.
1. Gebruik de **[!UICONTROL Create element]** knop om een veld te selecteren uit de velden die u hebt gemaakt.
1. Het gemaakte veld wordt weergegeven in de lijst. U kunt het label en de breedte ervan bewerken.

   ![](assets/schema_extension_20.png)

1. Controleer in de **[!UICONTROL Simple search]** sectie welke velden worden opgenomen in de zoekopdracht **[!UICONTROL Specify the fields to be taken into account in the search]** om te definiëren.

   >[!CAUTION]
   >
   >Deze configuratie vervangt de gebieden die in het standaardonderzoek worden gebruikt.

1. Schakel in de **[!UICONTROL Advanced filtering]** sectie het **[!UICONTROL Add search fields]** vakje in om extra velden toe te voegen die verder gaan dan het eenvoudige zoekveld. Als u bijvoorbeeld het veld &quot;date&quot; selecteert in de velden die u hebt gemaakt, kan de gebruiker een zoekopdracht uitvoeren die alleen naar de datum verwijst.
1. U kunt de volgorde van de velden voor de twee zoektypen wijzigen.
1. Voor een geavanceerd onderzoek, kunt u gebieden toevoegen die met een verbonden middel verbinden. Deze filters worden weergegeven in het **[!UICONTROL Search]** menu van het gegenereerde scherm.

Het overzichtsscherm van de bron is nu gedefinieerd.

## De configuratie van het detailscherm definiëren {#defining-the-detail-screen-configuration}

In het **[!UICONTROL Detail screen configuration]** gedeelte van de schermdefinitie kunt u de kolommen en informatie definiëren die in het detailscherm van elk element van de bron worden weergegeven.

1. Ontgrendel de **[!UICONTROL Detail screen configuration]** sectie en controleer **[!UICONTROL Define a detail screen]** om het scherm te vormen dat aan elk element van het middel beantwoordt. Als u dit selectievakje niet inschakelt, is de gedetailleerde weergave van elementen van deze bron niet toegankelijk.
1. U kunt alle gebieden van uw douanemiddel in één klik toevoegen. Klik hiertoe op het ![](assets/addallfieldsicon.png) pictogram of gebruik de **[!UICONTROL Add an element]** knop.
1. Selecteer een element van die gecreeerd voor deze middel en specificeer een gebiedstype:

   * **[!UICONTROL Input field]**: is een bewerkbaar veld.
   * **[!UICONTROL Value]**: is een alleen-lezen veld.
   * **[!UICONTROL List]**: is een tabel.
   * **[!UICONTROL Separator]**: Hiermee splitst u de elementen in categorieën.
   ![](assets/schema_extension_23.png)

1. Het toegevoegde element wordt weergegeven in de lijst. U kunt het label ervan bewerken.

   ![](assets/schema_extension_22.png)

1. Voeg zoveel elementen toe **[!UICONTROL Separator]** als nodig is om de elementen in verschillende categorieën te splitsen.

   Zo kunt u scheidingstekens weergeven om de vensters beter te organiseren.

   ![](assets/schema_extension_25.png)

Het detailscherm van het middel wordt nu gevormd.

## Handelingen in gegevenssectie {#actions-on-data-section}

Deze montages staan u toe om een controlebar in het scherm van het douanemiddel te tonen. Er zijn drie opties beschikbaar:

![](assets/schema_extension_actions.png)

* **[!UICONTROL Authorize creating]**: met deze optie kunt u het maken van elementen van de bron activeren. De gebruiker kan daarom aanvullende records toevoegen.

   >[!NOTE]
   >
   >U moet eerst het detailscherm activeren dat aan de bron is gekoppeld om deze optie beschikbaar te maken.

* **[!UICONTROL Authorize duplicating]**: met deze optie kunt u dubbele records activeren die zijn gekoppeld aan de aangepaste bron.
* **[!UICONTROL Authorize deleting]**: met deze optie kunt u verwijderingsrecords activeren die zijn gekoppeld aan de aangepaste bron.

