---
title: Interactie met de marketinggeschiedenis
description: Leer hoe u kunt communiceren met de marketinggeschiedenis van profielen.
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
source-wordcount: '147'
ht-degree: 10%

---


# Interactie met de marketinggeschiedenis {#interacting-with-marketing-history}

Het **** geschiedeniseindpunt laat u met de marketing geschiedenis van een profiel in wisselwerking staan.
Op deze manier kunt u bijvoorbeeld gemakkelijk de spiegelpagina ophalen voor een levering die naar een profiel is verzonden. Volg de onderstaande stappen om dit te doen:

1. Voer een GET met het **geschiedeniseindpunt** en de primaire sleutel van het profiel uit.
1. Voer een verzoek van de GET uit op de teruggekeerde **gebeurtenissen** href.
1. Het keert de lijst van gebeurtenissen voor het profiel met verbindingen aan spiegelpagina&#39;s in de **mirrorPage** knoop terug.

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
