---
title: Adobe IO configureren voor integratie met Microsoft Dynamics 365
description: Leer hoe u Adobe IO for Microsoft Dynamics 365-integratie configureert.
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
source-git-commit: 4e05dafb087c43a13c60d6bb2f54d0e44455ea8d

---


# Adobe IO configureren voor integratie met Microsoft Dynamics 365

Activeer uw CRM-gegevens voor kanaalcommunicatie: leert stappen tijdens post-levering worden vereist om een nieuwe integratie voor de Dynamica 365 van Microsoft tot stand te brengen die.

## Overzicht

De integratie van Adobe Campaign Standard - Microsoft Dynamics 365 wordt beschreven in [deze pagina](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md).

Alvorens de post-provisioning stappen in dit artikel uit te voeren, wordt verondersteld dat u reeds provisioned bent en beheerdertoegang tot de Standaardinstantie van de Campagne van uw organisatie hebt.  Als dit niet is gebeurd, moet u contact opnemen met de klantenservice van Adobe om de levering van campagnes te voltooien.

>[!CAUTION]
>
>De hieronder beschreven stappen moeten door een beheerder worden uitgevoerd.

## Configuratie

U moet API toegang instellen en een nieuwe integratie voor Unifi configureren.

Configuratie wordt uitgevoerd in Adobe IO: u moet een nieuwe integratie voor Unifi tot stand brengen, zoals voorgesteld in deze video:

>[!VIDEO](https://video.tv.adobe.com/v/27308)

### Een nieuwe integratie maken

Hiervoor volgt u de onderstaande procedure:

1. Navigeer naar [Adobe IO Console](https://console.adobe.io/home#) en selecteer uw Adobe IMS Organisatie-id in het vervolgkeuzemenu linksboven (zie hieronder).

Klik vervolgens **[!UICONTROL New Integration]** rechtsboven.

>[!NOTE]
>
>Als dit de eerste integratie van uw organisatie is, **[!UICONTROL New Integration]** kan de knoop voor in het centrum van de pagina zijn.

1. Selecteer **[!UICONTROL Access an API]** en klik op **[!UICONTROL Continue]**.

1. Selecteer _Adobe-campagne_ in de **[!UICONTROL Experience Cloud]** sectie en klik op **[!UICONTROL Continue]**.

1. Genereer een certificaat en sleutel.

**Voor MacOS- en Linux-platforms**

Open de terminaltoepassing en voer de onderstaande opdracht uit:

```
openssl req -x509 -sha256 -nodes -days 365 -newkey rsa:2048 -keyout private.key -out certificate_pub.crt
```

**Voor Windows-platforms**

* Een open client downloaden om openbare certificaten te genereren (bijvoorbeeld de [OpenSl-vensterclient](https://bintray.com/vszakats/generic/download_file?file_path=openssl-1.1.1-win64-mingw.zip))

* De map uit het ZIP-bestand extraheren

* Opdrachtregelprompt openen en onder opdrachten uitvoeren.

Vervang `<containing folder path>` hieronder door het pad van de uitgepakte map (bijvoorbeeld C:\Users\labuser\Downloads\openssl-1.1.1-win64-mingw\openssl-1.1.1-win64-mingw):

```
set OPENSSL_CONF=<containing folder path>/openssl.cnf
 
cd <containing folder path>/
 
openssl req -x509 -sha256 -nodes -days 365 -newkey rsa:2048 -keyout private.key -out certificate_pub.crt
```

**Voor alle platforms**

Volg de aanwijzingen om de certificaataanvraag te voltooien:

```
Generating a 2048 bit RSA private key
 
.................+++
 
.......................................+++
 
writing new private key to 'private.key'
 
-----
 
You are about to be asked to enter information that will be incorporated
 
into your certificate request.
 
What you are about to enter is what is called a Distinguished Name or a DN.
 
There are quite a few fields but you can leave some blank
 
For some fields there will be a default value,
 
If you enter '.', the field will be left blank.
 
-----
```

Nadat u de gegevens hebt ingevoerd, worden twee bestanden gegenereerd: **[!UICONTROL certificate_pub.crt]** en **[!UICONTROL private.key]**.

* **[!UICONTROL certificate_pub.crt]** verloopt over 365 dagen. U kunt de vervalperiode wijzigen door de waarde van dagen in het bovenstaande openssl bevel te veranderen, maar het periodiek roteren van geloofsbrieven is een goede veiligheidspraktijk.

* **[!UICONTROL certificate_pub.crt]** wordt gebruikt in het volgende scherm om de integratie in de Adobe I/O-console te voltooien.

>[!NOTE]
>
> **[!UICONTROL private.key]** worden later tijdens de post-provisioningstappen voor Unifi gebruikt.

1. Ga terug naar de Adobe I/O-console en voer een naam en beschrijving in voor de integratie.

1. Uploaden **[!UICONTROL certificate_pub.crt]**

1. Selecteer het productprofiel in de titel:

   * De organisatie-id van uw Campagne-instantie
   * **[!UICONTROL Administrators]**

Voorbeeld:  Campagnestandaard - uw campagne-organisatieID - Beheerders

Klik op **[!UICONTROL Create Integration]**.

![](assets/do-not-localize/MSdynACSIntegration-4B.png)

### Integratiedetails instellen

1. Selecteren **[!UICONTROL Continue to Integration Details]**

Controleer de integratiedetails.  U moet naar deze instructies terugverwijzen wanneer u Unifi-postprovisioning-stappen doorloopt.

![](assets/do-not-localize/MSdynACSIntegration-5.png)

1. Klik op de tab en voeg **[!UICONTROL Services]** services **[!UICONTROL I/O Events]** **[!UICONTROL I/O Management API]** en services toe.  Klik vervolgens op het keuzerondje om de service toe te voegen **[!UICONTROL Add service]**.  U zult dit voor elke dienst afzonderlijk doen.

Als je klaar bent, worden je services bovenaan weergegeven, zoals in de onderstaande afbeelding. U zult niet de sectie a-op moeten voltooien die een JWT en toegangstoken produceert.

![](assets/do-not-localize/MSdynACSIntegration-6.png)

Post provisioning in Campaign is nu voltooid.  Ga aan volledige [postleveringsstappen voor de Dynamica 365](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md)van Microsoft te werk.

**Verwante onderwerpen**

* [Adobe IO - Integratie van serviceaccount](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)
* [Campagnestandaard - API Access Setup](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#setting-up-api-access)
* [Campagnestandaard - Integratie met Dynamics 365](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md)
