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
source-git-commit: 3450c549f4910a6c5f6be7bf82fbc93ac06625e8
workflow-type: tm+mt
source-wordcount: '442'
ht-degree: 4%

---

# API-toegang instellen {#setting-up-api-access}

Adobe Campaign Standard API-toegang wordt ingesteld via de onderstaande stappen. Elk van deze stappen wordt beschreven in [Adobe Developer-documentatie](https://developer.adobe.com/developer-console/docs/guides/#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!IMPORTANT]
>
>Certificaten beheren in [Adobe Developer](https://developer.adobe.com/), zorg ervoor dat u **Systeembeheerder** rechten van de organisatie of [ontwikkelingsaccount](https://helpx.adobe.com/enterprise/using/manage-developers.html) in de Admin Console.

1. **Controleer of u een digitaal certificaat hebt** of maak indien nodig een sjabloon. De openbare en persoonlijke sleutels die van het certificaat worden voorzien zijn vereist in de volgende stappen.
1. **Een nieuwe integratie met Adobe Campaign Service maken** in [Adobe Developer](https://developer.adobe.com/) en configureren. Uw referenties worden vervolgens gegenereerd (API-sleutel, clientgeheim...).
1. **Een JSON-webtoken (JWT) maken** uit de eerder gegenereerde referenties en deze ondertekenen met uw persoonlijke sleutel. De JWT codeert alle identiteits- en beveiligingsgegevens die door de Adobe nodig zijn om uw identiteit te verifiëren en u toegang tot de API te verlenen.

   >[!IMPORTANT]
   >
   >JWT (JSON Web Tokens) wordt momenteel uitgefaseerd en wordt vervangen door OAuth. De overgang wordt geleidelijk uitgevoerd in de komende releases van Campagne. De referenties van de serviceaccount (JWT) zijn gemarkeerd als afgekeurd. Ze blijven werken tot 27 januari 2025. Daarom moet u uw toepassing of integratie migreren om de nieuwe server-aan-server referentie OAuth vóór 27 jan. 2025 te gebruiken. OAuth-verificatie verdient de voorkeur. U zult alle elementen vinden om van authentificatie JWT aan authentificatie OAuth op deze pagina&#39;s te migreren:
   >* [Migratie](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)
   >* [Implementatie](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)
   >* [Veelgestelde vragen over Deprectie JWT](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)

1. **Uitwisseling uw JWT voor een Token van de Toegang** via een verzoek van de POST. Dit toegangstoken moet worden gebruikt in elke header van uw API-aanvragen.

Om een veilige service-to-service Adobe I/O API-sessie tot stand te brengen, moet elke aanvraag naar een Adobe-service de onderstaande informatie bevatten in de machtigingheader.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

* **&lt;organization>**: Dit is uw persoonlijke ORGANISATIE-ID, één ORGANISATIE-ID wordt per Adobe opgegeven voor elk van uw gevallen:

   * &lt;organization> : uw productie-instantie,
   * &lt;organization-mkt-stage>: uw werkgebiedinstantie.

  Als u de waarde van uw ORGANISATIE-id wilt opvragen, raadpleegt u uw beheerder of uw technische contactpersoon voor de Adobe. U kunt het in Adobe I/O ook terugwinnen wanneer het creëren van een nieuwe integratie, in de vergunningslijst (zie <a href="https://developer.adobe.com/developer-console/docs/guides/authentication/">Adobe Developer-documentatie</a>).

* **&lt;access_token>**: Uw persoonlijke toegangstoken, die werd teruggewonnen toen het ruilen van uw Token van het Web JSON door een verzoek van de POST.

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
