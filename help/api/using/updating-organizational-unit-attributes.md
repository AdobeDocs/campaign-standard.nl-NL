---
title: Kenmerken van een organisatie-eenheid bijwerken
description: Leer hoe u kenmerken van een organisatie-eenheid kunt bijwerken
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 90841afd-ebc2-4b6a-895e-a96ef65740d7
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '84'
ht-degree: 0%

---

# Kenmerken van een organisatie-eenheid bijwerken {#updating-organizational-unit-attributes}

1. Voer een verzoek van de GET uit op **orgUnitBase** bron voor het ophalen van de PKey-organisatie.
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
