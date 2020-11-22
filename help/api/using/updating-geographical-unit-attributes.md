---
solution: Campaign Standard
product: campaign
title: Kenmerken van een geografische eenheid bijwerken
description: Leer hoe u kenmerken van een geografische eenheid kunt bijwerken met API's
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '86'
ht-degree: 11%

---


# Kenmerken van een geografische eenheid bijwerken {#managing-geographical-units}

1. Voer een verzoek van de GET op het **geoUnitBase** middel uit om de Geografische eenheid PKey terug te winnen.
1. Voer een verzoek van de PATCH op de Geografische eenheid uit, met de attributen in de lading bij te werken.

<br/>

***Voorbeeldverzoek***

Hiermee wordt de lijst van geografische eenheden opgehaald.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/geoUnitBase/ \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Alle geografische eenheden worden geretourneerd. Haal de sleutel van de gewenste eenheid op.

```
{
 "PKey": "<PKEY>",
 "created": "2019-04-06 22:36:19.089Z",
 "desc": "",
 "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/geoUnitBase/<PKEY>",
 "label": "Europe",
 "lastModified": "2019-04-06 22:36:19.086Z",
 "name": "eu",
 "parentTitle": "All (all)",
 "title": "Europe (eu)"
},
```

Voer een verzoek van de PATCH op de Geografische eenheid uit, met de attributen in de lading bij te werken.

```
-X PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
-i
-d {
-d "label":"Asia",
-d "name":"asia"
-d }
```

<!-- + réponse -->
