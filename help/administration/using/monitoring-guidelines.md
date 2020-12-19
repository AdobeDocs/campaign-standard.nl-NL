---
solution: Campaign Standard
product: campaign
title: Bewakingsrichtlijnen
description: In deze paragraaf worden algemene richtsnoeren voor de monitoring van Campaign Standard uiteengezet.
audience: production
content-type: reference
topic-tags: introduction
index: y
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 9%

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

**System**
notificationsCampaign Standard interface biedt een meldingsvenster waarmee u op de hoogte kunt worden gehouden van wat er in het systeem gebeurt: status van gebeurtenissen, systeemupdates, vereiste actie, enz. [Meer informatie](../../start/using/interface-description.md#top-bar)


**Technische**
workflowsTechnische workflows zijn bewerkingen of taken die volgens planning regelmatig op de server worden uitgevoerd. Om ervoor te zorgen dat uw instantie gezond is en correct werkt, moet u ervoor zorgen dat zij altijd in gebruik zijn. [Meer informatie](../../administration/using/technical-workflows.md)

**ConfiguratieschermIn**
het Configuratiescherm kunt u verschillende instellingen van uw exemplaar beheren: URL-machtigingen, controleer de instantiedetails zoals de buildversies van uw servers, controleer het gebruik van actieve profielen, enzovoort. Hiermee kunt u ook de beschikbare ruimte op de SFTP-servers controleren die met uw instantie zijn verbonden. [Meer informatie](https://docs.adobe.com/content/help/nl-NL/control-panel/using/control-panel-home.html).

>[!NOTE]
>
>Houd er rekening mee dat het Configuratiescherm alleen toegankelijk is voor gebruikers met beheerdersrechten en beschikbaar is voor alle klanten die Adobe Managed Services gebruiken.

**Technische**
objectenHet  **[!UICONTROL Diagnosis]** menu is een belangrijk hulpmiddel voor het bewaken en analyseren van de verschillende technische objecten die door de toepassing worden gegenereerd: gegevensschema&#39;s, webpagina&#39;s, batchtaken, enz. [Meer informatie](../../developing/using/monitoring-data-model-changes.md)

**Met**
exportcontroles kunt u controleren of er exportcontroles op uw exemplaren zijn uitgevoerd: bestanden die zijn geüpload van workflows, exporteerlijsten en bestanden die zijn gedownload van direct-mailberichten.
[Meer informatie](../../administration/using/auditing-export-logs.md)

****
LicentiesMet het  **[!UICONTROL Licenses]** menu controleert u de informatie over uw instanties: geïnstalleerde licenties, build-versies en geaccepteerde termen.
[Meer informatie](../../administration/using/licenses.md)

## Workflows controleren {#monitoring-workflows}

<img src="assets/do-not-localize/icon_workflows.svg" width="60px">

**Aanbevolen werkwijzen en**
probleemoplossingVolg de best practices en richtlijnen voor het oplossen van problemen bij het gebruik van workflows om de prestaties te verbeteren.
[Meer informatie](../../automating/using/best-practices-workflows.md)

**Logboeken en**
takenControleren van workflows is een belangrijke stap om uw workflows te analyseren en ervoor te zorgen dat deze correct worden uitgevoerd.
[Meer informatie](../../automating/using/monitoring-workflow-execution.md#workflow-log-and-tasks)

**Met**
NotificationsCampaign Standard kunt u meldingen verzenden naar supervisors om de uitvoering van uw workflows te controleren en te controleren of er een fout is die uw aandacht vereist.
[Meer informatie](../../automating/using/monitoring-workflow-execution.md#error-management)

## Leveringen controleren{#monitoring-deliveries}

<img src="assets/do-not-localize/icon_send.svg" width="60px">

****
DeliverabilityCampaign Standard biedt verschillende hulpmiddelen om u te helpen het aantal succesvol afgeleverde berichten te verbeteren: rapporten over de leveringsrekening, tijdoptimalisatie verzenden, voorvertoning van berichten, rendering van e-mail, quarantainebeheer, enz.
[Meer informatie](../../sending/using/about-deliverability.md)

****
DeliveriesOnce uw berichten worden verzonden, staat gedetailleerde logboeken u toe om de leveringen te controleren en het succes van uw campagne te meten, evenals het gedrag van de berichtontvangers te volgen.
[Meer informatie](../../sending/using/monitoring-a-delivery.md)

**LeveringswaarschuwingMet de**
waarschuwingsfunctie voor levering kunt u waarschuwingen instellen die automatisch naar een groep gebruikers worden verzonden met betrekking tot de uitvoering van leveringen: het niet verzenden of voorbereiden, slechte schommelingsverhouding, lage productie, enz.
[Meer informatie](../../sending/using/receiving-alerts-when-failures-happen.md)

**Dynamische**
rapporteringDynamische rapportering verstrekt diverse rapporten om u te helpen op de hoogte worden gehouden van hoe uw leveringen presteren: stormen, de meest bekeken leveringen per ontvanger, de omzet van de leveringen, enz.
[Meer informatie](../../reporting/using/about-dynamic-reports.md)
