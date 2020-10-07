---
title: Privacy en toestemming in Adobe Campaign Standard
description: In dit gedeelte wordt een overzicht gegeven van privacy, persoonsgegevens en toestemmingsbeheer in Adobe Campaign Standard en van de instrumenten die beschikbaar zijn om deze te verwerken.
page-status-flag: never-activated
uuid: ed9e631c-5ad1-49f1-be1e-b710bc64dc91
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: discovering-the-interface
discoiquuid: 5227ca05-3856-4e54-aec6-14444d6534e3
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '1479'
ht-degree: 3%

---


# Privacy and Consent{#privacy-and-consent}

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
>Zie [deze pagina](https://helpx.adobe.com/nl/campaign/kb/campaign-privacy-overview.html#whatisgdpr)voor meer informatie over hoe GDPR, CCPA en PDPA van toepassing zijn op Adobe Campaign.

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

De [belangrijkste wetgeving](#privacy-regulations) heeft als volgt betrekking op de verschillende entiteiten die gegevens beheren:
* Een **gegevenscontroller** is de instantie die de middelen en het doel van het verzamelen, gebruiken en delen van persoonsgegevens bepaalt.
* Een **gegevensprocessor** is een persoon of partij die persoonlijke gegevens verzamelt, gebruikt of deelt op de wijze die door de gegevenscontroller wordt aangegeven.
* Een **betrokkene** is een levende persoon wiens persoonsgegevens worden verzameld, gebruikt of gedeeld en die direct of indirect kan worden geïdentificeerd aan de hand van die persoonsgegevens.

Als bedrijf dat persoonlijke gegevens verzamelt en deelt, bent u dus de Data Controller, zijn uw klanten de Data Subjects en Adobe Campaign fungeert als een Data Processor bij het verwerken van hun persoonlijke gegevens op de door u aangegeven wijze. Merk op dat het uw verantwoordelijkheid als Controlemechanisme van Gegevens is om de verhouding met de Onderwerpen van Gegevens te behandelen zoals wanneer het beheren van [privacyverzoeken](#privacy-requests).

Wanneer het integreren van Campagne met andere oplossingen van Experience Cloud waar het publiek van één systeem aan een andere, zoals de dienst [van de Doelen van het](../../audiences/using/aep-about-audience-destinations-service.md)Publiek, [Adobe Analytics](../../integrating/using/about-campaign-analytics-integration.md), de [Audience Manager of de kerndienst](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md)van het Mensen, of met andere oplossingen zoals de Dynamica 365 [van](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md)Microsoft kan worden overgebracht, moet u extra zorg aan persoonlijke gegevensbescherming betalen.

## Gegevensverwerving {#data-acquisition}

Met Adobe Campaign kunt u gegevens verzamelen, waaronder persoonlijke en vertrouwelijke informatie. Het is daarom van essentieel belang dat u de toestemming van uw ontvangers ontvangt en controleert.

* Heb altijd ontvangers overeenkomen om mededelingen te ontvangen. Om dit te doen, moet u zo snel mogelijk aan de &quot;opt-out&quot;-verzoeken blijven voldoen en moet u de toestemming controleren via een &quot;double opt-in&quot;-proces. Zie Optie- en [opt-out beheren in Campagne](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md) en een dubbel opt-in-proces [](../../channels/using/setting-up-a-double-opt-in-process.md)instellen voor meer informatie hierover.
* Importeer geen frauduleuze lijsten en gebruik geen overvullingen om te controleren of uw clientbestand niet frauduleus wordt gebruikt. Zie [Overvullen](../../sending/using/using-traps.md)gebruiken voor meer informatie.
* Via toestemmings- en rechtenbeheer kunt u de voorkeuren van uw ontvangers bijhouden en beheren wie binnen uw organisatie toegang heeft tot welke gegevens. Zie [deze sectie](#consent)voor meer informatie.
* De privacyverzoeken van uw ontvangers faciliteren en beheren. Zie [deze sectie](#privacy-requests)voor meer informatie.

## Privacybeheer {#privacy-management}

Het beheer van de privacy verwijst naar alle processen en hulpmiddelen die u kunnen helpen aan de verordeningen van de Privacy (GDPR, CCPA, enz.) voldoen. Bekijk een overzicht van het privacybeheer op [deze pagina](https://helpx.adobe.com/nl/campaign/kb/campaign-privacy-overview.html).

Adobe Campaign biedt u verschillende functies voor privacybeheer:
* Goedkeuringsbeheer, gegevensbewaring en gebruikersrollen. Zie [deze sectie](#consent).
* Privacyverzoeken (recht op toegang en recht om te worden vergeten). Zie [deze sectie](#privacy-requests).
* Opt-out voor de Verkoop van Persoonlijke Informatie (specifiek CCPA). Zie [deze sectie](https://helpx.adobe.com/campaign/kb/acs-privacy.html#ccpa).

De belangrijkste mogelijkheden van de Privacy in Campagne en een voorbeeld van de betrokken personen worden voorgesteld in [deze sectie](https://helpx.adobe.com/campaign/kb/campaign-privacy-more.html#gdprpersonasandflow).


### Toestemming, bewaring en rollen {#consent}

Oorspronkelijk biedt Adobe Campaign belangrijke functies die essentieel zijn voor privacy:

* **Toegangsbeheer**: Via het abonnementsbeheerproces kunt u de voorkeuren van uw ontvangers beheren en bijhouden welke ontvangers hebben gekozen voor welk type abonnement. Zie [Abonnementen](../../audiences/using/about-subscriptions.md) en pagina&#39;s [Landing voor meer informatie](../../channels/using/getting-started-with-landing-pages.md).
* **Bewaren** van gegevens: Alle ingebouwde standaardlogtabellen hebben vooraf ingestelde retentieperioden, waarbij de gegevensopslag doorgaans tot 6 maanden of minder wordt beperkt. Er kunnen extra retentieperiodes worden ingesteld met workflows. Neem hiervoor contact op met de consultants van de Adobe of met technische beheerders.
* **Rechtenbeheer**: Adobe Campaign biedt u de mogelijkheid om de rechten te beheren die aan de verschillende campagneoperatoren zijn toegewezen via verschillende vooraf gebouwde of aangepaste rollen. Hierdoor kunt u bepalen wie binnen uw bedrijf toegang heeft tot verschillende typen gegevens, deze kan wijzigen of exporteren. Zie [Informatie over toegangsbeheer](../../administration/using/about-access-management.md)voor meer informatie hierover.

Zie [deze pagina](https://helpx.adobe.com/campaign/kb/campaign-privacy-overview.html#consent)voor meer informatie over deze functies en hoe u deze kunt beheren in Adobe Campaign.

### Privacyverzoeken {#privacy-requests}

Adobe Campaign biedt extra mogelijkheden om u te helpen uw bereidheid als Data Controller voor bepaalde privacyverzoeken te vergemakkelijken:

* Het **recht op toegang** is het recht van de betrokkene om van de verantwoordelijke voor de verwerking bevestiging te krijgen dat al dan niet persoonsgegevens worden verwerkt, waar en waarom.

* Het **recht om te worden vergeten** (schrappingsverzoek) geeft de betrokkene het recht om zijn/haar persoonlijke gegevens te laten wissen door de verantwoordelijke voor de verwerking.

>[!NOTE]
>
>Deze reeks hulpmiddelen is hier om u met uw privacynaleving voor GDPR, CCPA, en PDPA te helpen. Zie [deze pagina](https://helpx.adobe.com/nl/campaign/kb/campaign-privacy-overview.html#whatisgdpr)voor meer informatie over deze verschillende verordeningen.

<!--* **GDPR** (General Data Protection Regulation) is the European Union’s (EU) privacy law that harmonizes and modernizes data protection requirements. GDPR applies to Adobe Campaign customers who hold data for Data Subjects residing in the EU.

* **CCPA** (California Consumer Privacy Act) provides California residents new rights in regards to their personal information and imposes data protection responsibilities on certain entities whom conduct business in California.

* **Thailand's PDPA** (Personal Data Protection Act) is the new privacy law that harmonizes and modernizes data protection requirements for Thailand. This regulation applies to Adobe Campaign customers who hold data for Data Subjects residing in this country.-->

De **verzoeken om toegang** en **om verwijderen** worden weergegeven op [deze pagina](https://helpx.adobe.com/campaign/kb/acs-privacy.html#righttoaccess). De implementatiestappen voor het maken van deze aanvragen worden gedetailleerd weergegeven op [deze pagina](https://helpx.adobe.com/nl/campaign/kb/acs-privacy.html#ManagingPrivacyRequests). Tutorials zijn ook [hier](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/privacy/privacy-overview.html)beschikbaar.

## Traceermogelijkheden {#tracking-capabilities}

Dankzij de trackingfuncties van Adobe Campaign kunt u het gedrag van de ontvangers bijhouden met sessiecookies en permanente cookies. For more on tracking, see [this page](../../sending/using/tracking-messages.md).

>[!NOTE]
>
>In verordeningen zoals de algemene gegevensbeschermingsverordening (GDPR) wordt bepaald dat bedrijven de toestemming van webgebruikers eisen voordat ze cookies installeren. U moet gebruikers via een vergunningsaanvraag laten weten dat uw sites zijn uitgerust met webtraceringsprogramma&#39;s.

U kunt ook [bijgehouden koppelingen](../../designing/using/links.md#about-tracked-urls) in uw berichten toevoegen om de impact van uw levering en het gedrag van de ontvanger in het ingebouwde rapport van ingebouwde [volgindicatoren](../../reporting/using/tracking-indicators.md) te meten, of uw eigen [specifieke rapporten](../../reporting/using/about-dynamic-reports.md)creëren.
