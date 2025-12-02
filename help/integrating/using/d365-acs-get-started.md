---
title: Aan de slag met de Microsoft Dynamics 365-integratie
description: Leer hoe u aan de slag kunt met de Microsoft Dynamics 365-integratie
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Microsoft CRM Integration
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: fa0f790d-6a4d-4b83-a51f-f565e9545a1a
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '874'
ht-degree: 4%

---

# Aan de slag met de Microsoft Dynamics 365-integratie

Activeer uw CRM-gegevens voor communicatie via meerdere kanalen: leer hoe u contactpersonen van Microsoft Dynamics 365 kunt doorgeven aan Adobe Campaign en hoe u gegevens over de campagneprestaties (verzenden, openen, klikken en bellen) kunt delen van Adobe Campaign naar Microsoft Dynamics 365.

Voor deze integratie zijn de volgende softwareversies vereist:

* Microsoft Dynamics 365 alleen voor Sales Online, nieuwste versie

* Adobe Campaign Standard, nieuwste versie

>[!CAUTION]
>
>Deze mogelijkheid is niet rechtstreeks beschikbaar als onderdeel van het product. Voor de implementatie moet Adobe Consulting worden ingeschakeld. Neem contact op met uw Adobe-vertegenwoordiger voor meer informatie.
>

## Principes

Dankzij de Adobe Campaign Standard-integratie met Microsoft Dynamics 365 kunnen alle beschikbare contactgegevens in het CRM-systeem worden gesynchroniseerd, zodat alle relevante contactgegevens beschikbaar zijn voor campagneactiviteiten.

Omgekeerd, aangezien de profielen binnen Adobe Campaign Standard met berichten in wisselwerking staan, stromen die gegevens (b.v.: verzendt, opent, klikt, en stuit) automatisch naar Microsoft Dynamics 365 om contactverslagen te houden volledig met marketing activiteit.

