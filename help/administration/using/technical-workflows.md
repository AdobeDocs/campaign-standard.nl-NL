---
title: Technische workflows
description: Meer informatie over technische workflows
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: da3a3af5-207a-4289-bd07-00a8c5d1cf57
source-git-commit: f87795ee2378a1e9e1b393c6cce002bcb70178b8
workflow-type: tm+mt
source-wordcount: '791'
ht-degree: 74%

---

# Technische workflows{#technical-workflows}

De technische workflows worden kant-en-klaar geleverd met Adobe Campaign. Technische workflows zijn bewerkingen of taken die regelmatig en volgens een planning op de server moeten worden uitgevoerd.

Met deze workflows kunt u onderhoudsbewerkingen uitvoeren op de database, de traceringsinformatie gebruiken in de leveringen en de voorlopige taken bijwerken voor de leveringen.

Functionele beheerders hebben toegang tot technische workflows via het menu **[!UICONTROL Administration > Application settings > Workflows]**.

>[!NOTE]
>
>Als functionele beheerder kunt u technische workflows opnieuw starten of pauzeren en de eigenschappen en structuur van deze workflows wijzigen.

![](assets/technical_workflows.png)

## Lijst van technische werkstromen {#list-of-technical-workflows}

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
   <td> <span class="uicontrol"> Kopballen van het Exemplaar van leveringsmalplaatjes </span> <br /> </td> 
   <td> <span class="uicontrol"> smtpHeaderupdate </span> <br /> </td> 
   <td> Deze werkstroom kopieert SMTP kopballen die voor e-mailleveringsmalplaatjes aan de overeenkomstige kindniet-malplaatjeleveringen worden geplaatst. In deze workflow worden alleen e-mailmarketingproducten opgehaald. SMTP-headers worden niet gekopieerd naar transactieleveringen en proefdrukken. <br> Deze workflow wordt niet periodiek uitgevoerd. Het moet door de gebruiker per gebruik worden gestart. <!--So it'not really a technical workflow like all workflows on this page, because it's not run automatically - TBC--> <br> als er een hoog volume van leveringen op uw instantie is, kunt u de optie NmsCleanup_DeliveryPurgeDelay in de <strong> montages van de Toepassing </strong> bijwerken. Als u een verandering in kopballen SMTP van om het even welk malplaatje aanbrengt, dan moet u het werkschema opnieuw na de verandering uitvoeren zodat de gecorrigeerde kopballen over aan niet-malplaatjeleveringen worden gekopieerd.<a href="data-retention.md#deliveries"> Leer meer </a>
   <br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Database opschonen</span> <br /> </td> 
   <td> <span class="uicontrol">cleanup</span> <br /> </td> 
   <td> Deze workflow is de workflow voor databaseonderhoud: deze stelt verschillende statistieken en processen in werking en schrapt verouderde data uit de database volgens de configuratie die is gedefinieerd. Standaard wordt deze workflow elke dag automatisch om 4.00 uur gestart.<br /> </td> 
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
   <td> Deze workflow synchroniseert de in Adobe Campaign Standard geïmporteerde eigenschappen voor mobiele tags. De workflow wordt elke 15 minuten gestart.<br /> </td> 
  </tr>
  <tr> 
   <td> <span class="uicontrol"> het Volgen logboekterugwinning </span> <br /> </td> 
   <td> <span class="uicontrol">SyncWithLaunch</span> <br /> </td> 
   <td> Deze workflow synchroniseert de in Adobe Campaign Standard geïmporteerde eigenschappen voor mobiele tags. De workflow wordt elke 15 minuten gestart.<br /> </td> 
  </tr>
  <tr> 
   <td> <span class="uicontrol"> Herstel het Volgen Logs </span> <br /> </td> 
   <td> <span class="uicontrol"> trackingLogRecovery </span> <br /> </td> 
   <td> Met deze workflow worden verloren traceringslogbestanden hersteld. Deze technische workflow wordt in specifieke omstandigheden gebruikt en beperkt tot Adobe voor intern gebruik. <br> Standaard wordt deze elke 10 minuten gestart. <br /> </td> 
  </tr>
  <tr> 
   <td> <span class="uicontrol">Uitvoering van levering bijwerken</span> <br/> </td> 
   <td> <span class="uicontrol">updateDeliveryExecInfo</span> <br/> </td> 
   <td> Deze workflow kopieert de logboeken voor de weblogs en tracering in de lokale database. Standaard wordt deze workflow elke 10 minuten gestart.<br/> </td> 
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
