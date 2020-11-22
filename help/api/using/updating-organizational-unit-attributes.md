---
solution: Campaign Standard
product: campaign
title: Kenmerken van een organisatorische eenheid bijwerken
description: Leer hoe u kenmerken van een organisatie-eenheid kunt bijwerken
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '84'
ht-degree: 11%

---


# Kenmerken van een organisatorische eenheid bijwerken {#updating-organizational-unit-attributes}

1. Voer een verzoek van de GET op het **middel orgUnitBase** uit om de Organisatorische eenheid PKey terug te winnen.
1. Voer een verzoek van de PATCH op de Organisatorische eenheid uit, met de attributen om in de lading bij te werken.

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

Alle organisatie-eenheden worden geretourneerd. Haal de sleutel van de gewenste eenheid op.

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

Voer een verzoek van de PATCH op de Organisatorische eenheid uit, met de attributen om in de lading bij te werken.

```
-X PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
-i
-d {
-d "label":"brand1",
-d "name":"brand1"
-d }
```

<!-- + réponse -->
