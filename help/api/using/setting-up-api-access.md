---
title: API-toegang instellen
description: Leer hoe u toegang tot Campaign Standard-API's instelt.
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
source-wordcount: '361'
ht-degree: 1%

---


# API-toegang instellen {#setting-up-api-access}

Adobe Campaign Standard API-toegang wordt ingesteld via de onderstaande stappen. Elk van deze stappen wordt gedetailleerd beschreven in de [Adobe IO documentatie](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!IMPORTANT]
>
>Om certificaten in Adobe IO te beheren, zorg ervoor u de <b>beheerderrechten</b> van het Systeem op de organisatie of een [ontwikkelaarrekening](https://helpx.adobe.com/enterprise/using/manage-developers.html)</a> in de Admin console hebt.

1. **Controleer of u een digitaal certificaat** hebt of maak er zo nodig een. De openbare en persoonlijke sleutels die van het certificaat worden voorzien zijn vereist in de volgende stappen.
1. **Creeer een nieuwe integratie aan de Dienst** van Adobe Campaign in Adobe IO en vorm het. Uw referenties worden vervolgens gegenereerd (API-sleutel, clientgeheim...).
1. **Maak een JSON Web Token (JWT)** van de eerder gegenereerde referenties en onderteken deze met uw persoonlijke sleutel. De JWT codeert alle identiteits- en beveiligingsgegevens die Adobe nodig heeft om uw identiteit te verifiëren en u toegang tot de API te verlenen.
1. **Uitwisseling uw JWT voor een Token** van de Toegang door een verzoek van de POST. Dit toegangstoken moet worden gebruikt in elke header van uw API-aanvragen.

Om een veilige dienst-aan-dienst Adobe I/O API zitting tot stand te brengen, moet elk verzoek aan de dienst van de Adobe in de kopbal van de Vergunning de hieronder informatie omvatten.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

* **&lt;ORGANISATIE>**: Dit is uw persoonlijke ORGANIZATION ID, één ORGANIZATION ID wordt verstrekt door Adobe voor elk van uw instanties:

   * &lt;ORGANISATIE>: uw productieexemplaar,
   * &lt;ORGANIZATION-market-stage>: de instantie van het werkgebied.

   Raadpleeg de beheerder of uw technische contactpersoon voor Adobe om de waarde van uw ORGANISATIE-id op te vragen. U kunt het in Adobe I/O ook terugwinnen wanneer het creëren van een nieuwe integratie, in de vergunningslijst (zie de documentatie <a href="https://www.adobe.io/authentication.html">van</a>Adobe IO).

* **&lt;ACCESS_TOKEN>**: Uw persoonlijk toegangstoken, dat werd teruggewonnen toen het ruilen van uw Token van het Web JSON door een verzoek van de POST.

* **&lt;API_KEY>**: uw persoonlijke API-sleutel. Het wordt geleverd in Adobe I/O na het creëren van een nieuwe integratie aan de Dienst van Adobe Campaign.

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