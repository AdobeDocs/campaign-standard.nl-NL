---
title: Profielen maken
description: Meer informatie over het maken van profielen met API's.
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: aee0e0437cbfe578cb2f715a2433099c79dd1748

---


# Profielen maken {#creating-profiles}

Het maken van profielen wordt uitgevoerd met een **POST** -aanvraag op de profielbron.

>[!CAUTION]
>
>Als u een <b>orgUnit</b> aan het gecreeerde profiel wilt associëren, moet u het profielmiddel met dit gebied uitbreiden en, na de publicatie van de uitbreiding, een verzoek van de POST op het <b>eindpunt uitvoeren ProfileAndServicesExt</b> .
>
>Raadpleeg de documentatie bij de <a href="https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html#partitioning-profiles">campagne voor meer informatie over de bronextensie van het profiel</a>.

<br/>

***Voorbeeldverzoek***

Voorbeeld van een POST-aanvraag om een profiel te maken met de e-mail &quot;john.doe@mail.com&quot;.

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
