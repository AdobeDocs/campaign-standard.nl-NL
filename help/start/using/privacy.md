---
title: Privacy en toestemming in Adobe Campaign Standard
description: In deze sectie wordt een overzicht gegeven van privacy, persoonsgegevens en toestemmingsbeheer in Adobe Campaign Standard, en van de beschikbare tools om hiermee om te gaan.
page-status-flag: never-activated
uuid: ed9e631c-5ad1-49f1-be1e-b710bc64dc91
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: discovering-the-interface
discoiquuid: 5227ca05-3856-4e54-aec6-14444d6534e3
feature: Privacy
role: User
level: Intermediate
exl-id: 0fc71c2f-f294-43f7-825c-73ab4d43fcf7
source-git-commit: 6b683ccd93e10f78ff643eed9f374a794c085cb1
workflow-type: tm+mt
source-wordcount: '1377'
ht-degree: 100%

---

# Privacy en toestemming{#privacy-and-consent}

## Algemene aanbevelingen {#general-recommendations}

Adobe Campaign is een krachtige tool voor het verzamelen en verwerken van zeer grote hoeveelheden gegevens, waaronder persoonlijke informatie en gevoelige gegevens. Daarom moet privacy zorgvuldig worden beheerd.

* Ga altijd op verantwoordelijke en ethische wijze te werk bij het gebruik van persoonsgegevens.

* Stuur geen ongewenste e-mails, pushberichten en sms-berichten (&quot;spam&quot;). Adobe gelooft sterk in de principes van permission marketing, in het bevorderen van customer lifetime value en in de loyaliteit van klanten, en verbiedt daarom strikt het gebruik van Adobe Campaign voor het verzenden van ongevraagde berichten.

### Privacywetgeving {#privacy-regulations}

