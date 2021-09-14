---
title: Profielen bijwerken
description: Meer informatie over het bijwerken van profielen met API's.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: fa3796ee-a00c-4d70-bf3d-e8d2099f1116
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 4%

---

# Profielen bijwerken {#updating-profiles}

Het bijwerken van profielen wordt uitgevoerd met een **PATCH** verzoek.

`https://mc.adobe.io/<ORGANIZATION>/campaign/<apiName>/<resourceName>/<PKEY>`

1. De eerste stap is het **ophalen van het profiel**.

1. In een tweede verzoek, zullen wij **PATCH verzoek** op het profiel met de voltooide informatie in de nuttige lading uitvoeren.

1. Om te controleren of het PATCH verzoek het profiel heeft bijgewerkt, kunnen wij een definitieve GET verzoek uitvoeren.

<br/>

***Voorbeeldverzoek***

Voorbeeld van GET-aanvraag om een profiel op te halen.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY>\
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Antwoord op het verzoek.

```
{
    "content": [
        {
            "PKey": "<PKEY>",
            "firstName": "Amy",
            "lastName":"Dakota",
            "birthDate": "1980-10-24",
            ...
        }
    ]
}
```

PATCH request to update the &quot;phone&quot; attribute.

```
-X PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-d '{"phone":"3301020304"}'
```

De URL en PKEY worden geretourneerd om het bijgewerkte profiel op te halen.

```
{
    "PKey": "<PKEY>",
    "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/@2v1dr3ZKJveMDhAdh0MPnh9hNQQ93qb7AW6BNVVKknjwXvTZRBAgUqz1SNcB4ZndgjqOofx3BwBZYBftlmObISoM3rs"
}
```
