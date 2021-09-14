---
title: Tellen
description: Leer hoe u telbewerkingen uitvoert.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: d6354249-3b0d-4532-951f-b0fae953f7e1
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '87'
ht-degree: 2%

---

# Tellen

De Adobe Campaign REST API kan het aantal records in een aanvraag tellen. Om dit te doen, gebruik URL die in **count** knoop is teruggekeerd.

<br/>

***Voorbeeldverzoek***

Om alle diensten te tellen die een **messageType** waarde gelijk aan &quot;sms&quot;hebben, voer een verzoek van de GET met **byChannel** filter uit.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/byChannel?channel=sms \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Het keert de diensten terug die aan de filter beantwoorden.

```
{
    "content": [
        {
            ...
            "messageType": "sms",
            "mode": "newsletter",
            "name": "SVC6",
            ...
        },
        ...
    ],
    "count": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/byChannel/_count?channel=sms&_lineStart=@iKTZ2q3IiSEDqZ5Nw1vdoGnQCqF-8DAUJRaVwR9obqqTxhMy"
    },
    "serverSidePagination": true
}
```

Voer een verzoek van de GET op **count** knoop URL uit om het aantal resultaten terug te winnen.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/byChannel/_count?channel=sms&_lineStart=@iKTZ2q3IiSEDqZ5Nw1vdoGnQCqF-8DAUJRaVwR9obqqTxhMy \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Het retourneert het aantal records.

```
{
    "count": 26
}
```
