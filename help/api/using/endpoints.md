---
title: Eindpunten
description: Meer informatie over de eindpunten van de API's.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 9f6d3da6-374d-47f5-bc8f-b31b19cbb5ca
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 10%

---

# Eindpunten {#endpoints}

De beschikbare eindpunten voor de Adobe Campaign REST API:

* **/profileAndServices**: communiceren met velden buiten het vak. Uitgebreide velden zijn niet toegankelijk met dit eindpunt.
* **/profileAndServicesExt**: interactie met douanevelden die tijdens de uitbreiding van het Profiel of van de Douane van de Diensten worden toegevoegd. Raadpleeg [deze sectie](../../api/using/custom-resources.md) voor meer informatie over aangepaste bronnen.
* **/&lt;transactionalapi>**: wisselt met de transactie berichten API (de naam van het transactie berichten API eindpunt hangt van uw instantieconfiguratie af). Raadpleeg [deze sectie](../../api/using/managing-transactional-messages.md) voor meer informatie.
* **/workflow/uitvoering**: werken met workflows. Raadpleeg [deze sectie](../../api/using/controlling-a-workflow.md) voor meer informatie.
* **/privacy/privacyTool**: communiceren met de privacy-API zodat het automatische proces van privacyverzoeken mogelijk is. Raadpleeg [deze sectie](../../api/using/creating-a-privacy-request.md) voor meer informatie.
* **/geschiedenis**: de marketinggeschiedenis van de profielen ophalen. Raadpleeg de [Campagne-documentatie](https://helpx.adobe.com/campaign/standard/audiences/using/integrated-customer-profile.html) voor meer informatie over geïntegreerde klantprofielen in Campagne.

Standaard zijn de belangrijkste bronnen die beschikbaar zijn voor de API&#39;s **profileAndServices** en **profileAndServicesExt**:

* **/profiel**: communiceren met profielen uit de Campagne-database. Als u profielen wilt toevoegen aan een service, gebruikt u het **/service**-eindpunt. Raadpleeg de [Campagne-documentatie](https://helpx.adobe.com/campaign/standard/audiences/using/about-profiles.html) voor meer informatie over profielen in campagne.
* **/service**: abonnementsservices beheren. Raadpleeg de [Campagne-documentatie](https://helpx.adobe.com/campaign/standard/audiences/using/creating-a-service.html) voor meer informatie over services in Campagne.

>[!NOTE]
>
>Alle andere bronnen die zijn uitgebreid of gemaakt, zijn alleen beschikbaar via de **ProfileAndServicesExt**-API. Ze moeten gekoppeld zijn aan de **Profile**-bron om toegankelijk te zijn.
