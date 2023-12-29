---
title: Interactie met de marketinggeschiedenis
description: Leer hoe u communiceert met de marketinggeschiedenis van profielen
feature: API
role: Data Engineer
level: Experienced
exl-id: 67282d21-b4ed-4af5-b751-848a6d705118
source-git-commit: 64f24fb692754973331b4fb2f7b95e9a6f31cd0d
workflow-type: tm+mt
source-wordcount: '147'
ht-degree: 0%

---

# Interactie met de marketinggeschiedenis{#interacting-with-marketing-history}

De **geschiedenis** Met het eindpunt kunt u communiceren met de marketinggeschiedenis van een profiel.
Op deze manier kunt u bijvoorbeeld gemakkelijk de spiegelpagina ophalen voor een levering die naar een profiel is verzonden. Hiervoor voert u de volgende stappen uit:

1. Voer een GET uit met de **geschiedenis** en de primaire sleutel van het profiel.
1. Voer een verzoek van de GET uit op **gebeurtenissen** href gaf terug.
1. De lijst met gebeurtenissen voor het profiel wordt geretourneerd met koppelingen naar spiegel van pagina&#39;s in het dialoogvenster **mirrorPage** knooppunt.

<br/>

***Voorbeeldverzoek***

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

Voer een verzoek van de GET uit op de gebeurtenissen die href heeft geretourneerd.

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
