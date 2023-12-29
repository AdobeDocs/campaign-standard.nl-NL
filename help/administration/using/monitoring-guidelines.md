---
title: Controlerichtlijnen
description: Deze pagina bevat algemene richtsnoeren voor het toezicht op Campaign Standard
audience: production
feature: Access Management
role: Admin
level: Experienced
exl-id: 5f25f2b2-ca41-4baf-ade2-42bbafb4790d
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 12%

---

# Controlerichtlijnen {#monitoring-guidelines}

<table>
<tr><td><img src="assets/do-not-localize/icon_system.svg" width="60px"><p><a href="#monitoring-system">Toezicht op het systeem</a></p></td>
<td><img src="assets/do-not-localize/icon_workflows.svg" width="60px"><p><a href="#moniroting-workflows">Workflows controleren</a></p></td>
<td><img src="assets/do-not-localize/icon_send.svg" width="60px"><p><a href="#monitoring-deliveries">Bewaking van leveringen</a></p></td></tr>
</table>

Campaign Standard biedt verschillende manieren om uw instanties te controleren om ervoor te zorgen dat uw systeem gezond is en uiteindelijk problemen op te lossen die kunnen optreden bij het instellen van workflows, het verzenden van leveringen, enz.

## Toezicht op het systeem {#monitoring-system}

<img src="assets/do-not-localize/icon_system.svg" width="60px">

**Systeemmeldingen**

De interface van het Campaign Standard verstrekt een berichtruit die u toelaat om op de hoogte worden gehouden van wat in het systeem gebeurt: gebeurtenisstatussen, systeemupdates, vereiste actie, enz. [Meer informatie](../../start/using/interface-description.md#top-bar)


**Technische workflows**

Technische workflows zijn bewerkingen of taken die volgens de planning regelmatig op de server moeten worden uitgevoerd. Om ervoor te zorgen dat uw instantie gezond is en correct werkt, moet u ervoor zorgen dat zij altijd in gebruik zijn. [Meer informatie](../../administration/using/technical-workflows.md)

**Configuratiescherm**

In het Configuratiescherm kunt u verschillende instellingen van uw instantie beheren: URL-machtigingen, controle de instantiedetails zoals de buildversies van uw servers, controle van het gebruik van actieve profielen, enzovoort. Hiermee kunt u ook de beschikbare ruimte op de SFTP-servers controleren die met uw instantie zijn verbonden. [Meer informatie](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=nl).

>[!NOTE]
>
>Het configuratiescherm is toegankelijk voor alle gebruikers met beheerdersrechten. De stappen om toegang met beheerdersrechten aan een gebruiker te verlenen worden gedetailleerd beschreven op [deze pagina](https://experienceleague.adobe.com/docs/control-panel/using/discover-control-panel/managing-permissions.html?lang=nl#discover-control-panel).

**Technische objecten**

De **[!UICONTROL Diagnosis]** het menu is een belangrijk hulpmiddel voor het bewaken en analyseren van de verschillende technische objecten die door de toepassing worden gegenereerd: gegevensschema&#39;s, webpagina&#39;s, batchtaken, enz. [Meer informatie](../../developing/using/monitoring-data-model-changes.md)

**Exportcontroles**

Met exportcontroles kunt u controleren welke exportbewerkingen op uw instanties worden uitgevoerd: bestanden die zijn geüpload uit workflows, exporteerlijsten en bestanden die zijn gedownload uit direct-mailberichten.
[Meer informatie](../../administration/using/auditing-export-logs.md)

**Licenties**

Met de **[!UICONTROL Licenses]** -menu, informatie over uw instanties controleren: geïnstalleerde licenties, build-versies en geaccepteerde termen.
[Meer informatie](../../administration/using/licenses.md)

## Workflows controleren {#monitoring-workflows}

<img src="assets/do-not-localize/icon_workflows.svg" width="60px">

**Aanbevolen werkwijzen en problemen oplossen**

Volg de best practices en richtlijnen voor het oplossen van problemen bij het gebruik van workflows om de prestaties te verbeteren.
[Meer informatie](../../automating/using/best-practices-workflows.md)

**Logboeken en taken**

Controle van workflowlogbestanden is een belangrijke stap om uw workflows te analyseren en ervoor te zorgen dat deze correct worden uitgevoerd.
[Meer informatie](../../automating/using/monitoring-workflow-execution.md#workflow-log-and-tasks)

**Meldingen**

Met Campaign Standard kunt u meldingen verzenden naar supervisors om te controleren of de workflows worden uitgevoerd en of er een fout is die uw aandacht vereist.
[Meer informatie](../../automating/using/monitoring-workflow-execution.md#error-management)

## Bewaking van leveringen {#monitoring-deliveries}

<img src="assets/do-not-localize/icon_send.svg" width="60px">

**Aflevering**

Campaign Standard biedt verschillende gereedschappen voor het leveren van gegevens waarmee u het aantal gelukte berichten kunt verbeteren: rapporten over de leveringstijd, optimalisatie van de verzendtijd, voorvertoning van berichten, rendering van e-mail, quarantainebeheer, enz.
[Meer informatie](../../sending/using/about-deliverability.md)

**Leveringen**

Zodra uw berichten worden verzonden, staat het gedetailleerde logboeken u toe om de leveringen te controleren en het succes van uw campagne te meten, evenals het gedrag van de berichtontvangers te volgen.
[Meer informatie](../../sending/using/monitoring-a-delivery.md)

**Afleveringswaarschuwing**

Met de voorziening voor het waarschuwen van de levering kunt u waarschuwingen instellen die automatisch naar een groep gebruikers worden verzonden met betrekking tot de uitvoering van leveringen: verzending of voorbereiding mislukt, onjuiste verhouding tussen boetes, lage doorvoer, enzovoort.
[Meer informatie](../../sending/using/receiving-alerts-when-failures-happen.md)

**Dynamische rapportage**

Dynamische rapportage biedt verschillende rapporten die u helpen op de hoogte te blijven van de manier waarop uw leveringen worden uitgevoerd: stormen, de meeste bekeken leveringen door ontvangers, de doorvoer van de leveringen, enz.
[Meer informatie](../../reporting/using/about-dynamic-reports.md)
