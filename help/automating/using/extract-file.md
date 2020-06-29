---
title: Bestand uitpakken
description: Met de bestandsactiviteit Extraheren kunt u gegevens uit Adobe Campaign exporteren in de vorm van een extern bestand.
page-status-flag: never-activated
uuid: 631f0fbd-9e8d-4f77-a338-fcb7f4fc1774
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: a06509f9-4731-4187-b43d-3bfa361284d3
context-tags: fileExport,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 15e5aebdd67e8f5ddee89506c0469a101d94d2e8
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 0%

---


# Bestand uitpakken{#extract-file}

## Beschrijving {#description}

![](assets/export.png)

Met deze **[!UICONTROL Extract file]** activiteit kunt u gegevens uit Adobe Campaign exporteren in de vorm van een extern bestand.

## Gebruikscontext {#context-of-use}

De manier waarop de gegevens worden geëxtraheerd, wordt gedefinieerd bij het configureren van de activiteit.

>[!CAUTION]
>
>De **[!UICONTROL Extract file]** activiteit moet na een **[!UICONTROL Query]** activiteit worden geplaatst om te worden gebruikt.

**Verwante onderwerpen:**

* [Hoofdlettergebruik: Profielen exporteren in een extern bestand](../../automating/using/exporting-profiles-in-file.md)

## Configuratie {#configuration}

1. Sleep een **[!UICONTROL Extract file]** activiteit naar uw werkstroom.

   ![](assets/wkf_data_export1.png)

1. Selecteer de activiteit, dan open het gebruikend de ![](assets/edit_darkgrey-24px.png) knoop van de snelle acties die verschijnen.
1. Voer het label van het **uitvoerbestand** in. Het label van het bestand wordt automatisch aangevuld met de datum en tijd waarop het is gemaakt, zodat het uniek is. Bijvoorbeeld: receiving_20150815_081532.txt for a file generated the 15th of August 2015 at 08:15:32.

   >[!NOTE]
   >
   >U kunt de **[!UICONTROL formatDate]** functie in dit veld gebruiken om de bestandsnaam op te geven.

1. Indien gewenst, kunt u het uitvoerbestand comprimeren door dit **[!UICONTROL Compression]** in het **[!UICONTROL Add a pre-processing step]** veld te selecteren. Het uitvoerbestand wordt gecomprimeerd tot een GZIP-bestand (.gz).

   In het **[!UICONTROL Add a pre-processing step]** veld kunt u een bestand ook versleutelen voordat u het uitpakt. Raadpleeg [deze sectie voor meer informatie over het werken met gecodeerde bestanden](../../automating/using/managing-encrypted-data.md)

1. Klik op de ![](assets/add_darkgrey-24px.png) knop of de **[!UICONTROL Add an element]** knop om een uitvoerkolom toe te voegen.

   ![](assets/wkf_data_export2.png)

   Er wordt een nieuw venster geopend.

   ![](assets/wkf_data_export3.png)

1. Voer een expressie in. Hiervoor kunt u een bestaande expressie selecteren of een nieuwe expressie maken met de **expressieeditor**.
1. Bevestig uw uitdrukking.

   De expressie wordt toegevoegd aan de uitvoerkolommen.

1. Maak zoveel kolommen als u nodig hebt. U kunt kolommen bewerken door op de bijbehorende expressies en labels te klikken.

   Als u profielen exporteert en wilt gebruiken in een extern gereedschap, moet u ervoor zorgen dat u een unieke id exporteert. Standaard hebben niet alle profielen een unieke id, afhankelijk van de manier waarop ze aan de database worden toegevoegd. Raadpleeg de sectie Een unieke id [voor profielen](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources) genereren voor meer informatie.

1. Klik op het **[!UICONTROL File structure]** tabblad om de uitvoer-, datum- en getalnotaties te configureren voor het bestand dat wordt geëxporteerd.

   Schakel de **[!UICONTROL Export labels instead of internal values of enumerations]** optie in als u opsommingswaarden exporteert. Met deze optie kunt u kortere labels ophalen die u gemakkelijk kunt begrijpen in plaats van id&#39;s.

1. Selecteer op het **[!UICONTROL Properties]** tabblad de **[!UICONTROL Do not generate a file if the inbound transition is empty]** optie om te voorkomen dat er lege bestanden worden gemaakt en geüpload op SFTP-servers als de binnenkomende overgang leeg is.
1. Bevestig de configuratie van uw activiteit en sla uw werkschema op.
