---
title: Gegevens bijwerken
description: Met de gegevensactiviteit Update kunt u een massa-update uitvoeren op velden in de database.
page-status-flag: never-activated
uuid: 1dc55db5-affd-4688-b673-adfb8c1338b5
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: 4db83c95-4b75-4a16-8dbf-bd8940431fa9
context-tags: writer,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 87e0611fae0560aca276caa3c4cf793e9c095d72
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 0%

---


# Gegevens bijwerken{#update-data}

## Beschrijving {#description}

![](assets/data_update.png)

Met deze **[!UICONTROL Update data]** activiteit kunt u een massale update uitvoeren op velden in de database.

## Gebruikscontext {#context-of-use}

De **activiteit van de Gegevens** van de Update kan na het invoeren van een dossier worden gebruikt om de gegevens op te nemen die in het gegevensbestand van Adobe Campaign worden teruggekregen. Met verschillende opties kunt u het bijwerken van de gegevens aanpassen.

**Verwante onderwerpen:**

* [Hoofdlettergebruik: Gegevens bijwerken die zijn gebaseerd op een bestand](../../automating/using/update-database-file.md)
* [Gegevens bijwerken op basis van een automatische bestandsdownload](../../automating/using/update-data-automatic-download.md)

## Configuratie {#configuration}

1. Sleep een **[!UICONTROL Update data]** activiteit naar uw werkstroom.
1. Selecteer de activiteit, dan open het gebruikend de ![](assets/edit_darkgrey-24px.png) knoop van de snelle acties die verschijnen.
1. Geef aan welke **[!UICONTROL Operation type]** acties moeten worden uitgevoerd:

   * **[!UICONTROL Insert or update]**: gegevens invoegen of bijwerken als de records al in de database bestaan.
   * **[!UICONTROL Insert only]**: alleen gegevens invoegen. De records die al bestaan, worden niet bijgewerkt. Als er afstemmingscriteria worden gedefinieerd, worden alleen de niet-afstemmende gegevens toegevoegd.

      Schakel het **[!UICONTROL Generate an outbound transition for rejects]** selectievakje in als de geïmporteerde gegevens bepaalde records bevatten die al in de database staan om mogelijke fouten te voorkomen.

   * **[!UICONTROL Update]**: gegevens bijwerken van de records die alleen in de database bestaan.
   * **[!UICONTROL Delete]**: gegevens verwijderen.
   >[!NOTE]
   >
   >In het **[!UICONTROL Batch size]** veld kunt u de maximale batchgrootte definiëren voor de gegevens die u wilt uploaden.

1. Geef op het **[!UICONTROL Identification]** tabblad aan hoe de records in de database moeten worden geïdentificeerd:

   * **[!UICONTROL Using the targeting dimension]**: Selecteer vervolgens het **[!UICONTROL Dimension to update]** veld en geef het **[!UICONTROL Keys for finding records]** op. Voor meer dit, verwijs naar het [richten dimensies en middelen](../../automating/using/query.md#targeting-dimensions-and-resources).
   * Als de ingevoerde gegevens overeenkomen met een bestaande doeldimensie, selecteert u de **[!UICONTROL Using one or more links]** optie. Selecteer vervolgens de **[!UICONTROL Dimension to update]** selectie.
   Als het geselecteerde bewerkingstype een update vereist, moet u afstemmingssleutels gebruiken.

1. Geef op het **[!UICONTROL Fields to update]** tabblad de velden op waarop de update wordt toegepast en voeg, indien nodig, voorwaarden toe zodat deze update wordt uitgevoerd. Hiervoor gebruikt u de **[!UICONTROL Taken into account if]** kolom. De voorwaarden worden achter elkaar toegepast in de volgorde van de lijst. Gebruik de pijlen aan de rechterkant om de volgorde van de updates te wijzigen. U kunt hetzelfde doelveld meerdere keren gebruiken.

   U kunt velden automatisch koppelen met de ![](assets/wkf_magic_wand-24px.png) knop. Door automatische koppeling worden velden met dezelfde naam gedetecteerd.

   Tijdens een **[!UICONTROL Insert or update]** tekstbewerking kunt u afzonderlijk de bewerking selecteren die u voor elk veld wilt toepassen. Selecteer hiertoe de gewenste waarde in de **[!UICONTROL Operation]** kolom.

   >[!NOTE]
   >
   >**Het beheren van updates** de **[!UICONTROL lastModified]**, **[!UICONTROL modifiedBy]**, **[!UICONTROL created]** en **[!UICONTROL createdBy]** gebieden wordt automatisch bijgewerkt wanneer een activiteit van updategegevens in werking wordt gesteld, tenzij hun configuratie uitdrukkelijk op de lijst van de gebiedsupdate wordt uitgevoerd. De update wordt alleen uitgevoerd in de registers waar ten minste één verschil is vastgesteld. Als de waarden gelijk zijn, wordt geen update uitgevoerd.

1. Indien nodig, beheer de [Overgangen](../../automating/using/activity-properties.md) van de activiteit om tot de geavanceerde opties voor de uitgaande bevolking toegang te hebben.

   Als u hebt geselecteerd **[!UICONTROL Insert only]** en de geïmporteerde gegevens records kunnen bevatten die al in de database aanwezig zijn, schakelt u het **[!UICONTROL Generate an outbound transition for the rejects]** vakje in om mogelijke fouten te voorkomen.

1. Bevestig de configuratie van uw activiteit en sla uw werkschema op.
