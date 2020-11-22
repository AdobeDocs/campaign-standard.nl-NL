---
solution: Campaign Standard
product: campaign
title: Profielen maken
description: Meer informatie over het maken van profielen met API's.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 3%

---


# Profielen maken {#creating-profiles}

Profielen maken wordt uitgevoerd met een **POST** -aanvraag voor de profielbron.

>[!CAUTION]
>
>Als u een <b>orgUnit</b> aan het gecreeerde profiel wilt associëren, moet u het profielmiddel met dit gebied uitbreiden en, na de publicatie van de uitbreiding, een verzoek van de POST op het <b>eindpunt uitvoeren ProfileAndServicesExt</b> .
>
>Raadpleeg de documentatie bij de <a href="https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html#partitioning-profiles">campagne voor meer informatie over de bronextensie van het profiel</a>.

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
