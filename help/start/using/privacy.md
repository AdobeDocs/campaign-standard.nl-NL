---
solution: Campaign Standard
product: campaign
title: Privacy en instemming
description: Meer informatie over privacy, persoonsgegevens en toestemmingsbeheer in Adobe Campaign Standard
audience: start
content-type: reference
topic-tags: discovering-the-interface
translation-type: tm+mt
source-git-commit: c76f4b6e3bc0feb50e5776836552fdceaff61ea7
workflow-type: tm+mt
source-wordcount: '1657'
ht-degree: 2%

---


# Privacy and Consent {#privacy-and-consent}

## Algemene aanbevelingen {#general-recommendations}

Adobe Campaign is een krachtig instrument voor het verzamelen en verwerken van zeer grote hoeveelheden gegevens, waaronder persoonlijke informatie en gevoelige gegevens. Daarom moet de privacy zorgvuldig worden beheerd.

* Altijd verantwoordelijk en ethisch gebruik maken van persoonlijke informatie.

* Stuur geen ongewenste e-mail, pushberichten en SMS-berichten (&quot;spam&quot;). Adobe gelooft sterk in de beginselen van toestemmings marketing in het bevorderen van de waarde en loyaliteit van het klantenleven, en verbiedt daarom strikt het gebruik van Adobe Campaign in het verzenden van ongevraagde berichten.

### Privacyregels {#privacy-regulations}

