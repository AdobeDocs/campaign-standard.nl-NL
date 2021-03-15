---
solution: Campaign Standard
product: campaign
title: Profielen maken
description: Meer informatie over het maken van profielen met API's.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Gegevensengineer
level: Ervaren
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 4%

---


# Profielen maken {#creating-profiles}

Het creëren van profielen wordt uitgevoerd met een **POST** verzoek op het profielmiddel.

>[!CAUTION]
>
>Als u een <b>orgUnit</b> aan het gecreeerde profiel wilt associëren, moet u de profielmiddel met dit gebied uitbreiden en, na de publicatie van de uitbreiding, een verzoek van de POST op het <b>ProfileAndServicesExt</b> eindpunt uitvoeren.
>
>Raadpleeg de <a href="https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html#partitioning-profiles">Campagne-documentatie</a> voor meer informatie over de bronextensie van het profiel.

<br/>

***Voorbeeldverzoek***

Voorbeeld van POST-aanvraag om een profiel te maken met de e-mail &quot;john.doe@mail.com&quot;.

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-i
-d '{"email":"john.doe@mail.com"}'
```

Het nieuwe profiel wordt geretourneerd met het e-mailadres &quot;john.doe@mail.com&quot;.

```
{
    "PKey": "<PKEY>",
    "firstName": "John",
    "lastName":"Doe",
    "birthDate": "1980-10-24",
    "email": "john.doe@mail.com",
    ...
}
```
