---
title: Privacybeheer in Adobe Campaign Standard
description: Ontdek meer over de Adobe Campaign Standard-functies voor het beheer van privacy.
audience: start
content-type: reference
topic-tags: discovering-the-interface
feature: Privacy
role: User
level: Intermediate
exl-id: 84cf8f6e-9ba0-4cd5-80e2-a61cefa31e0a
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '825'
ht-degree: 99%

---

# Privacybeheer {#privacy-management}

Adobe Campaign biedt een reeks tools om u te helpen voldoen aan de [privacyverordeningen](#privacy-management-regulations) (zoals AVG, CCPA, PDPA, LGPD).

Hier volgen de vijf voornaamste mogelijkheden die Adobe Campaign biedt om u gereed te maken voor de AVG en andere privacyregels:

![](assets/privacy-gdpr-use-cases.png)

* **Recht op toegang**

* **Recht op verwijdering**

Zie [Recht op toegang en recht om te worden vergeten](#right-access-forgotten) voor meer informatie.

* **Toestemmingsbeheer**

* **Dataretentie**

* **Rights Management**

Zie [Toestemming, retentie en rollen](#consent-retention-roles) voor meer informatie.

<!--This section presents general information on what Privacy management is and the features provided by Adobe Campaign to manage the [Right to Access and Right to be Forgotten](#right-access-forgotten).

It also contains information on important features to manage Privacy ([consent, data retention and user roles](#consent-retention-roles)), as well as best practices to help you with your Privacy compliance when using Adobe Campaign.-->

## Wetgeving voor privacybeheer {#privacy-management-regulations}

Met de opties van Adobe Campaign kunt u voldoen aan de volgende regels:

* **De AVG** ([Algemene Verordening Gegevensbescherming](https://ec.europa.eu/info/law/law-topic/data-protection/reform/what-does-general-data-protection-regulation-gdpr-govern_en)) is de privacyverordening van de Europese Unie (EU) die de vereisten inzake gegevensbescherming voor Europese landen harmoniseert en moderniseert. Volg de onderstaande koppelingen voor algemene informatie over de AVG:

   * https://www.adobe.com/nl/privacy/general-data-protection-regulation.html
   * https://www.adobe.com/marketing-cloud/campaign/general-data-protection-regulation.html

* **De CCPA** ([California Consumer Privacy Act](https://leginfo.legislature.ca.gov/faces/codes_displayText.xhtml?lawCode=CIV&amp;division=3.&amp;title=1.81.5.&amp;part=4.&amp;chapter=&amp;article=)) biedt inwoners van Californië nieuwe rechten met betrekking tot hun persoonsgegevens en legt verantwoordelijkheden op het gebied van gegevensbescherming op aan bepaalde entiteiten die zaken doen in Californië.
* **De PDPA** ([Thaise wet inzake de bescherming van persoonsgegevens](https://secureprivacy.ai/thailand-pdpa-summary-what-businesses-need-to-know/)) is de nieuwe privacywet die de vereisten inzake gegevensbescherming voor Thailand harmoniseert en moderniseert.
* **De LGPD** ([Lei Geral de Proteção de Dados](https://iapp.org/media/pdf/resource_center/Brazilian_General_Data_Protection_Law.pdf)) wordt begin 2021 van kracht voor alle bedrijven die in Brazilië persoonsgegevens verzamelen of verwerken.

Al deze voorschriften zijn van toepassing op Adobe Campaign-klanten die beschikken over gegevens van betrokkenen die in de bovengenoemde regio’s of landen wonen (EU, Californië, Thailand en Brazilië).

>[!NOTE]
>
>Voor meer informatie over persoonsgegevens en over de verschillende entiteiten die gegevens beheren (gegevenscontroller, gegevensprocessor en betrokkene) raadpleegt u [Persoonsgegevens en persona&#39;s](../../start/using/privacy.md#personal-data).

## Toegangsrecht en recht om te worden vergeten {#right-access-forgotten}

U kunt in Adobe Campaign verzoeken voor **Toegang** en **Verwijderen** afhandelen, zodat u zich gemakkelijker kunt voorbereiden op de privacyregels.

* Het **toegangsrecht** is het recht van de betrokkene om van de gegevenscontroller bevestiging te krijgen of er persoonsgegevens van de betrokkene worden verwerkt, waar en voor welk doel. De gegevenscontroller verstrekt kosteloos een kopie van de persoonsgegevens in elektronische vorm.

* Het **recht om te worden vergeten** (verwijderingsverzoek) geeft de betrokkene het recht om de gegevensbeheerder zijn of haar persoonsgegevens te laten wissen, de verdere verspreiding van de gegevens stop te zetten en eventueel de verwerking van de gegevens door derden te laten stopzetten.

Raadpleeg de [implementatiestappen](../../start/using/privacy-requests.md#about-privacy-requests) om te leren hoe u **toegangs**- en **verwijderings** verzoeken kunt maken en hoe Adobe Campaign ze verwerkt.

Tutorials over privacybeheer in Campaign Standard zijn ook [hier](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/privacy/privacy-overview.html#privacy) te vinden.

>[!NOTE]
>
>Voor meer informatie over persoonsgegevens en over de verschillende entiteiten die gegevens beheren (gegevenscontroller, gegevensprocessor en betrokkene) raadpleegt u [Persoonsgegevens en persona&#39;s](../../start/using/privacy.md#personal-data).

## Toestemming, retentie en rollen {#consent-retention-roles}

Naast de meest recente mogelijkheden voor **toegangsrecht** en **recht om te worden vergeten** biedt Adobe Campaign andere belangrijke functies die essentieel zijn voor privacy:

* [Toestemmingsbeheer](#consent-management): abonnementsfuncties voor voorkeurenbeheer
* [Dataretentie](../../administration/using/data-retention.md): dataretentieperioden in alle standaard logtabellen, er kunnen extra retentieperioden worden ingesteld met workflows
* [Rights Management](#rights-management): gegevenstoegang beheerd volgens opgegeven recht

### Toestemmingsbeheer {#consent-management}

Toestemming betekent instemming van een betrokkene om de persoonsgegevens betreffende de betrokkene te verwerken. De gegevenscontroller is verantwoordelijk voor het verkrijgen van de vereiste toestemming voor deze verwerking. Hoewel Adobe Campaign bepaalde functies kan bieden om een klant te helpen bij het beheren van de toestemming voor de service, is Adobe niet verantwoordelijk voor de toestemming. Klanten dienen samen met hun eigen juridische afdelingen hun eigen processen en praktijken vast te stellen voor de benodigde toestemming.

Vanaf het begin hebben in Adobe Campaign functies voor het helpen beheren van bepaalde aspecten van toestemming centraal gestaan. Via het abonnementsbeheerproces kunnen klanten bijhouden welke ontvangers hebben gekozen voor welk type abonnement, zoals nieuwsbrieven, dagelijkse of wekelijkse aanbiedingen of een ander type marketingprogramma.

![](assets/privacy-consent-management.png)

Zie [Abonnementen](../../audiences/using/about-subscriptions.md) en [Aan de slag met landingspagina’s ](../../channels/using/getting-started-with-landing-pages.md) voor meer informatie over toestemmingsbeheer.

Naast de tools voor toestemmingsbeheer van Adobe Campaign kunt u ook nagaan of een consument ervoor heeft gekozen om zich af te melden voor de verkoop van persoonsgegevens. Zie [deze sectie](../../start/using/privacy-requests.md#sale-of-personal-information-ccpa).

### Rights Management {#rights-management}

Adobe Campaign biedt u de mogelijkheid om via verschillende standaard of aangepaste rollen de rechten te beheren die aan de verschillende Campaign-operators zijn toegewezen.

Eén voordeel is dat u zo kunt bepalen wie binnen uw bedrijf toegang heeft tot verschillende typen gegevens. Als u bijvoorbeeld verschillende marketeers voor verschillende regio’s hebt, kunt u ervoor zorgen dat elke marketeer alleen toegang heeft tot de gegevens van zijn of haar regio.

Zo kunt u met deze functionaliteit ook verschillende mogelijkheden voor elke gebruiker configureren, zoals beperken wie leveringen kan verzenden, of relevanter voor privacy: wie gegevens kan wijzigen of exporteren.

![](assets/privacy-user-management.png)

Zie [deze sectie](../../administration/using/about-access-management.md) voor meer informatie over toegangscontrole.
