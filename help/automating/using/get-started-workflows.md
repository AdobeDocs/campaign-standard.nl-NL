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
source-git-commit: 31f62227736daf4f215fcbe1cf7b0a0a8574cda3
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
> Adobe raadt klanten aan niet meer dan 20 actieve workflows tegelijk uit te voeren en de uitvoering van de workflow in de loop der tijd te prioriteren en te verspreiden. Raadpleeg voor meer informatie de beste praktijken in [deze pagina](../../automating/using/best-practices-workflows.md).

## Workflowactiviteiten {#workflow-activities}

<img src="assets/do-not-localize/icon_workflows.svg" width="60px">

Er zijn verschillende activiteiten beschikbaar om u te helpen uw workflows ontwerpen.

[Gerichte activiteiten](../../automating/using/about-targeting-activities.md) staat u toe om één of meerdere doelstellingen te bouwen door reeksen te bepalen en deze reeksen te verdelen of te combineren gebruikend doorsnede, vereniging, of uitsluitingsverrichtingen.

Met [Uitvoeringsactiviteiten](../../automating/using/about-execution-activities.md), uw workflow en activiteiten te coördineren, terwijl [Kanaalactiviteiten](../../automating/using/about-channel-activities.md) Hiermee kunt u communicatiekanalen van Campaigns Standard combineren om kanaalworkflows te maken.

Tot slot: [Gegevensbeheeractiviteiten](../../automating/using/about-data-management-activities.md) kunt u gegevens uit uw database bewerken.

Meer informatie:

* [Een workflow maken](../../automating/using/building-a-workflow.md)
* [Een workflow uitvoeren](../../automating/using/about-workflow-execution.md)
* [Best practices voor workflows](../../automating/using/best-practices-workflows.md)

## Gegevens filteren {#filter-data}

<img src="assets/do-not-localize/icon_filter.svg" width="60px">

Gebruik de **queryeditor** om gegevens van uw gegevensbestand te filtreren en een bevolking te bouwen om uw ontvangers beter te richten. De vraagredacteur is beschikbaar om verscheidene acties in Campaign Standard uit te voeren: creeer het type van Vraag publiek, bepaal leveringsdoelstellingen, of populaties in werkschemaactiviteiten.

De vraagredacteur komt met **vooraf gedefinieerde filters en regels** voor snel en gemakkelijk filtreren. U kunt echter ook **geavanceerde expressies bewerken** mogelijkheden. Op deze manier kunt u handmatig voorwaarden invoeren en functies gebruiken om uw eigen regels op te stellen.

Meer informatie:

* [Query&#39;s bewerken](../../automating/using/editing-queries.md)
* [Geavanceerde expressies bewerken](../../automating/using/advanced-expression-editing.md)
* [Lijst met functies](../../automating/using/list-of-functions.md)

## Gegevens importeren/exporteren {#import-export-data}

<img src="assets/do-not-localize/icon_manage.svg" width="60px">

Campaign Standard wordt geleverd met verschillende **gegevensbeheermogelijkheden** om gegevens te importeren en te exporteren.

[Werkstroomgegevensbeheeractiviteiten](../../automating/using/about-data-management-activities.md) kunt u gegevens importeren, massa-updates uitvoeren op velden, bestand ontvangen of verzenden of niet-geïdentificeerde gegevens koppelen aan bestaande bronnen.

Met [Sjablonen importeren](../../automating/using/importing-data-with-import-templates.md)beheert u bepaalde typen import die door beheerders zijn gedefinieerd via vereenvoudigde importfuncties.

[Logbestanden exporteren](../../automating/using/exporting-logs.md) Hiermee kunt u loggegevens exporteren via een eenvoudige workflow, zodat u de resultaten van uw marketingcampagnes kunt analyseren in uw eigen rapportage- of BI-gereedschappen.

Hefboomwerking [Pakketten](../../automating/using/managing-packages.md) om middelen tussen verschillende campagneinstanties, bijvoorbeeld, te ruilen om de configuratie van een geval te herhalen, of gegevens over te brengen van een server aan een andere met inbegrip van douanemiddelen.

Tot slot: [Lijsten exporteren](../../automating/using/exporting-lists.md) kunt u lijsten vanuit Campaigns Standard exporteren, zoals bijvoorbeeld de lijst met testprofielen, de lijst met e-mailadressen in quarantaine, enz.

Meer informatie:

* [Gegevens importeren en exporteren](../../automating/using/about-data-import-and-export.md)
* [Gebruiksscenario: aangepaste bronnen exporteren en importeren](../../automating/using/exporting-importing-custom-resources.md)

## Verdere bronnen

* [Zelfstudievideo&#39;s over processen en gegevensbeheer](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/managing-processes-and-data/creating-a-workflow.html?lang=nl)
* [Technische workflows](../../administration/using/technical-workflows.md)
* [Aan de slag met het Campaign Standard-gegevensmodel](../../developing/using/get-started-data-model.md)
