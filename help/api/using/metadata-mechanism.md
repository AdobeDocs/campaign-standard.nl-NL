---
title: Metagegevensmechanisme
description: Meer informatie over het mechanisme voor metagegevens.
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
source-wordcount: '227'
ht-degree: 1%

---


# Metagegevensmechanisme {#metadata-mechanism}

U kunt de middelmeta-gegevens terugwinnen gebruikend **resourceType** in een verzoek van de GET:

`GET /profileAndServices/resourceType/<resourceName>`

De reactie retourneert de hoofdmetagegevens van de bron (alle andere velden zijn beschrijvend of intern):

* De knoop van de **Inhoud** keert de gebieden van het middel terug. Voor elk gebied in de **inhoudknoop** , kunnen wij de volgende gebieden vinden:

   * &quot;apiName&quot;: naam van het kenmerk dat in de API&#39;s wordt gebruikt.
   * &quot;type&quot;: Dit is de typedefinitie op hoog niveau (tekenreeks, nummer, koppeling, verzameling, opsomming...).
   * &quot;dataPolicy&quot;: de waarde van het veld moet in overeenstemming zijn met de gegeven beleidsregels . Als de regel dataPolicy bijvoorbeeld is ingesteld op &#39;email&#39;, moet de waarde een geldige e-mail zijn. Tijdens een PATCH of een POST, kan dataPolicy de waarde controleren of de te transformeren waarde wijzigen (smartCase bijvoorbeeld).
   * &quot;categorie&quot;: geeft de categorie van het gebied in de vraagredacteur.
   * &quot;resType&quot;: dit is het technische type.

      Als &quot;type&quot;met de waarde &quot;verbinding&quot;of &quot;inzameling&quot;wordt voltooid, is de resTarget waarde de naam van het middel dat door de verbinding wordt gericht.
Als &quot;type&quot;met de waarde &quot;opsomming&quot;wordt voltooid, wordt een gebied &quot;waarden&quot;toegevoegd en elke opsommingswaarde is gedetailleerd in de **waardenknoop** .

* De **knoop van Filters** keert URL terug om de bijbehorende filters terug te winnen. For more on filters, refer to [this section](../../api/using/filtering.md) section.

<!-- créer une section au même niveau sur les liens -->
<!-- dans l'exemple: birthdate, email +  mettre 2 liens : un de type 1-1 , 1-N
si on prend l'exemple de l'org unit, on aura un bon exemple lien -->
<!-- plus reparler du node Data -->

<br/>

***Voorbeeldverzoek***

Voer een verzoek van de GET op het middel uit.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/resourceType/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

De volledige beschrijving van de profielbron wordt geretourneerd.

```
{
...
"content": {
  "email": {...},
    ...
    },
"data": "/profileAndServices/profile/",
"filters": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/resourceType/<PKEY>"
    },
"help": "Identified profiles",
"href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/metadata",
"label": "Profiles",
"mandatory": false,
"name": "profile",
"pkgStatus": "never",
"readOnly": false,
"schema": "nms:recipient",
"type": "item"
}
```
