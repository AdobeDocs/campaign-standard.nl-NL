---
solution: Campaign Standard
product: campaign
title: De geografische eenheid van een profiel bijwerken
description: Leer hoe u geografische eenheden beheert met API's.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '98'
ht-degree: 11%

---


# De geografische eenheid van een profiel bijwerken {#updating-a-geographical-unit}

1. Voer een verzoek van de GET op **geoUnitBase** middel uit om de Geografische eenheid PKey terug te winnen.
1. Voer een verzoek van PATCH op het profiel PKey, met de gewenste Geografische eenheid PKey in de lading uit.

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

Alle geografische eenheden worden geretourneerd. Haal de sleutel van de eenheid op waaraan u het profiel wilt toewijzen.

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

Voer een verzoek van PATCH op het profiel, met PKey van de gewenste Geografische eenheid in de lading uit.

```
-X PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
-i
-d {
-d "geoUnit":{
-d    "PKey":"<PKEY>"
-d  }
-d }
```

<!-- + réponse -->
