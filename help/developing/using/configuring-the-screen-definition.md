---
title: De schermdefinitie configureren
description: Ontdek hoe u nieuwe Adobe Campaign-schermen definieert op basis van de datastructuur van de resources.
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
translation-type: ht
source-git-commit: 8852adb5edeb42eba1acf2911c988071104f1401
workflow-type: ht
source-wordcount: '614'
ht-degree: 100%

---


# De schermdefinitie configureren{#configuring-the-screen-definition}

Wanneer u een resource maakt of nieuwe velden toevoegt aan een bestaande resource, kunt u definiëren hoe deze moeten worden weergegeven in de interface.

Deze stap is niet verplicht omdat u uw resource nog steeds kunt invullen en de data ervan kunt openen via workflows, doelgroepen en de REST API.

Op het tabblad **[!UICONTROL Screen definition]** kunt u het volgende doen:

* Toegang tot de aangepaste resource toevoegen in het navigatiedeelvenster
* De manier aanpassen waarop de lijst met elementen waaruit de resource bestaat, wordt weergegeven
* De manier bepalen waarop de detailweergave van elk element van de resource wordt getoond

## Toegang inschakelen via het navigatiemenu {#enabling-access-from-the-navigation-menu}

Als u wilt dat uw resource een speciaal scherm heeft, kunt u dit beschikbaar stellen via het navigatiemenu.

1. Vouw vanaf het tabblad **[!UICONTROL Screen definition]** van de resource de sectie **[!UICONTROL Navigation]** uit.
1. Schakel het selectievakje **[!UICONTROL Add an entry in the 'Client data' section]** in om toegang tot deze resource vanaf het navigatiedeelvenster toe te staan.

   ![](assets/schema_extension_19.png)

De resource wordt weergegeven als een subvermelding binnen de sectie **[!UICONTROL Client data]**.

## De standaardlijstconfiguratie definiëren {#defining-the-default-list-configuration}

In de sectie **[!UICONTROL List configuration]** van de schermdefinitie kunt u de kolommen en informatie definiëren die standaard worden weergegeven in het overzicht van een resource.

1. Schakel het selectievakje **[!UICONTROL Customize the list configuration]** in om de manier te bepalen waarop de kolommen van de resource worden weergegeven.
1. Gebruik de knop **[!UICONTROL Create element]** om een van de velden die u hebt gemaakt te selecteren.
1. Het gemaakte veld wordt weergegeven in de lijst. U kunt het label en de breedte ervan bewerken.

   ![](assets/schema_extension_20.png)

1. Schakel in de sectie **[!UICONTROL Simple search]** de optie **[!UICONTROL Specify the fields to be taken into account in the search]** in om te definiëren welke velden in de zoekopdracht worden opgenomen.

   >[!IMPORTANT]
   >
   >Deze configuratie vervangt de velden die in de standaardzoekopdracht worden gebruikt.

1. Schakel in de sectie **[!UICONTROL Advanced filtering]** het selectievakje **[!UICONTROL Add search fields]** in om meer velden toe te voegen in aanvulling op het veld voor een eenvoudige zoekopdracht. Als u bijvoorbeeld het veld ‘date’ selecteert in de velden die u hebt gemaakt, kan de gebruiker een zoekopdracht uitvoeren die alleen naar de datum verwijst.
1. U kunt de volgorde van de velden voor de twee typen zoekopdrachten wijzigen.
1. Voor een geavanceerde zoekopdracht kunt u velden toevoegen die met een gekoppelde resource zijn verbonden. Deze filters worden weergegeven in het menu **[!UICONTROL Search]** van het gegenereerde scherm.

Het overzichtsscherm van de resource is nu gedefinieerd.

## De configuratie van het detailscherm definiëren {#defining-the-detail-screen-configuration}

In de sectie **[!UICONTROL Detail screen configuration]** van de schermdefinitie kunt u de kolommen en informatie definiëren die in het detailscherm van elk element van de resource worden weergegeven.

1. Vouw de sectie **[!UICONTROL Detail screen configuration]** uit en schakel **[!UICONTROL Define a detail screen]** in om het scherm te configureren dat overeenkomt met elk element van de resource. Als u dit selectievakje niet inschakelt, is de gedetailleerde weergave van elementen van deze resource niet toegankelijk.
1. U kunt alle velden van uw aangepaste resource in één klik toevoegen. Klik hiertoe op het pictogram ![](assets/addallfieldsicon.png) of gebruik de knop **[!UICONTROL Add an element]**.
1. Selecteer een element uit de elementen die voor deze resource zijn gemaakt en geef een veldtype op:

   * **[!UICONTROL Input field]**: Is een bewerkbaar veld.
   * **[!UICONTROL Value]**: Is een alleen-lezen veld.
   * **[!UICONTROL List]**: Is een tabel.
   * **[!UICONTROL Separator]**: Hiermee splitst u de elementen in categorieën.
   ![](assets/schema_extension_23.png)

1. Het toegevoegde element wordt weergegeven in de lijst. U kunt het label ervan bewerken.

   ![](assets/schema_extension_22.png)

1. Voeg zoveel **[!UICONTROL Separator]** toe als nodig is om de elementen in verschillende categorieën te splitsen.

   Zo kunt u scheidingstekens weergeven om de vensters beter te organiseren.

   ![](assets/schema_extension_25.png)

Het detailscherm van de resource is nu gedefinieerd.

## De sectie Actions on data {#actions-on-data-section}

Met deze instellingen kunt u een controlebalk in het scherm van de aangepaste resource weergeven. Er zijn drie opties beschikbaar:

![](assets/schema_extension_actions.png)

* **[!UICONTROL Authorize creating]**: Met deze optie kunt u het maken van elementen van de resource activeren. De gebruiker kan daarom aanvullende records toevoegen.

   >[!NOTE]
   >
   >U moet eerst het detailscherm activeren dat aan de resource is gekoppeld om deze optie beschikbaar te maken.

* **[!UICONTROL Authorize duplicating]**: Met deze optie kunt u duplicatierecords activeren die aan de aangepaste resource zijn gekoppeld.
* **[!UICONTROL Authorize deleting]**: Met deze optie kunt u verwijderingsrecords activeren die aan de aangepaste resource zijn gekoppeld.
