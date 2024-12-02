---
title: Lijsten aanpassen
description: Leer hoe u de weergave kunt aanpassen en kunt werken op lijstschermen in Adobe Campaign Standard:elementen sorteren, filteren, verwijderen of dupliceren. De schermen van lijsten tonen elementen van één of verscheidene bepaalde middelen.
audience: start
content-type: reference
topic-tags: discovering-the-interface
source-git-commit: bee4da592e0b3727949bc44c6e41b81d4e7e73d4
workflow-type: tm+mt
source-wordcount: '775'
ht-degree: 5%

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

Adobe Campaign-profielen vertegenwoordigen alle contactpersonen die in de database zijn opgeslagen. Elk profiel komt overeen met één item in de database dat de nodige informatie bevat om dat profiel als doel, gekwalificeerd en afzonderlijk te kunnen traceren. Dit betekent dat een profiel kan zijn: een cliënt, een vooruitzicht, een individu die aan een nieuwsbrief, een ontvanger, een gebruiker, of een andere denominatie afhankelijk van de organisatie wordt ingetekend.

**Meer informatie**

* [Over profielen](../../audiences/using/about-profiles.md)
* [Het aantal actieve profielen in uw organisatie openen](../../audiences/using/active-profiles.md)

## De database verrijken {#populating-database}

<img width="60px" alt="voorwaarden" src="assets/icon_populate.svg"/>

Campaign Standard biedt verschillende hulpmiddelen aan om u te helpen uw marketing gegevensbestand kweken. In deze sectie worden de verschillende methoden beschreven die u kunt gebruiken om gegevens in campagne te injecteren, met verwijzingen naar de desbetreffende documenten.

### Gegevens importeren via workflows {#importing-data-through-workflows}

Met workflows kunt u gegevens verzamelen en importeren in de Campagne-database via [**[!UICONTROL Data management]**](../../automating/using/about-data-management-activities.md) -activiteiten. Algemene informatie en beste praktijken wanneer het invoeren van gegevens door werkschema&#39;s worden voorgesteld in [ deze sectie ](../../automating/using/about-data-import-and-export.md).

Daarnaast kunt u sjablonen instellen voor het importeren van gegevens. Het gebruik van importsjablonen is het aanbevolen om regelmatig bestanden met dezelfde structuur te importeren. U kunt twee typen sjablonen instellen:

* **malplaatjes van het Werkschema**: dit zijn pre-gevormde werkschema&#39;s die u opstelling eens volgens uw behoeften kunt, en telkens opnieuw gebruiken wanneer u gegevens wilt invoeren en het gegevensbestand bijwerken. Een voorbeeld van werkschemamalplaatje om gegevens in te voeren wordt gedetailleerd in [ deze sectie ](../../automating/using/creating-import-workflow-templates.md).

* **de gegevensmalplaatjes van de Invoer**: als werkschemamalplaatjes, zijn deze malplaatjes die op werkschema&#39;s worden gebaseerd, die opstelling zijn om dossiers te uploaden om het gegevensbestand bij te werken. Zodra deze zijn geconfigureerd, worden ze beschikbaar gesteld voor gebruikers met een vereenvoudigde weergave in het menu **[!UICONTROL Profile & audiences]** / **[!UICONTROL Imports]** . Voor meer op de malplaatjes van de invoergegevens, verwijs naar de [ specifieke documentatie ](../../automating/using/importing-data-with-import-templates.md).

### Gegevens van bestemmingspagina&#39;s verzamelen {#collecting-data-from-landing-pages}

Openingspagina&#39;s zijn webformulieren die kunnen worden gebruikt om gegevens te verzamelen en bestaande gegevens in uw database te maken of bij te werken. Het beginsel is als volgt:

* Maak en ontwerp de openingspagina door invoervelden toe te voegen voor het verzamelen van gegevens (voornaam, achternaam, e-mail, enz.).
* Wijs elk invoerveld toe aan het corresponderende veld in de database.
* Maak de openingspagina online beschikbaar via een website of via een directe koppeling naar een bericht.

Voor meer bij het landen van pagina&#39;s, verwijs naar de [ specifieke documentatie ](../../channels/using/getting-started-with-landing-pages.md).

**Meer informatie**

* xxxx
* xxxx

### Profielen synchroniseren vanuit Microsoft Dynamics 365

Dankzij de integratie van Campaigns Standard met Microsoft Dynamics 365 kunt u contactgegevens doorgeven van Microsoft Dynamics 365 naar de Campagne-database.
Deze contacten zijn dan zichtbaar in de lijst van Profielen en kunnen in marketing campagnes worden gericht. Voor meer op deze integratie, verwijs naar de [ specifieke documentatie ](../../integrating/using/d365-acs-get-started.md).

>[!NOTE]
>
>Houd er rekening mee dat Campaign Standard-Microsoft Dynamics 365-connector momenteel in Beperkte beschikbaarheid is en dat er enkele beperkingen op van toepassing zijn, die in de documentatie nader worden beschreven.

**Meer informatie**

* xxxx
* xxxx

### Gegevens importeren via API-aanroepen

Met Campaign Standard-API&#39;s kunt u bewerkingen uitvoeren om de database bij te werken, zoals het maken, bijwerken of verwijderen van profielen of services. Voor meer op hoe te om APIs te gebruiken, verwijs naar de [ specifieke documentatie ](../../api/using/get-started-apis.md).

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

GDPR is de nieuwe privacywet van de Europese Unie (EU) die de vereisten inzake gegevensbescherming harmoniseert en moderniseert. GDPR is van toepassing op Adobe Campaign-klanten die gegevens aanhouden voor in de EU verblijvende gegevenssubjecten. Naast de privacymogelijkheden die al beschikbaar zijn in Adobe Campaign (waaronder beheer van toestemming, instellingen voor gegevensbewaring en gebruikersrollen), maken we van deze gelegenheid gebruik in onze rol als gegevensverwerker om extra mogelijkheden op te nemen, zodat u gemakkelijker klaar bent als Data Controller voor bepaalde GDPR-verzoeken.

Verwijs naar [ deze sectie ](../../start/using/privacy.md) om meer over de hulpmiddelen en de functionaliteiten te leren die Adobe Campaign verstrekt om u te helpen volgzaam GDPR worden.

**Meer informatie**

* xxxx
* xxxx