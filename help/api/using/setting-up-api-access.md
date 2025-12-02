---
title: API-toegang instellen
description: Leer hoe u toegang tot Campaign Standard API's instelt.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
old-role: Data Architect
role: Developer
level: Experienced
exl-id: efbbd0cd-9c56-4ad0-8bcb-efba4b63c28b
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '442'
ht-degree: 5%

---

# API-toegang instellen {#setting-up-api-access}

Adobe Campaign Standard API-toegang wordt ingesteld via de onderstaande stappen. Elk van deze stappen wordt gedetailleerd in de [&#x200B; documentatie van Adobe Developer &#x200B;](https://developer.adobe.com/developer-console/docs/guides/#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!IMPORTANT]
>
>Om certificaten in [&#x200B; Adobe Developer &#x200B;](https://developer.adobe.com/) te beheren, zorg ervoor u **de beheerderrechten van het Systeem** op de organisatie of a [&#x200B; ontwikkelaarrekening &#x200B;](https://helpx.adobe.com/nl/enterprise/using/manage-developers.html) in Admin Console hebt.

1. **Controle u een digitaal certificaat** hebt, of creeer indien nodig. De openbare en persoonlijke sleutels die van het certificaat worden voorzien zijn vereist in de volgende stappen.
1. **creeer een nieuwe integratie aan de Dienst van Adobe Campaign** in [&#x200B; Adobe Developer &#x200B;](https://developer.adobe.com/) en vorm het. Uw referenties worden vervolgens gegenereerd (API-sleutel, clientgeheim...).
1. **creeer een Token van het Web JSON (JWT)** van de geloofsbrieven eerder geproduceerd en onderteken het met uw privé sleutel. De JWT codeert alle identiteits- en beveiligingsgegevens die Adobe nodig heeft om uw identiteit te verifiëren en u toegang te verlenen tot de API.

   >[!IMPORTANT]
   >
   >JWT (JSON Web Tokens) wordt momenteel uitgefaseerd en wordt vervangen door OAuth. De overgang wordt geleidelijk uitgevoerd in de komende releases van Campagne. De referenties van de serviceaccount (JWT) zijn gemarkeerd als afgekeurd. Ze blijven werken tot 27 januari 2025. Daarom moet u uw toepassing of integratie migreren om de nieuwe server-aan-server referentie OAuth vóór 27 jan. 2025 te gebruiken. OAuth-verificatie verdient de voorkeur. U zult alle elementen vinden om van authentificatie JWT aan authentificatie OAuth op deze pagina&#39;s te migreren:
   >* [&#x200B; Migratie &#x200B;](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)
   >* [&#x200B; Implementatie &#x200B;](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)
   >* [&#x200B; Veelgestelde Veelgestelde vragen van de Verdringing JWT &#x200B;](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)

1. **ruilt uw JWT voor een Symbolisch van de Toegang** door een POST- verzoek. Dit toegangstoken moet worden gebruikt in elke header van uw API-aanvragen.

Om een veilige service-to-service Adobe I/O API-sessie tot stand te brengen, moet elke aanvraag naar een Adobe-service de onderstaande informatie bevatten in de machtigingheader.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

* **&lt;ORGANIZATION>**: Dit is uw persoonlijke ORGANIZATION identiteitskaart, één ORGANIZATION identiteitskaart wordt verstrekt door Adobe voor elk van uw instanties:

   * &lt;ORGANIZATION>: uw productieexemplaar
   * &lt;ORGANIZATION-market-stage>: de instantie van het werkgebied.

  Als u de waarde van uw ORGANISATIE-id wilt opvragen, raadpleegt u uw beheerder of uw technische contactpersoon voor Adobe. U kunt het in Adobe I/O ook terugwinnen wanneer het creëren van een nieuwe integratie, in de vergunningslijst (zie de <a href="https://developer.adobe.com/developer-console/docs/guides/authentication/"> documentatie van Adobe Developer </a>).

* **&lt;ACCESS_TOKEN>**: Uw persoonlijk toegangstoken, dat werd teruggewonnen toen het ruilen van uw Tken van het Web JSON door een POST verzoek.

* **&lt;API_KEY>**: uw persoonlijke API Sleutel. Het wordt geleverd in Adobe I/O na het creëren van een nieuwe integratie aan de Dienst van Adobe Campaign.

  ![&#x200B; alt tekst &#x200B;](assets/tenant.png)

## Problemen oplossen

Als de volgende fout optreedt tijdens de integratie met AdobeIO:

```
{ 
"code": 502, 
"message": "Oops. Something went wrong. Check your URI and try again." 
}
```


Raadpleeg uw beheerder of uw technische contactpersoon voor Adobe om te controleren of de CNAME-parameter correct is gemaakt.
