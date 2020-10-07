---
title: Filteren
description: Leer hoe u filterbewerkingen kunt uitvoeren.
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
source-wordcount: '434'
ht-degree: 1%

---


# Filteren {#filtering}

## Metagegevens van filters ophalen

Filters zijn beschikbaar voor elke bron. Om de filters te identificeren verbonden aan een middel, moet u een verzoek van de GET op de middelmeta-gegevens uitvoeren. Dit verzoek retourneert de URL waar alle filters zijn gedefinieerd voor een bepaalde bron. For more on metadata, refer to [this section](../../api/using/metadata-mechanism.md).

Om de meta-gegevens van een filter te identificeren en te bepalen hoe te om het te gebruiken, moet u een verzoek van de GET op eerder teruggekeerde URL uitvoeren.

<br/>

***Voorbeeldverzoek***

In de onderstaande voorbeeldladingen ziet u hoe u de metagegevens van de &quot;byText&quot;-filter voor de &quot;profile&quot;-bron ophaalt. Voer eerst een verzoek van de GET op &quot;profiel&quot;middelmetada uit.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/resourceType/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

De URL waar de filters worden beschreven, wordt geretourneerd.

```
{
"filters": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/resourceType/<PKEY>/filters/"
    }
  }
```

Voer een verzoek van de GET op URL uit. De lijst met filters voor de profielbron wordt geretourneerd, met de metagegevens die aan elk filter zijn gekoppeld.

```
{
"birthday": {
        "PKey": "@FL-CbDFXbnHbXcVpeCGWL46VXJLn1LqxLMPagt2vz8sCxQ52lvB15KiUaxXkxJYQw-tZXYrgUWG6K8QcB4gxVY9RKoba5bRFY3294YFshDmorRr8",
        "category": "0150_profile",
        "condition": ...,
        "data": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/birthday?type=$value&precision=$value&operator=$value&day=$value&month=$value&includeStart=$value&endDay=$value&endMonth=$value&includeEnd=$value&relativeValue=$value&nextUnitsValue=$value&previousUnitsValue=$value",
        "formType": "webPage",
        "fragmentName": "",
        "label": "Birthday",
}
```

## Metagegevensstructuur filteren

Voor elk filter is dezelfde metagegevensstructuur beschikbaar:

* De velden **@formType** en **@webPage** zijn technische velden.
* Het **gegevensveld** geeft een voorbeeld van het gebruik van het filter.
* In het **knooppunt metadata** worden de filterparameters beschreven.
* Het **voorwaardenknooppunt** beschrijft wat het filter moet doen. De filterparameters die in het metagegevensknooppunt worden beschreven, worden gebruikt om filtervoorwaarden te maken. Voor elke filtervoorwaarde, als **enabledIf** waar is, zal **expr** worden toegepast.

<br/>

Voorbeeld van de structuur van filtermetagegevens:

```
"byText": {
        "PKey": "...",
        "category": "99_none",
        "condition": ...,
        "data": "/profileAndServices/profile/byText?text=$value",
        "formType": "none",
        "fragmentName": "",
        "label": "By name or email",
    }
```

## Filters gebruiken

Filteren wordt uitgevoerd met het volgende verzoek:

`GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/<resourceName>/by<filterName>?<filterParam>=<filterValue>`

Het is mogelijk meerdere filters te combineren in één aanvraag:

`GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/<resourceName>/<filter1name>/<filter2name>?<filter1param>=<filter1value>&<filter2param>=<filter2value>`

<br/>

***Voorbeeldverzoeken***

* Voorbeeld van een GET-aanvraag om de &#39;service&#39;-bronnen op te halen met het type &#39;email&#39;.

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/byChannel?channel=email \
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
               "created": "2019-09-25 23:20:35.000Z",
               "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/@I_FIiDush4OQPc0mbOVR9USoh36Tt5CsD35lATvQjdWlXrYc0lFkvle2XIwZUbD8GqTVvSp8AfWFUvjkGMe1fPe5nok",
               "label": "Marketing Newsletter",
               "lastModified": "2019-09-25 23:20:35.000Z",
               "limitedDuration": false,
               "messageType": "email",
               "mode": "newsletter",
               ...
           },
           ...
       ],
       ...
   }
   ```

* Voorbeeld van een GET-aanvraag om de &quot;profiel&quot;-bronnen op te halen die &quot;Doe&quot; bevatten in de velden voor e-mail- of achternaam (het filter byText zoekt naar zowel de velden voor e-mail als achternaam).

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/byText?text=Doe \
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
               "firstName": "John",
               "lastName":"Doe",
               "birthDate": "1980-10-24",
               ...
           }
           ...
       ],
       ...
   }
   ```

* Voorbeeld van een GET-verzoek om de servicemiddelen op te halen met het type &quot;email&quot; en het label &quot;sport&quot;.

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/byChannel/byText?channel=email&text=sport \
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
               "created": "2019-09-26 09:36:01.014Z",
               "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>",
               "label": "sport",
               "lastModified": "2019-09-26 09:36:01.014Z",
               "limitedDuration": false,
               "messageType": "email",
               "mode": "newsletter",
               "name": "SVC13",
               ...
           }
       ],
       ...
   }
   ```

## Aangepaste filters

Als u een aangepast filter wilt gebruiken, moet u het maken en aanpassen in de Adobe Campaign Standard-interface. Het aangepaste filter heeft dan hetzelfde gedrag als de vervagingsfilters:

`GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/<resourceName>/by<customFilterName>?<customFilterparam>=<customFilterValue>`

Raadpleeg de documentatie bij Campaign Standard voor meer informatie hierover:

* [De filterdefinitie configureren](https://helpx.adobe.com/campaign/standard/developing/using/configuring-filter-definition.html).
* [Hoofdlettergebruik: Een bron aanroepen met een samengestelde identificatiesleutel](https://docs.adobe.com/content/help/en/campaign-standard/using/developing/adding-or-extending-a-resource/uc-calling-resource-id-key.html).

<br/>

***Voorbeeldverzoek***

Voorbeeld-GET-verzoek om de &quot;profiel&quot;-bronnen op te halen met transactiebedragen van 100$ of meer. Het filter &quot;byAmount&quot; is eerst gedefinieerd in de Adobe Campaign Standard-interface en gekoppeld aan de aangepaste tabel &quot;Transaction&quot;.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/byAmount?amount_parameter=100 \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

<!--
Response to the request.

```

{
    "content": [
        {
            "PKey": "<PKEY>",
            "builtIn": false,
            "created": "2019-09-26 09:36:01.014Z",
            "desc": "",
            "end": "",
            "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY>",
            ...
        }
    ],
}

```

-->

<!-- exemple à vérifier de bout en bout-->

<!--+category = query editor
privacy ?
displayFOrmat ?
pour faire un POST sur une enum, il faut lui passer le @name décrit dans le noeud values, chaque @name a une correspondance en format = au format définit par le resType
-->





<!--
 if link ou collection.* resName +
* resTarget tout ca, ca va ensemble : le système de lien, resTarget va donner la ressource targetée par le lien. type
resType = type technique (long..) resType = link alors unbound='false' ou 'true'
If type = enumeration alors champ "values" rajouté et les valeurs sont dans values
pour faire un POST sur une enum, il faut lui passer le @name décrit dans le noeud values, chaque @name a une correspondance en format = au format définit par le resType
ail faut que la valeur poster soit conforme ,elle doit valider la dataPolicy . La dataPolicy peut soit controler la valeur (email invalide), soit transformé (cas du smartCase par exemple)
type dans les metadata = type de haut-niveau (nombre, text)
-->
