---
title: Aan de slag met processen en gegevensbeheer
description: Adobe Campaign biedt een uitgebreide grafische omgeving waarmee u processen kunt ontwerpen en automatiseren.
page-status-flag: never-activated
uuid: 7c1e8cea-90d0-491f-ab8f-6cd69f8a6c3b
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
discoiquuid: 40503917-7a53-4d99-96a4-57aa9e98ec87
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 21faea89b3b38f3e667ed6c4de0be6d07f0b7197
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 0%

---


# Aan de slag met processen en gegevensbeheer {#get-started-processes-data-management}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_workflows.svg" width="60px"><p><a href="#workflow-activities">Workflowactiviteiten</a></p></td><td><img src="assets/do-not-localize/icon_activities.svg" width="60px"><p><a href="../../automating/using/workflow-created-query-with-complement.md">Gebruik hoofdletters</a></p></td><td><img src="assets/do-not-localize/icon_filter.svg" width="60px"><p><a href="#filter-data">Gegevens filteren</a></p></td>
<td><img src="assets/do-not-localize/icon_manage.svg" width="60px"><p><a href="#import-export-data">Gegevens importeren/exporteren</a></p></td></tr>
</table>

Adobe Campaign biedt een uitgebreide grafische omgeving waarmee u complexe processen kunt ontwerpen, zoals segmentatie, uitvoering van campagnes, bestandsverwerking, goedkeuringen, enzovoort. U kunt bijvoorbeeld een workflow gebruiken om een bestand van een server te downloaden, het te decomprimeren en vervolgens de records ervan te importeren in de Adobe Campagne-database.

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

Met de activiteiten [van de](../../automating/using/about-execution-activities.md)Uitvoering, coördineer uw werkschema en zijn activiteiten, terwijl de activiteiten [van het](../../automating/using/about-channel-activities.md) Kanaal u de Standaard communicatie van de Campagne kanalen laten combineren om kanaalwerkschema&#39;s tot stand te brengen.

Tot slot staan de [gegevensbeheeractiviteiten](../../automating/using/about-data-management-activities.md) u toe om gegevens van uw gegevensbestand te manipuleren.

Meer informatie:

* [Een workflow maken](../../automating/using/building-a-workflow.md)
* [Een workflow uitvoeren](../../automating/using/about-workflow-execution.md)
* [Best practices voor workflows](../../automating/using/best-practices-workflows.md)

## Gegevens filteren {#filter-data}

<img src="assets/do-not-localize/icon_filter.svg" width="60px">

Gebruik de **vraagredacteur** om gegevens van uw gegevensbestand te filtreren en een bevolking te bouwen om uw ontvangers beter te richten. De vraagredacteur is beschikbaar om verscheidene acties in de Norm van de Campagne uit te voeren: Maak het type van Vraag publiek, bepaal leveringsdoelstellingen, of populaties in werkschemaactiviteiten.

De vraagredacteur komt met **vooraf bepaalde filters en regels** voor snel en gemakkelijk het filtreren. U kunt echter ook gebruikmaken van de **geavanceerde bewerkingsmogelijkheden** voor expressies. Op deze manier kunt u handmatig voorwaarden invoeren en functies gebruiken om uw eigen regels op te stellen.

Meer informatie:

* [Bewerkquery&#39;s](../../automating/using/editing-queries.md)
* [Geavanceerde expressies bewerken](../../automating/using/advanced-expression-editing.md)
* [Lijst met functies](../../automating/using/list-of-functions.md)

## Gegevens importeren/exporteren {#import-export-data}

<img src="assets/do-not-localize/icon_manage.svg" width="60px">

De standaard van de campagne komt met verscheidene mogelijkheden **van het** gegevensbeheer om gegevens in te voeren en uit te voeren.

[Met de activiteiten](../../automating/using/about-data-management-activities.md) voor gegevensbeheer van workflows kunt u gegevens importeren, massa-updates uitvoeren op velden, bestanden ontvangen of verzenden of niet-geïdentificeerde gegevens koppelen aan bestaande bronnen.

Met de malplaatjes [van de](../../automating/using/importing-data-with-import-templates.md)Invoer, beheer bepaalde types van invoer die door beheerders door vereenvoudigde de invoerfuncties worden bepaald.

[Door logbestanden](../../automating/using/exporting-logs.md) te exporteren kunt u loggegevens via een eenvoudige workflow exporteren, zodat u de resultaten van uw marketingcampagnes kunt analyseren in uw eigen rapportage- of BI-programma&#39;s.

Gebruik [Pakketten](../../automating/using/managing-packages.md) van de hefboomwerking om middelen tussen verschillende campagneinstanties, bijvoorbeeld, te ruilen om de configuratie van een instantie te herhalen, of gegevens over te brengen van een server aan een andere met inbegrip van douanemiddelen.

Ten slotte kunt u met lijsten [voor](../../automating/using/exporting-lists.md) exporteren lijsten exporteren uit de campagnestandaard, zoals bijvoorbeeld de lijst met testprofielen, de lijst met e-mailadressen voor quarantaines, enzovoort.

Meer informatie:

* [Gegevens importeren](../../automating/using/importing-data.md)
* [Werkstroomgegevens gebruiken](../../automating/using/using-workflow-data.md)
* [Hoofdlettergebruik: Aangepaste bronnen exporteren/importeren](../../automating/using/exporting-importing-custom-resources.md)

## Aanvullende bronnen

* [Zelfstudievideo&#39;s over processen en gegevensbeheer](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/getting-started/create-workflow.html)
* [Technische workflows](../../administration/using/technical-workflows.md)
* [Aan de slag met het standaard gegevensmodel van de campagne](../../developing/using/get-started-data-model.md)
