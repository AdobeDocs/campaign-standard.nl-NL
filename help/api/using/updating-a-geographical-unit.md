---
title: De geografische eenheid van een profiel bijwerken
description: Leer hoe u geografische eenheden beheert met API's.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 9dc07d86-00b2-4885-b6ac-0a6f9bc45236
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '94'
ht-degree: 10%

---

# De geografische eenheid van een profiel bijwerken {#updating-a-geographical-unit}

1. Voer een verzoek van GET op het **geoUnitBase** middel uit om de Geografische eenheid PKey terug te winnen.
1. Voer een PATCH-verzoek uit op het profiel PKey met de gewenste geografische eenheid PKey in de lading.

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

Voer een PATCH-aanvraag voor het profiel uit met de PKey van de gewenste geografische eenheid in de payload.

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