Werken binnen de wetgeving die van toepassing is op de regio(s) waar u actief bent, om de privacy correct te behandelen en persoonsgegevens te beheren. Deze verordeningen omvatten:
* [GDPR](https://ec.europa.eu/info/law/law-topic/data-protection/reform/what-does-general-data-protection-regulation-gdpr-govern_en) (Europese algemene gegevensbeschermingsverordening)
* [DPA](https://www.gov.uk/data-protection) (tenuitvoerlegging door het Verenigd Koninkrijk van de GDPR)
* [Europese richtlijn betreffende privacy en elektronische communicatie](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:02002L0058-20091219)
* [CAN-SPAM Act](https://www.ftc.gov/tips-advice/business-center/guidance/can-spam-act-compliance-guide-business) (Amerikaanse wet tot vaststelling van de regels en vereisten voor commerciële e-mail)
* [CCPA](https://leginfo.legislature.ca.gov/faces/codes_displayText.xhtml?lawCode=CIV&amp;division=3.&amp;titel=1.81.5.&amp;part=4.&amp;hoofdstuk=&amp;artikel=) (California Consumer Privacy Act)
* [PDPA](https://secureprivacy.ai/thailand-pdpa-summary-what-businesses-need-to-know/) (Thailand Personal Data Protection Act)

>[!NOTE]
>
>Zie [deze sectie](../../start/using/privacy-management.md#privacy-management-regulations)voor meer informatie over hoe GDPR, CCPA, PDPA en LGPD van toepassing zijn op Adobe Campaign.

### Adobe Experience Cloud privacy {#experience-cloud-privacy}

Adobe Campaign maakt deel uit van de Adobe Experience Cloud-oplossingen. De manier waarop in Campaign met privacy wordt omgegaan, is in overeenstemming met de algemene Adobe Experience Cloud-beginselen, zoals:

* **Welke informatie wordt verzameld bij gebruik van Adobe Experience Cloud**

   Als bedrijf dat Adobe Experience Cloud-oplossingen gebruikt, kiest u welke gegevens u wilt verzamelen en naar uw Adobe Experience Cloud-account verzenden. Voorbeelden van de soorten informatie die kunnen worden verzameld zijn onder andere webbrowseractiviteiten, IP-adressen, locatiegegevens van mobiele apparaten, succespercentages van campagnes, items die zijn aangeschaft of in een winkelwagentje zijn geplaatst, enz.

   >[!NOTE]
   >
   >Net als voor alle Adobe-producten verzamelt Campagne informatie over gebruikers van apps en websites. Zie het [Adobe-privacybeleid](https://www.adobe.com/privacy/policy.html)voor meer informatie.

* **Hoe Adobe Experience Cloud wordt gebruikt om informatie te verzamelen**

   * Adobe Experience Cloud-oplossingen gebruiken cookies en vergelijkbare technologieën, zoals webbakens (ook wel tags of pixels genoemd), om u in staat te stellen informatie te verzamelen. Zie [deze sectie](#tracking-capabilities)voor meer informatie over cookies en trackingmogelijkheden met Adobe Campaign.
   * U kunt ook Adobe Experience Cloud-technologieën gebruiken in uw mobiele apps. Zie [deze pagina](https://helpx.adobe.com/nl/campaign/kb/acs-mobile.html)voor meer informatie over het verzenden van mobiele leveringen met Campagne.

* **De privacyopties van uw gebruikers met betrekking tot uw gebruik van Adobe Experience Cloud**

   Adobe vraagt u om het privacybeleid van uw klanten te beschrijven:

   * Je privacy-praktijken in verband met Adobe Experience Cloud
   * Hoe gebruikers hun voorkeuren kunnen instellen voor het verzamelen of gebruiken van hun gegevens in verband met Adobe Experience Cloud

   >[!NOTE]
   >
   >Net als voor alle Adobe-producten kunnen Campagnegebruikers weigeren om informatie over hen te delen via apps en websites. Raadpleeg de veelgestelde vragen over [Adobe Experience Cloud-gebruiksgegevens voor meer informatie](https://www.adobe.com/privacy/experience-cloud-usage-info-faq.html).

Zie [deze pagina](https://www.adobe.com/privacy/marketing-cloud.html)voor meer informatie over de Adobe Experience Cloud-privacy.

## Persoonlijke gegevens en personen {#personal-data}

Bij het beheren van Privacy, is het belangrijk om te bepalen welke gegevens met zorg en door wie moeten worden behandeld.
* **Persoonsgegevens** zijn informatie die direct of indirect een levende persoon kan identificeren.
* **Gevoelige persoonsgegevens** zijn gegevens over ras, politieke opvattingen, godsdienstige overtuiging, criminele achtergrond, genetische informatie, gezondheidsgegevens, seksuele voorkeur, biometrische informatie en lidmaatschap van een vakvereniging.

Wanneer het integreren van Campagne met andere oplossingen van Experience Cloud waar het publiek van één systeem aan een andere, zoals de dienst [van de Doelen van het](../../audiences/using/aep-about-audience-destinations-service.md)Publiek, [Adobe Analytics](../../integrating/using/about-campaign-analytics-integration.md), de [Audience Manager of de kerndienst](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md)van het Mensen, of met andere oplossingen zoals de Dynamica 365 [van](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md)Microsoft kan worden overgebracht, moet u extra zorg aan persoonlijke gegevensbescherming betalen.

De [belangrijkste verordeningen](#privacy-regulations) verwijzen naar de verschillende entiteiten die gegevens beheren als volgt:
* Een **gegevenscontroller** is de instantie die de middelen en het doel van het verzamelen, gebruiken en delen van persoonsgegevens bepaalt.
* Een **gegevensprocessor** is een persoon of partij die persoonlijke gegevens verzamelt, gebruikt of deelt op de wijze die door de gegevenscontroller wordt aangegeven.
* Een **betrokkene** is een levende persoon wiens persoonsgegevens worden verzameld, gebruikt of gedeeld en die direct of indirect kan worden geïdentificeerd aan de hand van die persoonsgegevens.

Als bedrijf dat persoonlijke gegevens verzamelt en deelt, bent u dus de Data Controller, zijn uw klanten de Data Subjects en Adobe Campaign fungeert als een Data Processor bij het verwerken van hun persoonlijke gegevens op de door u aangegeven wijze. Merk op dat het uw verantwoordelijkheid als Controlemechanisme van Gegevens is om de verhouding met de Onderwerpen van Gegevens te behandelen zoals wanneer het beheren van [privacyverzoeken](#privacy-requests).

### Hoofdscenario gebruiken {#use-case-scenario}

Om te illustreren hoe de verschillende personen met elkaar communiceren, is dit een voorbeeld van een GDPR-gebruiksgeval op hoog niveau.

In dit voorbeeld is een luchtvaartmaatschappij de klant van Adobe Campaign. Dit bedrijf is de **Data Controller** en alle klanten van het luchtvaartbedrijf zijn **Data Subjects**. Laura is in dit specifieke geval een klant van de luchtvaartmaatschappij.

Hier volgen de verschillende personen die in dit voorbeeld worden gebruikt:

* **Laura** is het **onderwerp** Data. Zij is de ontvanger die berichten van de luchtvaartmaatschappij ontvangt. Laura kan vaak vliegen, maar kan op een gegeven moment besluiten dat ze geen gepersonaliseerde reclame- of marketingberichten van de luchtvaartmaatschappij wil. Ze zal de luchtvaartmaatschappij (op basis van hun proces) vragen haar frequent flyer nummer te verwijderen.

* **Anne** is de **Data Controller** bij de luchtvaartmaatschappij. Ze ontvangt het verzoek van Laura, haalt nuttige id&#39;s op die zijn gevraagd om het onderwerp te identificeren en verzendt het verzoek in Adobe Campaign.

* **Adobe Campaign** is de **Data Processor**.

![](assets/privacy-gdpr-flow.png)

Hier volgt de algemene stroom voor dit geval van gebruik:

1. Het **Gegevenssubject** (Laura) verzendt een GDPR-verzoek naar de **Data Controller**, via e-mail, klantenservice of een webportaal.

1. De **Datacontrole** (Bijlage) duwt het GDPR- verzoek aan Campagne via de interface of het gebruiken van API.

1. Zodra de **Gegevensverwerker** (Adobe Campaign) de informatie ontvangt, neemt het actie op het GDPR- verzoek en verzendt een antwoord of erkenning naar de **Datacontrole** (Bijlage).

1. Het **Controlemechanisme** van Gegevens (Anne) herziet dan de informatie en verzendt het terug naar het **Onderwerp** van Gegevens (Laura).

## Gegevensverwerving {#data-acquisition}

Met Adobe Campaign kunt u gegevens verzamelen, waaronder persoonlijke en vertrouwelijke informatie. Het is daarom van essentieel belang dat u de toestemming van uw ontvangers ontvangt en controleert.

* Heb altijd ontvangers overeenkomen om mededelingen te ontvangen. Om dit te doen, moet u zo snel mogelijk aan de &quot;opt-out&quot;-verzoeken blijven voldoen en moet u de toestemming controleren via een &quot;double opt-in&quot;-proces. Zie Optie- en [opt-out beheren in Campagne](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md) en een dubbel opt-in-proces [](../../channels/using/setting-up-a-double-opt-in-process.md)instellen voor meer informatie hierover.
* Importeer geen frauduleuze lijsten en gebruik geen overvullingen om te controleren of uw clientbestand niet frauduleus wordt gebruikt. Zie [Overvullen](../../sending/using/using-traps.md)gebruiken voor meer informatie.
* Via toestemmings- en rechtenbeheer kunt u de voorkeuren van uw ontvangers bijhouden en beheren wie binnen uw organisatie toegang heeft tot welke gegevens. Zie [deze sectie](#consent)voor meer informatie.
* De privacyverzoeken van uw ontvangers faciliteren en beheren. Zie [deze sectie](#privacy-requests)voor meer informatie.

## Privacybeheer {#privacy-management}

Het beheer van de privacy verwijst naar alle processen en hulpmiddelen die u kunnen helpen aan de verordeningen van de Privacy (GDPR, CCPA, enz.) voldoen. Bekijk een overzicht van het privacybeheer op [deze pagina](../../start/using/privacy-management.md).

Adobe Campaign biedt u verschillende functies voor privacybeheer:
* Goedkeuringsbeheer, gegevensbewaring en gebruikersrollen. Zie [deze sectie](#consent).
* Privacyverzoeken (recht op toegang en recht om te worden vergeten). Zie [deze sectie](#privacy-requests).
* Opt-out voor de Verkoop van Persoonlijke Informatie (specifiek CCPA). Zie [deze sectie](https://helpx.adobe.com/nl/campaign/kb/acs-privacy.html#ccpa).

De belangrijkste mogelijkheden van de Privacy in Campagne en een voorbeeld van de betrokken personen worden voorgesteld in [deze sectie](https://helpx.adobe.com/campaign/kb/campaign-privacy-more.html#gdprpersonasandflow).


### Toestemming, bewaring en rollen {#consent}

Oorspronkelijk biedt Adobe Campaign belangrijke functies die essentieel zijn voor privacy:

* **Toegangsbeheer**: Via het abonnementsbeheerproces kunt u de voorkeuren van uw ontvangers beheren en bijhouden welke ontvangers hebben gekozen voor welk type abonnement. Zie [Abonnementen](../../audiences/using/about-subscriptions.md) en pagina&#39;s [Landing voor meer informatie](../../channels/using/getting-started-with-landing-pages.md).
* **Bewaren** van gegevens: Alle ingebouwde standaardlogtabellen hebben vooraf ingestelde retentieperioden, waarbij de gegevensopslag doorgaans tot 6 maanden of minder wordt beperkt. Er kunnen extra retentieperiodes worden ingesteld met workflows. Neem hiervoor contact op met de consultants van de Adobe of met technische beheerders.
* **Rechtenbeheer**: Adobe Campaign biedt u de mogelijkheid om de rechten te beheren die aan de verschillende campagneoperatoren zijn toegewezen via verschillende vooraf gebouwde of aangepaste rollen. Hierdoor kunt u bepalen wie binnen uw bedrijf toegang heeft tot verschillende typen gegevens, deze kan wijzigen of exporteren. Zie [Informatie over toegangsbeheer](../../administration/using/about-access-management.md)voor meer informatie hierover.

Zie [deze sectie](../../start/using/privacy-management.md#consent-retention-roles)voor meer informatie over deze functies en hoe u ze in Adobe Campaign kunt beheren.

### Privacyverzoeken {#privacy-requests}

Adobe Campaign biedt extra mogelijkheden om u te helpen uw bereidheid als Data Controller voor bepaalde privacyverzoeken te vergemakkelijken:

* Het **recht op toegang** is het recht van de betrokkene om van de verantwoordelijke voor de verwerking bevestiging te krijgen dat al dan niet persoonsgegevens worden verwerkt, waar en waarom.

* Het **recht om te worden vergeten** (schrappingsverzoek) geeft de betrokkene het recht om zijn/haar persoonlijke gegevens te laten wissen door de verantwoordelijke voor de verwerking.

De verzoeken **om toegang** en **schrapping** worden voorgesteld in [deze sectie](../../start/using/privacy-management.md#right-access-forgotten).

De implementatiestappen voor het maken van deze aanvragen worden in [deze sectie](../../start/using/privacy-requests.md)beschreven. Tutorials zijn ook [hier](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/privacy/privacy-overview.html)beschikbaar.

## Traceermogelijkheden {#tracking-capabilities}

Dankzij de trackingfuncties van Adobe Campaign kunt u het gedrag van de ontvangers bijhouden met sessiecookies en permanente cookies. For more on tracking, see [this section](../../sending/using/tracking-messages.md).

>[!NOTE]
>
>In verordeningen zoals de algemene gegevensbeschermingsverordening (GDPR) wordt bepaald dat bedrijven de toestemming van webgebruikers eisen voordat ze cookies installeren. U moet gebruikers via een vergunningsaanvraag laten weten dat uw sites zijn uitgerust met webtraceringsprogramma&#39;s.

U kunt ook [bijgehouden koppelingen](../../designing/using/links.md#about-tracked-urls) in uw berichten toevoegen om de impact van uw levering en het gedrag van de ontvanger in het ingebouwde rapport van ingebouwde [volgindicatoren](../../reporting/using/tracking-indicators.md) te meten, of uw eigen [specifieke rapporten](../../reporting/using/about-dynamic-reports.md)creëren.
