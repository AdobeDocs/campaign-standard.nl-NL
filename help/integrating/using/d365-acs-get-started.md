---
title: Aan de slag met de integratie van Microsoft Dynamics 365
description: Leer hoe u aan de slag kunt met de integratie van Microsoft Dynamics 365
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Microsoft CRM Integration
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '848'
ht-degree: 5%

---


# Aan de slag met de integratie van Microsoft Dynamics 365

Activeer uw CRM-gegevens voor kanaalcommunicatie: Leer hoe te om contacten van de Dynamiek 365 van Microsoft aan Adobe Campaign over te gaan, en gegevens van campagneprestaties (verzendt, opent, klikt, en stuitingen) terug van Adobe Campaign naar de Dynamica 365 van Microsoft te delen.

Voor deze integratie zijn de volgende softwareversies vereist:

* Microsoft Dynamics 365 for Sales Online, nieuwste versie

* Adobe Campaign Standard, nieuwste versie

>[!CAUTION]
>
>Deze mogelijkheid is niet rechtstreeks beschikbaar als onderdeel van het product. Voor de implementatie moet Adobe Consulting worden ingeschakeld. Neem contact op met uw Adobe-vertegenwoordiger voor meer informatie.


## Beginselen

De integratie van Adobe Campaign Standard met de Dynamica 365 van Microsoft laat synchronisatie van alle beschikbare contactgegevens in het systeem van CRM toe, die alle relevante contactgegevens ter beschikking stellen voor campagneactiviteiten.

Omgekeerd, aangezien de profielen binnen Adobe Campaign Standard met berichten in wisselwerking staan, die gegevens (b.v.: verzendt, opent, klikt, en stuitingen) stromen automatisch in de Dynamiek 365 van Microsoft om contactverslagen te houden volledig met marketing activiteit eveneens.

De integratie steunt ook het toelaten [douaneentiteiten](../../integrating/using/d365-acs-self-service-app-settings.md) in Dynamiek 365 om aan overeenkomstige **douanemiddelen** in Campagne worden gesynchroniseerd.

Deze integratie is bedoeld ter ondersteuning van vier belangrijke gebruiksgevallen:

1. Het synchroniseren van contacten van Dynamiek 365 aan Campagne zodat kunnen zij in marketing campagnes worden gericht
1. Het synchroniseren van douaneentiteiten van Dynamiek 365 aan Campagne zodat kunnen zij voor segmentatie en verpersoonlijking worden gebruikt
1. Het verzenden van e-mail marketing gebeurtenissen (verzendt, opent, klikt, stuit) van Campagne aan Dynamica 365 om aan verkoopbewaarplaats in de interface van de Dynamiek 365 te tonen
1. Synchroniseren van de status Weigeren (e-mail bijvoorbeeld niet) tussen Dynamics 365 en Campagne om de privacyvoorkeuren van de klant te behouden.

Belangrijkste voordelen zijn:

* Consistent overseinen tussen verkoop en marketing: de integratie van Adobe Campaign Standard met Dynamica 365 integratie verleent zowel systeemtoegang tot klanteninzicht als e-mailmarketing geschiedenis die alle berichten aan de klant toestaan om het zelfde verenigbare overseinen te delen.

* Holistische mening van alle vooruitzichten en klantengegevens: door Adobe Campaign Standard te integreren met Dynamics 365 is het mogelijk om e-mailmarketinggeschiedenis te delen en te openen voor elk contact vanuit het CRM-systeem.

* Activeer Dynamics 365-gegevens op elk kanaal: Als contactgegevens zijn gesynchroniseerd met Adobe Campaign, kunnen communicatie via elk online of offline kanaal worden verzonden met Campagne, zoals mobiele push, in-app, e-mail of direct mail. De campagne &quot;heeft u&quot;ongeacht elke contacten&#39; aangewezen kanaal behandeld.

>[!CAUTION]
>
>Deze integratie beschouwt Dynamiek 365 als bron van waarheid voor contact en douaneentiteitsynchronisatie.  Wijzigingen in gesynchroniseerde kenmerken moeten worden uitgevoerd in Dynamics 365, niet in Adobe Campaign Standard.  Als er wijzigingen worden aangebracht in Campagne, kunnen deze tijdens de synchronisatie worden overschreven.


