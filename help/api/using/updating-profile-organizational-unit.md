---
title: De organisatorische eenheid van een profiel bijwerken
description: Leer hoe u de Organizer-eenheid van een profiel kunt bijwerken met API's.
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
source-wordcount: '96'
ht-degree: 10%

---


# De organisatorische eenheid van een profiel bijwerken {#managing-organizational-units}

1. Voer een verzoek van de GET op het **orgUnitBase** middel uit om de Organisatorische eenheid PKey terug te winnen
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
