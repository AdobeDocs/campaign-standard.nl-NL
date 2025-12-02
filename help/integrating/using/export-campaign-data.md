---
title: Gegevens exporteren van Campaign naar Adobe Experience Platform
description: Leer hoe u gegevens exporteert van Campaign Standard naar Adobe Experience Platform.
audience: integrating
content-type: reference
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: eccd2922-0e75-4525-9b60-b48f628deeae
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 4%

---

# Gegevens exporteren van Campaign naar Adobe Experience Platform {#sources}

Als u Campaign Standard-gegevens wilt exporteren naar Adobe Real-time Customer Data Platform (RTCDP), moet u eerst een workflow in Campaign Standard maken om de gegevens die u wilt delen naar uw Amazon Storage Service (S3) of Azure Blob-opslaglocatie te exporteren.

Zodra het werkschema is gevormd en de gegevens die naar uw opslagplaats worden verzonden, moet u uw S3 of Azure opslagplaats van de blob als a **Source** in de ervaringsplatform van Adobe verbinden.

>[!NOTE]
>
>Houd er rekening mee dat we het exporteren van gegevens die zijn gegenereerd door campagne alleen aanbevelen (bijvoorbeeld verzenden, openen, klikken, enz.) naar Adobe Experience Platform. Gegevens die van een bron van derden (zoals uw CRM) worden ontvangen, moeten rechtstreeks in Adobe Experience Platform worden geïmporteerd.

## Een exportworkflow maken in Campaign Standard

Als u gegevens van Campaign Standard naar de opslaglocatie van de S3- of Azure Blob wilt exporteren, moet u een workflow maken om de gegevens die u wilt exporteren als doel in te stellen en deze naar de opslaglocatie te verzenden.

Hiervoor kunt u toevoegen en configureren:

* Een **[!UICONTROL Extract file]** -activiteit om de doelgegevens uit te pakken in een CSV-bestand. Voor meer op hoe te om deze activiteit te vormen, verwijs naar [&#x200B; deze sectie &#x200B;](../../automating/using/extract-file.md).

  ![](assets/rtcdp-extract-file.png)

* Een **[!UICONTROL Transfer file]** -activiteit om het CSV-bestand over te brengen naar de opslaglocatie. Voor meer op hoe te om deze activiteit te vormen, verwijs naar [&#x200B; deze sectie &#x200B;](../../automating/using/transfer-file.md).

  ![](assets/rtcdp-transfer-file.png)

In de onderstaande workflow worden logbestanden regelmatig uitgepakt in een CSV-bestand en wordt het bestand vervolgens overgebracht naar een opslaglocatie.

![](assets/aep-export.png)

De voorbeelden van werkschema&#39;s van het gegevensbeheer zijn beschikbaar in de [&#x200B; werkschema&#39;s gebruiken gevallen &#x200B;](../../automating/using/about-workflow-use-cases.md#management) sectie.

Verwante onderwerpen:

* [Gegevensbeheeractiviteiten](../../automating/using/about-data-management-activities.md)
* [Informatie over gegevens importeren en exporteren](../../automating/using/about-data-import-and-export.md)


## Sluit uw opslaglocatie aan als een Source

De belangrijkste stappen om uw de opslagplaats van de Opslag van de Opslag van Amazon te verbinden (S3) of Azure Blob als a **Source** in het de ervaringsplatform van Adobe zijn hieronder vermeld. De gedetailleerde informatie over elk van deze stappen is beschikbaar in de [&#x200B; connectordocumentatie van Source &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=nl).

1. Maak in het menu van het Adobe Experience-platform een verbinding met uw opslaglocatie:**[!UICONTROL Sources]**

   * [&#x200B; creeer een Amazon S3 bronverbinding &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/s3.html?lang=nl-NL)
   * [&#x200B; Azure Blob schakelaar &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/cloud-storage/blob.html?lang=nl-NL)

   >[!NOTE]
   >
   >De opslaglocatie kan Amazon S3, SFTP met wachtwoord, SFTP met SSH-sleutel of Azure Blob-verbindingen zijn. De voorkeursmethode voor het verzenden van gegevens naar Adobe Campaign is Amazon S3 of Azure Blob:

   ![](assets/rtcdp-connector.png)

1. Configureer een gegevensstroom voor een batchverbinding voor cloudopslag. Een dataflow is een geplande taak die gegevens van de opslagplaats aan een dataset van Adobe Experience Platform terugwint en opneemt. Met deze stappen kunt u de gegevensinvoer vanaf uw opslaglocatie configureren, inclusief gegevensselectie en de toewijzing van de CSV-velden aan een XDM-schema.

   De gedetailleerde informatie is beschikbaar in [&#x200B; deze pagina &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html?lang=nl-NL).

   ![](assets/rtcdp-map-xdm.png)

1. Nadat de Source is geconfigureerd, importeert Adobe Experience Platform het bestand vanaf de opslaglocatie die u hebt opgegeven.

   Deze bewerking kan volgens uw behoeften worden gepland. We raden u aan de exportbewerking tot zes keer per dag uit te voeren, afhankelijk van de belasting die al op het exemplaar aanwezig is.
