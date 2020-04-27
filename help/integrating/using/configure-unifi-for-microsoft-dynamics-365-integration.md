---
title: Unifi configureren voor integratie met Microsoft Dynamics 365
description: Leer hoe te om Unifi voor de integratie van de Dynamica 365 van Microsoft te vormen
page-status-flag: never-activated
uuid: effa1028-66b2-4bef-b5e4-7319dbb23d5d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
discoiquuid: eb3639f5-7246-46c4-8ddb-da9413b40c32
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 37e86c6143c52841e69d610fa9db35dff70a3587

---



# Unifi configureren voor integratie met Microsoft Dynamics 365

Configureer Unifi voor het instellen en activeren van Microsoft Dynamics 365 - Adobe Campagne-integratie.

## Vereisten

Alvorens de post-provisioning stappen in dit artikel uit te voeren, wordt verondersteld dat u reeds met succes de [post-levering stappen voor Campagne](../../integrating/using/configure-adobe-io-for-ms-dynamic.md) en [voor Dynamiek 365](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md)hebt voltooid.  Als dit niet is gebeurd, dan zult u die stappen moeten volgen om Norm van de Campagne en Dynamiek 365 post-provisioning te voltooien.

Er wordt ook aangenomen dat u contact hebt opgenomen met Unifi, een Unifi-account voor u hebt gemaakt en u met succes hebt aangemeld.  Als dit niet is gebeurd, volgt u de stappen die in [dit artikel](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md)worden beschreven.

>[!CAUTION]
>
>Het wordt ten zeerste aanbevolen om met Unifi en/of Adobe Consulting (neem contact op met uw Adobe CSM) te werken bij het configureren van Unifi.

## Integratie van campagne configureren

Bij uw eerste verbinding, klik **[!UICONTROL Adobe Campaign Standard]** om uw geloofsbrieven van de Campagne in te gaan.

De meeste van deze referenties zijn afkomstig van de integratie die u tijdens de configuratiestappen [van](../../integrating/using/configure-adobe-io-for-ms-dynamic.md)Campagnestandaard hebt gemaakt in de Adobe I/O-console.

>[!NOTE]
>
>Om veiligheid en privacy te verzekeren, verschijnen de gevoelige geloofsbrieven leeg wanneer het herzien van deze configuratievensters.

1. Voer voor de URL voor Adobe-verificatie de volgende gegevens in `https://ims-na1.adobelogin.com/ims/exchange/jwt`

1. Voer uw **[!UICONTROL Adobe IO Organization ID]** en uw **[!UICONTROL Adobe IO Integration ID]**.

Navigeer naar het scherm Integratie van Adobe I/O-console boven om uw Adobe IO-organisatie- en integratie-id&#39;s op te halen. Noteer de web-URL.

Het moet er ongeveer als volgt uitzien: `https://console.adobe.io/integrations/<Org ID>/<Int ID>/overview`, waarbij Org ID en Int ID getallen zijn.

1. Voer uw **[!UICONTROL Tenant ID]**

Voer de onderstaande stappen uit om uw huurnummer te verkrijgen:

