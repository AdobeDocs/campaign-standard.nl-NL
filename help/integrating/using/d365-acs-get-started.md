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
exl-id: fa0f790d-6a4d-4b83-a51f-f565e9545a1a
source-git-commit: e7fdaa4b1d77afdae8004a88bbe41bbbe75a3f3c
workflow-type: tm+mt
source-wordcount: '842'
ht-degree: 5%

---

# Aan de slag met de integratie van Microsoft Dynamics 365

Activeer uw gegevens van CRM over dwars-kanaalmededeling: leer hoe te om contacten van de Dynamiek 365 van Microsoft aan Adobe Campaign over te brengen, en de gegevens van de campagneprestaties (verzendt, opent, klikt, en stuit) terug van Adobe Campaign aan de Dynamica 365 van Microsoft te delen.

Voor deze integratie zijn de volgende softwareversies vereist:

* Microsoft Dynamics 365 for Sales Online, nieuwste versie

* Adobe Campaign Standard, nieuwste versie

>[!CAUTION]
>
>Deze mogelijkheid is niet rechtstreeks beschikbaar als onderdeel van het product. Voor de implementatie moet Adobe Consulting worden ingeschakeld. Neem contact op met uw Adobe-vertegenwoordiger voor meer informatie.
>

## Principes

Dankzij de Adobe Campaign Standard-integratie met Microsoft Dynamics 365 kunnen alle beschikbare contactgegevens in het CRM-systeem worden gesynchroniseerd, zodat alle relevante contactgegevens beschikbaar zijn voor campagneactiviteiten.

Omgekeerd, aangezien de profielen binnen Adobe Campaign Standard met berichten in wisselwerking staan, stromen die gegevens (b.v.: verzendt, opent, klikt, en stuitingen) automatisch in de Dynamica 365 van Microsoft om contactverslagen te houden volledig met marketing activiteit.

De integratie ondersteunt ook het inschakelen van [aangepaste entiteiten](../../integrating/using/d365-acs-self-service-app-settings.md) in Dynamics 365 to be synchronized to corresponding **aangepaste bronnen** in Campaign.

Deze integratie is ontworpen om vier hoofdgebruiksituaties te ondersteunen:

1. Het synchroniseren van contacten van Dynamiek 365 aan Campagne zodat kunnen zij in marketing campagnes worden gericht
1. Het synchroniseren van douaneentiteiten van Dynamiek 365 aan Campagne zodat kunnen zij voor segmentatie en verpersoonlijking worden gebruikt
1. Het verzenden van e-mail marketing gebeurtenissen (verzendt, opent, klikt, stuit) van Campagne aan Dynamica 365 om aan verkoopbewaarplaats in de interface van de Dynamiek 365 te tonen
1. Synchroniseren van de status Weigeren (e-mail bijvoorbeeld niet) tussen Dynamics 365 en Campagne om de privacyvoorkeuren van de klant te behouden.

Belangrijkste voordelen zijn:

* Consistent overseinen tussen verkoop &amp; marketing: de integratie van Adobe Campaign Standard met Dynamics 365 integratie geeft zowel systeemtoegang tot klanteninzicht als e-mailmarketing geschiedenis die alle berichten aan de klant toestaat om het zelfde verenigbare overseinen te delen.

* Holistische mening van alle vooruitzichten en klantengegevens: door Adobe Campaign Standard met Dynamica 365 te integreren, is het mogelijk om e-mailmarketing geschiedenis op elk contact van binnen het systeem van CRM te delen en toegang te hebben.

* Activate Dynamics 365 data on any channel: with contact data synchronized to Adobe Campaign, kunnen de mededelingen op om het even welk online of off-line kanaal met Campagne met inbegrip van mobiele duw, in-app, e-mail, of directe post worden verzonden. De campagne &quot;heeft u&quot;ongeacht elke contacten&#39; aangewezen kanaal behandeld.

>[!CAUTION]
>
>Deze integratie beschouwt Dynamiek 365 als bron van waarheid voor contact en douaneentiteitsynchronisatie.  Wijzigingen in gesynchroniseerde kenmerken moeten worden uitgevoerd in Dynamics 365, niet in Adobe Campaign Standard.  Als er wijzigingen worden aangebracht in Campagne, kunnen deze tijdens de synchronisatie worden overschreven.
>

