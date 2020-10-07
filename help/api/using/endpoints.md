---
title: Eindpunten
description: Meer informatie over de eindpunten van de API's.
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 10%

---


# Eindpunten {#endpoints}

De beschikbare eindpunten voor de Adobe Campaign REST API:

* **/profileAndServices**: communiceren met velden buiten het vak. Uitgebreide velden zijn niet toegankelijk met dit eindpunt.
* **/profileAndServicesExt**: interactie met douanevelden die tijdens de uitbreiding van het Profiel of van de Douane van de Diensten worden toegevoegd. For more on custom resources, refer to [this section](../../api/using/custom-resources.md).
* **/&lt;transactieAPI>**: wisselt met de transactie berichten API (de naam van het transactie berichten API eindpunt hangt van uw instantieconfiguratie af). Raadpleeg [deze sectie](../../api/using/managing-transactional-messages.md) voor meer informatie.
* **/workflow/uitvoering**: werken met workflows. Raadpleeg [deze sectie](../../api/using/controlling-a-workflow.md) voor meer informatie.
* **/privacy/privacyTool**: communiceren met de privacy-API zodat het automatische proces van privacyverzoeken mogelijk is. Raadpleeg [deze sectie](../../api/using/creating-a-privacy-request.md) voor meer informatie.
* **/geschiedenis**: de marketinggeschiedenis van de profielen ophalen. Raadpleeg de [documentatie](https://helpx.adobe.com/campaign/standard/audiences/using/integrated-customer-profile.html)bij Campagne voor meer informatie over geïntegreerde klantprofielen in Campagne.

Standaard zijn de belangrijkste bronnen beschikbaar voor de API&#39;s **profileAndServices** en **profileAndServicesExt** :

* **/profiel**: communiceren met profielen uit de Campagne-database. Om profielen aan de dienst toe te voegen, gebruik het **/de diensteindpunt** . Raadpleeg de documentatie bij [Campagne voor meer informatie over profielen in Campagne](https://helpx.adobe.com/campaign/standard/audiences/using/about-profiles.html).
* **/service**: abonnementsservices beheren. Raadpleeg de documentatie bij [Campagne voor meer informatie over services in Campagne](https://helpx.adobe.com/campaign/standard/audiences/using/creating-a-service.html).

>[!NOTE]
>
>Alle andere bronnen die zijn uitgebreid of gemaakt, zijn alleen beschikbaar via de **ProfileAndServicesExt** -API. Ze moeten gekoppeld zijn aan de **profielbron** om toegankelijk te zijn.
