---
solution: Campaign Standard
product: campaign
title: Een privacyaanvraag maken
description: Leer hoe u een privacyaanvraag maakt met API's
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: ad7322905c69f9575e11efc9d8f68cf909dc425f
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 6%

---


# Een privacyaanvraag maken {#creating-a-privacy-request}

>[!CAUTION]
>
>De [Integratie van de Kern van de Privacy](https://adobe.io/apis/cloudplatform/gdpr.html) is de methode u voor alle toegang zou moeten gebruiken en verzoeken schrapt. Vanaf 19.4 is het gebruik van de campagne-API en de interface voor toegangs- en verwijderingsverzoeken afgekeurd. Raadpleeg [deze pagina](../../rn/using/deprecated-features.md) voor meer informatie over afgekeurde en verwijderde functies van Campaign Standard.

De verzoeken van de privacy worden gecreeerd gebruikend een **POST** verzoek.

Voordat u aanvragen maakt, moet u de naamruimte definiëren die u wilt gebruiken. Raadpleeg de [documentatie over privacybeheer](https://helpx.adobe.com/nl/campaign/kb/acs-privacy.html#ManagingPrivacyRequests) voor meer informatie.

De lading moet de volgende parameters bevatten:

* **naam**: een unieke interne naam
* **naamruimte**: de naamruimtenaam die is geconfigureerd in de Campaign Standard-interface
* **reconciliatiewaarde**: de afstemmingswaarde gebaseerd op de afstemmingssleutel die is gedefinieerd in de naamruimte
* **label**: het aanvraaglabel
* **type**: het type aanvraag. Accepteerde waarden zijn &quot;access&quot; of &quot;delete&quot;.
* **verordening** : het type regelgeving. Voorbeeld: &quot;GDPR&quot;, &quot;CCPA&quot;. Deze parameter is verplicht en is beschikbaar vanaf Campaign Standard 19.4. Als u zich op een oudere build bevindt, hoeft u deze niet toe te voegen aan uw lading.

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
