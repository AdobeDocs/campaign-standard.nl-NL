---
title: Aan de slag met processen en data management
description: Automatiseer processen met workflows, beheer gegevens en publiek, verzend berichten, en meer.
page-status-flag: never-activated
uuid: 7c1e8cea-90d0-491f-ab8f-6cd69f8a6c3b
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
discoiquuid: 40503917-7a53-4d99-96a4-57aa9e98ec87
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '519'
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

[Met doelgerichte activiteiten](../../automating/using/about-targeting-activities.md) kunt u een of meer doelen maken door sets te definiëren en deze sets te splitsen of te combineren met behulp van doorsnede-, samenvoegings- of uitsluitingsbewerkingen.

Met [de activiteiten](../../automating/using/about-execution-activities.md)van de Uitvoering, coördineer uw werkschema en zijn activiteiten, terwijl de activiteiten [van het](../../automating/using/about-channel-activities.md) Kanaal u Campaign Standard communicatie kanalen laten combineren om kanaalwerkschema&#39;s tot stand te brengen.

Tot slot staan de [gegevensbeheeractiviteiten](../../automating/using/about-data-management-activities.md) u toe om gegevens van uw gegevensbestand te manipuleren.

Meer informatie:

* [Een workflow maken](../../automating/using/building-a-workflow.md)
* [Een workflow uitvoeren](../../automating/using/about-workflow-execution.md)
* [Best practices voor workflows](../../automating/using/best-practices-workflows.md)

## Gegevens filteren {#filter-data}

<img src="assets/do-not-localize/icon_filter.svg" width="60px">

Gebruik de **vraagredacteur** om gegevens van uw gegevensbestand te filtreren en een bevolking te bouwen om uw ontvangers beter te richten. De vraagredacteur is beschikbaar om verscheidene acties in Campaign Standard uit te voeren: Maak het type van Vraag publiek, bepaal leveringsdoelstellingen, of populaties in werkschemaactiviteiten.

De vraagredacteur komt met **vooraf bepaalde filters en regels** voor snel en gemakkelijk het filtreren. U kunt echter ook gebruikmaken van de **geavanceerde bewerkingsmogelijkheden** voor expressies. Op deze manier kunt u handmatig voorwaarden invoeren en functies gebruiken om uw eigen regels op te stellen.

Meer informatie:

* [Query&#39;s bewerken](../../automating/using/editing-queries.md)
* [Geavanceerde expressies bewerken](../../automating/using/advanced-expression-editing.md)
* [Lijst met functies](../../automating/using/list-of-functions.md)

## Gegevens importeren/exporteren {#import-export-data}

<img src="assets/do-not-localize/icon_manage.svg" width="60px">

Campaign Standard wordt geleverd met verschillende mogelijkheden **voor** gegevensbeheer voor het importeren en exporteren van gegevens.

[Met de activiteiten](../../automating/using/about-data-management-activities.md) voor gegevensbeheer van workflows kunt u gegevens importeren, massa-updates uitvoeren op velden, bestanden ontvangen of verzenden of niet-geïdentificeerde gegevens koppelen aan bestaande bronnen.

Met de malplaatjes [van de](../../automating/using/importing-data-with-import-templates.md)Invoer, beheer bepaalde types van invoer die door beheerders door vereenvoudigde de invoerfuncties worden bepaald.

[Door logbestanden](../../automating/using/exporting-logs.md) te exporteren kunt u loggegevens via een eenvoudige workflow exporteren, zodat u de resultaten van uw marketingcampagnes kunt analyseren in uw eigen rapportage- of BI-programma&#39;s.

Gebruik [Pakketten](../../automating/using/managing-packages.md) van de hefboomwerking om middelen tussen verschillende campagneinstanties, bijvoorbeeld, te ruilen om de configuratie van een instantie te herhalen, of gegevens over te brengen van een server aan een andere met inbegrip van douanemiddelen.

Ten slotte kunt u met lijsten [voor](../../automating/using/exporting-lists.md) exporteren lijsten exporteren uit Campaign Standard, zoals bijvoorbeeld de lijst met testprofielen, de lijst met e-mailadressen voor quarantaines, enzovoort.

Meer informatie:

* [Data importeren en exporteren](../../automating/using/about-data-import-and-export.md)
* [Gebruiksscenario: Aangepaste resources exporteren en importeren](../../automating/using/exporting-importing-custom-resources.md)

## Aanvullende bronnen

* [Zelfstudievideo&#39;s over processen en gegevensbeheer](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/getting-started/create-workflow.html)
* [Technische workflows](../../administration/using/technical-workflows.md)
* [Aan de slag met het Campaign Standard-datamodel](../../developing/using/get-started-data-model.md)
