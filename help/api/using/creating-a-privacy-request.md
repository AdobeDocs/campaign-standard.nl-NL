---
title: Een privacyverzoek maken
description: Leer hoe u een privacyaanvraag maakt met API's
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 06ad2e13-922b-4f35-8726-007427125c63
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 4%

---

# Een privacyverzoek maken {#creating-a-privacy-request}

>[!CAUTION]
>
>De [&#x200B; Integratie van de Dienst van de Kern van de Privacy 0&rbrace; &lbrace;is de methode u voor alle toegang zou moeten gebruiken en verzoeken schrapt. &#x200B;](https://developer.adobe.com/experience-platform-apis/references/privacy-service)<!--Starting 19.4, the use of the Campaign API and interface for access and delete requests is deprecated. For more on Campaign Standard deprecated and removed features, refer to [this page](../../rn/using/deprecated-features.md).-->

De verzoeken van de privacy worden gecreeerd gebruikend a **POST** verzoek.

Voordat u aanvragen maakt, moet u de naamruimte definiëren die u wilt gebruiken. Voor meer op dit, verwijs de [&#x200B; het beheersdocumentatie van de Privacy &#x200B;](../../start/using/privacy-requests.md).

De lading moet de volgende parameters bevatten:

* **naam**: een unieke interne naam
* **namespace**: De namespace naam die in de interface van Campaign Standard wordt gevormd
* **connectionValue**: de verzoeningswaarde die op de verzoeningssleutel wordt gebaseerd die in namespace wordt bepaald
* **etiket**: het verzoeketiket
* **type**: het verzoektype. Accepteerde waarden zijn &quot;access&quot; of &quot;delete&quot;.
* **regeling**: het regulatietype. Voorbeeld: &quot;GDPR&quot;, &quot;CCPA&quot;. Deze parameter is verplicht en is beschikbaar vanaf de Campaign Standard 19.4-release. Als u zich op een oudere build bevindt, hoeft u deze niet toe te voegen aan uw payload.

<br/>

***verzoek van de Steekproef***

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

Antwoord op het POST-verzoek.

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