## Belangrijke stappen om de integratie van de Dynamica 365 van Microsoft{#request-and-implement-this-integration} uit te voeren

Om deze integratie mogelijk te maken, moet u de onderstaande stappen volgen.

Volg hieronder het stroomschema en de stroomdiagramdetails om de integratie aan te vragen en te vormen.

![](assets/provisioning-wf.png)

Stroomdiagramdetails (afbeeldingen tot bovenstaande stappen):

* **Stap 1**  - Men veronderstelt dat u reeds hebt, of bezig bent om, een vergunning voor de Dynamica 365 van Microsoft voor Verkoop en voor Adobe Campaign Standard te kopen.
* **Stap 2**  - het standaard integratieaanbod is gratis aan alle klanten; Afhankelijk van uw vereisten kunnen er echter extra kosten van toepassing zijn. Meer informatie over [Aanbevolen werkwijzen en beperkingen](../../integrating/using/d365-acs-notices-and-recommendations.md). Er moet een nieuwe verkooporder (SO) worden ondertekend om van de integratie te kunnen profiteren als deze niet in de oorspronkelijke mededeling van punten van bezwaar was opgenomen.
* **Stap 3**  - Voltooi pre-integratiestappen voor Dynamiek 365 en Campagne. Zie [Deze integratie configureren](#configure-this-integration).
* **Stap 4**  - het Adobe onboarding team zal u toegang tot het gebruikersinterface van de integratietoepassing (UI) verlenen.
* **Stap 5**  - U zult uw gegevenstoewijzingen, vervangingen, filters, enz. kunnen vormen. en test uw integratie vanuit de interface van de integratietoepassing.

   >[!IMPORTANT]
   >
   > Als u de bidirectionele of Campagne aan Dynamiek 365 opt-out configuratie vereist, zult u het verzoek aan uw Adobe technisch contact voor de opt-out werkschema&#39;s moeten indienen om opstelling op uw instantie van de Campagne te zijn. [Meer informatie](../../integrating/using/d365-acs-notices-and-recommendations.md#opt-out).

### Deze integratie configureren {#configure-this-integration}

Voor deze integratie moeten drie systemen worden ingericht en geconfigureerd:

* **Adobe Campaign Standard**: u moet API toegang instellen en een nieuwe integratie configureren voor het integratieprogramma. Om dit te bereiken, verwijs naar [dit artikel](../../integrating/using/d365-acs-configure-adobe-io.md).
* **Microsoft Dynamics 365**: u moet een nieuwe toepassingsregistratie tot stand brengen en een toepassingsgebruiker toelaten om de integratie te gebruiken.  Om de Dynamiek 365 van Microsoft voor deze integratie te vormen, verwijs naar [dit artikel](../../integrating/using/d365-acs-configure-d365.md).
* **Adobe Campaign Standard-integratie met Microsoft Dynamics 365 Self-Service App**: u moet de stappen in  [dit artikel](../../integrating/using/d365-acs-self-service-app-control-access.md) volgen.

>[!IMPORTANT]
>
>Voor elk systeem, moeten deze stappen door een **beheerder** worden uitgevoerd.
>
>De stappen in deze documentatie zullen u door het creëren van integratie/registraties begeleiden die het toewijzen van toestemmingen en/of admin toegang impliceren.  Het is uw verantwoordelijkheid om ervoor te zorgen dat deze stappen voldoen aan uw bedrijfsbeleid alvorens uit te voeren, en hen zorgvuldig uit te voeren.


### Ondersteuning aanvragen

De kaartjes van de steun kunnen met de Zorg van de Klant van Adobe worden geregistreerd.

Voor alle problemen met integratiegegevensstromen moet u de volgende informatie opnemen:

* **Proceeigenaar**: Engineering-architecten
* **ES-verwerkings-id**: Wordt verstrekt tijdens het instapproces
* **Procestitel**: Integratie van Microsoft Dynamics 365 / Adobe Campaign Standard
* **Beschrijving** van uitgave: Beschrijving van het probleem

Integratieondersteuning is momenteel 24x5 (beschikbaar van maandag tot en met vrijdag, met uitzondering van Adobe-feestdagen en onderbrekingsperiodes).
