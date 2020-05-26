---
title: Lijsten aanpassen
description: '"Leer hoe u de weergave kunt aanpassen en kunt werken op lijstschermen in Adobe Campagne Standard:elementen sorteren, filteren, verwijderen of dupliceren. De schermen van lijsten tonen elementen van één of verscheidene bepaalde middelen."'
page-status-flag: never-activated
uuid: 3350583c-91ca-4ea5-ac14-6b6f11c4a64a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: discovering-the-interface
discoiquuid: 4ba4f766-fdee-4ff0-8fe4-0612ed2b69a4
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 44d6126023e9411477ccd7ffc07ecde806e7976d
workflow-type: tm+mt
source-wordcount: '793'
ht-degree: 0%

---


# Werken met profielen en soorten publiek

<table>
<tr>
    <td valign="top">
        <a href="../../start/using/work-with-audiences.md"><img width="60px" alt="voorwaarden" src="assets/icon_profile.svg"/></a>
    </td>
    <td valign="top">
        <a href="../../api/using/creating-a-service.md"><img width="60px" alt="voorwaarden" src="assets/icon_profile.svg"/></a>
    </td>
    <td valign="top">
        <a href="../../api/using/interacting-with-custom-resources.md"><img width="60px" alt="voorwaarden" src="assets/icon_profile.svg"/></a>
    </td>
    <td valign="top">
        <a href="../../api/using/interacting-with-marketing-history.md"><img width="60px" alt="voorwaarden" src="assets/icon_profile.svg"/></a>
    </td>
</tr>
<tr>
<td>Klantprofielen</td>
<td>De database verrijken</td>
<td>Uw publiek organiseren</td>
<td>Privacybeheer</td>
</tr>
</table>

## Klantprofielen {#customer-profiles}

<img width="60px" alt="voorwaarden" src="assets/icon_profile.svg"/>

Adobe Campagneprofielen vertegenwoordigen alle contactpersonen die in de database zijn opgeslagen. Elk profiel komt overeen met één item in de database dat de nodige informatie bevat om dat profiel als doel, gekwalificeerd en afzonderlijk te kunnen traceren. Dit betekent dat een profiel: een cliënt, een vooruitzicht, een individu aan een nieuwsbrief, een ontvanger, een gebruiker, of een andere denominatie die afhankelijk van de organisatie wordt ingetekend.

**Meer informatie**

* [Profielen](../../audiences/using/about-profiles.md)
* [Het aantal actieve profielen in uw organisatie openen](../../audiences/using/active-profiles.md)

## De database verrijken {#populating-database}

<img width="60px" alt="voorwaarden" src="assets/icon_populate.svg"/>

De Standaard van de campagne biedt verscheidene hulpmiddelen aan om u te helpen uw marketing gegevensbestand kweken. In deze sectie worden de verschillende methoden beschreven die u kunt gebruiken om gegevens in campagne te injecteren, met verwijzingen naar de desbetreffende documenten.

### Gegevens importeren via workflows {#importing-data-through-workflows}

Met workflows kunt u gegevens verzamelen en importeren in de Campagne-database via het gebruik van [**[!UICONTROL Data management]**](../../automating/using/about-data-management-activities.md) activiteiten. Algemene informatie en aanbevolen procedures bij het importeren van gegevens via workflows worden in [deze sectie](../../automating/using/about-data-import-and-export.md)weergegeven.

Daarnaast kunt u sjablonen instellen voor het importeren van gegevens. Het gebruik van importsjablonen is de beste manier als u regelmatig bestanden met dezelfde structuur moet importeren. U kunt twee typen sjablonen instellen:

* **Workflowsjablonen**: Dit zijn vooraf geconfigureerde workflows die u één keer kunt instellen op basis van uw behoeften en die u telkens opnieuw kunt gebruiken wanneer u gegevens wilt importeren en de database wilt bijwerken. In [deze sectie](../../automating/using/creating-import-workflow-templates.md)wordt een voorbeeld van een werkstroomsjabloon voor het importeren van gegevens beschreven.

* **Gegevenssjablonen** importeren: dit zijn, net als workflowsjablonen, sjablonen die zijn gebaseerd op workflows, die zijn ingesteld om bestanden te uploaden om de database bij te werken. Zodra gevormd, worden zij ter beschikking gesteld aan gebruikers met een vereenvoudigde mening onder **[!UICONTROL Profile & audiences]** / **[!UICONTROL Imports]** menu. Raadpleeg de [desbetreffende documentatie](../../automating/using/importing-data-with-import-templates.md)voor meer informatie over sjablonen voor importgegevens.

