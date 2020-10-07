---
title: Paginering
description: Leer hoe u pagineringsbewerkingen kunt uitvoeren.
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
source-wordcount: '157'
ht-degree: 1%

---


# Paginering

Standaard worden 25 bronnen in een lijst geladen.

Met de parameter **_lineCount** kunt u het aantal bronnen beperken dat in de reactie wordt vermeld.  Vervolgens kunt u het **volgende** knooppunt gebruiken om de volgende resultaten weer te geven.

>[!NOTE]
>
>Gebruik altijd de URL-waarde die in het **volgende** knooppunt wordt geretourneerd om een pagineringsverzoek uit te voeren.
>
>Het **_lineStart** verzoek wordt berekend en moet altijd binnen URL worden gebruikt die in de **volgende** knoop is teruggekeerd.

<br/>

***Voorbeeldverzoek***

Voorbeeld van GET-verzoek om 1 record van de profielbron weer te geven.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile?_lineCount=1 \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Antwoord op het verzoek, met de **volgende** knoop om paginering uit te voeren.

```
{
    "content": [
        {
            "PKey": "<PKEY>",
            "firstName": "John",
            "lastName":"Doe",
            "birthDate": "1980-10-24",
            ...
        }
    ],
    "next": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_lineCount=10&_
        lineStart=@Qy2MRJCS67PFf8soTf4BzF7BXsq1Gbkp_e5lLj1TbE7HJKqc"
    }
    ...
}
```

Standaard is het **volgende** knooppunt niet beschikbaar bij interactie met tabellen met veel gegevens. Om paginering uit te kunnen voeren, moet u de parameter **_forcePagination=true** aan uw vraag URL toevoegen.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile?_forcePagination=true \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

>[!NOTE]
>
>Het aantal records waarboven een tabel als groot wordt beschouwd, wordt gedefinieerd in de optie Campaign Standard **XtkBigTableThreshold** . De standaardwaarde is 100.000 records.
