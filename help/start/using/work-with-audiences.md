---
title: Lijsten aanpassen
description: '"Leer hoe u de weergave kunt aanpassen en hoe u kunt werken op lijstschermen in Adobe Campaign Standard:elementen sorteren, filteren, verwijderen of dupliceren. De schermen van lijsten tonen elementen van één of verscheidene bepaalde middelen."'
audience: start
content-type: reference
topic-tags: discovering-the-interface
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '788'
ht-degree: 9%

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

Adobe Campaign-profielen vertegenwoordigen alle contactpersonen die in de database zijn opgeslagen. Elk profiel komt overeen met één item in de database dat de nodige informatie bevat om dat profiel als doel, gekwalificeerd en afzonderlijk te kunnen traceren. Dit betekent dat een profiel: een cliënt, een vooruitzicht, een individu aan een nieuwsbrief, een ontvanger, een gebruiker, of een andere denominatie die afhankelijk van de organisatie wordt ingetekend.

**Meer informatie**

* [Over profielen](../../audiences/using/about-profiles.md)
* [Het aantal actieve profielen in uw organisatie openen](../../audiences/using/active-profiles.md)

## De database verrijken {#populating-database}

<img width="60px" alt="voorwaarden" src="assets/icon_populate.svg"/>

Campaign Standard biedt verschillende hulpmiddelen aan om u te helpen uw marketing gegevensbestand kweken. In deze sectie worden de verschillende methoden beschreven die u kunt gebruiken om gegevens in campagne te injecteren, met verwijzingen naar de desbetreffende documenten.

### Gegevens importeren via workflows {#importing-data-through-workflows}

Met workflows kunt u gegevens verzamelen en importeren in de Campagne-database via [**[!UICONTROL Data management]**](../../automating/using/about-data-management-activities.md)-activiteiten. Algemene informatie en beste praktijken wanneer het invoeren van gegevens door werkschema&#39;s worden voorgesteld in [deze sectie](../../automating/using/about-data-import-and-export.md).

Daarnaast kunt u sjablonen instellen voor het importeren van gegevens. Het gebruik van importsjablonen is de beste manier als u regelmatig bestanden met dezelfde structuur moet importeren. U kunt twee typen sjablonen instellen:

* **Workflowsjablonen**: Dit zijn vooraf geconfigureerde workflows die u één keer kunt instellen op basis van uw behoeften en die u telkens opnieuw kunt gebruiken wanneer u gegevens wilt importeren en de database wilt bijwerken. Een voorbeeld van een werkstroomsjabloon voor het importeren van gegevens vindt u in [deze sectie](../../automating/using/creating-import-workflow-templates.md).

* **Gegevenssjablonen** importeren: dit zijn, net als workflowsjablonen, sjablonen die zijn gebaseerd op workflows, die zijn ingesteld om bestanden te uploaden om de database bij te werken. Zodra gevormd, worden zij ter beschikking gesteld aan gebruikers met een vereenvoudigde mening onder **[!UICONTROL Profile & audiences]** / **[!UICONTROL Imports]** menu. Raadpleeg de [specifieke documentatie](../../automating/using/importing-data-with-import-templates.md) voor meer informatie over sjablonen voor importgegevens.

### Gegevens van bestemmingspagina&#39;s verzamelen {#collecting-data-from-landing-pages}

Openingspagina&#39;s zijn webformulieren die kunnen worden gebruikt om gegevens te verzamelen en bestaande gegevens in uw database te maken of bij te werken. Het beginsel is als volgt:

* Maak en ontwerp de openingspagina door invoervelden toe te voegen voor het verzamelen van gegevens (voornaam, achternaam, e-mail, enz.).
* Wijs elk invoerveld toe aan het corresponderende veld in de database.
* Maak de openingspagina online beschikbaar via een website of via een directe koppeling naar een bericht.

Raadpleeg de [specifieke documentatie](../../channels/using/getting-started-with-landing-pages.md) voor meer informatie over bestemmingspagina&#39;s.

**Meer informatie**

* xxxx
* xxxx

### Profielen synchroniseren vanuit Microsoft Dynamics 365

De integratie van Campaign Standard met de Dynamica 365 van Microsoft staat u toe om contactgegevens van de Dynamica 365 van Microsoft tot het gegevensbestand van de Campagne over te gaan.
Deze contacten zijn dan zichtbaar in de lijst van Profielen en kunnen in marketing campagnes worden gericht. Raadpleeg de [specifieke documentatie](../../integrating/using/d365-acs-get-started.md) voor meer informatie over deze integratie.

>[!NOTE]
>
>Houd er rekening mee dat de Campaign Standard-Microsoft Dynamics 365-connector momenteel in Beperkte beschikbaarheid beschikbaar is en dat er verschillende beperkingen op van toepassing zijn, die in de documentatie worden beschreven.

**Meer informatie**

* xxxx
* xxxx

### Gegevens importeren via API-aanroepen

Met Campaign Standard-API&#39;s kunt u bewerkingen uitvoeren om de database bij te werken, zoals het maken, bijwerken of verwijderen van profielen of services. Raadpleeg de [specifieke documentatie](../../api/using/get-started-apis.md) voor meer informatie over het gebruik van de API&#39;s.

>[!CAUTION]
>
>Controleer voordat u profielen massaal maakt of bijwerkt via API-aanroepen de schaalbeperkingen die overeenkomen met uw licentieovereenkomst. Raadpleeg [deze pagina](https://helpx.adobe.com/nl/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers) voor meer informatie.

**Meer informatie**

* xxxx
* xxxx

## Uw publiek organiseren {#organizing-audiences}

<img width="60px" alt="voorwaarden" src="assets/icon_audience.svg"/>

Om u in staat te stellen relevante en effectieve berichten te leveren en uw klanten effectief te betrekken, integreert Adobe Campaign geavanceerde analyse- en doelfuncties.

Dankzij de workflows en de query-editor kunt u een publiek maken dat de verschillende campagnes als doelgroep hebben, afhankelijk van de informatie die u over de campagnes hebt, hun activiteiten, hun taal, voorkeuren of hun marketinggeschiedenis. Zo kunt u bijvoorbeeld geabonneerde profielen filteren of doelsoorten maken op een onbeperkt aantal criteria.

**Meer informatie**

* [Informatie over doelgroepen](../../audiences/using/about-audiences.md)
* [Doelgroepen maken](../../audiences/using/creating-audiences.md)

## Privacybeheer {#privacy-management}

<img width="60px" alt="voorwaarden" src="assets/icon_privacy.svg"/>

GDPR is de nieuwe privacywet van de Europese Unie (EU) die de vereisten inzake gegevensbescherming harmoniseert en moderniseert. AVG is van toepassing op Adobe Campaign-klanten die data bewaren voor in de EU wonende betrokken personen. Naast de privacymogelijkheden die al beschikbaar zijn in Adobe Campaign (waaronder beheer van toestemming, instellingen voor gegevensbewaring en gebruikersrollen), maken we van deze gelegenheid gebruik in onze rol als gegevensverwerker om extra mogelijkheden op te nemen, zodat u gemakkelijker klaar bent als Data Controller voor bepaalde GDPR-verzoeken.

Raadpleeg deze [handleiding](https://helpx.adobe.com/nl/campaign/kb/campaign-privacy.html) voor meer informatie over de tools en functies die Adobe Campaign biedt om u te helpen aan de GDPR-standaard te voldoen.

**Meer informatie**

* xxxx
* xxxx