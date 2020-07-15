---
title: Monitoringrichtsnoeren
description: In deze paragraaf worden algemene richtsnoeren voor de bewaking van Campaign Standard uiteengezet.
page-status-flag: never-activated
uuid: cf0d782d-47bf-40ae-ab6f-d1d47fa15792
contentOwner: sauviat
products: SG_CAMPAIGN/CLASSIC
audience: production
content-type: reference
topic-tags: introduction
discoiquuid: 8b33e6af-15c3-4b30-8ad6-d76a1f33be21
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b4bac585ec25340d1f1d047f9a1f8dcd8e243821
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 5%

---


# Monitoringrichtsnoeren {#monitoring-guidelines}

<table>
<tr><td><img src="assets/do-not-localize/icon_system.svg" width="60px"><p><a href="#monitoring-system">Toezicht op het systeem</a></p></td>
<td><img src="assets/do-not-localize/icon_workflows.svg" width="60px"><p><a href="#moniroting-workflows">Workflows controleren</a></p></td>
<td><img src="assets/do-not-localize/icon_send.svg" width="60px"><p><a href="#monitoring-deliveries">Bewaking van leveringen</a></p></td></tr>
</table>

Campaign Standard biedt verschillende manieren om uw instanties te controleren om ervoor te zorgen dat uw systeem gezond is en uiteindelijk problemen op te lossen die zich kunnen voordoen bij het instellen van workflows, het verzenden van leveringen, enz.

## Toezicht op het systeem {#monitoring-system}

<img src="assets/do-not-localize/icon_system.svg" width="60px">

**De interface van de berichten** Campaign Standard van het systeem verstrekt een berichtruit die u toelaat om op de hoogte te worden gehouden van wat in het systeem gebeurt: status van gebeurtenissen, systeemupdates, vereiste actie, enz. [Meer informatie](../../start/using/interface-description.md#top-bar)


**Technische workflows** Technische workflows zijn bewerkingen of taken die volgens de planning regelmatig op de server moeten worden uitgevoerd. Om ervoor te zorgen dat uw instantie gezond is en correct werkt, moet u ervoor zorgen dat zij altijd in gebruik zijn. [Meer informatie](../../administration/using/technical-workflows.md)

**In** het regelpaneel kunt u verschillende instellingen van uw exemplaar beheren: URL-machtigingen, controleer de instantiedetails zoals de buildversies van uw servers, controleer het gebruik van actieve profielen, enzovoort. Hiermee kunt u ook de beschikbare ruimte op de SFTP-servers controleren die met uw instantie zijn verbonden. [Meer informatie](https://docs.adobe.com/content/help/en/control-panel/using/control-panel-home.html).

>[!NOTE]
>
>Houd er rekening mee dat het Configuratiescherm alleen toegankelijk is voor Admin-gebruikers en beschikbaar is voor alle klanten die Adobe Managed Services gebruiken.

**Technische objecten** Het **[!UICONTROL Diagnosis]** menu is een belangrijk hulpmiddel voor het bewaken en analyseren van de verschillende technische objecten die door de toepassing worden gegenereerd: gegevensschema&#39;s, webpagina&#39;s, batchtaken, enz. [Meer informatie](../../developing/using/monitoring-data-model-changes.md)

**Met exportcontroles**kunt u controleren of er exportcontroles op uw exemplaar worden uitgevoerd: bestanden die zijn geüpload van workflows, exporteerlijsten en bestanden die zijn gedownload van direct-mailberichten.
[Meer informatie](../../administration/using/auditing-export-logs.md)

**Licenties** Met het **[!UICONTROL Licenses]** menu controleert u de informatie over uw instanties: geïnstalleerde licenties, build-versies en geaccepteerde termen.
[Meer informatie](../../administration/using/licenses.md)

## Workflows controleren {#monitoring-workflows}

<img src="assets/do-not-localize/icon_workflows.svg" width="60px">

**Aanbevolen werkwijzen en probleemoplossing**Volg de best practices en richtlijnen voor het oplossen van problemen bij het gebruik van workflows om de prestaties te verbeteren.
[Meer informatie](../../automating/using/best-practices-workflows.md)

**Logboeken en taken**Worklow logs monitoring is een belangrijke stap om uw workflows te analyseren en ervoor te zorgen dat deze correct worden uitgevoerd.
[Meer informatie](../../automating/using/monitoring-workflow-execution.md#workflow-log-and-tasks)

**Met Meldingen**Campaign Standard kunt u meldingen verzenden naar supervisors om te controleren of uw werkbestanden worden uitgevoerd en of er een fout is die uw aandacht vereist.
[Meer informatie](../../automating/using/monitoring-workflow-execution.md#error-management)

## Bewaking van leveringen {#monitoring-deliveries}

<img src="assets/do-not-localize/icon_send.svg" width="60px">

**Leverbaarheid**Campaign Standard biedt verschillende hulpmiddelen voor de levering, waarmee u het aantal succesvol afgeleverde berichten kunt verbeteren: rapporten over de leveringsrekening, tijdoptimalisatie verzenden, voorvertoning van berichten, rendering van e-mail, quarantainebeheer, enz.
[Meer informatie](../../sending/using/about-deliverability.md)

**Leveringen**Zodra uw berichten worden verzonden, staan de gedetailleerde logboeken u toe om de leveringen te controleren en het succes van uw campagne te meten, evenals het gedrag van de berichtontvangers te volgen.
[Meer informatie](../../sending/using/monitoring-a-delivery.md)

**De alarmering**van de leveringMet de het alarmerende eigenschap van de Levering, kunt u alarm plaatsen die automatisch naar een groep gebruikers over de uitvoering van levering zullen worden verzonden: het niet verzenden of voorbereiden, slechte schommelingsverhouding, lage productie, enz.
[Meer informatie](../../sending/using/receiving-alerts-when-failures-happen.md)

**Dynamische rapportage**Dynamische rapportage biedt verschillende rapporten om u op de hoogte te houden van de prestaties van uw leveringen: stormen, de meest bekeken leveringen per ontvanger, de omzet van de leveringen, enz.
[Meer informatie](../../reporting/using/about-dynamic-reports.md)
