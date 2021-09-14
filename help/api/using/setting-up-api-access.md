---
title: API-toegang instellen
description: Leer hoe u toegang tot Campaign Standard-API's instelt.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: efbbd0cd-9c56-4ad0-8bcb-efba4b63c28b
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 1%

---

# API-toegang instellen {#setting-up-api-access}

Adobe Campaign Standard API-toegang wordt ingesteld via de onderstaande stappen. Elk van deze stappen wordt gedetailleerd in [Adobe IO documentatie](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!IMPORTANT]
>
>Als u certificaten in Adobe IO wilt beheren, moet u <b>Systeembeheerder</b> rechten hebben op de organisatie of een [ontwikkelingsaccount](https://helpx.adobe.com/enterprise/using/manage-developers.html)</a> in de beheerconsole.

1. **Controleer of u een digitaal certificaat** hebt of maak er zo nodig een. De openbare en persoonlijke sleutels die van het certificaat worden voorzien zijn vereist in de volgende stappen.
1. **Creeer een nieuwe integratie aan de Dienst van Adobe Campaign** in Adobe IO en vorm het. Uw referenties worden vervolgens gegenereerd (API-sleutel, clientgeheim...).
1. **Maak een JSON Web Token (JWT)** van de eerder gegenereerde referenties en onderteken deze met uw persoonlijke sleutel. De JWT codeert alle identiteits- en beveiligingsgegevens die Adobe nodig heeft om uw identiteit te verifiëren en u toegang tot de API te verlenen.
1. **Wisselt uw JWT voor een** Tokenthrough van de Toegang door een verzoek van de POST. Dit toegangstoken moet worden gebruikt in elke header van uw API-aanvragen.

Om een veilige dienst-aan-dienst Adobe I/O API zitting tot stand te brengen, moet elk verzoek aan de dienst van de Adobe in de kopbal van de Vergunning de informatie hieronder omvatten.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

* **&lt;organization>**: Dit is uw persoonlijke ORGANIZATION ID, één ORGANIZATION ID wordt verstrekt door Adobe voor elk van uw instanties:

   * &lt;organization> : uw productieexemplaar,
   * &lt;organization-mkt-stage>: de instantie van het werkgebied.

   Raadpleeg de beheerder of uw technische contactpersoon voor Adobe om de waarde van uw ORGANISATIE-id op te vragen. U kunt het in Adobe I/O ook terugwinnen wanneer het creëren van een nieuwe integratie, in de vergunningslijst (zie <a href="https://www.adobe.io/authentication.html">Adobe IO documentatie</a>).

* **&lt;access_token>**: Uw persoonlijk toegangstoken, dat werd teruggewonnen toen het ruilen van uw Token van het Web JSON door een verzoek van de POST.

* **&lt;api_key>**: uw persoonlijke API-sleutel. Het wordt geleverd in Adobe I/O na het creëren van een nieuwe integratie aan de Dienst van Adobe Campaign.

   ![alt-tekst](assets/tenant.png)

## Problemen oplossen

Als de volgende fout optreedt tijdens de integratie met AdobeIO:

```
{ 
"code": 502, 
"message": "Oops. Something went wrong. Check your URI and try again." 
}
```


Verwijs naar uw beheerder of uw Adobe technisch contact om te controleren of wordt de parameter CNAME correct gecreeerd.
