---
title: De organisatorische eenheid van een profiel bijwerken
description: Leer hoe u de Organizer-eenheid van een profiel kunt bijwerken met API's.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 6ce49aeb-a113-43ee-bfe3-f26a4a9e2a56
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 10%

---

# De organisatorische eenheid van een profiel bijwerken {#managing-organizational-units}

1. Voer een verzoek van de GET uit op **orgUnitBase** bron voor het ophalen van de PKey-organisatie
1. Voer een verzoek van PATCH op het profiel PKey, met de gewenste Organisatorische eenheid PKey in de lading uit.

<br/>

***Voorbeeldverzoek***

Hiermee wordt de lijst met organisatorische eenheden opgehaald.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/ \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Alle organisatie-eenheden worden geretourneerd. Haal de sleutel van de eenheid op waaraan u het profiel wilt toewijzen.

```
{
  "PKey": "<PKEY>",
  "created": "2019-04-02 22:36:13.252Z",
  "desc": "",
  "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/<PKEY>",
  "label": "Brand 4",
  "lastModified": "2019-04-03 07:34:56.579Z",
  "name": "brand4",
  "parentTitle": "All (all)",
  "title": "Brand 4 (brand1)"
},
```

Voer een verzoek van de PATCH op het profiel, met PKey van de gewenste Organisatorische eenheid in de lading uit.

```
-X PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
-i
-d {
-d "orgUnit":{
-d    "PKey":"<PKEY>"
-d  }
-d }
```

<!-- + réponse -->
