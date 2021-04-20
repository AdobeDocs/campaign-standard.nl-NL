---
solution: Campaign Standard
product: campaign
title: Bewakingsrichtlijnen
description: In deze paragraaf worden algemene richtsnoeren voor de monitoring van Campaign Standard uiteengezet.
audience: production
content-type: reference
topic-tags: introduction
index: y
feature: Access Management
role: Administrator
level: Experienced
translation-type: tm+mt
source-git-commit: 7979d8fd88b93a1cdd7b5a11bb66e894ab12f1c2
workflow-type: tm+mt
source-wordcount: '511'
ht-degree: 14%

---


# Bewakingsrichtlijnen {#monitoring-guidelines}

<table>
<tr><td><img src="assets/do-not-localize/icon_system.svg" width="60px"><p><a href="#monitoring-system">Toezicht op het systeem</a></p></td>
<td><img src="assets/do-not-localize/icon_workflows.svg" width="60px"><p><a href="#moniroting-workflows">Workflows controleren</a></p></td>
<td><img src="assets/do-not-localize/icon_send.svg" width="60px"><p><a href="#monitoring-deliveries">Leveringen controleren</a></p></td></tr>
</table>

Campaign Standard biedt verschillende manieren om uw instanties te controleren om ervoor te zorgen dat uw systeem gezond is en uiteindelijk problemen op te lossen die kunnen optreden bij het instellen van workflows, het verzenden van leveringen, enz.

## Bewaking van het systeem {#monitoring-system}

<img src="assets/do-not-localize/icon_system.svg" width="60px">

**Systeemmeldingen**

De interface van Campaign Standard verstrekt een berichtruit die u toelaat om op de hoogte worden gehouden van wat in het systeem gebeurt: status van gebeurtenissen, systeemupdates, vereiste actie, enz. [Meer informatie](../../start/using/interface-description.md#top-bar)


**Technische workflows**

Technische workflows zijn bewerkingen of taken die regelmatig en volgens een planning op de server moeten worden uitgevoerd. Om ervoor te zorgen dat uw instantie gezond is en correct werkt, moet u ervoor zorgen dat zij altijd in gebruik zijn. [Meer informatie](../../administration/using/technical-workflows.md)

**Configuratiescherm**

In het Configuratiescherm kunt u verschillende instellingen van uw exemplaar beheren: URL-machtigingen, controleer de instantiedetails zoals de buildversies van uw servers, controleer het gebruik van actieve profielen, enz. Hiermee kunt u ook de beschikbare ruimte op de SFTP-servers controleren die met uw instantie zijn verbonden. [Meer informatie](https://docs.adobe.com/content/help/nl-NL/control-panel/using/control-panel-home.html).

>[!NOTE]
>
>Het Configuratiescherm is toegankelijk voor alle beheergebruikers. De stappen om Admin toegang tot een gebruiker te verlenen zijn gedetailleerd in [deze pagina](https://experienceleague.adobe.com/docs/control-panel/using/discover-control-panel/managing-permissions.html?lang=en#discover-control-panel).

**Technische objecten**

Het menu **[!UICONTROL Diagnosis]** is een belangrijk hulpmiddel om de verschillende technische voorwerpen te controleren en te analyseren die door de toepassing worden geproduceerd: gegevensschema&#39;s, webpagina&#39;s, batchtaken, enz. [Meer informatie](../../developing/using/monitoring-data-model-changes.md)

**Exportcontroles**

Met exportcontroles kunt u de uitgevoerde exportbewerkingen op uw exemplaren controleren: bestanden die zijn geüpload van workflows, exporteerlijsten en bestanden die zijn gedownload van direct-mailberichten.
[Meer informatie](../../administration/using/auditing-export-logs.md)

**Licenties**

Met het **[!UICONTROL Licenses]** menu, monitorinformatie over uw instanties: geïnstalleerde licenties, build-versies en geaccepteerde termen.
[Meer informatie](../../administration/using/licenses.md)

## Workflows controleren {#monitoring-workflows}

<img src="assets/do-not-localize/icon_workflows.svg" width="60px">

**Best practices en probleemoplossing**

Volg de best practices en richtlijnen voor het oplossen van problemen bij het gebruik van workflows om de prestaties te verbeteren.
[Meer informatie](../../automating/using/best-practices-workflows.md)

**Logboeken en taken**

Controle van workflowlogbestanden is een belangrijke stap om uw workflows te analyseren en ervoor te zorgen dat deze correct worden uitgevoerd.
[Meer informatie](../../automating/using/monitoring-workflow-execution.md#workflow-log-and-tasks)

**Meldingen**

Met Campaign Standard kunt u meldingen verzenden naar supervisors om te controleren of de workflows worden uitgevoerd en of er een fout is die uw aandacht vereist.
[Meer informatie](../../automating/using/monitoring-workflow-execution.md#error-management)

## Leveringen controleren{#monitoring-deliveries}

<img src="assets/do-not-localize/icon_send.svg" width="60px">

**Bezorging**

Campaign Standard biedt verschillende gereedschappen voor het leveren van informatie waarmee u het aantal gelukte berichten kunt verbeteren: rapporten over de leveringstijd, tijdoptimalisatie verzenden, voorvertoning van berichten, rendering van e-mail, quarantainebeheer, enz.
[Meer informatie](../../sending/using/about-deliverability.md)

**Leveringen**

Zodra uw berichten worden verzonden, staat het gedetailleerde logboeken u toe om de leveringen te controleren en het succes van uw campagne te meten, evenals het gedrag van de berichtontvangers te volgen.
[Meer informatie](../../sending/using/monitoring-a-delivery.md)

**Afleveringswaarschuwing**

Met de functie voor leveringswaarschuwingen kunt u waarschuwingen instellen die automatisch naar een groep gebruikers worden verzonden met betrekking tot de uitvoering van leveringen: het niet verzenden of voorbereiden, slechte schommelingsverhouding, lage productie, enz.
[Meer informatie](../../sending/using/receiving-alerts-when-failures-happen.md)

**Dynamische rapportage**

De dynamische rapportering verstrekt diverse rapporten om u te helpen op de hoogte worden gehouden van hoe uw leveringen presteren: schommelingen, de meest bekeken leveringen door de ontvangers, de omzet van de leveringen, enz.
[Meer informatie](../../reporting/using/about-dynamic-reports.md)