Werk binnen de wetgeving die geldt voor de regio(’s) waar u actief bent om privacy en persoonsgegevens correct te behandelen en te beheren. Het gaat bijvoorbeeld om de volgende wetgevingen:
* [AVG](https://ec.europa.eu/info/law/law-topic/data-protection/reform/what-does-general-data-protection-regulation-gdpr-govern_en) (Algemene verordening gegevensbescherming)
* [DPA](https://www.gov.uk/data-protection) (Britse implementatie van de AVG)
* [Europese richtlijn betreffende privacy en elektronische communicatie](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:02002L0058-20091219)
* [CAN-SPAM Act](https://www.ftc.gov/business-guidance/resources/can-spam-act-compliance-guide-business) (Amerikaanse wetgeving over regels en vereisten voor commerciële e-mail)
* [CCPA](https://leginfo.legislature.ca.gov/faces/codes_displayText.xhtml?lawCode=CIV&amp;division=3.&amp;title=1.81.5.&amp;part=4.&amp;chapter=&amp;article=) (California Consumer Privacy Act)
* [PDPA](https://secureprivacy.ai/thailand-pdpa-summary-what-businesses-need-to-know/) (Thaise wet inzake de bescherming van persoonsgegevens)

>[!NOTE]
>
>Zie [deze pagina](../../start/using/privacy-management.md#privacy-management-regulations) voor meer informatie over hoe de AVG, CCPA en PDPA van toepassing zijn op Adobe Campaign.

### Adobe Experience Cloud-privacy {#experience-cloud-privacy}

Adobe Campaign maakt deel uit van de Adobe Experience Cloud-oplossingen. De manier waarop in Campaign met privacy wordt omgegaan, volgt de algemene Adobe Experience Cloud-beginselen:

* **Welke informatie wanneer wordt verzameld bij het gebruik van Adobe Experience Cloud**

  Als bedrijf dat Adobe Experience Cloud-oplossingen gebruikt, bepaalt u welke gegevens u verzamelt en naar uw Adobe Experience Cloud-account verzendt. Voorbeelden van soorten informatie die mogelijk worden verzameld, zijn webbrowseractiviteiten, IP-adressen, locatiegegevens van mobiele apparaten, succespercentages van campagnes, items die zijn aangeschaft of in een winkelwagentje zijn geplaatst, enz.

  >[!NOTE]
  >
  >Net als alle andere Adobe-producten verzamelt Campaign informatie over gebruikers van apps en websites. Zie het [Adobe-privacybeleid](https://www.adobe.com/nl/privacy/policy.html) voor meer informatie.

* **Hoe Adobe Experience Cloud wordt gebruikt om informatie te verzamelen**

   * Adobe Experience Cloud-oplossingen gebruiken cookies en vergelijkbare technologieën zoals webbakens (ook wel tags of pixels genoemd), waarmee u informatie kunt verzamelen. Zie [deze sectie](#tracking-capabilities) voor meer informatie over cookies en trackingmogelijkheden met Adobe Campaign.
   * U kunt in uw mobiele apps ook Adobe Experience Cloud-technologieën gebruiken. Zie [deze pagina](../../channels/using/mobile-guide.md) voor meer informatie over het verzenden van mobiele leveringen met Campaign.

* **De privacyopties van uw gebruikers voor uw gebruik van Adobe Experience Cloud**

  Adobe vraagt u om uw klanten een privacybeleid te verstrekken waarin het volgende wordt beschreven:

   * Uw privacymethoden in verband met Adobe Experience Cloud
   * Hoe gebruikers hun voorkeuren kunnen instellen voor het verzamelen of gebruiken van hun gegevens in verband met Adobe Experience Cloud

  >[!NOTE]
  >
  >Net als bij alle Adobe-producten kunnen Campaign-gebruikers weigeren om verzamelde informatie over hen te delen via apps en websites. Raadpleeg de [Veelgestelde vragen over Adobe Experience Cloud-gebruiksgegevens](https://www.adobe.com/nl/privacy/experience-cloud-usage-info-faq.html) voor meer informatie daarover.

Zie [deze pagina](https://www.adobe.com/nl/privacy/marketing-cloud.html) voor meer informatie over de Adobe Experience Cloud-privacy.

## Persoonsgegevens en persona&#39;s {#personal-data}

Bij privacybeheer is het belangrijk om te bepalen welke gegevens met zorg moeten worden behandeld en door wie.
* **Persoonsgegevens** omvatten informatie aan de hand waarvan een levende persoon direct of indirect kan worden geïdentificeerd.
* **Gevoelige persoonsgegevens** zijn gegevens over etnische afkomst, politieke opvattingen, godsdienstige overtuiging, criminele achtergrond, genetische informatie, gezondheidsgegevens, seksuele voorkeur, biometrische informatie en lidmaatschap van een vakbond.

De [belangrijkste wetgevingen](#privacy-regulations) betreffen de verschillende entiteiten die gegevens als volgt beheren:
* Een **gegevenscontroller** is de instantie die de middelen en het doel van het verzamelen, gebruiken en delen van persoonsgegevens bepaalt.
* Een **gegevensprocessor** is een persoon of partij die persoonsgegevens verzamelt, gebruikt of deelt op de manier die door de gegevenscontroller wordt aangegeven.
* Een **betrokkene** is een levende persoon wiens persoonsgegevens worden verzameld, gebruikt of gedeeld en die aan de hand van deze persoonsgegevens direct of indirect kan worden geïdentificeerd.

Als bedrijf dat persoonsgegevens verzamelt en deelt, bent u dus de gegevenscontroller, zijn uw klanten de betrokkenen en fungeert Adobe Campaign als gegevensprocessor bij het verwerken van deze persoonsgegevens op uw aanwijzingen. Als gegevenscontroller bent u verantwoordelijk voor de relatie met de betrokkenen, bijvoorbeeld bij het beheren van [verzoeken om toegang tot persoonsgegevens](#privacy-requests).

Bij de integratie van Campaign met andere Experience Cloud-oplossingen waarbij doelgroepen kunnen worden overgezet van het ene systeem naar het andere zoals [Adobe Analytics](../../integrating/using/about-campaign-analytics-integration.md), [Audience Manager of de People-kernservice](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md), of met andere oplossingen zoals [Microsoft Dynamics 365](../../integrating/using/d365-acs-get-started.md), moet u extra aandacht besteden aan de bescherming van persoonsgegevens.

## Gegevensacquisitie {#data-acquisition}

Met Adobe Campaign kunt u gegevens verzamelen, waaronder persoonlijke en gevoelige informatie. Het is daarom van essentieel belang dat u de toestemming van uw ontvangers ontvangt en controleert.

* Zorg ervoor dat ontvangers altijd toestemming geven voor het ontvangen van communicatie. Daarvoor moet u opt-outverzoeken altijd zo snel mogelijk verwerken en moet u toestemming controleren via een dubbele opt-inprocedure. Zie [Opt-in en opt-out beheren in Campaign](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md) en [Een dubbele opt-inprocedure instellen](../../channels/using/setting-up-a-double-opt-in-process.md) voor meer informatie.
* Importeer geen frauduleuze lijsten en gebruik traps om te controleren of uw clientbestand niet onrechtmatig wordt gebruikt. Zie [Traps gebruiken](../../sending/using/using-traps.md) voor meer informatie.
* Via toestemmings- en rechtenbeheer kunt u de voorkeuren van uw ontvangers bijhouden en beheren wie binnen uw organisatie toegang heeft tot welke gegevens. Zie [deze sectie](#consent)voor meer informatie.
* Faciliteer en beheer de verzoeken om toegang tot persoonsgegevens van uw ontvangers. Zie [deze sectie](#privacy-requests)voor meer informatie.

## Privacybeheer {#privacy-management}

Privacybeheer verwijst naar alle processen en tools die u kunnen helpen te voldoen aan de privacywetgeving (AVG, CCPA, enz.). Bekijk een overzicht van privacybeheer op [deze pagina](../../start/using/privacy-management.md#privacy-management-regulations).

Adobe Campaign biedt u verschillende functiesets voor privacybeheer:
* toestemmingsbeheer, dataretentie en gebruikersrollen. Zie [deze sectie](#consent).
* Verzoeken om toegang tot persoonsgegevens (toegangsrecht en recht om te worden vergeten). Zie [deze sectie](#privacy-requests).
* Opt-out voor de verkoop van persoonsgegevens (CCPA-specifiek). Zie [deze sectie](../../start/using/privacy-requests.md#sale-of-personal-information-ccpa).

De belangrijkste privacymogelijkheden in Campaign en een voorbeeld van de betrokken persona’s worden weergegeven in [deze sectie](#personal-data).


### Toestemming, retentie en rollen {#consent}

Oorspronkelijk biedt Adobe Campaign belangrijke functies die essentieel zijn voor privacy:

* **Toestemmingsbeheer**: via de procedure van abonnementsbeheer kunt u de voorkeuren van uw ontvangers beheren en bijhouden welke ontvangers zich hebben aangemeld voor welke soorten abonnementen. Zie [Abonnementen](../../audiences/using/about-subscriptions.md) en [Landingspagina’s](../../channels/using/getting-started-with-landing-pages.md) voor meer informatie.
* **Dataretentie**: alle ingebouwde standaard logtabellen bevatten vooraf ingestelde retentieperioden, waarbij de gegevensopslag over het algemeen is beperkt tot 6 maanden of korter. Er kunnen extra retentieperioden worden ingesteld met workflows. Neem hiervoor contact op met de adviseurs van Adobe of met technische beheerders.
* **Rights Management**: Adobe Campaign biedt u de mogelijkheid om via verschillende standaard of aangepaste rollen de rechten te beheren die aan de verschillende Campaign-operators zijn toegewezen. Hierdoor kunt u bepalen wie binnen uw bedrijf toegang heeft tot verschillende typen gegevens en deze kan wijzigen of exporteren. Zie [Toegangscontrole](../../administration/using/about-access-management.md) voor meer informatie.

Zie [deze pagina](../../start/using/privacy-management.md#consent-retention-roles) voor meer informatie over deze functies en hoe u ze kunt beheren in Adobe Campaign.

### Privacyverzoeken {#privacy-requests}

Adobe Campaign biedt extra mogelijkheden om uw taak als gegevenscontroller voor bepaalde verzoeken om toegang tot persoonsgegevens te vergemakkelijken:

* Het **toegangsrecht** is het recht van de betrokkene om van de gegevenscontroller bevestiging te krijgen of er persoonsgegevens van de betrokkene worden verwerkt, waar en voor welk doel.

* Het **recht om te worden vergeten** (verwijderingsverzoek) geeft de betrokkene het recht om zijn of haar persoonsgegevens door de gegevensbeheerder te laten wissen.

>[!NOTE]
>
>Deze reeks tools is bedoeld om u te helpen bij uw privacynaleving voor de AVG, CCPA, en PDPA. Zie [deze pagina](../../start/using/privacy-management.md#privacy-management-regulations) voor meer informatie over deze verschillende verordeningen.

Verzoeken om **toegang** en **verwijdering** worden weergegeven op [deze pagina](../../start/using/privacy-management.md#right-access-forgotten). De implementatiestappen voor het maken van deze verzoeken worden uiteengezet op [deze pagina](../../start/using/privacy-requests.md#about-privacy-requests). [Hier](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/privacy/privacy-overview.html?lang=nl) zijn ook tutorials beschikbaar.

## Trackingmogelijkheden {#tracking-capabilities}

Dankzij de trackingfunctionaliteiten kunt u met Adobe Campaign het gedrag van de ontvangers van uw bezorging volgen met behulp van sessiecookies en permanente cookies. Zie [deze pagina](../../sending/using/tracking-messages.md) voor meer informatie over tracking.

>[!NOTE]
>
>In verordeningen zoals de Algemene verordening gegevensbescherming (AVG) wordt bepaald dat bedrijven de toestemming van webgebruikers nodig hebben voordat ze cookies mogen installeren. U moet gebruikers via een autorisatieverzoek laten weten dat uw sites webtraceringsprogramma&#39;s bevatten.

U kunt ook [getraceerde koppelingen](../../designing/using/links.md#about-tracked-urls) in uw berichten toevoegen om de invloed van uw levering en het gedrag van ontvangers te meten in het ingebouwde rapport [Trackingsindicatoren](../../reporting/using/tracking-indicators.md), of zelf [speciale rapporten](../../reporting/using/about-dynamic-reports.md) maken.
