---
title: De integratie van Microsoft Dynamics 365 aanvragen en configureren
description: Leer hoe te om de Dynamica 365 van Microsoft met de integratie van Campaign Standard te verzoeken en te vormen
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0ce73bf7e250c5e88bbb525854e81ef27662ab06
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 3%

---


# De integratie van Microsoft Dynamics 365 aanvragen en configureren

Om deze integratie mogelijk te maken, moet u de onderstaande stappen volgen.

Volg hieronder het stroomschema en de stroomdiagramdetails om de integratie aan te vragen en te vormen.

![](assets/provisioning-wf.png)

Stroomdiagramdetails (afbeeldingen tot bovenstaande stappen):

* **Stap 1** - Men veronderstelt dat u reeds hebt, of in de aanschaf bent van, een vergunning voor de Dynamiek van Microsoft 365 voor Verkoop en voor Adobe Campaign Standard.

* **Stap 2** - het standaard integratieaanbod is gratis aan alle klanten; Afhankelijk van uw vereisten kunnen er echter extra kosten van toepassing zijn (zie [Integratiegaranties en grenzen](../../integrating/using/ms-dynamics-365-integration-guardrails.md). Er moet een nieuwe verkooporder worden ondertekend om van de integratie te kunnen profiteren.

* **Stap 3** - Voltooi pre-integratiestappen voor Dynamiek 365 en Campagne. Zie Deze integratie [configureren](#configure-this-integration).

* **Stappen 4-7** - Het Adobe onboarding team zal met u door het onboarding proces werken.

## Deze integratie configureren {#configure-this-integration}

Voor deze integratie moeten drie systemen worden ingericht en geconfigureerd: Adobe Campaign Standard, Microsoft Dynamics 365 for Sales en the integration tool. De artikelen van de configuratie zijn hieronder verbonden.

>[!CAUTION]
>
>Voor elk systeem, moeten deze stappen door een beheerder worden uitgevoerd.
>
>De stappen in de onderstaande artikelen begeleiden u bij het maken van integraties/registraties die het toewijzen van machtigingen en/of beheerderstoegang inhouden.  Het is uw verantwoordelijkheid om ervoor te zorgen dat deze stappen voldoen aan uw bedrijfsbeleid alvorens uit te voeren, en hen zorgvuldig uit te voeren.

In ADOBE CAMPAIGN moet u API-toegang instellen en een nieuwe integratie configureren voor het integratieprogramma. Raadpleeg [dit artikel](../../integrating/using/configure-adobe-io-for-ms-dynamic.md)om dit te bereiken.

In MICROSOFT DYNAMICS 365, moet u een nieuwe toepassingsregistratie tot stand brengen en een toepassingsgebruiker toelaten om de integratie te gebruiken.  Om de Dynamiek 365 van Microsoft voor deze integratie te vormen, verwijs naar [dit artikel](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md).

U zult met het Adobe onboarding team aan opstelling de configuratie voor toegang, uitgang, en opt-out gegevensstromen moeten werken.


## Ondersteuning aanvragen

De kaartjes van de steun kunnen met de Aangepaste Zorg van Adobe worden geregistreerd, zoals gebruikelijk; De Zorg van de klant zal ondersteuningspersoneel, zoals nodig brengen.

Voor om het even welke kwesties met de stromen van integratiegegevens, zorg ervoor om de rapportreeks als deel van de vraagbeschrijving evenals de volgende informatie te omvatten:

* **Proceeigenaar**: Engineering-architecten

* **ES-verwerkings-id**: Wordt verstrekt tijdens het instapproces

* **Procestitel**: Dynamics 365 / Adobe Campaign Standard Integration

* **Beschrijving** van uitgave: Beschrijving van het probleem

Integratieondersteuning is momenteel 24x5 (beschikbaar van maandag tot en met vrijdag, met uitzondering van Adobe-feestdagen en onderbrekingsperiodes).