---
solution: Campaign Standard
product: campaign
title: Gegevens exporteren van Campaign naar Adobe Experience Platform
description: Leer hoe u gegevens exporteert van Campaign Standard naar Adobe Experience Platform.
audience: integrating
content-type: reference
feature: Bronnen en bestemmingen
role: Data Architect
level: Intermediate
exl-id: eccd2922-0e75-4525-9b60-b48f628deeae
translation-type: tm+mt
source-git-commit: 4855585539653a0bb496d210b001765b5b557570
workflow-type: tm+mt
source-wordcount: '529'
ht-degree: 4%

---

# Gegevens exporteren van Campaign naar Adobe Experience Platform {#sources}

Als u Campaign Standard-gegevens wilt exporteren naar het RTCDP-Platform (Adobe Real-Time Customer Data ), moet u eerst een workflow in Campaign Standard maken om de gegevens die u wilt delen naar uw Amazon Storage Service (S3) of Azure Blob-opslaglocatie te exporteren.

Nadat de workflow is geconfigureerd en de gegevens naar de opslaglocatie zijn verzonden, moet u de opslaglocatie van uw S3- of Azure-blok aansluiten als een **Source** in het Platform Adobe Experience.

>[!NOTE]
>
>Houd er rekening mee dat we alleen het exporteren van door campagne gegenereerde gegevens aanbevelen (bijvoorbeeld verzenden, openen, klikken enz.) naar Adobe Experience Platform. Gegevens die van een bron van derden (zoals uw CRM) worden ontvangen, moeten rechtstreeks in Adobe Experience Platform worden geïmporteerd.

## Een exportworkflow maken in Campaign Standard

Als u gegevens van Campaign Standard naar uw opslaglocatie van S3 of Azure Blob wilt exporteren, moet u een workflow maken om de gegevens die u wilt exporteren als doel in te stellen en deze naar uw opslaglocatie te verzenden.

Hiervoor kunt u toevoegen en configureren:

* Een **[!UICONTROL Extract file]** activiteit om de gerichte gegevens in een Csv- dossier te halen. Raadpleeg [deze sectie](../../automating/using/extract-file.md) voor meer informatie over het configureren van deze activiteit.

   ![](assets/rtcdp-extract-file.png)

* Een **[!UICONTROL Transfer file]** activiteit om het CSV dossier naar uw opslagplaats over te brengen. Raadpleeg [deze sectie](../../automating/using/transfer-file.md) voor meer informatie over het configureren van deze activiteit.

   ![](assets/rtcdp-transfer-file.png)

In de onderstaande workflow worden logbestanden regelmatig uitgepakt in een CSV-bestand en wordt het bestand vervolgens overgebracht naar een opslaglocatie.

![](assets/aep-export.png)

De voorbeelden van werkschema&#39;s van het gegevensbeheer zijn beschikbaar in [werkschema&#39;s gebruiken gevallen](../../automating/using/about-workflow-use-cases.md#management) sectie.

Verwante onderwerpen:

* [Databeheeractiviteiten](../../automating/using/about-data-management-activities.md)
* [Informatie over data importeren en exporteren](../../automating/using/about-data-import-and-export.md)


## De opslaglocatie aansluiten als bron

De belangrijkste stappen om uw opslagplaats van Amazon Storage Service (S3) of Azure Blob als **Bron** in het Platform van de Ervaring van Adobe aan te sluiten zijn hieronder vermeld. Gedetailleerde informatie over elk van deze stappen is beschikbaar in de [documentatie van de bronschakelaars](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html).

1. Maak in het menu van het Adobe Experience-platform een verbinding met uw opslaglocatie:**[!UICONTROL Sources]**

   * [Een Amazon S3-bronverbinding maken](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/s3.html)
   * [Azure Blob-connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/cloud-storage/blob.html)

   >[!NOTE]
   >
   >De opslaglocatie kan Amazon S3, SFTP met wachtwoord, SFTP met SSH-sleutel of Azure Blob-verbindingen zijn. De voorkeursmethode voor het verzenden van gegevens naar Adobe Campaign is Amazon S3 of Azure Blob:

   ![](assets/rtcdp-connector.png)

1. Configureer een gegevensstroom voor een batchverbinding voor cloudopslag. Een dataflow is een geplande taak die gegevens van de opslagplaats aan een dataset van Adobe Experience Platform terugwint en opneemt. Met deze stappen kunt u de gegevensinvoer vanaf uw opslaglocatie configureren, inclusief gegevensselectie en de toewijzing van de CSV-velden aan een XDM-schema.

   Gedetailleerde informatie is beschikbaar in [deze pagina](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html).

   ![](assets/rtcdp-map-xdm.png)

1. Nadat de Bron is gevormd, zal Adobe Experience Platform het dossier van de opslagplaats invoeren die u verstrekte.

   Deze bewerking kan volgens uw behoeften worden gepland. We raden u aan de exportbewerking tot zes keer per dag uit te voeren, afhankelijk van de belasting die al op het exemplaar aanwezig is.
