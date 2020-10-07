---
title: Technische workflows
description: Technische workflows zijn kant-en-klare workflows die zijn ontworpen om technische achtergrondprocessen in Adobe Campaign af te handelen, zodat het platform correct functioneert.
page-status-flag: never-activated
uuid: 6e763dc1-e1d3-4d94-bc0b-ef5b1703d8e5
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: application-settings
discoiquuid: e9f147bd-6a5b-4b82-b9bb-311e38e22c62
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '678'
ht-degree: 100%

---


# Technische workflows{#technical-workflows}

De technische workflows worden kant-en-klaar geleverd met Adobe Campaign. Technische workflows zijn bewerkingen of taken die regelmatig en volgens een planning op de server moeten worden uitgevoerd.

Met deze workflows kunt u onderhoudsbewerkingen uitvoeren op de database, de traceringsinformatie gebruiken in de leveringen en de voorlopige taken bijwerken voor de leveringen.

Functionele beheerders hebben toegang tot technische workflows via het menu **[!UICONTROL Administration > Application settings > Workflows]**.

>[!NOTE]
>
>Als functionele beheerder kunt u technische workflows opnieuw starten of pauzeren en de eigenschappen en structuur van deze workflows wijzigen.

![](assets/technical_workflows.png)

## Lijst met technische workflows{#list-of-technical-workflows}

