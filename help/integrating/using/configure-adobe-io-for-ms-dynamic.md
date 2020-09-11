---
title: De integratie van Adobe IO voor Microsoft Dynamics 365 configureren
description: Leer hoe te om Adobe IO voor de Integratie van de Dynamica 365 van Microsoft te vormen.
page-status-flag: never-activated
uuid: effa1028-66b2-4bef-b5e4-7319dbb23d5d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
discoiquuid: eb3639f5-7246-46c4-8ddb-da9413b40c32
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 60a67adf51881b785ad2f0b40ff544a0b9988afd
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 3%

---


# De integratie van Adobe IO voor Microsoft Dynamics 365 configureren

Activeer uw CRM-gegevens voor kanaalcommunicatie: leert stappen tijdens pre-integratieopstelling worden vereist om een nieuw project van Adobe IO tot stand te brengen en het voor de Integratie van de Dynamica 365 van Microsoft te vormen die.

## Overzicht

De integratie Adobe Campaign Standard - Microsoft Dynamics 365 wordt beschreven in [deze pagina](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md).

Alvorens de pre-integratieopstelling in dit artikel uit te voeren, wordt verondersteld dat u reeds provisioned bent en beheerdertoegang tot de instantie van de Campaign Standard van uw organisatie hebt.  Als dit niet is gebeurd, moet u contact opnemen met de klantenservice van Adobe om de levering van de campagne te voltooien.

>[!CAUTION]
>
>De hieronder beschreven stappen moeten door een beheerder worden uitgevoerd.

## Configuratie

U zult een nieuw project van Adobe IO moeten creëren en het voor de integratie vormen.

### Een nieuw project maken

Hiervoor volgt u de onderstaande procedure:

1. Navigeer naar [Adobe IO Console](https://console.adobe.io/home#) en selecteer uw Adobe IMS Organisatie-id van het drop-down menu bij het hoogste recht van het scherm.

1. Klik vervolgens **[!UICONTROL Create new project]** onder **[!UICONTROL Quick Start]**.

   ![](assets/adobeIO1.png)

1. Klik onder **[!UICONTROL Get started with your new project]** op **[!UICONTROL Add API]**.

   ![](assets/adobeIO2.png)

1. Selecteer de Adobe Campaign API (u moet mogelijk naar de onderkant schuiven) en klik **[!UICONTROL Next]**.

   ![](assets/adobeIO3.png)

1. Op het volgende scherm kunt u uw eigen openbare sleutel uploaden of Adobe IO de sleutel laten genereren voor u. Deze instructies volgen de laatste optie. Als u besluit Adobe IO te laten het zeer belangrijke paar produceren, klik op optie 1; klikt u op de **[!UICONTROL Generate keypair]** knop.

   ![](assets/adobeIO4.png)

1. In het volgende scherm wordt u gevraagd een naam te geven en de downloadlocatie van het zip-bestand met sleutelpaar te selecteren.

Nadat u het bestand hebt gedownload, kunt u het uitpakken om de openbare en persoonlijke sleutels weer te geven. Adobe IO heeft reeds de openbare sleutel op uw Adobe IO project toegepast. U moet uw persoonlijke sleutel voor later behouden; de persoonlijke sleutel wordt gebruikt tijdens de installatie vóór de integratie van het integratieprogramma.

1. Klik **[!UICONTROL Next]** om door te gaan

   ![](assets/adobeIO5.png)

1. In het volgende scherm selecteert u productprofielen die u aan dit project wilt koppelen. Selecteer het productprofiel in de titel: De huurder-id van uw campagneexemplaar - [!UICONTROL Administrators]

   Voorbeeld: Campaign Standard - uw campagne-huurderID - Beheerders

1. Klik op **[!UICONTROL Save configured API]**.

   ![](assets/adobeIO6.png)

1. Op het volgende scherm zult u de details van uw nieuw Adobe IO project zien. Klik **[!UICONTROL Add to Project]** bij de bovenkant verlaten van het scherm en selecteer **API** van het drop down.

   ![](assets/adobeIO7.png)

1. In het volgende scherm moet u de API voor I/O-gebeurtenissen selecteren en vervolgens op **[!UICONTROL Next]** klikken.

1. Klik op het volgende scherm **[!UICONTROL Save the configured API]**.  U wordt teruggebracht naar het scherm met projectdetails.

1. Klik nu **[!UICONTROL Add to Project]** bij de bovenkant verlaten van het scherm en selecteer **API** van de drop-down daling, zoals u eerder deed.

1. In het volgende scherm moet u de API voor I/O-beheer selecteren en op deze knop klikken **[!UICONTROL Next]**.

1. Klik op het volgende scherm **[!UICONTROL Save the configured API]**.

Installatie vóór integratie in campagne is nu voltooid.  Ga aan volledige [pre-integratieopstelling voor de Dynamica 365](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md)van Microsoft te werk.

**Verwante onderwerpen**

* [Adobe IO - Integratie van serviceaccount](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)
* [Campaign Standard - API Access Setup](../../api/using/setting-up-api-access.md)
* [Campaign Standard - Integratie met Dynamics 365](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md)