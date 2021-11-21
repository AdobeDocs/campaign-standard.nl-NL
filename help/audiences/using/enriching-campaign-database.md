---
title: De database verrijken
description: Leer over de diverse methodes om het gegevensbestand te verrijken.
audience: start
content-type: reference
topic-tags: about-adobe-campaign
feature: Profiles
role: User
level: Intermediate
exl-id: 9c55a8b3-034e-4319-8a88-7b59e83fa458
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 3%

---

# De database verrijken{#enriching-the-database}

Campaign Standard biedt verschillende hulpmiddelen aan om u te helpen uw marketing gegevensbestand kweken. In deze sectie worden de verschillende methoden beschreven die u kunt gebruiken om gegevens in campagne te injecteren, met verwijzingen naar de desbetreffende documenten.

## Gegevens importeren via workflows {#importing-data-through-workflows}

Met workflows kunt u gegevens verzamelen en importeren in de Campagne-database via [[!UICONTROL Data management]](../../automating/using/about-data-management-activities.md) activiteiten.

Algemene informatie en aanbevolen procedures bij het importeren van gegevens via workflows worden weergegeven in [deze sectie](../../automating/using/about-data-import-and-export.md).

Daarnaast kunt u sjablonen instellen voor het importeren van gegevens. Het gebruik van importsjablonen is de beste manier als u regelmatig bestanden met dezelfde structuur moet importeren.

U kunt twee typen sjablonen instellen:

* **Workflowsjablonen**: Dit zijn vooraf geconfigureerde workflows die u één keer kunt instellen op basis van uw behoeften en die u telkens opnieuw kunt gebruiken wanneer u gegevens wilt importeren en de database wilt bijwerken.

   Een voorbeeld van een werkstroomsjabloon voor het importeren van gegevens vindt u in [deze sectie](../../automating/using/creating-import-workflow-templates.md).

* **Gegevenssjablonen importeren**: dit zijn, net als workflowsjablonen, sjablonen die zijn gebaseerd op workflows, die zijn ingesteld om bestanden te uploaden om de database bij te werken. Zodra gevormd, worden zij ter beschikking gesteld aan gebruikers met een vereenvoudigde mening onder **[!UICONTROL Profile & audiences]** / **[!UICONTROL Imports]** -menu.

   Voor meer informatie over de malplaatjes van de invoergegevens, verwijs naar [speciale documentatie](../../automating/using/importing-data-with-import-templates.md).

## Gegevens van bestemmingspagina&#39;s verzamelen {#collecting-data-from-landing-pages}

Openingspagina&#39;s zijn webformulieren die kunnen worden gebruikt om gegevens te verzamelen en bestaande gegevens in uw database te maken of bij te werken.

Het beginsel is als volgt:

* Maak en ontwerp de openingspagina door invoervelden toe te voegen voor het verzamelen van gegevens (voornaam, achternaam, e-mail, enz.).
* Wijs elk invoerveld toe aan het corresponderende veld in de database.
* Maak de openingspagina online beschikbaar via een website of via een directe koppeling naar een bericht.

Raadpleeg voor meer informatie over bestemmingspagina&#39;s de [speciale documentatie](../../channels/using/getting-started-with-landing-pages.md).

## Profielen synchroniseren vanuit Microsoft Dynamics 365

Dankzij de Campaign Standard-integratie met Microsoft Dynamics 365 kunt u contactgegevens van Microsoft Dynamics 365 doorgeven aan de Campagne-database.
Deze contacten zijn dan zichtbaar in de lijst van Profielen en kunnen in marketing campagnes worden gericht.

Raadpleeg voor meer informatie over deze integratie de [speciale documentatie](../../integrating/using/d365-acs-get-started.md).

>[!NOTE]
>
>Houd er rekening mee dat de Campaign Standard-Microsoft Dynamics 365-connector momenteel in Beperkte beschikbaarheid beschikbaar is en dat er verschillende beperkingen op van toepassing zijn, die in de documentatie worden beschreven.

## Gegevens importeren via API-aanroepen

Met Campaign Standard-API&#39;s kunt u bewerkingen uitvoeren om de database bij te werken, zoals het maken, bijwerken of verwijderen van profielen of services.

Raadpleeg voor meer informatie over het gebruik van de API&#39;s de [speciale documentatie](../../api/using/get-started-apis.md).

>[!IMPORTANT]
>
>Controleer voordat u profielen massaal maakt of bijwerkt via API-aanroepen de schaalbeperkingen die overeenkomen met uw licentieovereenkomst. Raadpleeg [deze pagina](https://helpx.adobe.com/nl/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers) voor meer informatie.
