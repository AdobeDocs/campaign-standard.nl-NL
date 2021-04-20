---
solution: Campaign Standard
product: campaign
title: Een service maken
description: Leer hoe u een service maakt met API's.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '77'
ht-degree: 9%

---


# Een service maken {#creating-a-service}

De verwezenlijking van de diensten wordt uitgevoerd met een **POST** verzoek op de de dienstmiddel.

Als u de dienst met specifieke attributen wilt tot stand brengen, voeg hen in de lading toe. Anders, zal de nieuwe dienst met standaarddegenen worden gecreeerd.

<br/>

***Voorbeeldverzoek***

De vraag van de POST van de steekproef om de dienst met specifieke attributen tot stand te brengen.

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/ \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
-i
-d {
-d "label": "My newsletter",
-d "messageType": "email",
-d "name": "email_newsletter",
-d "start": "2019-10-06"
-d }
```

Het keert de pas gecreëerde dienst met de bijgewerkte attributen terug.

```
{
    "PKey": "<PKEY>",
    "builtIn": false,
    "created": "2019-09-26 12:00:37.005Z",
    "href": "https://mc.adobe.io/<ORGANIZATION>/profileAndServices/service/@NLscZuVHxdVu9rPftvrMWFfR1zRIxQGswSOmGLrK09JTF_iWhB0JCUHEndA_vvy__k9mzOYa5NVkcWDcrK8qGh0wygahX9kRcD44kiWWSEceShn3",
    "label": "My newsletter",
    ...
}
```
