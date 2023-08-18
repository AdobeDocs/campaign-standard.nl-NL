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
source-git-commit: 4b0c4fb13cc11c06e2487e531ca96574e49b6beb
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 4%

---

# Een privacyverzoek maken {#creating-a-privacy-request}

>[!CAUTION]
>
>De [Privacy Core-service](https://developer.adobe.com/experience-platform-apis/references/privacy-service) De integratie is de methode u voor alle toegang en schrappingsverzoeken zou moeten gebruiken. <!--Starting 19.4, the use of the Campaign API and interface for access and delete requests is deprecated. For more on Campaign Standard deprecated and removed features, refer to [this page](../../rn/using/deprecated-features.md).-->

De verzoeken van de privacy worden gecreeerd gebruikend **POST** verzoek.

Voordat u aanvragen maakt, moet u de naamruimte definiëren die u wilt gebruiken. Raadpleeg voor meer informatie de [Privacy Management-documentatie](../../start/using/privacy-requests.md).

De lading moet de volgende parameters bevatten:

* **name**: een unieke interne naam
* **namespace**: de naamruimtenaam die in de interface van het Campaign Standard is geconfigureerd
* **connectionValue**: de reconciliatiewaarde gebaseerd op de reconciliatietoets die in de naamruimte is gedefinieerd
* **label**: het aanvraaglabel
* **type**: het type aanvraag. Accepteerde waarden zijn &quot;access&quot; of &quot;delete&quot;.
* **verordening**: het type regelgeving. Voorbeeld: &quot;GDPR&quot;, &quot;CCPA&quot;. Deze parameter is verplicht en is beschikbaar vanaf Campaign Standard 19.4. Als u zich op een oudere build bevindt, hoeft u deze niet toe te voegen aan uw payload.

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

Antwoord op de POST verzoek.

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
