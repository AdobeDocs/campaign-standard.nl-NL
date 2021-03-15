---
solution: Campaign Standard
product: campaign
title: Aan de slag met processen en data management
description: Automatiseer processen met workflows, beheer gegevens en publiek, verzend berichten, en meer.
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
feature: Workflows
role: Gegevensarchitect
level: Begin
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 11%

---


# Aan de slag met processen en data management {#get-started-processes-data-management}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_workflows.svg" width="60px"><p><a href="#workflow-activities">Workflowactiviteiten</a></p></td><td><img src="assets/do-not-localize/icon_activities.svg" width="60px"><p><a href="../../automating/using/workflow-created-query-with-complement.md">Gebruiksscenario’s</a></p></td><td><img src="assets/do-not-localize/icon_filter.svg" width="60px"><p><a href="#filter-data">Gegevens filteren</a></p></td>
<td><img src="assets/do-not-localize/icon_manage.svg" width="60px"><p><a href="#import-export-data">Gegevens importeren/exporteren</a></p></td></tr>
</table>

Adobe Campaign biedt een uitgebreide grafische omgeving waarmee u complexe processen kunt ontwerpen, zoals segmentatie, uitvoering van campagnes, bestandsverwerking, enzovoort. U kunt bijvoorbeeld een workflow gebruiken om een bestand van een server te downloaden, het te decomprimeren en vervolgens de records in de Adobe Campaign-database te importeren.

Een werkstroom kan gebruikers ook betrekken door hen taken toe te wijzen of hen te laten uitgevoerde taken goedkeuren. Dit betekent u een taak aan één of verscheidene gebruikers kunt toewijzen om aan inhoud te werken of doelstellingen te specificeren, en proefdrukken goed te keuren alvorens het bericht te verzenden.

Workflows kunnen in verschillende contexten worden gebruikt, zoals:

* Het richten om publiek te beheren of berichten te verzenden.
* Gegevensbeheer (ETL) voor het manipuleren van gegevens.
* Gegevens importeren in de Campagne-database.
* Technische processen zoals het opschonen van databases, het herstellen van trackinggegevens, enz.

## Workflowactiviteiten {#workflow-activities}

<img src="assets/do-not-localize/icon_workflows.svg" width="60px">

Er zijn verschillende activiteiten beschikbaar om u te helpen uw workflows ontwerpen.

[Met doelgerichte ](../../automating/using/about-targeting-activities.md) activiteiten kunt u een of meer doelen maken door sets te definiëren en deze sets te splitsen of te combineren met gebruik van doorsnede-, samenvoegings- of uitsluitingsbewerkingen.

Met [Uitvoeringsactiviteiten](../../automating/using/about-execution-activities.md), coördineer uw werkschema en zijn activiteiten, terwijl [Kanaalactiviteiten](../../automating/using/about-channel-activities.md) u Campaign Standard communicatiekanalen laten combineren om kanaalwerkschema&#39;s tot stand te brengen.

Tot slot [Met gegevensbeheeractiviteiten](../../automating/using/about-data-management-activities.md) kunt u gegevens uit uw database manipuleren.

Meer informatie:

* [Een workflow maken](../../automating/using/building-a-workflow.md)
* [Een workflow uitvoeren](../../automating/using/about-workflow-execution.md)
* [Best practices voor workflows](../../automating/using/best-practices-workflows.md)

## Gegevens filteren {#filter-data}

<img src="assets/do-not-localize/icon_filter.svg" width="60px">

Gebruik **query redacteur** aan filtergegevens van uw gegevensbestand en bouwt een bevolking om uw ontvangers beter te richten. De vraagredacteur is beschikbaar om verscheidene acties in Campaign Standard uit te voeren: Maak het type van Vraag publiek, bepaal leveringsdoelstellingen, of populaties in werkschemaactiviteiten.

De vraagredacteur komt met **vooraf bepaalde filters en regels** voor snel en gemakkelijk het filtreren. U kunt echter ook **geavanceerde expressies bewerken**-mogelijkheden gebruiken. Op deze manier kunt u handmatig voorwaarden invoeren en functies gebruiken om uw eigen regels op te stellen.

Meer informatie:

* [Query&#39;s bewerken](../../automating/using/editing-queries.md)
* [Geavanceerde expressies bewerken](../../automating/using/advanced-expression-editing.md)
* [Lijst met functies](../../automating/using/list-of-functions.md)

## Gegevens {#import-export-data} importeren/exporteren

<img src="assets/do-not-localize/icon_manage.svg" width="60px">

Campaign Standard wordt geleverd met verschillende **mogelijkheden voor gegevensbeheer** voor het importeren en exporteren van gegevens.

[Met ](../../automating/using/about-data-management-activities.md) activiteiten voor gegevensbeheer in workflows kunt u gegevens importeren, massaupdates uitvoeren op velden, bestanden ontvangen of verzenden of niet-geïdentificeerde gegevens koppelen aan bestaande bronnen.

Met [Sjablonen importeren](../../automating/using/importing-data-with-import-templates.md) kunt u bepaalde typen importeren beheren die door beheerders zijn gedefinieerd via vereenvoudigde importfuncties.

[Bij het exporteren van ](../../automating/using/exporting-logs.md) logbestanden exporteert u loggegevens via een eenvoudige workflow, zodat u de resultaten van uw marketingcampagnes kunt analyseren in uw eigen rapportage- of BI-programma&#39;s.

Gebruik [Pakketten](../../automating/using/managing-packages.md) aan uitwisselingsmiddelen tussen verschillende campagneinstanties, bijvoorbeeld, om de configuratie van een instantie te herhalen, of gegevens over te brengen van een server aan een andere met inbegrip van douanemiddelen.

Tot slot [Met het exporteren van lijsten](../../automating/using/exporting-lists.md) kunt u elke lijst uit Campaign Standard exporteren, zoals bijvoorbeeld de lijst met testprofielen, de lijst met e-mailadressen in quarantaine, enzovoort.

Meer informatie:

* [Data importeren en exporteren](../../automating/using/about-data-import-and-export.md)
* [Gebruiksscenario: Aangepaste resources exporteren en importeren](../../automating/using/exporting-importing-custom-resources.md)

## Aanvullende bronnen

* [Zelfstudievideo&#39;s over processen en gegevensbeheer](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/getting-started/create-workflow.html)
* [Technische workflows](../../administration/using/technical-workflows.md)
* [Aan de slag met het Campaign Standard-datamodel](../../developing/using/get-started-data-model.md)
