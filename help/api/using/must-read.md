---
title: Doorlezen
description: Moet lezen voordat API's kunnen worden gebruikt.
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
source-git-commit: c0c0be79613f99a15676343d8ce10d335baf968a

---


# Doorzichtig {#must-read}

## Technische voorschriften

* Adobe Campagne-API&#39;s mogen alleen worden gebruikt op de server.
* Neem altijd contact op met de technische contactpersoon van Adobe als het gebruiksscenario dat u wilt implementeren is uitgelijnd met de schaal die is toegestaan door de API&#39;s voor campagnes van Adobe.
* Voor het instellen van een AdobeIO-toegang zijn specifieke machtigingen vereist. Neem contact op met de Technische Ondersteuning van Adobe voor problemen.

## Bronrepresentatie

Alle API-bronnen zijn beschikbaar in **JSON** met een URL-extensie of in een HTTP Accept-header:

`GET /profileAndServices/<resourceName>.json`

>[!NOTE]
>
>Zonder extensie in de URL is de **json-indeling de standaardindeling** voor het inhoudstype.

<br/>

***aanvraagvoorbeeld***

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile.json \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

## Primaire sleutel en URL&#39;s

* Probeer niet zelf een URL te maken. Alle URL&#39;s worden geretourneerd door de API. Het is echter mogelijk een URL te maken op basis van de resourcenaam op het hoogste niveau.

* De waarden voor de automatische primaire sleutel (PKey) die de voorbeelden illustreren, zijn niet bedoeld om in een andere specifieke implementatie te werken. Ze worden gemaakt door de Adobe Campaign API.

* De waarden voor Automatische primaire sleutels die door de Campagne van Adobe worden geproduceerd mogen nooit in een externe gegevensbestand of een website worden opgeslagen. U moet specifieke zeer belangrijke gebieden in uw gegevensbestanddefinitie produceren en het gebruiken tijdens uw ontwikkelingen.

## Aangepaste toetsen {#custom-keys}

Als de profielbron is uitgebreid met een veld met een aangepaste sleutel, kunt u dit veld gebruiken als een sleutel in plaats van de automatische primaire sleutel die wordt gegenereerd door Adobe Campagne:

`GET /.../profileAndServicesExt/profile/<customKey>`

Aangepaste sleutels kunnen niet worden gewijzigd met een PATCH-bewerking als de sleutelwaarde afwijkt van de oorspronkelijke sleutel of als u uw eigen zakelijke sleutel gebruikt als URI in plaats van de sleutel die door Adobe wordt geleverd.

Gebruik een aangepaste sleutel alleen voor profielbronnen **op het** hoogste niveau. URL&#39;s worden geretourneerd door de API en mogen nooit door uzelf worden gemaakt.

<br/>

***Voorbeeldverzoek***

Als u de abonnementen voor een profiel wilt ophalen met behulp van een aangepaste sleutel, voert u een GET-bewerking uit op de aangepaste sleutel.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/<customKey> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Voer een GET verzoek uit op de geretourneerde abonnements-URL.

```
-X GET <SUBSCRIPTION_URL> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

De lijst met abonnementen voor het profiel wordt geretourneerd.

```
"service": {
"PKey": "<PKEY>",
"href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>",
"label": "Sport Newsletter",
"name": "SVC1",
"title": "Sport Newsletter (SVC1)"
}
```
