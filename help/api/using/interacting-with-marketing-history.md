---
title: Interactie met de marketinggeschiedenis
description: Leer hoe u communiceert met de marketinggeschiedenis van profielen
feature: API
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 67282d21-b4ed-4af5-b751-848a6d705118
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '147'
ht-degree: 0%

---

# Interactie met de marketinggeschiedenis{#interacting-with-marketing-history}

Het **historie** eindpunt laat u met de marketing van een profiel in wisselwerking staan.
Op deze manier kunt u bijvoorbeeld gemakkelijk de spiegelpagina ophalen voor een levering die naar een profiel is verzonden. Hiervoor voert u de volgende stappen uit:

1. Voer een GET met het **historie** eindpunt en de primaire sleutel van het profiel uit.
1. Voer een verzoek van GET op de **teruggekeerde gebeurtenissen** href uit.
1. Het keert de lijst van gebeurtenissen voor het profiel met verbindingen aan spiegelpagina&#39;s in de **mirrorPage** knoop terug.

<br/>

***verzoek van de Steekproef***

Haal de marketinggeschiedenis van het profiel op met een GET-aanvraag.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/history/"<PKEY>" \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Het knooppunt &quot;events&quot; retourneert de URL die u toegang geeft tot de gebeurtenissen in het profiel.

```
{
  "PKey": "<PKEY>",
  "firstName": "John",
  "lastName":"Doe",
  "birthDate": "1980-10-24",
  "events": {
    "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/history/<PKEY>/events/",
    "metadata": "subHisto"
    },
}
```

Voer een GET-verzoek uit op de gebeurtenissen die door href zijn geretourneerd.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/history/<PKEY>/events \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Het keert de lijst van gebeurtenissen voor het profiel met verbindingen aan spiegelpagina&#39;s in de knoop &quot;mirrorPage&quot;terug.

```
    {
      "PKey": "<PKEY>",
      "category": "email",
      "date": "2018-05-17 08:44:49.366Z",
      "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/history/<PKEY>/events/<PKEY>",
      "label": "Send via email",
      "mirrorPage": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/history/<PKEY>/events/<PKEY>/mirrorPage/"
      },
      "type": "outbound"
    }
```
