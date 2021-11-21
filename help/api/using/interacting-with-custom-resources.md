---
title: Aangepaste bronnen
description: Meer informatie over het beheer van aangepaste bronnen met API's/
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 19bfeecb-da60-479c-a929-0cfb72ef59e3
source-git-commit: 13d419c5fc51845ee14f8a3b288f4c467e0a60d9
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 3%

---

# Interactie met aangepaste resources {#interacting-with-custom-resources}

De **/customResources** het eindpunt staat u toe om de de douanemiddelen van de Campagne in REST bloot te stellen. Op basis van deze API is er een integratie tussen aangepaste entiteiten en externe eindpunten beschikbaar.

Het /customResources eindpunt heeft precies het zelfde gedrag zoals /profileAndServices eindpunt.

De aangepaste bronnen die worden weergegeven in deze API zijn:

* alle entiteiten die niet onder /profileAndServicesExt worden blootgesteld
* alle entiteiten die niet aan een profiel zijn gekoppeld en, voor deze entiteiten, hun kinderen en kleinkinderen.
* standaard alle entiteiten die niet aan iets zijn gekoppeld, en hun kinderen en kleinkinderen.

>[!NOTE]
>De douanemiddelen die onder /profileAndServicesExt beschikbaar zijn worden niet blootgesteld in /customResources API.


Hier volgt een voorbeeld om de metagegevens op te halen uit een aangepaste bron:

```
GET /customResources/resourceType/<customResourceName>
```

Voor het maken, bijwerken of verwijderen worden de GET, POST, PATCH, DELETE gebruikt.

```
POST /customResources/<customResourceName>
```

>[!NOTE]
>Het API-eindpunt en de workflows voor privacy (of privacy/privacyTool) beheren niet de aangepaste bronnen die niet aan de profielentiteit zijn gekoppeld.
>U bent verantwoordelijk voor het beheren en opschonen van alle PII&#39;s voor deze aangepaste bronnen. Voor meer informatie over het privacygereedschap, [klik hier](../../api/using/creating-a-privacy-request.md).
