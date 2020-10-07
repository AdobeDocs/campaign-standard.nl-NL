---
title: Aangepaste resources exporteren en importeren
description: In deze tutorial wordt uitgelegd hoe u een pakket met aangepaste resources kunt exporteren en importeren.
page-status-flag: never-activated
uuid: 631f0fbd-9e8d-4f77-a338-fcb7f4fc1774
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: a06509f9-4731-4187-b43d-3bfa361284d3
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '629'
ht-degree: 100%

---


# Aangepaste resources exporteren en importeren {#exporting-importing-custom-resources}

In deze tutorial wordt uitgelegd hoe u een pakket met aangepaste resources kunt exporteren vanuit een ontwikkelomgeving en importeren in een productieomgeving.

Dit voorbeeld is gericht op functionele beheerders die zijn gekoppeld aan Adobe Campaign.

De voorwaarden zijn:

* **Een of meer aangepaste resources** die beschikbaar en gepubliceerd zijn.

   Bovendien moet u een unieke sleutel voor deze resources gedefinieerd hebben omdat de automatische primaire sleutels niet in de pakketten worden geëxporteerd. De resource kan daarom een primaire sleutel en een aanvullende unieke sleutel hebben om de uniekheid van de records te garanderen.
* **De benodigde rechten** om een pakket te maken en te exporteren.

Aanvullende resources:

* [Pakketten beheren](../../automating/using/managing-packages.md)
* [Pakketten implementeren: werkwijze](../../developing/using/data-model-concepts.md)
* [Een resource toevoegen of uitbreiden](../../developing/using/key-steps-to-add-a-resource.md)

## De structuur exporteren {#exporting-the-structure}

In deze sectie gaan we een eerste pakket exporteren dat de fysieke structuur van de data van de aangepaste resource aangeeft.

Dit voorbeeld heeft twee aangepaste resources: **Producten** en **Bestellingen**.

1. Ga naar het menu **[!UICONTROL Administration]** / **[!UICONTROL Deployment]** / **[!UICONTROL Package exports]**.

   We maken een nieuw pakket om de **[!UICONTROL Custom resource (cusResource)]** te exporteren, gefilterd met de twee aangepaste resources ‘Producten’ en ‘Bestellingen’.

1. Klik op de pagina **[!UICONTROL Package exports]** op **[!UICONTROL Create]** om een nieuw pakket te maken.
1. Voltooi het label en klik op **[!UICONTROL Create element]**.

   ![](assets/cusresources_export1.png)

1. Zoek naar en selecteer de **[!UICONTROL Custom resource (cusResource)]**.

   ![](assets/cusresources_export2.png)

1. Configureer de details van de **[!UICONTROL Custom resource]** door de twee resources **Producten** en **Bestellingen** te selecteren in de filtervoorwaarden.

   Vergeet niet de logische operator te veranderen. De waarde moet worden ingesteld op **OR** zodat de structuur van de resource Producten en de resource Bestellingen in het pakket wordt geïntegreerd.

   ![](assets/cusresources_export3.png)

1. Bevestig de pakketdefinitie en sla deze op.

U kunt nu op **[!UICONTROL Start export]** klikken.

![](assets/cusresources_export4.png)

Het gegenereerde pakket is beschikbaar in de map Downloads. De naam van het zip-bestand wordt willekeurig gegenereerd. U kunt de naam ervan wijzigen.

## De data exporteren {#exporting-the-data}

Met deze tweede export kunnen we de data uit de aangepaste resources **Producten** en **Bestellingen** exporteren.

Op basis van hetzelfde type export als de structuurexport maakt u een tweede pakket maken dat de data bevat.

1. Klik op de pagina **[!UICONTROL Package exports]** op **[!UICONTROL Create]** om een nieuw pakket te maken.
1. Voltooi het label met **[!UICONTROL Export data of my resources]** en klik vervolgens op **[!UICONTROL Create element]** op het tabblad **[!UICONTROL Export content]**.
1. Zoek naar en selecteer de resource **Producten**.

   ![](assets/cusresources_exportdata1.png)

1. Configureer een geavanceerde **filtervoorwaarde** met **@Label IS NOT NULL**.

   ![](assets/cusresources_exportdata2.png)

1. Controleer het aantal.

   ![](assets/cusresources_exportdata3.png)

1. Herhaal dezelfde bewerking voor de aangepaste resource **Bestellingen**.

   ![](assets/cusresources_exportdata4.png)

1. Bevestig de pakketdefinitie en sla deze op.

U kunt nu op **[!UICONTROL Start export]** klikken.

![](assets/cusresources_exportdata5.png)

Het gegenereerde pakket is beschikbaar in de map Downloads. De naam van het zip-bestand wordt willekeurig gegenereerd. U kunt de naam ervan wijzigen.

## De structuur importeren {#importing-the-structure}

### Het pakket importeren {#importing-the-structure-package}

1. Maak verbinding met de **doelinstantie** waarnaar u de nieuw gemaakte pakketten wilt importeren.
1. Ga naar het menu **[!UICONTROL Administration]** / **[!UICONTROL Deployment]** / **[!UICONTROL Package imports]** om een nieuw pakket te maken waarmee u het bestand uit de eerste exportbewerking kunt importeren.
1. Sleep het **structuurbestand** en zet het neer in de zone die voor dit doel is opgegeven. De toegestane indelingen zijn zip of xml.

   ![](assets/cusresources_import2.png)

1. Wijzig het label, bijvoorbeeld **Structuur importeren** en klik op **[!UICONTROL Save]**.
1. Klik op **[!UICONTROL Start import]**.

   ![](assets/cusresources_import3.png)

### Publiceren {#publish-structure}

1. Ga naar het menu **[!UICONTROL Administration]** / **[!UICONTROL Development]** / **[!UICONTROL Publication]**.
1. Klik eerst op **[!UICONTROL Prepare publication]** en vervolgens op **[!UICONTROL Publish]** om de instantie bij te werken met de data van de nieuwe aangepaste resources.
1. De menu-items die overeenkomen met het geïnstalleerde pakket worden in het menu **[!UICONTROL Client data]** ingevoegd.

   ![](assets/cusresources_import1.png)

## De data importeren {#importing-the-data}

In deze sectie **importeren we de data** die zijn gekoppeld aan het pakket dat in de vorige stap op de instantie is geïnstalleerd.

Op dezelfde manier als bij de vorige stap wordt deze bewerking in twee delen opgesplitst: het pakket importeren en het pakket publiceren.

### Het pakket importeren {#importing-the-data-package}

1. Ga naar het menu **[!UICONTROL Administration]** / **[!UICONTROL Deployment]** / **[!UICONTROL Package imports]** om een nieuw pakket te maken waarmee u het bestand met de data kunt importeren.
1. Sleep het databestand en zet het neer in de zone die voor dit doel is opgegeven. De toegestane indelingen zijn zip of xml.
1. Wijzig het label, bijvoorbeeld Data importeren, en klik vervolgens op **[!UICONTROL Save]**.
1. Klik op **[!UICONTROL Start import]**.

   ![](assets/cusresources_importdata.png)

### Publiceren {#publish-data}

1. Ga naar het menu **[!UICONTROL Administration]** / **[!UICONTROL Development]** / **[!UICONTROL Publication]**.
1. Klik eerst op **[!UICONTROL Prepare publication]** en vervolgens op **[!UICONTROL Publish]** om de instantie bij te werken met de data van de aangepaste resources.