Technische workflows worden gebruikt om door uzelf geactiveerde achtergrond- en technische processen in Adobe Campaign af te handelen.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Label</strong><br /> </td> 
   <td> <strong>Id</strong><br /> </td> 
   <td> <strong>Beschrijving</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">A/B-tests</span> <br /> </td> 
   <td> <span class="uicontrol">abTesting</span> <br /> </td> 
   <td> In deze workflow worden de trackinglogboeken van elke variant geanalyseerd. Aan het einde van de A/B-testperiode wordt automatisch de winnende variant berekend. Standaard wordt deze workflow elke dag gestart.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Facturering</span> <br /> </td> 
   <td> <span class="uicontrol">billing</span> <br /> </td> 
   <td> Deze workflow verzendt het rapport over de systeemactiviteit per e-mail naar de gebruiker die het systeem ‘factureert’. Standaard wordt de workflow elke dag automatisch om 1.00 uur gestart.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Database opschonen</span> <br /> </td> 
   <td> <span class="uicontrol">cleanup</span> <br /> </td> 
   <td> Deze workflow is de workflow voor databaseonderhoud: deze stelt verschillende statistieken en processen in werking en schrapt verouderde data uit de database volgens de configuratie die is gedefinieerd. Standaard wordt deze workflow elke dag automatisch om 4.00 uur gestart.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Prognose</span> <br /> </td> 
   <td> <span class="uicontrol">forecasting</span> <br /> </td> 
   <td> Deze workflow voert de analyse uit van de leveringen die zijn opgeslagen in de voorlopige prognose (het maken van de voorlopige logboeken). Standaard wordt deze workflow elke dag om 1.00 uur gestart. <br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Een gedeelde doelgroep importeren</span> <br /> </td> 
   <td> <span class="uicontrol">importSharedAudience</span> <br /> </td> 
   <td> Deze workflow synchroniseert de Adobe Experience Cloud-doelgroepsdata die zijn geïmporteerd in Adobe Campaign. Standaard wordt deze workflow elk uur gestart.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Instant rapport delen</span> <br /> </td> 
   <td> <span class="uicontrol">reportSendingNow</span> <br /> </td> 
   <td> Deze workflow wordt gestart zodra een rapport volgens planning moet worden verzonden. De workflow zet uw rapport om in een pdf-bestand en verzendt het in een e-mail naar de doelontvangers.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">KPI-afstemming met Adobe Analytics</span> <br /> </td> 
   <td> <span class="uicontrol">kpiReconciliation</span> <br /> </td> 
   <td> Deze workflow haalt KPI’s eenmaal per dag op uit de Reporting-service en stemt deze af op de data van Adobe Analytics. Het verschil wordt vervolgens gepusht als dat nodig is. Standaard wordt de workflow elke dag om 4.20 uur gestart.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">NMAC-opt-outs beheren</span> <br /> </td> 
   <td> <span class="uicontrol">mobileAppOptOutMgt</span> <br /> </td> 
   <td> Deze workflow werkt uitschrijvingen op meldingen op mobiele apparaten bij. Standaard wordt de workflow om de 6 uur tussen 1.00 uur en middernacht gestart.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Lokale archivering in Berichtencentrum</span> <br /> </td> 
   <td> <span class="uicontrol">mcSynch_local</span> <br /> </td> 
   <td> Deze workflow archiveert realtimegebeurtenissen in een historische tabel. Standaard wordt deze workflow elk uur gestart.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Rapportageaggregaten</span> <br /> </td> 
   <td> <span class="uicontrol">reportingAggregates</span> <br /> </td> 
   <td> Deze workflow werkt de aggregaten bij die in de rapporten worden gebruikt. Standaard wordt deze workflow automatisch om 2.00 uur gestart.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">KPI’s delen met Adobe Analytics</span> <br /> </td> 
   <td> <span class="uicontrol">kpiSharing</span> <br /> </td> 
   <td> Met deze workflow worden KPI-data om de 15 minuten van Adobe Campaign Standard naar Adobe Analytics gepusht.<br /> </td> 
  </tr> 
    </tr> 
   <tr> 
   <td> <span class="uicontrol">Synchroniseren met Launch</span> <br /> </td> 
   <td> <span class="uicontrol">SyncWithLaunch</span> <br /> </td> 
   <td> Deze workflow synchroniseert de mobiele eigenschappen in Adobe Launch die zijn geïmporteerd in Adobe Campaign Standard. De workflow wordt elke 15 minuten gestart.<br /> </td> 
  </tr>
  <tr> 
   <td> <span class="uicontrol">Uitvoering van levering bijwerken</span> <br /> </td> 
   <td> <span class="uicontrol">updateDeliveryExecInfo</span> <br /> </td> 
   <td> Deze workflow werkt de tracking van de levering bij. Standaard wordt deze workflow elke 10 minuten gestart.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Leveringsindicatoren bijwerken</span> <br /> </td> 
   <td> <span class="uicontrol">updateDeliveryIndicators</span> <br /> </td> 
   <td> Deze workflow werkt de KPI’s (Key Performance Indicators) van de levering bij. Standaard wordt deze workflow elk uur gestart.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Gebeurtenisstatus bijwerken</span> <br /> </td> 
   <td> <span class="uicontrol">updateEventsStatus</span> <br /> </td> 
   <td> Met deze workflow kunt u een status aan een gebeurtenis toewijzen. De volgende gebeurtenisstatussen zijn beschikbaar:<br /> <strong>Pending</strong>: De gebeurtenis bevindt zich in een wachtrij. Er is nog geen berichtsjabloon aan toegewezen.<br /> <span class="uicontrol">Pending delivery</span>: De gebeurtenis bevindt zich in de wachtrij, er is een berichtsjabloon aan toegewezen en de gebeurtenis wordt verwerkt door de levering.<br /> <strong>Sent</strong>: Deze status wordt gekopieerd uit de leveringslogboeken. Het betekent dat de levering is verzonden.<br /> <strong>Ignored by the delivery</strong>: Deze status wordt gekopieerd uit de leveringslogboeken. Het betekent dat de levering is genegeerd.<br /> <strong>Delivery failed</strong>: Deze status wordt gekopieerd uit de leveringslogboeken. Het betekent dat de levering is mislukt.<br /> <span class="uicontrol">Event not taken into account</span>: De gebeurtenis kan niet worden gekoppeld aan een berichtsjabloon. De gebeurtenis wordt niet verwerkt.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Update for deliverability</span> <br /> </td> 
   <td> <span class="uicontrol">deliverabilityUpdate</span> <br /> </td> 
   <td> Met deze workflow kunt u een lijst met kwalificatieregels voor niet-bezorging maken, plus de lijst met domeinen en MX in het platform. Deze workflow werkt alleen als HTTPS is geopend. Standaard wordt deze workflow automatisch om 2.00 uur gestart.<br /> </td> 
  </tr> 
 </tbody> 
</table>

