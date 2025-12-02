---
title: Eindpunten
description: Meer informatie over de eindpunten van de API's.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 9f6d3da6-374d-47f5-bc8f-b31b19cbb5ca
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '225'
ht-degree: 11%

---

# Eindpunten {#endpoints}

De beschikbare eindpunten voor de Adobe Campaign REST API:

* **/profileAndServices**: interactie met uit de vakgebieden. Uitgebreide velden zijn niet toegankelijk met dit eindpunt.
* **/profileAndServicesExt**: communiceer met douanevelden die tijdens de uitbreiding van het Profiel of van de Dienstbron worden toegevoegd. Voor meer op douanemiddelen, verwijs naar [&#x200B; deze sectie &#x200B;](../../api/using/custom-resources.md).
* **/&lt;transactieAPI>**: interactie met de transactie berichten API (de naam van het transactie berichten API eindpunt hangt van uw instantieconfiguratie af). Raadpleeg [deze sectie](../../api/using/managing-transactional-messages.md) voor meer informatie.
* **/ workflow/uitvoering** : communiceer met workflows. Raadpleeg [deze sectie](../../api/using/controlling-a-workflow.md) voor meer informatie.
* **/privacy/privacyTool**: communiceer met privacy API om het automatische proces van privacyverzoeken toe te staan. Raadpleeg [deze sectie](../../api/using/creating-a-privacy-request.md) voor meer informatie.
* **/history**: wik de de marketing geschiedenis van de profielen terug. Voor meer op geïntegreerde klantenprofielen in Campagne, verwijs naar de [&#x200B; documentatie van de Campagne &#x200B;](https://helpx.adobe.com/nl/campaign/standard/audiences/using/integrated-customer-profile.html).

Door gebrek, zijn de belangrijkste middelen beschikbaar voor **profileAndServices** en **profileAndServicesExt** APIs:

* **/profile**: interactie met profielen van het gegevensbestand van de Campagne. Om profielen aan de dienst toe te voegen, gebruik het **/dienst** eindpunt. Voor meer op profielen in Campagne, verwijs naar de [&#x200B; documentatie van de Campagne &#x200B;](https://helpx.adobe.com/nl/campaign/standard/audiences/using/about-profiles.html).
* **/service**: beheer abonnementsservices. Voor meer op de diensten in Campagne, verwijs naar de [&#x200B; documentatie van de Campagne &#x200B;](https://helpx.adobe.com/nl/campaign/standard/audiences/using/creating-a-service.html).

>[!NOTE]
>
>Alle andere middelen die zijn uitgebreid of gecreeerd zijn beschikbaar via **ProfileAndServicesExt** slechts API. Zij moeten met het **1&rbrace; middel van het Profiel &lbrace;worden verbonden om toegankelijk te zijn.**
