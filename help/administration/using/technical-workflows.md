---
title: Technische workflows
description: Technische workflows zijn out-of-the-box workflows die zijn ontworpen om technische achtergrondprocessen in Adobe Campaign af te handelen, zodat het platform correct functioneert.
page-status-flag: never-activated
uuid: 6e763dc1-e1d3-4d94-bc0b-ef5b1703d8e5
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: application-settings
discoiquuid: e9f147bd-6a5b-4b82-b9bb-311e38e22c62
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b4cbc56973a57cde8af6cefa9ff89c7d29ab7b79

---


# Technische workflows{#technical-workflows}

De technische workflows worden geleverd uit-van-de-doos met de Campagne van Adobe. Technische workflows zijn bewerkingen of taken die volgens de planning regelmatig op de server moeten worden uitgevoerd.

Met deze services kunt u onderhoudsbewerkingen uitvoeren op de database, de traceringsinformatie gebruiken in de leveringen en de voorlopige taken bijwerken voor de leveringen.

Functionele beheerders hebben toegang tot technische workflows via het **[!UICONTROL Administration > Application settings > Workflows]** menu.

>[!NOTE]
>
>Als functionele beheerder kunt u technische workflows opnieuw starten of pauzeren en de eigenschappen en structuur van deze workflows wijzigen.

![](assets/technical_workflows.png)

## Lijst van technische werkstromen {#list-of-technical-workflows}

