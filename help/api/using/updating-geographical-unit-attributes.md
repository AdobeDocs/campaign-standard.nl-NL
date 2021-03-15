---
solution: Campaign Standard
product: campaign
title: Kenmerken van een geografische eenheid bijwerken
description: Leer hoe u kenmerken van een geografische eenheid kunt bijwerken met API's
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Gegevensengineer
level: Ervaren
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '90'
ht-degree: 12%

---


# Kenmerken van een geografische eenheid bijwerken {#managing-geographical-units}

1. Voer een verzoek van de GET op **geoUnitBase** middel uit om de Geografische eenheid PKey terug te winnen.
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
