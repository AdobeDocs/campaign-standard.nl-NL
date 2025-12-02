---
title: Kenmerken van een geografische eenheid bijwerken
description: Leer hoe u kenmerken van een geografische eenheid kunt bijwerken met API's
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 86810821-6f62-46ab-ba0b-2175797fe9dd
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '86'
ht-degree: 0%

---

# Kenmerken van een geografische eenheid bijwerken {#managing-geographical-units}

1. Voer een verzoek van GET op het **geoUnitBase** middel uit om de Geografische eenheid PKey terug te winnen.
1. Voer een PATCH-verzoek uit op de geografische eenheid, met de kenmerken die moeten worden bijgewerkt in de lading.

<br/>

***verzoek van de Steekproef***

De lijst van geografische eenheden ophalen.

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

Voer een PATCH-verzoek uit op de geografische eenheid, met de kenmerken die moeten worden bijgewerkt in de lading.

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
