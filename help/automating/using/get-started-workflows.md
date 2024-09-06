---
title: Aan de slag met processen en gegevensbeheer
description: Automatiseer processen met workflows, beheer gegevens en doelgroepen, verzend berichten, en meer.
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
feature: Workflows
role: Data Architect
level: Beginner
exl-id: 26be942a-c252-458f-a590-eb235567ca67
source-git-commit: 47f47a624b8a1d941d1ab4b49e67f0260ac68cf1
workflow-type: tm+mt
source-wordcount: '506'
ht-degree: 9%

---

# Aan de slag met processen en gegevensbeheer {#get-started-processes-data-management}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_workflows.svg" width="60px"><p><a href="#workflow-activities">Workflowactiviteiten</a></p></td><td><img src="assets/do-not-localize/icon_activities.svg" width="60px"><p><a href="../../automating/using/workflow-created-query-with-complement.md">Gebruiksscenario’s</a></p></td><td><img src="assets/do-not-localize/icon_filter.svg" width="60px"><p><a href="#filter-data">Gegevens filteren</a></p></td>
<td><img src="assets/do-not-localize/icon_manage.svg" width="60px"><p><a href="#import-export-data">Gegevens importeren/exporteren</a></p></td></tr>
</table>

Adobe Campaign biedt een uitgebreide grafische omgeving waarmee u complexe processen kunt ontwerpen, zoals segmentatie, uitvoering van campagnes, bestandsverwerking, enzovoort. U kunt bijvoorbeeld een workflow gebruiken om een bestand van een server te downloaden, het te decomprimeren en vervolgens de records in de Adobe Campaign-database te importeren.

Workflows kunnen in verschillende contexten worden gebruikt, zoals:

* Het richten om publiek te beheren of berichten te verzenden.
* Gegevensbeheer (ETL) voor het manipuleren van gegevens.
* Gegevens importeren in de Campagne-database.
* Technische processen zoals het opschonen van databases, het herstellen van trackinggegevens, enz.

>[!IMPORTANT]
>
> Adobe raadt klanten aan niet meer dan 20 actieve workflows tegelijk uit te voeren en de uitvoering van de workflow in de loop der tijd te prioriteren en te verspreiden. Voor meer op dit, verwijs naar de beste praktijken die in [ worden verstrekt deze pagina ](../../automating/using/best-practices-workflows.md).

## Workflowactiviteiten {#workflow-activities}

<img src="assets/do-not-localize/icon_workflows.svg" width="10%px">

Er zijn verschillende activiteiten beschikbaar om u te helpen uw workflows ontwerpen.

[ het richten activiteiten ](../../automating/using/about-targeting-activities.md) staat u toe om één of meerdere doelstellingen te bouwen door reeksen te bepalen en deze reeksen te splitsen of te combineren gebruikend doorsnede, vereniging, of uitsluitingsverrichtingen.

Met [ de activiteiten van de Uitvoering ](../../automating/using/about-execution-activities.md), coördineer uw werkschema en zijn activiteiten, terwijl [ de activiteiten van het Kanaal ](../../automating/using/about-channel-activities.md) u Campaign Standard communicatie kanalen laten combineren om kanaalwerkschema&#39;s tot stand te brengen.

Tot slot [ de beheersactiviteiten van Gegevens ](../../automating/using/about-data-management-activities.md) staan u toe om gegevens van uw gegevensbestand te manipuleren.

Meer informatie:

* [Een workflow maken](../../automating/using/building-a-workflow.md)
* [Een workflow uitvoeren](../../automating/using/about-workflow-execution.md)
* [Best practices voor workflows](../../automating/using/best-practices-workflows.md)

## Gegevens filteren {#filter-data}

<img src="assets/do-not-localize/icon_filter.svg" width="60px">

Hefboomwerking de **vraagredacteur** om gegevens van uw gegevensbestand te filtreren en een bevolking te bouwen om uw ontvangers beter te richten. De vraagredacteur is beschikbaar om verscheidene acties in Campaign Standard uit te voeren: creeer het type van Vraag publiek, bepaal leveringsdoelstellingen, of populaties in werkschemaactiviteiten.

De vraagredacteur komt met **vooraf bepaalde filters en regels** voor snel en gemakkelijk het filtreren. Nochtans, kunt u **geavanceerde uitdrukking ook gebruiken die** mogelijkheden uitgeeft. Op deze manier kunt u handmatig voorwaarden invoeren en functies gebruiken om uw eigen regels op te stellen.

Meer informatie:

* [Query&#39;s bewerken](../../automating/using/editing-queries.md)
* [Geavanceerde expressies bewerken](../../automating/using/advanced-expression-editing.md)
* [Lijst met functies](../../automating/using/list-of-functions.md)

## Gegevens importeren/exporteren {#import-export-data}

<img src="assets/do-not-localize/icon_manage.svg" width="60px">

Het Campaign Standard komt met verscheidene **mogelijkheden van het gegevensbeheer** om gegevens in te voeren en uit te voeren.

[ de activiteiten van het gegevensbeheer van de Werkschema&#39;s ](../../automating/using/about-data-management-activities.md) staan u toe om gegevens in te voeren, massaupdates op gebieden uit te voeren, dossier te ontvangen of te verzenden, of geen geïdentificeerde gegevens aan bestaande middelen te verbinden.

Met [ de malplaatjes van de Invoer ](../../automating/using/importing-data-with-import-templates.md), beheer bepaalde types van invoer die door beheerders door vereenvoudigde de invoerfuncties worden bepaald.

[ het Uitvoeren logboeken ](../../automating/using/exporting-logs.md) laat u logboekgegevens door een eenvoudig werkschema uitvoeren, toestaand u om de resultaten van uw marketing campagnes in uw eigen rapportering of hulpmiddelen van BI te analyseren.

Hefboomwerking [ Pakketten ](../../automating/using/managing-packages.md) aan uitwisselingsmiddelen tussen verschillende campagneinstanties, bijvoorbeeld, om de configuratie van een instantie te herhalen, of gegevens over te brengen van een server aan een andere met inbegrip van douanemiddelen.

Tot slot [ het Uitvoeren lijsten ](../../automating/using/exporting-lists.md) staan u toe om het even welke lijst van Campaign Standard als, bijvoorbeeld, de lijst van testprofielen, de lijst van quarantines e-mailadressen, enz. uit te voeren.

Meer informatie:

* [Gegevens importeren en exporteren](../../automating/using/about-data-import-and-export.md)
* [Gebruiksscenario: aangepaste bronnen exporteren en importeren](../../automating/using/exporting-importing-custom-resources.md)

## Verdere bronnen

* [ Van processen en van het gegevensbeheer zelfstudie video&#39;s ](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/managing-processes-and-data/creating-a-workflow.html?lang=nl)
* [Technische workflows](../../administration/using/technical-workflows.md)
* [Aan de slag met het Campaign Standard-gegevensmodel](../../developing/using/get-started-data-model.md)
