---
title: Kenmerken van een geografische eenheid bijwerken
description: Leer hoe u kenmerken van een geografische eenheid kunt bijwerken met API's
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 86810821-6f62-46ab-ba0b-2175797fe9dd
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '86'
ht-degree: 11%

---

# Kenmerken van een geografische eenheid bijwerken {#managing-geographical-units}

1. Voer een verzoek van de GET uit op **geoUnitBase** bron voor het ophalen van de geografische eenheid PKey.
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
