---
title: API-toegang instellen
description: Leer hoe u toegang tot standaard API's voor campagnes instelt.
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


# API-toegang instellen {#setting-up-api-access}

De toegang tot de API voor Adobe Campagne Standard wordt ingesteld via de onderstaande stappen. Elk van deze stappen wordt beschreven in de documentatie [van](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)Adobe IO.

>[!CAUTION]
>
>Als u certificaten wilt beheren in Adobe IO, moet u ervoor zorgen dat u <b>Systeembeheerdersrechten</b> hebt voor de organisatie of een <a href="https://helpx.adobe.com/enterprise/using/manage-developers.html">ontwikkelaarsaccount</a> in de beheerconsole.

1. **Controleer of u een digitaal certificaat** hebt of maak er zo nodig een. De openbare en persoonlijke sleutels die van het certificaat worden voorzien zijn vereist in de volgende stappen.
1. **Maak een nieuwe integratie met de Adobe Campagne Service** in Adobe IO en configureer deze. Uw referenties worden vervolgens gegenereerd (API-sleutel, clientgeheim...).
1. **Maak een JSON Web Token (JWT)** van de eerder gegenereerde referenties en onderteken deze met uw persoonlijke sleutel. De JWT codeert alle identiteits- en beveiligingsgegevens die Adobe nodig heeft om uw identiteit te verifiëren en u toegang te verlenen tot de API.
1. **Uitwisseling uw JWT voor een Token** van de Toegang door een POST- verzoek. Dit toegangstoken moet worden gebruikt in elke header van uw API-aanvragen.

Om een beveiligde service-to-service Adobe I/O API-sessie tot stand te brengen, moet elke aanvraag naar een Adobe-service de onderstaande informatie bevatten in de machtigingheader.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

* **&lt;ORGANISATIE>**: Dit is uw persoonlijke ORGANIZATION-id. Adobe levert één ORGANIZATION-id voor elk van uw varianten:

   * &lt;ORGANISATIE>: uw productieexemplaar,
   * &lt;ORGANIZATION-market-stage>: de instantie van het werkgebied.
   Raadpleeg de beheerder of uw technische contactpersoon van Adobe voor informatie over de waarde van uw organisatie-id. U kunt de software ook ophalen in de Adobe I/O-lijst wanneer u een nieuwe integratie maakt, in de lijst met licenties (zie de <a href="https://www.adobe.io/authentication.html">Adobe IO-documentatie</a>).

* **&lt;ACCESS_TOKEN>**: Uw persoonlijk toegangstoken, dat werd teruggewonnen toen het ruilen van uw Token van het Web JSON door een POST- verzoek.

* **&lt;API_KEY>**: uw persoonlijke API-sleutel. Deze vindt u in Adobe I/O nadat u een nieuwe integratie met de Adobe Campagne Service hebt gemaakt.

   ![alt-tekst](assets/tenant.png)
