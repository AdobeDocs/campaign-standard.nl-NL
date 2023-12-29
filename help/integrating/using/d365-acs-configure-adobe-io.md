---
title: Integratie van Adobe Developer for Microsoft Dynamics 365 configureren
description: Leer hoe u de integratie van Adobe Developer for Microsoft Dynamics 365 configureert
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
feature: Microsoft CRM Integration
role: Data Architect
level: Intermediate
exl-id: ab21b694-d05c-4ba4-b828-936803651b82
source-git-commit: c701043cbba22711de1ea7ddc5266e193d771e14
workflow-type: tm+mt
source-wordcount: '568'
ht-degree: 0%

---

# Adobe Campaign Standard en Adobe Developer Configuration for the Microsoft Dynamics 365 integration

Dit artikel zal verklaren hoe te om Adobe Campaign Standard en Adobe I/O te vormen om de integratietoepassing toegang tot de gegevens te geven.

## Adobe Campaign Standard configureren {#campaign-standard}

### Profielextensies

Schakel &quot;profielextensies&quot; in Adobe Campaign Standard in.   Dit is nodig om aangepaste velden in de profielbron te synchroniseren vanuit Microsoft Dynamics 365.   De volgende stappen moeten worden uitgevoerd:

1. Ga naar Instellingen -> Beheer -> Ontwikkeling -> Publiceren.
1. Klik op Publicatie voorbereiden om een publicatie voor te bereiden.
1. Nadat de voorbereiding is voltooid, schakelt u de optie &quot;Create the Profiles &amp; Services Ext API&quot; in en klikt u op &quot;Publish&quot;.

## Adobe I/O configureren {#adobe-io}

Met Adobe I/O kunt u API-toegang tot Adobe Campaign Standard en andere Adobe-producten inschakelen.   Dit artikel zal in detail hoe te om Adobe I/O te vormen om de integratie van Adobe Campaign Standard met de Dynamica 365 van Microsoft toegang te geven om de gegevens te synchroniseren.

### Overzicht

Alvorens de pre-integratieopstelling in dit artikel uit te voeren, wordt verondersteld dat u reeds provisioned bent en beheerdertoegang tot de instantie van het Campaign Standard van uw organisatie hebt.  Als dit niet is gebeurd, moet u contact opnemen met de klantenservice van de Adobe om de levering van de campagne te voltooien.

>[!CAUTION]
>
>De hieronder beschreven stappen moeten door een beheerder worden uitgevoerd.

### Configuratie

U zult een nieuw project van Adobe Developer moeten creëren en het voor de integratie vormen.

#### Een nieuw project maken

Hiervoor volgt u de onderstaande procedure:

1. Navigeren naar [Adobe Developer Console](https://console.adobe.io/home#) en selecteer uw organisatie-id voor Adobe in het keuzemenu rechtsboven in het scherm.

1. Klik vervolgens op **[!UICONTROL Create new project]** krachtens **[!UICONTROL Quick Start]**.

   ![](assets/adobeIO1.png)

1. Onder **[!UICONTROL Get started with your new project]**, klikt u op **[!UICONTROL Add API]**.

   ![](assets/adobeIO2.png)

1. Selecteer de Adobe Campaign en klik op **[!UICONTROL Next]**.

   ![](assets/adobeIO3.png)

1. Op het volgende scherm kunt u het verificatietype kiezen. U kunt kiezen voor OAuth Server-to-Server of Service Account (JWT). Merk op dat de geloofsbrieven van de Rekening van de Dienst (JWT) niet meer voor nieuwe projecten worden geadviseerd en voor de nieuwere geloofsbrieven van Server-aan-Server verouderd zijn. De instructies die in deze handleiding worden gegeven, zijn alleen van toepassing op OAuth Server-to-Server-verificatie.

   ![](assets/adobeIO4.png)

1. In het volgende scherm selecteert u productprofielen die u aan dit project wilt koppelen. Selecteer het productprofiel dat in de titel bevat: De huurder-id van uw campagneexemplaar - [!UICONTROL Administrators]

   Voorbeeld: Campaign Standard - uw-campagne-huurderID - Beheerders

1. Klik op **[!UICONTROL Save configured API]**.

   ![](assets/adobeIO5.png)

1. Op het volgende scherm ziet u de details van uw nieuwe Adobe Developer-project. Klikken **[!UICONTROL Add to Project]** links boven in het scherm en selecteert u **API** in de vervolgkeuzelijst.

   ![](assets/adobeIO6.png)

1. In het volgende scherm moet u de API voor I/O-gebeurtenissen selecteren en vervolgens op **[!UICONTROL Next]**.

1. Klik op het volgende scherm op **[!UICONTROL Save the configured API]**.  U wordt teruggebracht naar het scherm met projectdetails.

1. Klik nu op **[!UICONTROL Add to Project]** links boven in het scherm en selecteert u **API** in de vervolgkeuzelijst, zoals u eerder deed.

1. In het volgende scherm moet u de API voor I/O-beheer selecteren en op **[!UICONTROL Next]**.

1. Klik op het volgende scherm op **[!UICONTROL Save the configured API]**.

Installatie vóór integratie in campagne is nu voltooid.

**Verwante onderwerpen**

* [Integratie van Adobe Developer for Microsoft Dynamics 365 configureren](../../integrating/using/d365-acs-configure-adobe-io.md) is de volgende stap bij het opzetten van de integratie
* [Het overzicht van de toepassing van de Zelfbediening van de integratie](../../integrating/using/d365-acs-self-service-app-quick-start-guide.md) bevat de volledige lijst met stappen om de integratie op gang te brengen.
* [Adobe Developer - Integratie van serviceaccount](https://developer.adobe.com/developer-console/docs/guides/#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)
* [Campaign Standard - API Access Setup](../../api/using/setting-up-api-access.md)
* [Campaign Standard - Dynamiek 365-integratie](../../integrating/using/d365-acs-configure-d365.md)
* [Credentials migreren van JWT naar OAuth Server-aan-Server](../../integrating/using/d365-acs-self-service-app-migrate-credentials.md) bevat de stappen om geloofsbrieven van JWT aan OAuth server-aan-Server te migreren.
