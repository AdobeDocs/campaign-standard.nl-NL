---
title: Een privacyverzoek maken
description: Leer hoe u een privacyaanvraag maakt met API's
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 06ad2e13-922b-4f35-8726-007427125c63
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 22%

---

# Een privacyverzoek maken {#creating-a-privacy-request}

>[!CAUTION]
>
>De [Privacy Core-service](https://adobe.io/apis/cloudplatform/gdpr.html) De integratie is de methode u voor alle toegang en schrappingsverzoeken zou moeten gebruiken. Met ingang van versie 19.4 is het gebruik van de Campaign-API en -interface voor toegangs- en verwijderingsverzoeken afgeschaft. Raadpleeg [deze pagina](../../rn/using/deprecated-features.md) voor meer informatie over Campaign Standard-functies die zijn afgeschaft en verwijderd.

De verzoeken van de privacy worden gecreeerd gebruikend **POST** verzoek.

Voordat u aanvragen maakt, moet u de naamruimte definiëren die u wilt gebruiken. Raadpleeg voor meer informatie de [Privacy Management-documentatie](https://helpx.adobe.com/nl/campaign/kb/acs-privacy.html#ManagingPrivacyRequests).

De lading moet de volgende parameters bevatten:

* **name**: een unieke interne naam
* **namespace**: de naamruimtenaam die is geconfigureerd in de Campaign Standard-interface
* **connectionValue**: de afstemmingswaarde gebaseerd op de afstemmingssleutel die is gedefinieerd in de naamruimte
* **label**: het aanvraaglabel
* **type**: het type aanvraag. Accepteerde waarden zijn &quot;access&quot; of &quot;delete&quot;.
* **verordening**: het type regelgeving. Voorbeeld: &quot;GDPR&quot;, &quot;CCPA&quot;. Deze parameter is verplicht en is beschikbaar vanaf Campaign Standard 19.4. Als u zich op een oudere build bevindt, hoeft u deze niet toe te voegen aan uw lading.

<br/>

***Voorbeeldverzoek***

Met deze POST-aanvraag wordt een privacyaanvraag gemaakt op basis van een e-mailafstemmingssleutel die is gedefinieerd in de naamruimte AMCDS2:

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/privacy/privacyTool \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-H 'Content-Type: application/json;charset=utf-8'

{
"name":"PT11832",
"namespaceName": "AMCDS2",
"reconciliationValue": "customers@adobe.com",
"regulation": "gdpr",
"label":"Delete customers",
"type":"delete"
}
```

Antwoord op het verzoek van de POST.

```
{
    "PKey": "<PKEY>",
    "audit": "",
    "created": "2018-03-21 10:41:58.570Z",
    "desc": "",
    "gdprRequestData": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/head/privacyTool/<PKEY>/gdprRequestData/"
    },
    "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/privacy/privacyTool/<PKEY>",
    "label": "Delete customers",
    "lastModified": "2018-03-21 10:41:58.570Z",
    "name": "PT11832",
    "namespace": {
        "PKey": "<PKEY>",
        "title": "Doc (AMCDS2)"
    },
    "namespaceName": "AMCDS2",
    "reconciliationValue": "customers@adobe.com",
    "regulation": "gdpr",
    "retryCount": 0,
    "status": "new",
    "title": "Delete customers (PT11832)",
    "type": "delete"
}
```
