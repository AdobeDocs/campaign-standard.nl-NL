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
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 1%

---

# API-toegang instellen {#setting-up-api-access}

Adobe Campaign Standard API-toegang wordt ingesteld via de onderstaande stappen. Elk van deze stappen wordt beschreven in [Adobe IO-documentatie](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!IMPORTANT]
>
>Om certificaten in Adobe IO te beheren, zorg ervoor u hebt <b>Systeembeheerder</b> rechten van de organisatie of [ontwikkelaarsaccount](https://helpx.adobe.com/enterprise/using/manage-developers.html)</a> in de Admin Console.

1. **Controleer of u een digitaal certificaat hebt** of maak indien nodig een sjabloon. De openbare en persoonlijke sleutels die van het certificaat worden voorzien zijn vereist in de volgende stappen.
1. **Een nieuwe integratie met Adobe Campaign Service maken** in Adobe IO en vorm het. Uw referenties worden vervolgens gegenereerd (API-sleutel, clientgeheim...).
1. **Een JSON-webtoken (JWT) maken** uit de eerder gegenereerde referenties en deze ondertekenen met uw persoonlijke sleutel. De JWT codeert alle identiteits- en beveiligingsgegevens die Adobe nodig heeft om uw identiteit te verifiëren en u toegang tot de API te verlenen.
1. **Uitwisseling uw JWT voor een Token van de Toegang** via een verzoek van de POST. Dit toegangstoken moet worden gebruikt in elke header van uw API-aanvragen.

Om een veilige service-to-service Adobe I/O API-sessie tot stand te brengen, moet elke aanvraag naar een Adobe-service de onderstaande informatie bevatten in de machtigingheader.

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

   Raadpleeg de beheerder of uw technische contactpersoon voor Adobe om de waarde van uw ORGANISATIE-id op te vragen. U kunt het in Adobe I/O ook terugwinnen wanneer het creëren van een nieuwe integratie, in de vergunningslijst (zie <a href="https://www.adobe.io/authentication.html">Adobe IO-documentatie</a>).

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