Technische workflows worden gebruikt om door uzelf geactiveerde achtergrond- en technische processen in Adobe Campagne af te handelen.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Label</strong><br /> </td> 
   <td> <strong>ID</strong><br /> </td> 
   <td> <strong>Beschrijving</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">A/B-tests</span><br /> </td> 
   <td> <span class="uicontrol">abTesting</span><br /> </td> 
   <td> In deze workflow worden de trackinglogboeken van elke variant geanalyseerd. Aan het einde van de testperiode A/B wordt automatisch de winnende variant berekend. Standaard wordt deze elke dag gestart.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Facturering</span><br /> </td> 
   <td> <span class="uicontrol">facturering</span><br /> </td> 
   <td> Deze workflow stuurt het rapport over de systeemactiviteit per e-mail naar de gebruiker die het systeem 'factureert'. Door gebrek, wordt het automatisch begonnen elke dag om 1am.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Database opschonen</span><br /> </td> 
   <td> <span class="uicontrol">opruimen</span><br /> </td> 
   <td> Deze workflow is de workflow voor databaseonderhoud: het stelt verschillende statistieken en processen in werking, en schrapt verouderde gegevens uit het gegevensbestand volgens de configuratie die is bepaald. Standaard wordt deze elke dag 4 uur 's nachts automatisch gestart.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Voorspelling</span><br /> </td> 
   <td> <span class="uicontrol">voorspelling</span><br /> </td> 
   <td> Deze workflow voert de analyse uit van de leveringen die zijn opgeslagen in de voorlopige prognose (het maken van de voorlopige logboeken). Door gebrek, is het begonnen elke dag om 1 uur. <br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Een gedeeld publiek</span> importeren <br /> </td> 
   <td> <span class="uicontrol">importSharedAudience</span><br /> </td> 
   <td> Deze workflow synchroniseert de Adobe Experience Cloud-publieksgegevens die zijn geïmporteerd in Adobe Campaign. Standaard wordt deze elke uur gestart.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Meteen rapport delen</span><br /> </td> 
   <td> <span class="uicontrol">reportSendingNow</span><br /> </td> 
   <td> Deze workflow wordt gestart zodra een rapport is verzonden. Het zet uw rapport in een pdf- dossier om en verzendt het in een e-mail naar de gerichte ontvangers.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">KPI's-afstemming met Adobe Analytics</span><br /> </td> 
   <td> <span class="uicontrol">kpiReconciliatie</span><br /> </td> 
   <td> Deze werkstroom haalt KPIs van de dienst van de Rapportering eens per dag en past hen met de gegevens van de Analytics van Adobe aan. Het duwt het verschil als dat nodig is. Standaard wordt het elke dag om 4.20 uur gestart.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">NMAC-opt-outs</span> beheren <br /> </td> 
   <td> <span class="uicontrol">mobileAppOptOutMgt</span><br /> </td> 
   <td> Deze workflow werkt abonnementen op meldingen op mobiele apparaten bij. Door gebrek, is het begonnen om de 6 uur tussen 1am en middernacht.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Berichtencentrum lokale archivering</span><br /> </td> 
   <td> <span class="uicontrol">mcSynch_local</span><br /> </td> 
   <td> Deze workflow archiveert realtime-gebeurtenissen in een historische tabel. Standaard wordt deze elke uur gestart.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Rapportageaggregaten</span><br /> </td> 
   <td> <span class="uicontrol">reportingAggregates</span><br /> </td> 
   <td> Deze workflow werkt de aggregaten bij die in de rapporten worden gebruikt. Standaard wordt deze automatisch om 2 uur gestart.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">KPI's delen met Adobe Analytics</span><br /> </td> 
   <td> <span class="uicontrol">kpiSharing</span><br /> </td> 
   <td> Met deze workflow worden om de 15 minuten KPI-gegevens opgehaald van Adobe Campaign Standard naar Adobe Analytics.<br /> </td> 
  </tr> 
    </tr> 
   <tr> 
   <td> <span class="uicontrol">Synchroniseren met starten</span><br /> </td> 
   <td> <span class="uicontrol">SyncWithLaunch</span><br /> </td> 
   <td> Deze workflow synchroniseert de Adobe Launch mobile-eigenschappen die zijn geïmporteerd in Adobe Campagne Standard. Het wordt elke 15 minuten gestart.<br /> </td> 
  </tr>
  <tr> 
   <td> <span class="uicontrol">Uitvoering</span> van levering bijwerken <br /> </td> 
   <td> <span class="uicontrol">updateDeliveryExecInfo</span><br /> </td> 
   <td> Deze workflow werkt het bijhouden van de levering bij. Deze wordt standaard elke 10 minuten gestart.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Leveringsindicatoren</span> bijwerken <br /> </td> 
   <td> <span class="uicontrol">updateDeliveryIndicators</span><br /> </td> 
   <td> Deze workflow werkt de KPI's (Key Performance Indicator) van de levering bij. Standaard wordt deze elke uur gestart.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Gebeurtenisstatus</span> bijwerken <br /> </td> 
   <td> <span class="uicontrol">updateEventsStatus</span><br /> </td> 
   <td> Met deze workflow kunt u een status aan een gebeurtenis toewijzen. De volgende gebeurtenisstatussen zijn beschikbaar:<br /> In <strong>behandeling</strong>: De gebeurtenis bevindt zich in een wachtrij. Er is nog geen berichtsjabloon toegewezen.<br /> In <span class="uicontrol">afwachting van levering</span> : De gebeurtenis is in de rij, is een berichtmalplaatje toegewezen aan het en het wordt verwerkt door de levering.<br /> <strong>Verzonden</strong>: Deze status wordt gekopieerd uit de leveringslogboeken. Het betekent dat de levering is verzonden.<br /> Door de levering <strong></strong>genegeerd: Deze status wordt gekopieerd uit de leveringslogboeken. Het betekent dat de levering werd genegeerd.<br /> <strong>Aflevering mislukt</strong>: Deze status wordt gekopieerd uit de leveringslogboeken. Het betekent dat de levering is mislukt.<br /> <span class="uicontrol">Gebeurtenis niet in aanmerking genomen</span> : De gebeurtenis kan niet worden gekoppeld aan een berichtsjabloon. De gebeurtenis wordt niet verwerkt.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Update voor leverbaarheid</span><br /> </td> 
   <td> <span class="uicontrol">leverabilityUpdate</span><br /> </td> 
   <td> Met deze workflow kunt u een lijst met kwalificatieregels voor stuiteringsregels maken, plus de lijst met domeinen en MX in het platform. Deze workflow werkt alleen als het HTTPS-bestand is geopend. Standaard wordt deze automatisch om 2 uur gestart.<br /> </td> 
  </tr> 
 </tbody> 
</table>

