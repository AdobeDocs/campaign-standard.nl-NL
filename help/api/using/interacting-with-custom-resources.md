---
solution: Campaign Standard
product: campaign
title: Aangepaste bronnen
description: Meer informatie over het beheer van aangepaste bronnen met API's/
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
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

