---
title: Data bijwerken
description: Met de activiteit Data bijwerken kunt u velden in de database groepsgewijs bijwerken.
page-status-flag: never-activated
uuid: 1dc55db5-affd-4688-b673-adfb8c1338b5
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: 4db83c95-4b75-4a16-8dbf-bd8940431fa9
context-tags: writer,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 98%

---


# Data bijwerken{#update-data}

## Beschrijving {#description}

![](assets/data_update.png)

Met de activiteit **[!UICONTROL Update data]** kunt u velden in de database groepsgewijs bijwerken.

## Gebruikscontext {#context-of-use}

U kunt de activiteit **Data bijwerken** gebruiken nadat u een bestand hebt geïmporteerd om de herstelde data in de Adobe Campaign-database in te voegen. Met verschillende opties kunt u het bijwerken van de data aanpassen.

**Verwante onderwerpen:**

* [Hoofdlettergebruik: Gegevens bijwerken die zijn gebaseerd op een bestand](../../automating/using/update-database-file.md)
* [Data bijwerken op basis van een automatische bestandsdownload](../../automating/using/update-data-automatic-download.md)

## Configuratie {#configuration}

1. Sleep een activiteit **[!UICONTROL Update data]** en zet deze neer in uw workflow.
1. Selecteer de activiteit en open deze met de knop ![](assets/edit_darkgrey-24px.png) vanuit de snelle acties die verschijnen.
1. Geef de **[!UICONTROL Operation type]** op die moet worden uitgevoerd:

   * **[!UICONTROL Insert or update]**: Data invoegen of bijwerken als de records al bestaan in de database.
   * **[!UICONTROL Insert only]**: Alleen data invoegen. De al bestaande records worden niet bijgewerkt. Als er afstemmingscriteria worden gedefinieerd, worden alleen de niet-afgestemde records toegevoegd.

      Schakel het selectievakje **[!UICONTROL Generate an outbound transition for rejects]** in als de geïmporteerde data bepaalde records bevatten die al in de database bestaan om mogelijke fouten te voorkomen.

   * **[!UICONTROL Update]**: Data bijwerken van alleen de records die al in de database bestaan.
   * **[!UICONTROL Delete]**: Data verwijderen.

   >[!NOTE]
   >
   >In het veld **[!UICONTROL Batch size]** kunt u de maximale batchgrootte definiëren voor de data die u wilt uploaden.

1. Geef op het tabblad **[!UICONTROL Identification]** op hoe de records in de database moeten worden geïdentificeerd:

   * **[!UICONTROL Using the targeting dimension]**: Selecteer de **[!UICONTROL Dimension to update]** en geef vervolgens de **[!UICONTROL Keys for finding records]** op. Raadpleeg [Doeldimensies en resources](../../automating/using/query.md#targeting-dimensions-and-resources) voor meer informatie.
   * Als de ingevoerde data overeenkomen met een bestaande doeldimensie, selecteert u de optie **[!UICONTROL Using one or more links]**. Selecteer vervolgens de **[!UICONTROL Dimension to update]**.

   Als het geselecteerde bewerkingstype een update vereist, moet u afstemmingssleutels gebruiken.

1. Geef op het tabblad **[!UICONTROL Fields to update]** de velden op waarop de update wordt toegepast en voeg indien nodig voorwaarden toe zodat deze update wordt uitgevoerd. Hiervoor gebruikt u de kolom **[!UICONTROL Taken into account if]**. De voorwaarden worden een na een toegepast in de volgorde van de lijst. Gebruik de pijlen aan de rechterkant om de volgorde van de updates te wijzigen. U kunt hetzelfde bestemmingsveld meerdere keren gebruiken.

   U kunt velden automatisch koppelen met de knop ![](assets/wkf_magic_wand-24px.png). Door automatische koppeling worden velden met dezelfde naam gedetecteerd.

   Tijdens een bewerking van het type **[!UICONTROL Insert or update]** kunt u de bewerking die u voor elk veld wilt toepassen, afzonderlijk selecteren. Selecteer hiervoor de gewenste waarde in de kolom **[!UICONTROL Operation]**.

   >[!NOTE]
   >
   >**Updates beheren** De velden **[!UICONTROL lastModified]**, **[!UICONTROL modifiedBy]**, **[!UICONTROL created]** en **[!UICONTROL createdBy]** worden automatisch bijgewerkt wanneer een activiteit voor het bijwerken van data wordt uitgevoerd, tenzij hun configuratie uitdrukkelijk in de tabel voor het bijwerken van velden wordt uitgevoerd. De update wordt alleen uitgevoerd op de records waarvoor minstens één verschil is gedetecteerd. Als de waarden gelijk zijn, wordt geen update uitgevoerd.

1. Indien nodig beheert u de [Overgangen](../../automating/using/activity-properties.md) van de activiteit om toegang te krijgen tot de geavanceerde opties voor de uitgaande populatie.

   Als u **[!UICONTROL Insert only]** hebt geselecteerd en de geïmporteerde data mogelijk records bevatten die al in de database aanwezig zijn, schakelt u het selectievakje **[!UICONTROL Generate an outbound transition for the rejects]** in om mogelijke fouten te voorkomen.

1. Bevestig de configuratie van uw activiteit en sla de workflow op.
