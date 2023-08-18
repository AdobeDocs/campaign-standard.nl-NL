---
title: Een service met API's maken
description: Leer hoe u een service maakt met API's
feature: API
role: Data Engineer
level: Experienced
exl-id: 91bbce9e-a618-4be2-840b-c7d021271f4e
source-git-commit: 02f1ef1f960cf98b5277b2db960e61ae20e22209
workflow-type: tm+mt
source-wordcount: '77'
ht-degree: 0%

---

# Een service met API&#39;s maken{#creating-a-service-api}

Services maken wordt uitgevoerd met een **POST** verzoek op het de dienstmiddel.

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

De nieuwe service wordt met de bijgewerkte kenmerken geretourneerd.

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
