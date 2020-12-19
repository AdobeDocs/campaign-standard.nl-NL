---
solution: Campaign Standard
product: campaign
title: Paginering
description: Leer hoe u pagineringsbewerkingen kunt uitvoeren.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 1%

---


# Paginering

Standaard worden 25 bronnen in een lijst geladen.

Met de parameter **_lineCount** kunt u het aantal bronnen beperken dat in de reactie wordt vermeld.  U kunt de **next** knoop dan gebruiken om de volgende resultaten te tonen.

>[!NOTE]
>
>Gebruik altijd de waarde URL die in **next** knoop is teruggekeerd om een pagineringsverzoek uit te voeren.
>
>Het **_lineStart** verzoek wordt berekend en moet altijd binnen URL worden gebruikt die in **next** knoop is teruggekeerd.

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

Antwoord op het verzoek, met **next** knoop om paginering uit te voeren.

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

Standaard is het knooppunt **next** niet beschikbaar bij interactie met tabellen met een grote hoeveelheid gegevens. Om paginering uit te kunnen voeren, moet u **_forcePagination=true** parameter aan uw vraag URL toevoegen.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile?_forcePagination=true \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

>[!NOTE]
>
>Het aantal records waarboven een tabel als groot wordt beschouwd, wordt gedefinieerd in de optie Campaign Standard **XtkBigTableThreshold**. De standaardwaarde is 100.000 records.