De integratie steunt ook toelatend [&#x200B; douaneentiteiten &#x200B;](../../integrating/using/d365-acs-self-service-app-settings.md) in Dynamiek 365 om aan overeenkomstige **douanemiddelen** in Campagne worden gesynchroniseerd.

Deze integratie is ontworpen om vier hoofdgebruiksituaties te ondersteunen:

1. Het synchroniseren van contacten van Dynamiek 365 aan Campagne zodat kunnen zij in marketing campagnes worden gericht
1. Het synchroniseren van douaneentiteiten van Dynamiek 365 aan Campagne zodat kunnen zij voor segmentatie en verpersoonlijking worden gebruikt
1. Het verzenden van e-mail marketing gebeurtenissen (verzendt, opent, klikt, stuit) van Campagne aan Dynamica 365 om aan verkoopbewaarplaats in de interface van de Dynamiek 365 te tonen
1. Synchroniseren van de status Weigeren (e-mail bijvoorbeeld niet) tussen Dynamics 365 en Campagne om de privacyvoorkeuren van de klant te behouden.

Belangrijkste voordelen zijn:

* Consistent overseinen tussen verkoop &amp; marketing: de integratie van Adobe Campaign Standard met Dynamiek 365 integratie geeft zowel systeemtoegang tot klantinsight als e-mail marketing geschiedenis die alle berichten aan de klant toestaat om het zelfde verenigbare overseinen te delen.

* Holistische mening van alle vooruitzichten en klantengegevens: door Adobe Campaign Standard met Dynamica 365 te integreren, is het mogelijk om e-mailmarketing geschiedenis op elk contact van binnen het systeem van CRM te delen en toegang te hebben.

* Activate Dynamics 365 data on any channel: with contact data synchronized to Adobe Campaign, kunnen de mededelingen op om het even welk online of off-line kanaal met Campagne met inbegrip van mobiele duw, in-app, e-mail, of directe post worden verzonden. De campagne &quot;heeft u&quot;ongeacht elke contacten&#39; aangewezen kanaal behandeld.

>[!CAUTION]
>
>Deze integratie beschouwt Dynamiek 365 als bron van waarheid voor contact en douaneentiteitsynchronisatie.  Wijzigingen in gesynchroniseerde kenmerken moeten worden uitgevoerd in Dynamics 365, niet in Adobe Campaign Standard.  Als er wijzigingen worden aangebracht in Campagne, kunnen deze tijdens de synchronisatie worden overschreven.
>

## Belangrijkste stappen om de Microsoft Dynamics 365-integratie te verwezenlijken{#request-and-implement-this-integration}

Om deze integratie mogelijk te maken, moet u de onderstaande stappen volgen.

Volg hieronder het stroomschema en de stroomdiagramdetails om de integratie aan te vragen en te vormen.

![](assets/provisioning-wf.png)

Stroomdiagramdetails (afbeeldingen tot bovenstaande stappen):

* **Stap 1** - men veronderstelt dat u reeds hebt, of in het proces bent om, een vergunning voor Microsoft Dynamics 365 voor Verkoop en voor Adobe Campaign Standard aan te kopen.
* **Stap 2** - het standaard integratieaanbod is vrij aan alle klanten; nochtans, kunnen de extra kosten afhankelijk van uw vereisten van toepassing zijn. Leer meer over [&#x200B; Beste praktijken en beperkingen &#x200B;](../../integrating/using/d365-acs-notices-and-recommendations.md). Er moet een nieuwe verkooporder (SO) worden ondertekend om van de integratie te kunnen profiteren als deze niet in de oorspronkelijke mededeling van punten van bezwaar was opgenomen.
* **Stap 3** - voltooi pre-integratiestappen voor Dynamiek 365 en Campagne. Zie [&#x200B; deze integratie &#x200B;](#configure-this-integration) vormen.
* **Stap 4** - het Adobe onboarding team zal u toegang tot het gebruikersinterface van de integratietoepassing (UI) verlenen.
* **Stap 5** - U zult uw gegevenstoewijzingen, vervangingen, filters, enz. kunnen vormen. en test uw integratie vanuit de interface van de integratietoepassing.

  >[!IMPORTANT]
  >
  > Als u de bidirectionele of Campagne aan Dynamiek 365 opt-out configuratie vereist, zult u het verzoek aan uw technische contact van Adobe voor de opt-out werkschema&#39;s moeten indienen om opstelling op uw instantie van de Campagne te zijn. [Meer informatie](../../integrating/using/d365-acs-notices-and-recommendations.md#opt-out).

### Deze integratie configureren {#configure-this-integration}

Voor deze integratie moeten drie systemen worden ingericht en geconfigureerd:

* **Adobe Campaign Standard**: u moet opstelling API toegang en een nieuwe integratie voor het integratiehulpmiddel vormen. Om dit te bereiken, verwijs naar [&#x200B; dit artikel &#x200B;](../../integrating/using/d365-acs-configure-adobe-io.md).
* **Microsoft Dynamics 365**: u moet een nieuwe toepassingsregistratie tot stand brengen en een toepassingsgebruiker toelaten om de integratie te gebruiken.  Om Microsoft Dynamics 365 voor deze integratie te vormen, verwijs naar [&#x200B; dit artikel &#x200B;](../../integrating/using/d365-acs-configure-d365.md).
* **de integratie van Adobe Campaign Standard met Microsoft Dynamics 365 Zelfbediening App**: u zult de stappen in [&#x200B; dit artikel &#x200B;](../../integrating/using/d365-acs-self-service-app-control-access.md) moeten volgen.

>[!IMPORTANT]
>
>Voor elk systeem, moeten deze stappen door een **beheerder** worden uitgevoerd.
>
>De stappen in deze documentatie zullen u door het creëren van integratie/registraties begeleiden die het toewijzen van toestemmingen en/of admin toegang impliceren.  Het is uw verantwoordelijkheid om ervoor te zorgen dat deze stappen voldoen aan uw bedrijfsbeleid alvorens uit te voeren, en hen zorgvuldig uit te voeren.
>

### Verzoek om ondersteuning

Support-tickets kunnen worden geregistreerd bij de klantenservice van Adobe.

Voor alle problemen met integratiegegevensstromen moet u de volgende informatie opnemen:

* **Eigenaar van het Proces**: De Architecten van de Techniek
* **ES identiteitskaart van het Proces**: Verstrekt tijdens het instapproces
* **Titel van het Proces**: De Integratie van Microsoft Dynamics 365/Adobe Campaign Standard
* **Beschrijving van de Uitgave**: Beschrijving van de kwestie

Integratieondersteuning is momenteel 24x5 (beschikbaar van maandag tot en met vrijdag, met uitzondering van Adobe-feestdagen en onderbrekingsperiodes).