## Belangrijkste stappen om de integratie van Microsoft Dynamics 365 te implementeren{#request-and-implement-this-integration}

Om deze integratie mogelijk te maken, moet u de onderstaande stappen volgen.

Volg hieronder het stroomschema en de stroomdiagramdetails om de integratie aan te vragen en te vormen.

![](assets/provisioning-wf.png)

Stroomdiagramdetails (afbeeldingen tot bovenstaande stappen):

* **Stap 1** - Er wordt aangenomen dat u al een licentie voor Microsoft Dynamics 365 voor Sales en voor Adobe Campaign Standard hebt of in aanschaf bent.
* **Stap 2** - Het standaard integratieaanbod is gratis voor alle klanten, maar er kunnen, afhankelijk van uw vereisten, extra kosten van toepassing zijn. Meer informatie over [Aanbevolen werkwijzen en beperkingen](../../integrating/using/d365-acs-notices-and-recommendations.md). Er moet een nieuwe verkooporder (SO) worden ondertekend om van de integratie te kunnen profiteren als deze niet in de oorspronkelijke mededeling van punten van bezwaar was opgenomen.
* **Stap 3** - Voltooi de pre-integratiestappen voor Dynamics 365 en Campaign. Zie [Deze integratie configureren](#configure-this-integration).
* **Stap 4** - Het Adobe instapkaartteam biedt u toegang tot de gebruikersinterface van de integratietoepassing (UI).
* **Stap 5** - U kunt uw gegevenstoewijzingen, vervangingen, filters, enz. configureren. en test uw integratie vanuit de interface van de integratietoepassing.

  >[!IMPORTANT]
  >
  > Als u de bidirectionele of Campagne aan Dynamiek 365 opt-out configuratie vereist, zult u het verzoek aan uw Adobe technisch contact voor de opt-out werkschema&#39;s moeten indienen om opstelling op uw instantie van de Campagne te zijn. [Meer informatie](../../integrating/using/d365-acs-notices-and-recommendations.md#opt-out).

### Deze integratie configureren {#configure-this-integration}

Voor deze integratie moeten drie systemen worden ingericht en geconfigureerd:

* **Adobe Campaign Standard**: u moet API-toegang instellen en een nieuwe integratie configureren voor het integratieprogramma. Om dit te bereiken, raadpleegt u [dit artikel](../../integrating/using/d365-acs-configure-adobe-io.md).
* **Microsoft Dynamics 365**: u moet een nieuwe toepassingsregistratie maken en een toepassingsgebruiker de integratie laten gebruiken.  Als u Microsoft Dynamics 365 voor deze integratie wilt configureren, raadpleegt u [dit artikel](../../integrating/using/d365-acs-configure-d365.md).
* **Adobe Campaign Standard-integratie met Microsoft Dynamics 365 Self-Service App**: u moet de stappen in [dit artikel](../../integrating/using/d365-acs-self-service-app-control-access.md).

>[!IMPORTANT]
>
>Voor elk systeem moeten deze stappen door een **beheerder**.
>
>De stappen in deze documentatie zullen u door het creëren van integratie/registraties begeleiden die het toewijzen van toestemmingen en/of admin toegang impliceren.  Het is uw verantwoordelijkheid om ervoor te zorgen dat deze stappen voldoen aan uw bedrijfsbeleid alvorens uit te voeren, en hen zorgvuldig uit te voeren.
>

### Verzoek om ondersteuning

De kaartjes van de steun kunnen met de Zorg van de Klant van de Adobe worden geregistreerd.

Voor alle problemen met integratiegegevensstromen moet u de volgende informatie opnemen:

* **Proceseigenaar**: Engineering-architecten
* **ES-proces-id**: Wordt verstrekt tijdens instapprocedure
* **Procestitel**: Microsoft Dynamics 365 / Adobe Campaign Standard Integration
* **Probleembeschrijving**: Beschrijving van het probleem

Integratieondersteuning is momenteel 24x5 (beschikbaar van maandag tot en met vrijdag, met uitzondering van feestdagen en onderbrekingsperiodes in de Adobe).
