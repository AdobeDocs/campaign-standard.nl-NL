---
title: Aangepaste bronnen
description: Meer informatie over het beheer van aangepaste bronnen met API's/
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
source-wordcount: '183'
ht-degree: 3%

---


# Interactie met aangepaste resources {#interacting-with-custom-resources}

Het **/customResources** eindpunt staat u toe om de ACS douanemiddelen in REST bloot te stellen. Op basis van deze API is er een integratie tussen aangepaste entiteiten en externe eindpunten beschikbaar.

Het /customResources eindpunt heeft precies het zelfde gedrag zoals /profileAndServices eindpunt.

De aangepaste bronnen die worden weergegeven in deze API zijn:

* alle entiteiten die aan de profielentiteit zijn gekoppeld
* alle entiteiten die zijn gekoppeld aan de onderliggende items van de profielentiteit
* alle entiteiten die niet aan een profiel zijn gekoppeld en, voor deze entiteiten, hun kinderen en kleinkinderen.

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
>U bent verantwoordelijk voor het beheren en opschonen van alle PII&#39;s voor deze aangepaste bronnen. Klik [hier](../../api/using/creating-a-privacy-request.md)voor meer informatie over het privacygereedschap.

