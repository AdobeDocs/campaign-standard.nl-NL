---
title: De integratie van Adobe IO voor Microsoft Dynamics 365 configureren
description: Leer hoe te om Adobe IO voor de Integratie van de Dynamica 365 van Microsoft te vormen.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
feature: Microsoft CRM Integration
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '634'
ht-degree: 2%

---


# Adobe Campaign Standard en de Configuratie van de Adobe I/O voor de Integratie van de Dynamica 365 van Microsoft

Dit artikel zal verklaren hoe te om Adobe Campaign Standard en Adobe I/O te vormen om de integratietoepassing toegang tot de gegevens te geven.

## Adobe Campaign Standard {#campaign-standard} configureren

### Profielextensies

Schakel &quot;profielextensies&quot; in Adobe Campaign Standard in.   Dit is nodig om douanevelden in het middel van het Profiel te synchroniseren van de Dynamica 365 van Microsoft.   De volgende stappen moeten worden uitgevoerd:

1. Ga naar Instellingen -> Beheer -> Ontwikkeling -> Publiceren.
1. Klik op Publicatie voorbereiden om een publicatie voor te bereiden.
1. Nadat de voorbereiding is voltooid, schakelt u de optie &quot;Create the Profiles &amp; Services Ext API&quot; in en klikt u op &quot;Publish&quot;.

## Adobe I/O configureren {#adobe-io}

Met Adobe I/O kunt u API-toegang tot Adobe Campaign Standard en andere Adobe-producten inschakelen.   Dit artikel zal in detail hoe te om Adobe I/O te vormen om de integratie van Adobe Campaign Standard met de Dynamica 365 van Microsoft toegang te geven om de gegevens te synchroniseren.

### Overzicht

Alvorens de pre-integratieopstelling in dit artikel uit te voeren, wordt verondersteld dat u reeds provisioned bent en beheerdertoegang tot de instantie van de Campaign Standard van uw organisatie hebt.  Als dit niet is gebeurd, moet u contact opnemen met de klantenservice van Adobe om de levering van de campagne te voltooien.

>[!CAUTION]
>
>De hieronder beschreven stappen moeten door een beheerder worden uitgevoerd.

### Configuratie

U zult een nieuw project van Adobe IO moeten creëren en het voor de integratie vormen.

#### Een nieuw project maken

Hiervoor volgt u de onderstaande procedure:

1. Navigeer naar [Adobe IO Console](https://console.adobe.io/home#) en selecteer uw Adobe IMS Organisatie-id in het keuzemenu rechtsboven in het scherm.

1. Klik vervolgens onder **[!UICONTROL Create new project]** onder **[!UICONTROL Quick Start]**.

   ![](assets/adobeIO1.png)

1. Klik onder **[!UICONTROL Get started with your new project]** op **[!UICONTROL Add API]**.

   ![](assets/adobeIO2.png)

1. Selecteer de Adobe Campaign API (mogelijk moet u naar de onderkant schuiven) en klik op **[!UICONTROL Next]**.

   ![](assets/adobeIO3.png)

1. Op het volgende scherm kunt u uw eigen openbare sleutel uploaden of Adobe IO de sleutel laten genereren voor u. Deze instructies volgen de laatste optie. Als u besluit Adobe IO te laten het zeer belangrijke paar produceren, klik op optie 1; Klik vervolgens op de knop **[!UICONTROL Generate keypair]**.

   ![](assets/adobeIO4.png)

1. In het volgende scherm wordt u gevraagd een naam te geven en de downloadlocatie van het zip-bestand met sleutelpaar te selecteren.

Nadat u het bestand hebt gedownload, kunt u het uitpakken om de openbare en persoonlijke sleutels weer te geven. Adobe IO heeft reeds de openbare sleutel op uw Adobe IO project toegepast. U moet uw persoonlijke sleutel voor later behouden; de persoonlijke sleutel wordt gebruikt tijdens de installatie vóór de integratie van het integratieprogramma.

1. Klik **[!UICONTROL Next]** om door te gaan

   ![](assets/adobeIO5.png)

1. In het volgende scherm selecteert u productprofielen die u aan dit project wilt koppelen. Selecteer het productprofiel in de titel: De huurder-id van uw Campagne-instantie - [!UICONTROL Administrators]

   Voorbeeld: Campaign Standard - uw campagne-huurderID - Beheerders

1. Klik op **[!UICONTROL Save configured API]**.

   ![](assets/adobeIO6.png)

1. Op het volgende scherm zult u de details van uw nieuw Adobe IO project zien. Klik op **[!UICONTROL Add to Project]** linksboven in het scherm en selecteer **API** in de vervolgkeuzelijst.

   ![](assets/adobeIO7.png)

1. In het volgende scherm moet u de API voor I/O-gebeurtenissen selecteren en vervolgens op **[!UICONTROL Next]** klikken.

1. Klik op **[!UICONTROL Save the configured API]** in het volgende scherm.  U wordt teruggebracht naar het scherm met projectdetails.

1. Klik nu **[!UICONTROL Add to Project]** bij de bovenkant verlaten van het scherm en selecteer **API** van de drop-down, aangezien u eerder deed.

1. In het volgende scherm moet u de API voor I/O-beheer selecteren en op **[!UICONTROL Next]** klikken.

1. Klik op **[!UICONTROL Save the configured API]** in het volgende scherm.

Installatie vóór integratie in campagne is nu voltooid.

**Verwante onderwerpen**

* [Adobe IO voor de Integratie van de Dynamica 365 van Microsoft vormen ](../../integrating/using/d365-acs-configure-adobe-io.md) is de volgende stap in vestiging de integratie
* [Het overzicht van de Toepassing van de Zelfbediening van de integratie ](../../integrating/using/d365-acs-self-service-app-quick-start-guide.md) van de Toepassing bevat de volledige lijst van stappen om de integratie in werking te stellen.


* [Adobe IO - Integratie van serviceaccount](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)
* [Campaign Standard - API Access Setup](../../api/using/setting-up-api-access.md)
* [Campaign Standard - Integratie met Dynamics 365](../../integrating/using/d365-acs-configure-d365.md)