1. Navigeer naar de [Adobe Admin Console](https://adminconsole.adobe.com/) en selecteer de IMS-organisatie in het keuzemenu rechtsboven.
1. Selecteer het Adobe Campagne Standard-product en selecteer vervolgens de instantie Campagne Standard (als u meerdere versies hebt).  Hiermee wordt een lijst met productprofielen weergegeven.

   De beschrijvingen van het productprofiel verschijnen typisch in één van de volgende formaten, waar huurder identiteitskaart van uw geval `<tenantID>` is.

`Campaign Standard – https://<tenantID> - <ROLE>`

`Campaign Standard – <tenantID> - <ROLE>`

>[!NOTE]
>
>Neem contact op met u > Technische contact of de klantenservice van Adobe als u problemen ondervindt met het identificeren van uw huurder-id.
>
>Instantie-id&#39;s van de partnersandbox volgen doorgaans het patroon `https://<tenantId>`, waarbij `tenantId` het patroon aanwezig is `tbd.campaign-sandbox.adobe.com`.

1. Voer uw **[!UICONTROL Campaign Instance ID]** naam in.

Voer de onderstaande stappen uit om uw instantie-id op te halen:

    1. Voer &#39;https://&lt;acs-instance-url>/r/test&#39; in een webbrowser in en vervang `&lt;acs-instance-url>` door de URL van uw instantie Campagne Standard.
    1. De reactie bevat &#39;instance=&#39;, gevolgd door de instantie-id.

1. Selecteer het gebied van uw instantie Campagne.

1. U kunt **[!UICONTROL Base Directory]** leeg laten.

1. Selecteer de **[!UICONTROL Allow as Output Destination]** optie.

Als er parameters zijn ingesteld, klikt u op **[!UICONTROL CONNECT]** en controleert u of de verbinding is gelukt.

Als dat niet het geval is, klikt u op parameters **[!UICONTROL CLOSE]** en controleert u deze.

>[!NOTE]
>
>Als u deze stap niet kunt voltooien, neemt u contact op met de [Unifi-klantenservice](mailto:support@unifisoftware.atlassian.net).

## Integratie van Dynamics 365 configureren

Klik CRM van de Dynamica van Microsoft om Dynamica 365 geloofsbrieven te vormen. De meeste van deze geloofsbrieven zullen uit de integratie komen u in Dynamica 365 van Microsoft tijdens de configuratiestappen van de Dynamiek 365 van Microsoft creeerde.

>[!NOTE]
>
>Om veiligheid en privacy te verzekeren, verschijnen de gevoelige geloofsbrieven leeg wanneer het herzien van deze configuratievensters.

1. Voer bijvoorbeeld de URL van uw instantie Dynamics 365 in, waarbij u &quot;.api&quot; moet invoegen vóór &quot;.crm&quot; (bijvoorbeeld **[!UICONTROL URL]**`https://mydynamicsinstance.api.crm.dynamics.com`)

1. U gebruikt **[!UICONTROL clientid]** bijvoorbeeld de toepassings-id die bij het maken van de toepassingsregistratie is gegenereerd, als het [configureren van Dynamics 365](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md).

1. Voor **[!UICONTROL clientsecret]**, zult u het cliëntgeheim gebruiken dat werd geproduceerd toen u een cliëntgeheim aan de toepassingsregistratie toevoegde als [vormend Dynamiek 365](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md).

1. Voeg bijvoorbeeld **[!UICONTROL callbackurl]** toe `http://localhost:33333`.

1. Laat **[!UICONTROL refresh token]** het veld leeg.

1. Voor **[!UICONTROLhuurdersidentiteitskaart]**, gebruik huurdersidentiteitskaart die u van portal.azure.com als het [vormen van Dynamiek 365](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md)kreeg.

1. Schakel ten slotte het selectievakje in voor **[!UICONTROL Allow as Output Destination]**.

Wanneer er parameters zijn ingevoerd, klikt u op **[!UICONTROL CONNECT]** en controleert u of de verbinding is gelukt.

Als dat niet het geval is, klikt u op parameters **[!UICONTROL CLOSE]** en controleert u deze.

>[!NOTE]
>
>Als u deze stap niet kunt voltooien, neemt u contact op met de [Unifi-klantenservice](mailto:support@unifisoftware.atlassian.net).

## Unifi setup voltooid

Nadat u uw aanmeldingsgegevens hebt ingesteld, moet u Unifi op de hoogte stellen, aangezien enkele aanvullende stappen moeten worden uitgevoerd voordat u de integratie-instellingen kunt voltooien.  Neem contact op met de UNIFI-contactgegevens die u hebt ontvangen om aan te geven dat u uw aanmeldingsgegevens hebt ingesteld.

U moet een optie voor een opt-out selecteren en Unifi op de hoogte brengen wanneer deze is voltooid (waarbij Unifi wordt aangegeven welke optie voor een opt-out wordt geselecteerd).  In de [Unifi-gebruikershandleiding](https://drive.google.com/drive/folders/16seHF45e6bFxHX15zWLqFLEXymCuA_wn)vindt u een uitleg van de opties voor het weigeren van toegang.

Zodra Unifi hun werk voltooit, zullen zij u op de hoogte brengen en verdere informatie verstrekken om u te helpen uw instantie van Unifi vormen, gegevenstoegang één keer in werking stellen en dan, zodra succesvolle voltooiing, kunt u programma&#39;s toelaten.

De volgende frequentie wordt aanbevolen voor verschillende gebruiksgevallen:

* Ingress: Elke 15 minuten
* Eieren: Elke 15 minuten
* Verwijdert: Elke dag
* Uitschakelen: Elke dag

>[!NOTE]
>
>Standaard worden SEND-marketinggebeurtenissen buiten de egress-taak gefilterd.  Als u SEND marketing gebeurtenissen in Dynamiek 365 wilt zien, moet u de filter (stap 5) van de uitgang baan in Unifi wijzigen.

Er zijn twee verschillende rollen in Unifi, een eigenaargebruiker en een read-only analist gebruiker. Een eigenaargebruiker heeft de mogelijkheid om taken en schema&#39;s te wijzigen, terwijl de alleen-lezen analist dat niet doet.  Er kan slechts één eigenaargebruiker voor een bepaalde klanteninstantie zijn.  Als de klant de toegewezen persoon als eigenaargebruiker moet wijzigen, kan hij of zij een e-mail sturen naar [adobe-support@unifisoftware.com](mailto:adobe-support@unifisoftware.com) met de gevraagde wijziging.

In de onderstaande video&#39;s wordt een overzicht gegeven van de unieke configuratie, taakdetails, installatie en bewaking.

## Unifi Jobs

### Overzicht van de banen in de Unie

>[!VIDEO](https://video.tv.adobe.com/v/27392)

In deze video worden de verschillende Unifi-taken uitgelegd die vereist zijn voor de integratie van Adobe Campagne Standard met Microsoft Dynamics 365 (2:10 min)

### Unifi-taakgegevens: Ingress &amp; Egress

>[!VIDEO](https://video.tv.adobe.com/v/27396)

In deze video wordt uitgelegd wat de toegang- en egress-taken zijn in Unifi (4:27 min.)

### Operationalisatie en bewaking

>[!VIDEO](https://video.tv.adobe.com/v/27391)

In deze video worden de workflows en planningen (3.03 uur) uitgelegd

Meer als dit
* [Werken met Adobe Campaign Standard - Microsoft Dynamics 365](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md)
* [Microsoft Dynamics 365 configureren voor integratie van campagnes](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md)
* [Adobe IO voor Microsoft Dynamics 365 configureren - integratie met de standaard campagne](../../integrating/using/configure-adobe-io-for-ms-dynamic.md)
* [pagina met Microsoft Dynamics 365-integratiefuncties](https://helpx.adobe.com/campaign/kt/acs/using/acs-ms-dynamics-crm-connector-tutorial.html)