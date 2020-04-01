---
title: De database verrijken
description: Leer over de diverse methodes om het gegevensbestand te verrijken.
page-status-flag: never-activated
uuid: 71f53808-0309-49f6-a4ee-3446eac9758a
contentOwner: lemaitre
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: about-adobe-campaign
discoiquuid: d8c8a318-9433-4aec-b378-fd0beb50e9fb
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a1bc9d23163d12517c4501a572fc92aac6aacbc6

---


# De database verrijken{#enriching-the-database}

De Standaard van de campagne biedt verscheidene hulpmiddelen aan om u te helpen uw marketing gegevensbestand kweken. In deze sectie worden de verschillende methoden beschreven die u kunt gebruiken om gegevens in campagne te injecteren, met verwijzingen naar de desbetreffende documenten.

## Gegevens importeren via workflows {#importing-data-through-workflows}

Met workflows kunt u gegevens verzamelen en importeren in de Campagne-database via het gebruik van [**[!UICONTROL Data management]**](../../automating/using/about-data-management-activities.md) activiteiten.

Algemene informatie en aanbevolen procedures bij het importeren van gegevens via workflows worden in [deze sectie](../../automating/using/importing-data.md)weergegeven.

Daarnaast kunt u sjablonen instellen voor het importeren van gegevens. Het gebruik van importsjablonen is de beste manier als u regelmatig bestanden met dezelfde structuur moet importeren.

U kunt twee typen sjablonen instellen:

* **Workflowsjablonen**: Dit zijn vooraf geconfigureerde workflows die u één keer kunt instellen op basis van uw behoeften en die u telkens opnieuw kunt gebruiken wanneer u gegevens wilt importeren en de database wilt bijwerken.

   In [deze sectie](../../automating/using/importing-data.md#example--import-workflow-template)wordt een voorbeeld van een werkstroomsjabloon voor het importeren van gegevens beschreven.

* **Gegevenssjablonen** importeren: dit zijn, net als workflowsjablonen, sjablonen die zijn gebaseerd op workflows, die zijn ingesteld om bestanden te uploaden om de database bij te werken. Zodra gevormd, worden zij ter beschikking gesteld aan gebruikers met een vereenvoudigde mening onder **[!UICONTROL Profile & audiences]** / **[!UICONTROL Imports]** menu.

   Raadpleeg de [desbetreffende documentatie](../../automating/using/importing-data-with-import-templates.md)voor meer informatie over sjablonen voor importgegevens.

## Gegevens van bestemmingspagina&#39;s verzamelen {#collecting-data-from-landing-pages}

Openingspagina&#39;s zijn webformulieren die kunnen worden gebruikt om gegevens te verzamelen en bestaande gegevens in uw database te maken of bij te werken.

Het beginsel is als volgt:

* Maak en ontwerp de openingspagina door invoervelden toe te voegen voor het verzamelen van gegevens (voornaam, achternaam, e-mail, enz.).
* Wijs elk invoerveld toe aan het corresponderende veld in de database.
* Maak de openingspagina online beschikbaar via een website of via een directe koppeling naar een bericht.

Raadpleeg de [desbetreffende documentatie](../../channels/using/getting-started-with-landing-pages.md)voor meer informatie over bestemmingspagina&#39;s.

## Profielen synchroniseren vanuit Microsoft Dynamics 365

De standaardintegratie van de campagne met de Dynamica 365 van Microsoft staat u toe om contactgegevens van de Dynamica 365 van Microsoft tot het gegevensbestand van de Campagne over te gaan.
Deze contacten zijn dan zichtbaar in de lijst van Profielen en kunnen in marketing campagnes worden gericht.

Raadpleeg de [desbetreffende documentatie](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md)voor meer informatie over deze integratie.

>[!NOTE]
>
>Houd er rekening mee dat de connector Standaard-Microsoft Dynamics 365 voor Campagne momenteel in Beperkte Beschikbaarheid is en dat er verschillende beperkingen op van toepassing zijn, die in de documentatie worden beschreven.

## Gegevens importeren via API-aanroepen

Met API&#39;s van de campagnestandaard kunt u bewerkingen uitvoeren om de database bij te werken, zoals het maken, bijwerken of verwijderen van profielen of services.

Raadpleeg de [specifieke documentatie](../../api/using/about-campaign-standard-apis.md)voor meer informatie over het gebruik van de API&#39;s.

>[!CAUTION]
>
>Controleer voordat u profielen massaal maakt of bijwerkt via API-aanroepen de schaalbeperkingen die overeenkomen met uw licentieovereenkomst. For more on this, refer to [this page](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers).