### Gegevens van bestemmingspagina&#39;s verzamelen {#collecting-data-from-landing-pages}

Openingspagina&#39;s zijn webformulieren die kunnen worden gebruikt om gegevens te verzamelen en bestaande gegevens in uw database te maken of bij te werken. Het beginsel is als volgt:

* Maak en ontwerp de openingspagina door invoervelden toe te voegen voor het verzamelen van gegevens (voornaam, achternaam, e-mail, enz.).
* Wijs elk invoerveld toe aan het corresponderende veld in de database.
* Maak de openingspagina online beschikbaar via een website of via een directe koppeling naar een bericht.

Raadpleeg de [desbetreffende documentatie](../../channels/using/getting-started-with-landing-pages.md)voor meer informatie over bestemmingspagina&#39;s.

**Meer informatie**

* xxxx
* xxxx

### Profielen synchroniseren vanuit Microsoft Dynamics 365

De standaardintegratie van de campagne met de Dynamica 365 van Microsoft staat u toe om contactgegevens van de Dynamica 365 van Microsoft tot het gegevensbestand van de Campagne over te gaan.
Deze contacten zijn dan zichtbaar in de lijst van Profielen en kunnen in marketing campagnes worden gericht. Raadpleeg de [desbetreffende documentatie](https://helpx.adobe.com/campaign/kb/acs-ms-dynamics.html)voor meer informatie over deze integratie.

>[!NOTE]
>
>Houd er rekening mee dat de connector Standaard-Microsoft Dynamics 365 voor Campagne momenteel in Beperkte Beschikbaarheid is en dat er verschillende beperkingen op van toepassing zijn, die in de documentatie worden beschreven.

**Meer informatie**

* xxxx
* xxxx

### Gegevens importeren via API-aanroepen

Met API&#39;s van de campagnestandaard kunt u bewerkingen uitvoeren om de database bij te werken, zoals het maken, bijwerken of verwijderen van profielen of services. Raadpleeg de [specifieke documentatie](../../api/using/get-started-apis.md)voor meer informatie over het gebruik van de API&#39;s.

>[!CAUTION]
>
>Controleer voordat u profielen massaal maakt of bijwerkt via API-aanroepen de schaalbeperkingen die overeenkomen met uw licentieovereenkomst. For more on this, refer to
[this page](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers).

**Meer informatie**

* xxxx
* xxxx

## Uw publiek organiseren {#organizing-audiences}

<img width="60px" alt="voorwaarden" src="assets/icon_audience.svg"/>

Om u in staat te stellen relevante en efficiënte berichten te leveren en uw klanten effectief te betrekken, integreert de Campagne van Adobe geavanceerde analyse en gerichte functionaliteit.

Dankzij de workflows en de query-editor kunt u een publiek maken dat de verschillende campagnes als doelgroep hebben, afhankelijk van de informatie die u over de campagnes hebt, hun activiteiten, hun taal, voorkeuren of hun marketinggeschiedenis. Zo kunt u bijvoorbeeld geabonneerde profielen filteren of doelsoorten maken op een onbeperkt aantal criteria.

**Meer informatie**

* [Informatie over publiek](../../audiences/using/about-audiences.md)
* [Soorten publiek maken](../../audiences/using/creating-audiences.md)

## Privacybeheer {#privacy-management}

<img width="60px" alt="voorwaarden" src="assets/icon_privacy.svg"/>

GDPR is de nieuwe privacywet van de Europese Unie (EU) die de vereisten inzake gegevensbescherming harmoniseert en moderniseert. GDPR is van toepassing op klanten van de Campagne van Adobe die gegevens voor de Onderwerpen van Gegevens in de EU houden. Naast de privacymogelijkheden die al beschikbaar zijn in Adobe Campaign (waaronder beheer van toestemming, instellingen voor gegevensbewaring en gebruikersrollen), maken we van deze gelegenheid gebruik in onze rol als gegevensprocessor om extra mogelijkheden op te nemen, zodat u gemakkelijker klaar bent als Data Controller voor bepaalde GDPR-verzoeken.

Raadpleeg deze [handleiding](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_GDPR.html) voor meer informatie over de gereedschappen en functies die Adobe Campaign biedt om u te helpen aan de GDPR-standaard te voldoen.

**Meer informatie**

* xxxx
* xxxx