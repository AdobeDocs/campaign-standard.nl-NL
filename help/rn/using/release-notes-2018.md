---
title: Aanvullende informatie 2018
description: Deze pagina bevat een overzicht van alle releases van Adobe Campaign Standard in 2018.
feature: Overview
role: User
level: Beginner
hidefromtoc: true
exl-id: 17521357-14ae-4751-bd7c-aeabbcf71d07
source-git-commit: bee4da592e0b3727949bc44c6e41b81d4e7e73d4
workflow-type: tm+mt
source-wordcount: '5386'
ht-degree: 3%

---

# Aanvullende informatie 2018{#release-notes}

## Release 18.9 - september 2018 {#release-18-9---september-2018}

**Nieuwe functies**

<table> 
 <thead> 
  <tr> 
   <th> Functionaliteit<br /> </th> 
   <th> Beschrijving<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> In-app berichten (bèta)<br /> </td> 
   <td> Met In-App-berichten kunt u gebruikers van Mobile App effectiever inschakelen door contextuele interactie te bieden en u in staat te stellen gebruikers te bereiken die mogelijk uit pushberichten hebben gekozen. Gebruik in-app berichten in combinatie met pushmeldingen om een zeer gepersonaliseerde en relevante ervaring te creëren. Dit leidt tot betere conversie en behoud van uw App-gebruikers.<br /> Raadpleeg voor meer informatie de <a href="../../channels/using/about-in-app-messaging.md">gedetailleerde documentatie</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Integratie van Adobe starten voor mobiele apps (bèta)<br /> </td> 
   <td> Adobe De integratie van de Lancering met Adobe Campaign vereenvoudigt en automatiseert nu het proces van de Activering van het Bezit van de Mobiele App in Campagne gebruikend Mobile SDK V5.<br /> Raadpleeg voor meer informatie de <a href="https://helpx.adobe.com/nl/campaign/kb/configuring-app-sdk.html">gedetailleerde documentatie</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Verbeteringen**

* Adobe Campaign Standard ondersteunt nu versie 4 van de Amazon S3 API.

**Andere wijzigingen**

* In de uitzendingen, is er nu een onderscheid tussen het maximumaantal verbindingen en het maximumaantal berichten per uur. Wanneer de grenzen worden bereikt, is het dan mogelijk te weten waarom de productie beperkt is. Eerder was hetzelfde bericht (&quot;met quotum bereikt&quot;) van toepassing op beide gevallen.
* Wanneer u een mobiele toepassing configureert in Campagne, kan de gebruiker nu weten of het iOS-certificaat en de Android-serversleutel zijn geüpload en of de vervaldatum van de toepassing geldig zijn.

  Raadpleeg voor meer informatie de gedetailleerde documentatie over het configureren van een mobiele toepassing met [SDK V4](https://helpx.adobe.com/nl/campaign/kb/configuring-app-sdkv4.html) en [SDK V5](https://helpx.adobe.com/nl/campaign/kb/configuring-app-sdk.html).

* Doelgebruikers voor een specifieke mobiele toepassing door een mobiele toepassing te selecteren terwijl de campagneeigenschappen worden gedefinieerd. Deze functie is bedoeld voor zowel Push- als In-App Messaging-kanalen.

  Raadpleeg de [gedetailleerde documentatie](../../channels/using/preparing-and-sending-a-push-notification.md#preparing-the-notification) voor meer informatie.

* Wanneer u een inhoudsblok selecteert met de Creative Designer-interface, worden alle inhoudsblokken uit de lijst nu geladen en weergegeven. (CAMP-27311)

  Raadpleeg voor meer informatie de [gedetailleerde documentatie](../../designing/using/personalization.md#adding-a-content-block).

**Patches**

* Probleem verholpen waarbij een discrepantie in het logbestand werd weergegeven tussen het dashboard voor e-mail en het samenvattingsrapport voor transactie-e-mails. (CAMP-28237)
* Probleem verholpen in workflows die een foutbericht konden weergeven bij het importeren van een bestand via bestandsoverdracht. (CAMP-27435)
* Probleem verholpen waarbij bestemmingspagina&#39;s meer dan 25 services bevatten, waardoor services willekeurig werden uitgeschakeld in het formulier. (CAMP-26572)
* Probleem verholpen in workflows die ervoor zorgden dat externe accounts niet konden worden geconfigureerd met een SFTP-URL wanneer de bestandsoverdrachtactiviteit werd gebruikt. (CAMP-26475)
* Probleem verholpen waardoor het samenvattingsrapport voor services niet kon worden bijgewerkt. (CAMP-26301)
* Probleem verholpen in workflows tijdens het gebruik van een verrijkingsactiviteit waardoor een aangepast veld de juiste datum niet kon weergeven. (CAMP-26242)
* Probleem verholpen waarbij het bijwerken van servicedescriptdatums tijdens het importeren van een bestand werd verhinderd.
* Probleem verholpen met de activiteit van het laadbestand waardoor werkstromen geen bestanden konden importeren (CAMP-27068).
* Probleem verholpen waarbij het onjuiste aantal abonnementen in de samenvattingsrapporten van de service (CAMP-25587) werd weergegeven.
* Oplossing voor een probleem met gegevensdiscrepantie tussen Adobe Analytics- en Adobe Campaign-rapporten. (CAMP-25393)
* Probleem verholpen waardoor een gebruiker met beperkte toegang zich niet kon aanmelden. (CAMP-27381)
* Probleem verholpen waardoor de lijst met Adobe Experience Manager-inhoud niet kon worden weergegeven wanneer een e-mailbericht werd bewerkt met Creative Designer. (CAMP-27181)
* Probleem verholpen waardoor Creative Designer niet kon worden geopend. Er is een fout opgetreden. (CAMP-27304)
* Probleem verholpen waardoor slepen en neerzetten niet correct werkte in Creative Designer bij gebruik van Internet Explorer 11.
* Probleem verholpen waarbij foto&#39;s die vanaf een camera zijn geüpload en die in de staande modus zijn genomen, werden weergegeven op een ongewenste geroteerde positie.
* Probleem verholpen waarbij onduidelijke selectiegegevens werden weergegeven wanneer de interface voor de query-editor in Creative Designer werd gebruikt.
* Probleem verholpen waarbij een element niet correct kon worden gedupliceerd wanneer de interface voor de query-editor in Creative Designer werd gebruikt.
* Probleem verholpen waarbij SMS-berichten aan ontvangers in de lijst van gewezen personen bleven leveren, ook al waren ze via een automatisch antwoord niet meer geabonneerd. (CAMP-27128)
* Probleem verholpen waarbij de fouten die de **Database opschonen** workflow mislukt. (CAMP-26876)
* Probleem verholpen waarbij het verwijderen van aangepaste velden in een definitie van een pushmelding werd voorkomen. (CAMP-25588)

## Release 18.7 - juli 2018 {#release-18-7---july-2018}

**Nieuwe functies**

<table> 
 <thead> 
  <tr> 
   <th> Functionaliteit<br /> </th> 
   <th> Beschrijving<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Markering voor hoge prioriteit voor Android-pushberichten<br /> </td> 
   <td> Markering met hoge prioriteit voor Android: hiermee kunt u een pushmelding met hoge prioriteit maken voor Android-toepassingen. Hierdoor wordt het slaapapparaat wakker en wordt de verwerking beperkt. De standaardprioriteit is Normal, waardoor de levering van het bericht kan worden vertraagd om de batterij op te slaan. <br /> Raadpleeg voor meer informatie de <a href="../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-android">gedetailleerde documentatie</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Typologisch filter voor abonnees van mobiele apps<br /> </td> 
   <td> Ondersteuningsabonnementen in typologiefilter - Wanneer u de filtercriteria voor een typologieregel opgeeft, kunnen de abonnementen van de toepassing worden geselecteerd als de filterings- en doelafmetingen, zodat u op kenmerken kunt filteren voor gebruikers met of zonder profiel. <br /> Raadpleeg voor meer informatie de <a href="../../sending/using/about-typology-rules.md">gedetailleerde documentatie</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Geautomatiseerde inhoud importeren van een URL tijdens berichtvoorbereiding<br /> </td> 
   <td> Het is nu mogelijk om e-mailinhoud te importeren vanaf een URL tijdens de voorbereidingsfase. Voor terugkerende e-mailleveringen wordt de meest recente HTML-inhoud opgehaald telkens wanneer het bericht wordt voorbereid, zodat de inhoud altijd up-to-date is op het moment dat de e-mail wordt verzonden. Met deze functie kunt u ook een geplande levering maken met inhoud van een URL, zelfs als de inhoud nog niet gereed is.<br /> Raadpleeg voor meer informatie de <a href="../../designing/using/using-existing-content.md#retrieving-content-from-a-url-automatically-at-preparation-time">gedetailleerde documentatie</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Meldingsbericht Campagne<br /> </td> 
   <td> Er wordt nu een pop-upbericht weergegeven wanneer een gebruiker zich aanmeldt nadat de instantie is bijgewerkt naar een nieuwe versie. Het bericht geeft het versienummer aan en bevat een koppeling naar de opmerkingen bij de release. U kunt het bericht verbergen tot de volgende versie. <br /> </td> 
  </tr> 
  <tr> 
   <td> Gebruikersbeheer<br /> </td> 
   <td> De mogelijkheid voor geografische eenheden is nu niet meer beschikbaar voor nieuwe exemplaren van Campaigns Standard en voor bestaande exemplaren zonder dat er geografische eenheden zijn gemaakt, vanaf de release 18.7.<br /> Raadpleeg deze voor meer informatie <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html?lang=nl#release-notes">page</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Verbeteringen**

* Dankzij de integratie met Adobe Campaign en Adobe Target kunt u nu gebruikmaken van de [Machtigingen](https://experienceleague.adobe.com/docs/target/using/administer/manage-users/enterprise/properties-overview.html?lang=nl-NL) gebruiken. Wanneer u een dynamische afbeelding van Adobe Target in een e-mail opneemt, kunt u nu een eigenschap Doel opgeven (at_property-code).
* Aangepaste bronnen met een eigen koppeling naar de profielbron worden nu in aanmerking genomen door verzoeken om toegang tot of verwijdering van GDPR-privacy. Voor 1 kardinaliteit eenvoudige verbindingen en de verbindingen van de kardinaliteitsinzameling van N, moet u &quot;het Schrappen/het Dupliceren van het doelverslag impliceren schrappend/het dupliceren van de verslagen van verwijzingen voorzien door de verbinding&quot;in het douanemiddel selecteren. Voor eenvoudige 0- of 1-cardinaliteit-koppelingen selecteert u &quot;Verwijderen/dupliceren van de record houdt in dat de doelrecord waarnaar door de koppeling wordt verwezen, wordt verwijderd/gedupliceerd&quot;.

**Andere wijzigingen**

* De time-out voor het delen van rapporten is verhoogd van een tot vier minuten om een time-outfout te voorkomen.
* Wanneer u de inhoud van een e-mailbericht bewerkt, wordt de nieuwe Creative Designer standaard geopend. Desgewenst kunt u na het opslaan van de wijzigingen desgewenst nog steeds terugkeren naar de standaardinhoudseditor. Raadpleeg voor meer informatie de [gedetailleerde documentatie](../../designing/using/designing-content-in-adobe-campaign.md).
* In Creative Designer kunt u nu een nieuwe inhoudcomponent toevoegen aan een e-mailbericht: de carrousel. Raadpleeg voor meer informatie de [gedetailleerde documentatie](../../designing/using/designing-from-scratch.md#about-content-components).
* Klik in een transactiemelding op het rapport wanneer u op de knop **Profiel wijzigen** nu worden alleen de testprofielen weergegeven die zijn gekoppeld aan de gebeurtenis die u voor uw transactiemelding hebt gedefinieerd.

**Patches**

* Probleem verholpen met het byEmail queryfilter waarbij geen resultaten werden geretourneerd. (CAMP-23420)
* Probleem verholpen waarbij een standaardgebruiker toegang kreeg tot bepaalde functies of schermen die beperkt waren tot beheerders (/rest/kop/&#42; eindpunten, transactiemeldschermen, profielen en doelgroepen (importschermen).
* Oplossing voor een probleem dat ervoor zorgde dat aanvragen voor GDPR-privacy niet konden worden verwerkt met aangepaste bronnen als hun naam met een nummer was begonnen.
* Correctie van een fout die ervoor zorgde dat de activiteit van het Publiek van het Opslaan van toepassingsabonnees in Adobe Experience Cloud kon delen.
* Probleem verholpen met de bestandsoverdrachtactiviteit die kon optreden wanneer de bestandsnaam lege spaties bevatte. (CAMP-25936)
* Probleem verholpen die kon optreden wanneer de knop Opnieuw verbinden werd gebruikt nadat een sessie was verlopen. (CAMP-25560)
* Probleem verholpen dat tot uitsluitingen kon leiden bij het verzenden van leveringen met optimalisatie voor tijdzone gekoppeld aan fatigues-regels. (CAMP-25425)
* Probleem verholpen bij het gebruik van de API GDPR-functie, die kan voorkomen dat gegevens met een koppeling van het type 0-1 worden verwijderd.
* Probleem verholpen dat tot een foutbericht kon leiden wanneer de uitgave van een moeilijkheidtypologieregel werd geannuleerd.
* Probleem verholpen dat kon optreden wanneer een voorvertoning van een leveringsinhoud werd weergegeven nadat deze was bewerkt.
* Oplossing voor een probleem dat kon optreden bij het verwerken van CSV ZIP-bestanden tijdens het gebruik van de optie Decompressie.
* Correctie van een probleem in Creative Designer dat resulteerde in ongewenste kleurenlettertypen en -opmaak bij het wijzigen van tekst met ingebouwde opmaak in een koppeling of bij het bewerken van die koppeling. (CAMP-26001)
* Probleem verholpen waarbij het rapport &#39;hot click&#39; de percentages voor elke voorwaarde niet kon weergeven in leveringen met dynamische inhoud. Eerder, slechts werden de kliks op de standaardvariant getoond.

## Release 18.6 - juni 2018 {#release-18-6---june-2018}

**Verbeteringen**

* De **[!UICONTROL History]** API is toegevoegd aan Adobe.IO. Hiermee hebt u toegang tot informatie over de marketinggeschiedenis van een profiel: aantal aanraakpunten, verzonden leveringen, URL van spiegelpagina enzovoort. Raadpleeg voor meer informatie de [speciaal gebruik](../../api/using/interacting-with-marketing-history.md) .
* De **[!UICONTROL Database cleanup]** de technische werkstroom is geoptimaliseerd om betere prestaties voor gegevensbestandsteun te verzekeren.
* De Creative Designer voor e-mail is nu ook beschikbaar in het Frans en Duits.

**Andere wijzigingen**

* A **[!UICONTROL Compute stats]** is toegevoegd in het dialoogvenster **[!UICONTROL Deployment]** venster met verzonden leveringen. Het staat u toe om recentste KPIs terug te winnen, bijvoorbeeld als de resultaten van het verzenden te lang om duren bij te werken of niet in aanmerking genomen. Raadpleeg deze [sectie](../../sending/using/confirming-the-send.md) voor meer informatie.
* In de **Update voor leverbaarheid** uit-van-de-doos technische werkschema, kunnen de functionele beheerders het aantal opeenvolgende fouten nu bepalen om in te negeren **Regels bijwerken** javascript-activiteit. De veldwaarde wordt standaard ingesteld op 0, wat betekent dat alle fouten worden genegeerd.
* De SQL-code die wordt gegenereerd wanneer de toegangsbeperkingsvoorwaarden voor eenheden worden beheerd, is geoptimaliseerd.
* De **[!UICONTROL Update]** Met activiteiten kunt u nu gegevens toevoegen, bijwerken of verwijderen die betrekking hebben op abonnementen (tabel nms:appSubscriptionRcp).
* De **[!UICONTROL Update delivery execution]** de technische workflow is onderverdeeld in twee workflows om de prestaties te optimaliseren: - **[!UICONTROL Update delivery execution]**: werkt het bijhouden van de levering bij. Deze wordt standaard elke 10 minuten gestart. **[!UICONTROL Update delivery indicators]**: werkt KPI&#39;s van de levering bij, is het begonnen elk uur door gebrek. Voor meer informatie over technische workflows raadpleegt u deze [sectie](../../administration/using/technical-workflows.md#list-of-technical-workflows).
* Wanneer een levering berichten verzendt, de status in **[!UICONTROL Deployment]** sectie kan nu twee waarden hebben: **[!UICONTROL Sending]**: de berichten worden verzonden. **[!UICONTROL Sending (retry)]**: er wordt een procedure voor het opnieuw proberen gestart.
* Gebruikers met de **[!UICONTROL Delivery preparation]** de rol kan nu proefdrukken verzenden . (CAMP-24313)
* De **TLS inschakelen via SMPP** is toegevoegd aan de **SMS-routering via SMPP** externe rekening. Zie voor meer informatie deze [sectie](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing).

**Patches**

* Probleem opgelost waarbij e-mailberichten niet konden worden verzonden wanneer een dynamische afbeelding uit Adobe Target werd opgenomen (CAMP-24848).
* Probleem met de **[!UICONTROL Privacy Access/Delete Request]** technische workflows, die niet zijn voltooid als een van de verzoeken is mislukt.
* Probleem verholpen waardoor de Privacy Core-service geen updates van de aanvraagstatus kon ontvangen vanuit de campagne.
* Probleem opgelost waarbij de technische workflow voor **[!UICONTROL Import shared audience]** niet goed kon werken (CAMP-25465).
* Probleem verholpen waarbij werd voorkomen dat privacyverzoeken voor campagnes werden gemarkeerd als voltooid in de Core Privacy Service.
* Probleem verholpen waardoor bepaalde gebruikers zich niet konden aanmelden bij een Campaign Standard via IMS-verificatie wanneer de Adobe ID te lang was. (CAMP-24095)
* Oplossing voor een probleem in Creative Designer dat kan optreden wanneer u inhoudsmodules verwijdert. (CAMP-25242)
* Probleem verholpen bij het gebruik van de vermoeiingsregels voor pushmeldingen voor abonnees zonder profiel in de database. (CAMP-25344)
* Probleem verholpen waarbij een foutbericht kon worden weergegeven wanneer toegang werd verkregen tot uitsluitingslogboeken voor leveringen. (CAMP-24724)
* Probleem verholpen waarbij proefdrukken niet konden worden voorbereid in gevallen met uitgebreide verzendende logboeken.
* Twee problemen verholpen die zich konden voordoen bij het publiceren van aangepaste bronnen met de **[!UICONTROL Sending log]** -extensie geactiveerd.
* Probleem verholpen dat zich kon voordoen wanneer bij terugkerende leveringen geen rekening was gehouden met de leveringsduur.
* Probleem verholpen dat zich kon voordoen bij het sorteren van gegevens in het dialoogvenster **[!UICONTROL Client data]** voor aangepaste bronnen met meer dan 100K records. (CAMP-24308)
* Probleem opgelost met aangepaste profielafmetingen waarmee geen rekening is gehouden bij het gebruik van de zoekfunctie in dynamische rapporten.
* Probleem opgelost met de weergave van internationale gegevens voor accountniveaus in dynamische rapporten.
* U kunt nu een service maken zonder een abonnement of een bevestigingsbericht zonder abonnement.

## Release 18.5 - mei 2018 {#release-18-5---may-2018}

**Nieuwe functies**

<table> 
 <thead> 
  <tr> 
   <th> Functionaliteit<br /> </th> 
   <th> Beschrijving<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> GDPR: Core Service Integration<br /> </td> 
   <td> De Integratie van de Dienst van de Kern van de privacy staat u toe om uw verzoeken GDPR in een multi-oplossingscontext door één enkele vraag van JSON API te automatiseren. <br /> GDPR-verzoeken die van de Privacy Core Service naar alle oplossingen voor Experiencen Cloud worden geduwd, worden nu automatisch door de Campagne afgehandeld. <br /> Raadpleeg voor meer informatie de <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/getting-started/privacy/privacy.html?lang=nl-NL">gedetailleerde documentatie</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Push-verbeteringen - gedetailleerde feedback voor levering<br /> </td> 
   <td> Adobe Campaign biedt nu de mogelijkheid om gedetailleerde feedback (het verzenden van logboeken en uitsluitingslogboeken) te ontvangen over pushberichten van APNS/GCM via MCPNS.<br /> Raadpleeg voor meer informatie de <a href="../../channels/using/preparing-and-sending-a-push-notification.md#sending-the-notification">gedetailleerde documentatie</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Extensie voor leveringslogs<br /> </td> 
   <td> Met de extensie Leveringslogbestanden kunt u het verzenden van logbestanden uitbreiden met profielgegevens en segmentcode die afkomstig zijn van workflows. Deze informatie kan dan in Dynamische Rapporten worden gebruikt, en laat u een momentopname van wat informatie bij de verzendende tijd van een levering houden.<br /> Er zijn nog twee gebruiksgevallen:<br /> 
    <ul> 
     <li> Exporteer uitgebreide uitzendingen met 'bevroren' gegevens: als een markeerteken wil ik alle profielen exporteren waarbij de segmentcode gelijk is aan 'A' (afkomstig uit de workflow-engine). </li> 
     <li> Segmentatie van "bevroren" gegevens: als markeerteken wil ik graag <strong>herrichten</strong> alle profielen die sinds de laatste verzending 1000 loyaliteitspunten hebben gewonnen of waar de segmentcode aan "A"gelijk was. </li> 
    </ul> Raadpleeg voor meer informatie de <a href="../../developing/using/configuring-the-resource-s-data-structure.md#defining-sending-logs-extension">gedetailleerde documentatie</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Dynamische rapportage met aangepaste profielgegevens<br /> </td> 
   <td> Met deze functie kunt u rapporten maken en beheren op basis van aangepaste profielgegevens die zijn gemaakt tijdens de bestandsextensie. U kunt rapporten onderverdelen door profielattributen zoals loyaliteitsprogramma, aangewezen kanaal, etc.<br /> Raadpleeg voor meer informatie de <a href="../../developing/using/configuring-the-resource-s-data-structure.md#defining-sending-logs-extension">gedetailleerde documentatie</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Verbeteringen**

* Het totale geheugen en CPU-gebruik van de toepassing is verbeterd

**Andere wijzigingen**

* De activiteit van de het werkschema van het publiek van het Leespubliek kan nu Experience Cloud publiek lezen. Eerder kon deze activiteit alleen het publiek Query en List lezen. Zie de [gedetailleerde documentatie](../../automating/using/read-audience.md). (CAMP-23623)
* De id van de standaard gezamenlijke gegevensbron bevindt zich nu in de modus Alleen-lezen en kan niet meer worden gewijzigd. Als u deze id wijzigt, kunnen er problemen optreden bij het delen van het publiek met het Experience Cloud.
* Het importeren van soorten publiek uit Audience Manager werkt nu met gesplitste bestanden. Eerder werd alleen het laatste bestand van het segment geïmporteerd door de technische workflow van importSharedAudience.
* De externe rekeningen van AWS S3 steunen nu gebieden en het versie 4 authentificatiemechanisme. Zie de [gedetailleerde documentatie](../../administration/using/external-accounts.md).
* Het venster Asset Selecting moet nu sneller worden geladen en het mogelijk maken om een element te selecteren en vervolgens het venster zonder probleem te sluiten.
* De eigenschappen en structuur van technische werkstromen kunnen nu worden gewijzigd door gebruikers met beheerrechten die tot de &quot;Alle&quot; organisatorische en geografische eenheden behoren.
* Er zijn verbeteringen aangebracht in de interface Segmenteringsactiviteit bij het maken van nieuwe segmenten: het tabblad Beperking wordt nu direct weergegeven nadat u een beperking hebt toegevoegd. Namen van nieuwe segmenten worden nu verhoogd (&quot;Segment 1&quot;, &quot;Segment 2&quot;, enz.).
* Een &quot;nextProcessingDate&quot;gebied wordt toegevoegd aan het middel van het Werkschema. Dit veld is alleen zichtbaar via REST API-aanroepen. Hiermee kunt u workflows volgende verwerkingsdatums visualiseren.
* Het veld &quot;sourceId&quot; wordt nu weergegeven in de bron van trackinglogbestanden (nms:trackingLog).
* De waarden &#39;Totaal openen&#39; en &#39;Totaal klikken&#39; kunnen nu worden geëxporteerd in een vlak bestand via een workflow. (CAMP-24186)
* &quot;Engels - Danmark&quot; is nu beschikbaar in de lijst Voorkeurstalen in profielen. (CAMP-23728)
* Wanneer het gebruiken van een activiteit van de Segmentatie met een Extra gegevens (targetData) verbinding, deelt een bericht u nu mee dat de gegevens niet beschikbaar buiten het werkschema zijn. Dit bericht wordt weergegeven wanneer u op de knop Tellen of Voorvertoning klikt vanuit de segmentatieactiviteit. (CAMP-23651)
* Er zijn verbeteringen aangebracht voor het optimaliseren van schijfruimte die wordt gebruikt door workflows: (CAMP-21979): De bestanden die worden verwerkt door de activiteit Bestand laden, worden nu standaard verwijderd. Met een optie kunt u deze voor specifieke behoeften behouden. Wanneer een werkstroom wordt geschrapt, wordt zijn specifieke omslag automatisch onderdrukt van de serverfolder.

**Patches**

* Probleem verholpen waarbij aan sommige onbewerkte rapportagegebeurtenissen geen traceergebeurtenissen waren gekoppeld omdat het veld eventDate niet correct was ingevuld.
* Probleem verholpen waarbij weergave van gepersonaliseerde velden in het voorvertoningsvenster van een pushmelding werd verhinderd.
* Probleem verholpen waardoor de tekst geen tekstomloop kon toepassen op de berichttekst van een pushmelding in het voorvertoningsvenster.
* Probleem verholpen bij het verzenden van een terugkerende levering vanuit een workflow wanneer het hoofddoel leeg is.
* Probleem verholpen waardoor een doeltoewijzing niet kon worden geopend als deze gekoppeld was aan een onbestaand schema.
* Probleem verholpen die kon optreden bij het importeren van een ZIP-bestand via een activiteit Bestand laden. (CAMP-24309)
* Probleem verholpen die tot een PostSQL-fout leidde bij het verzenden van een terugkerende levering. (CAMP-23613)
* Probleem verholpen waarbij een foutbericht werd weergegeven bij het verzenden van een REST API-aanvraag met een leeg JSON-kenmerk. (CAMP-23506)
* Correctie van een probleem in profielen waarbij de tekens na het teken ß als hoofdletter werden ingesteld. (CAMP-23136)
* Probleem verholpen bij het verzenden van leveringen die werden gebruikt met de geschiktheidsvoorwaarde van een verpersoonlijking of een dynamisch inhoudsblok terwijl kenmerken van een gekoppeld profielschema werden gebruikt. (CAMP-22751)
* Probleem opgelost waarbij services niet konden worden verwijderd. (CAMP-22050)
* Probleem verholpen waarbij het wijzigen van de land- of statuswaarden in een testprofiel werd voorkomen. (CAMP-20426)
* Correctie van een probleem waardoor Creative Designer niet kon worden geladen. (CAMP-24573)
* Probleem verholpen waarbij tekens werden verwijderd die na personalisatievelden in het onderwerp van de e-mail waren toegevoegd. (CAMP-24113)

## Release 18.4 - april 2018 {#release-18-4---april-2018}

**Patches**

_Platform_

* Oplossing voor een fout die kan voorkomen dat aanvragen voor GDPR-toegang correct worden verwerkt of verwijderd. Dit gedrag is waargenomen in enkele zeldzame gevallen waarin de geëxtraheerde gegevens een van de volgende tekens bevatten: &amp; &lt; > &quot; &#39;.

_E-mail, SMS-berichten en direct mail_

* Probleem verholpen waarbij KPI&#39;s met onjuiste waarden zouden worden overschreven als de synchronisatie van de broadlog meer dan een uur duurde.

_Workflows_

* Verbeterd geheugenbeheer en geoptimaliseerde prestaties in workflows.

_Rapportage_

* De workflow voor het delen van een PKI haalt nu leveringswaarden op voor de laatste twee maanden in plaats van de laatste zes maanden. Probleem verholpen waarbij voor KPI-delen externe account afgebroken datums werden weergegeven.
* Probleem verholpen waarbij bepaalde berichten niet in aanmerking konden worden genomen **Verzonden**, **Geleverd** en **Stuiteren** metriek.
* Oplossing voor een fout die optrad wanneer het gekozen tijdbereik in het dialoogvenster **Overzichtsrapport van levering** was te lang.

_Aangepaste resources_

* Probleem verholpen waarbij het voorbereiden van aangepaste bronnen mislukte.

## Release 18.3 - maart 2018 {#release-18-3---march-2018}

**Nieuwe functies**

<table> 
 <thead> 
  <tr> 
   <th> Functionaliteit<br /> </th> 
   <th> Beschrijving<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Algemene EU-verordening inzake gegevensbescherming (GDPR)<br /> </td> 
   <td> GDPR is de nieuwe privacywet van de Europese Unie (EU) die de vereisten inzake gegevensbescherming harmoniseert en moderniseert en op 25 mei 2018 van kracht wordt. AVG is van toepassing op Adobe Campaign-klanten die data bewaren voor in de EU wonende betrokken personen.<br /> Naast de privacy mogelijkheden reeds beschikbaar in Adobe Campaign (met inbegrip van toestemmingsbeheer, montages van het gegevensbehoud, en gebruikersrollen), nemen wij deze kans in onze rol als Bewerker van Gegevens om extra mogelijkheden te omvatten, om uw bereidheid als Datacontrole voor bepaalde GDPR verzoeken te helpen vergemakkelijken:<br /> 
    <ul> 
     <li> Recht op toegang: staat de betrokkene toe een kopie te ontvangen van zijn persoonsgegevens die door gegevensverwerkingsverantwoordelijken zijn vastgelegd, met inbegrip van gegevens die in Adobe Campaign zijn opgeslagen. </li> 
     <li> Recht op verwijderen: geeft de betrokkene het recht om zijn persoonsgegevens die door de gegevensverwerkingsverantwoordelijken zijn vastgelegd, te laten wissen, mogelijk met inbegrip van gegevens die in Adobe Campaign zijn opgeslagen. </li> 
    </ul> Raadpleeg voor meer informatie de <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/getting-started/privacy/privacy.html?lang=nl-NL">gedetailleerde documentatie</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Creative Designer voor e-mail (bèta)<br /> </td> 
   <td> De nieuwe Creative Designer-versie van Adobe Campaign biedt een volledig geïntegreerde ontwerpervaring in Campagne, waardoor u snel en moeiteloos visueel fascinerende, individueel gepersonaliseerde e-mails kunt maken zonder dat u een script hoeft te schrijven voor één regel code. Dankzij de krachtige interface voor slepen en neerzetten helpt Creative Designer het maken van e-mail te schalen, of gebruikers nu op een lege site beginnen of bestaande inhoudfragmenten of -sjablonen gebruiken. <br /> De belangrijkste mogelijkheden omvatten:<br /> 
    <ul> 
     <li> Ontwerp en maak visueel volledig persoonlijke, responsieve e-mails via een drag-and-drop interface, aangevuld met geïntegreerde native Creatives Cloud </li> 
     <li> Een sjabloon voor e-mailinhoud en opgeslagen sjablonen maken en opslaan om het maken van e-mail te helpen schalen </li> 
     <li> Inhoudsfragmenten maken en opslaan (zoals een kop-, voettekst-, artikel-, enz.) om het creëren van inhoud te stroomlijnen en merkconsistentie te verzekeren </li> 
     <li> Naadloos schakelen tussen maken in de interface voor slepen en neerzetten en rechtstreeks HTML van een e-mailbericht bewerken met één klik op een knop </li> 
    </ul> De Creative Designer voor e-mail is alleen beschikbaar in het Engels.<br /> Raadpleeg voor meer informatie de <a href="../../designing/using/designing-content-in-adobe-campaign.md">gedetailleerde documentatie</a> en bekijk dit <a href="https://www.youtube.com/watch?time_continue=1&amp;v=5S_6A4fsfms">video</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Meertalige pushleveringen<br /> </td> 
   <td> Dezelfde eenvoudige meertalige interface, die al bestaat op de e-mail- en sms-kanalen, is toegevoegd aan het pushkanaal, zodat u klanten kunt bereiken, ongeacht hun voorkeurstaal.<br /> Dit vermogen biedt een scalable en automatische oplossing voor klanten die Push campagnes leiden die veelvoudige gebieden overspannen en gebruikers in hun aangewezen taal willen richten. Hiermee kunt u alle taalvarianten via een sjabloonspreadsheet uploaden naar één pushbericht, met één klik. Adobe Campaign voert vervolgens een automatische segmentatie uit op basis van de taalvoorkeur van de gebruiker, waardoor de redundantie wordt verminderd door workflows en rapportering te vereenvoudigen.<br /> Raadpleeg voor meer informatie de <a href="../../channels/using/creating-a-multilingual-push-notification.md">gedetailleerde documentatie</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Gebruik van de Middelen van de Douane in Transactieoverseinen<br /> </td> 
   <td> Naast uit-van-de-doos gebieden, staat het transactieoverseinen u nu toe om douanemiddelen te gebruiken om de inhoud van uw berichten te verrijken.<br /> Bijvoorbeeld:<br /> 
    <ul> 
     <li> Aangepaste velden als afstemmingscriteria gebruiken om een transactiebericht aan een profiel aan te passen </li> 
     <li> Gebruik volledige profielen, de diensten en verbonden gegevens om transactieverslagen verder te personaliseren </li> 
    </ul> Raadpleeg voor meer informatie de <a href="../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content">gedetailleerde documentatie</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Patches**

_Platform_

* Probleem verholpen waarbij meer dan 5000 records uit een lijst konden worden geëxporteerd.
* Probleem verholpen bij het exporteren van gegevens naar bestanden die zijn benoemd met aanpassingsvelden.

_E-mail, SMS-berichten en direct mail_

* Probleem verholpen waarbij multipart-SMS werd afgebroken omdat de grootte van onderdelen werd berekend in tekens in plaats van bytes.
* Er is een optie toegevoegd waarmee de **[!UICONTROL Delivered]** of **[!UICONTROL Bounces + Errors]** KPI&#39;s die in real-time moeten worden bijgewerkt nadat u de levering hebt verzonden. Zij worden direct opnieuw berekend van SR (het Rapport van de Status) die van de leverancier wordt ontvangen.
* Probleem verholpen met de kalenderwidget in de leveringsplanner.
* Oplossing voor een weergaveprobleem bij het voor een tweede keer openen van een doel in een verzonden levering.
* Probleem verholpen dat leidde tot een foutbericht waarin een begindatum werd gevraagd bij het maken van een e-mailsjabloon met een vertraagde verzenddatum.
* Probleem verholpen waarbij weergaveproblemen met afbeeldingen konden optreden tijdens het bewerken van de inhoud van een levering.
* Probleem opgelost met proefdrukken tijdens het dupliceren van een campagne.
* Probleem verholpen dat tot een foutbericht leidde bij het openen van een campagnemalplaatje via de navigatiebalk, nadat een levering aan de workflow was toegevoegd.
* Probleem verholpen waardoor de winnaar van een e-mailtest voor A/B niet automatisch kon worden geselecteerd, waardoor het e-mailbericht niet werd verzonden. Dit gedrag kan optreden als de levering binnen **[!UICONTROL retryInProgress]** status.
* Probleem verholpen waarbij een foutbericht werd weergegeven wanneer de parameters van een e-mail met een A/B-test opnieuw werden geopend.

_Soorten publiek en vragen_

* Probleem verholpen waarbij gegevens niet konden worden benaderd en query&#39;s werden ingesteld voor ontvangers die van Adobe Campaign Classic naar Standard zijn gerepliceerd.
* Probleem verholpen die optrad bij het gebruik van een veld met filtertypen in de query-editor nadat de opdracht **Aantal** of **Voorvertoning** knoppen.

_Workflows_

* De **Facturering** de workflow is geoptimaliseerd om de voorbereidingstijd voor levering te verbeteren .
* Probleem verholpen waardoor bevolkingsgegevens niet konden worden weergegeven in een uitgaande overgang bij het gebruik van een terugkerende leveringsactiviteit.
* Probleem verholpen waarbij werd voorkomen dat records in een overgang werden weergegeven na een **Gegevens bijwerken** activiteit.
* Probleem verholpen waarbij de oorzaak van de **leverabilityUpdate** technische workflow mislukt.

_Integraties_

* Probleem verholpen waardoor internationale tekens niet correct naar Adobe Analytics konden worden verzonden.
* Elementen worden nu sneller geladen wanneer u een afbeelding probeert in te voegen vanuit de elementenbibliotheek van het Experience Cloud in een bericht.
* Probleem verholpen waardoor het venster voor het selecteren van elementen in sommige gevallen niet kon worden gesloten.
* Van een gegevensbrondetail, kunt u tot zijn verwante werkschema nu direct toegang hebben om de staat van het werkschema te controleren.
* U kunt het triggerschema nu rechtstreeks bijwerken wanneer u een triggergebeurtenis definieert of bewerkt. Door deze wijziging hoeft u de publicatie van de trigger niet meer ongedaan te maken en een andere trigger te maken.

_Transactieberichten_

* Oplossing voor een fout met een transactiemalplaatje van het bericht toen de leveringsbron werd uitgebreid.
* Het is nu mogelijk om transactieberichten te verwijderen.

## Release 18.2 - februari 2018 {#release-18-2---february-2018}

**Nieuwe functies**

<table> 
 <thead> 
  <tr> 
   <th> Functionaliteit<br /> </th> 
   <th> Beschrijving<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Abonnement - abonneren op een lijst met profielen voor meerdere services of het abonnement opzeggen<br /> </td> 
   <td> De <strong>Abonnementsservices</strong> met workflowactiviteit kunt u zich nu abonneren op of een abonnement nemen op een lijst met profielen voor meerdere services. Importeer in uw workflow een bestand met de profielen en voor elk profiel, het bewerkingstype en de service. De <strong>Abonnementsservices</strong> Deze gegevens kunnen door activiteit worden gebruikt en alle abonnementen en abonnementen op profielen tegelijk dynamisch worden verwerkt.<br /> Raadpleeg voor meer informatie de <a href="../../automating/using/subscription-services.md">gedetailleerde documentatie</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Verrijkingsactiviteit: verrijkt gegevens op basis van eerdere overgangen<br /> </td> 
   <td> De nieuwe <span class="uicontrol">Verrijking</span> Met workflowactiviteit kunt u de binnenkomende overgangen benutten en de uitvoerovergang voltooien met extra gegevens. Als u profielen als doel instelt, kunt u met de verrijkingsactiviteit de profielgegevens verrijken met aanvullende gegevens die niet in de database zijn opgeslagen (bijvoorbeeld afkomstig uit een geïmporteerd bestand).<br /> Raadpleeg voor meer informatie de <a href="../../automating/using/enrichment.md">gedetailleerde documentatie</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Patches**

_Platform_

* De bovenste balk van de Adobe Campaign-interface is bijgewerkt met het nieuwe menu Experience Cloud.
* Probleem verholpen waarbij koppeling naar **[!UICONTROL Offers]** in de vervolgkeuzelijst Oplossing worden weergegeven.

_E-mail, SMS-berichten en direct mail_

* De voorbereidingsfase van de levering is verbeterd om de prestaties te verbeteren.
* Verschillende problemen verholpen die ertoe konden leiden dat traceringslogbestanden in bepaalde nichesituaties beschadigd werden.
* Oplossing voor een probleem met een update van de contactdatum dat optrad toen de contactdatum tussen de voorbereiding en de bevestiging van de levering werd gewijzigd. Wanneer u nu de contactdatum na de voorbereiding wijzigt, moet u de levering opnieuw voorbereiden voordat u de verzending kunt bevestigen. Zie de [gedetailleerde documentatie](../../sending/using/preparing-the-send.md).

_Pushmeldingen_

* Correctie van een fout waardoor sommige personalisatievelden niet werkten in pushberichten van iOS.
* Probleem verholpen waarbij de klik en open frequenties werden weergegeven als 0% op het dashboard voor pushmeldingen.

_Rapporten_

* Probleem verholpen waarbij de rapportlijst in sommige browsers als leeg werd weergegeven.
* Oplossing voor een fout in het dialoogvenster **[!UICONTROL Report sharing]** de technische workflow vlak voordat de vervallimiet is bereikt.

_Workflows_

* Probleem verholpen waarbij activiteiten niet toegankelijk mochten zijn na slepen en neerzetten.
* Probleem verholpen waarbij de volgorde van uitvoerovergangen van een **[!UICONTROL Segmentation]** in sommige situaties te veranderen.
* Oplossing voor een fout die optrad bij het lezen van een publiek dat een opsommingstype veld bevatte en dat eerder was opgeslagen via een workflow
* Probleem verholpen waardoor de **[!UICONTROL Request confirmation before sending messages]** optie om gecontroleerd te blijven zelfs nadat het unchecking wanneer het bepalen van de het plannen eigenschappen van een levering die in een werkschema wordt gecreeerd.
* Automatisch verwijderen van dubbele rijen (DISTINCT-component) kan nu worden uitgeschakeld in **[!UICONTROL Query]** via een nieuwe optie in de **[!UICONTROL Additional data]** tab. U wordt aangeraden deze optie uit te schakelen wanneer u veel (meer dan 100) extra elementen definieert, om redenen van prestaties.

_Integraties_

* Er zijn enkele verbeteringen aangebracht in de **[!UICONTROL Data sources]** configuratiescherm.

_Bekende problemen_

We raden u aan Internet Explorer versie 11 niet te gebruiken vanwege mogelijke weergaveproblemen.

Sommige problemen kunnen zich voordoen bij het gebruik van contextafhankelijke Help-koppelingen vanuit de Campagne-interface. Zij worden vastgesteld in 18.3.

## Release 18.1 - januari 2018 {#release-18-1---january-2018}

**Nieuwe functies**

<table> 
 <thead> 
  <tr> 
   <th> Functionaliteit<br /> </th> 
   <th> Beschrijving<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Rapportage voor vermoeidheidsbeheer<br /> </td> 
   <td> De rapportering voor het Beheer van de Vermoeidheid is een specifiek, configureerbaar rapport dat de gevolgen de regels van de Vermoeidheid op leveringen over e-mail, Duw, SMS, en de Directe kanalen van de Post binnen een gespecificeerde datumwaaier toont alvorens te verzenden. Met het toegevoegde inzicht om alle conflicterende campagnes in één enkele mening snel te kunnen zien, kunnen de marketers marketing campagnes volgens de vastgestelde vermoeidheidsregels effectiever plannen, en mededelingen prioriteren.<br /> Raadpleeg voor meer informatie de <a href="../../sending/using/fatigue-rules.md#viewing-the-fatigue-rule-summary-report">gedetailleerde documentatie</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Rapportage delen<br /> </td> 
   <td> Met gedeelde rapporten kunt u uw rapporten delen met Adobe Campaign-gebruikers als e-mailbijlage, inclusief op een geautomatiseerde terugkerende basis. Gebruikers die terugkerende rapporten ontvangen, kunnen hun abonnement op deze berichten opzeggen via een speciale koppeling in elke e-mail.<br /> Raadpleeg voor meer informatie de <a href="../../reporting/using/reporting-interface.md#share-tab">gedetailleerde documentatie</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Nieuwe mogelijkheden duwen<br /> </td> 
   <td> Push Message Preview - Voorvertoning van pushberichten weergeven op iOS- en Android-apparaten vanuit de inhoudeditor voor pushberichten om precies te zien wat de ontvangers zullen zien voordat ze de levering testen of uitvoeren.<br /> Raadpleeg voor meer informatie de <a href="../../channels/using/preparing-and-sending-a-push-notification.md#preparing-the-notification">gedetailleerde documentatie</a>.<br /> Inhoud beschikbaar - Als apps niet gedurende langere perioden worden geopend, kunnen hun gegevens verouderd raken. Dit betekent dat de gegevens moeten worden bijgewerkt of vervangen op het moment dat een gebruiker de app eindelijk opent, wat kan leiden tot vertragingen bij het gebruik van de app. Met de extra ondersteuning voor Beschikbare inhoud kunnen Adobe Campaign-gebruikers hun app wakker maken om de gegevens op de achtergrond te vernieuwen bij het verzenden van een pushmelding, waardoor ze consistenter kunnen zijn en meer controle kunnen krijgen over de ervaringen in de app van een gebruiker.<br /> Mutable Content - Met de toegevoegde ondersteuning van Mutable Content kunnen Adobe Campaign-gebruikers hun mobiele app-extensies nu gebruiken om de inhoud of presentatie van aankomende pushberichten die vanuit Adobe Campaign worden verzonden, verder te wijzigen. Gebruikers kunnen bijvoorbeeld Mutable Content gebruiken voor: <br /> 
    <ul> 
     <li> gegevens decoderen die in een gecodeerde indeling zijn geleverd </li> 
     <li> afbeeldingen of andere mediabestanden downloaden en toevoegen als bijlagen aan een melding </li> 
     <li> de tekst van de hoofdtekst of titel van een kennisgeving wijzigen </li> 
     <li> voeg een draadherkenningsteken aan een bericht toe </li> 
    </ul> Raadpleeg voor meer informatie over Beschikbare inhoud en Mabelinhoud de <a href="../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-ios">gedetailleerde documentatie</a>.<br /> <strong>Waarschuwing:</strong> deze updates van pushberichten vereisen dat klanten hun mobiele toepassingen upgraden . Zie <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/configuring-mobile/push-payload.html?lang=nl-NL">dit technote</a> voor meer informatie .<br /> </td> 
  </tr> 
  <tr> 
   <td> Geoptimaliseerde leveringen in tijdzone<br /> </td> 
   <td> Plan terugkerende e-mail-, SMS- en pushberichten die op een bepaalde dag/tijd in de tijdzone van elke ontvanger moeten worden bezorgd, zodat uw berichten op het juiste moment worden afgeleverd zonder dat u meerdere leveringen hoeft in te stellen. <br /> Raadpleeg voor meer informatie de <a href="../../automating/using/scheduler.md">gedetailleerde documentatie</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> API Signaalactiviteit activeren<br /> </td> 
   <td> Het is nu mogelijk om een signaalactiviteit voor uw werkschema's direct van Adobe Campaign Standard API teweeg te brengen.<br /> Raadpleeg voor meer informatie de <a href="/help/api/using/triggering-a-signal-activity.md">gedetailleerde documentatie</a> .<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Patches**

_Platform_

* Het zoeken naar profielen is geoptimaliseerd om de prestaties te verbeteren.
* De interne id van standaardbeveiligingsgroepen bevindt zich nu in de modus Alleen-lezen voor standaardgebruikers.

_E-mail, SMS-berichten en direct mail_

* Oplossing voor een weergaveprobleem dat optrad bij het invoegen van emoties in de inhoud van uw leveringen.
* Probleem verholpen waarbij de gebruiker toegang kreeg tot verzendende logboeken terwijl de levering nog in de editie stond.
* De **[!UICONTROL Scheduler]** activiteit staat u nu toe om uw leveringen afhankelijk van de tijdzone van de ontvanger te verzenden.
* SMS: De optie **[!UICONTROL Store incoming MO]** in de database is toegevoegd aan externe accounts. Als deze optie is ingeschakeld, worden alle inkomende SMS opgeslagen in de **inSMS** tabel.
* SMS: De diensten zijn nu verbonden aan een gebeurtenis in plaats van een transactiesjabloon.
* SMS: De standaard SMTP verbindingstijd is verminderd tot 30 seconden.

_Pushmeldingen_

* Probleem verholpen waardoor levering van pushberichten niet kon worden gestopt.
* Er is een optie toegevoegd in de geavanceerde opties voor pushmeldingen om de toepassing weer te geven met een pushmelding.
* Er is een pauzeknop toegevoegd voor de voorvertoningsvideo voor pushmeldingen.
* De voorvertoning van de pushmelding is nu beschikbaar voor verschillende apparaten, zoals iPhone, Android, tablets.

_Rapporten_

* Probleem verholpen waarbij frequenties van meer dan 100% werden weergegeven.
* Probleem verholpen waardoor gebruikers geen rapporten konden downloaden in CSV.
* Een nieuwe **[!UICONTROL Report]** item op de startpagina.

_Workflows_

* Probleem verholpen die tot een foutbericht leidde wanneer aanvullende gegevens in een query werden gebruikt en aliassen met spaties werden toegevoegd. De niet-alfanumerieke tekens worden nu vervangen door &quot;_&quot;.
* Probleem verholpen waarbij de technische workflow voor het berekenen van KPI&#39;s in sommige gevallen standaard kon worden gestopt.

_Profielen en publiek_

* Oplossing voor een fout die optrad bij het toevoegen van meerdere filters in de query van een publiek.
* Oplossing voor een weergaveprobleem dat optrad bij het wijzigen van de afbeelding van een profiel.
* Knopinfo toegevoegd met het exacte resultaatnummer na het tellen van de populatie van een query.
* Probleem verholpen waardoor een gebruiker geen publiek kon selecteren of het venster van de publiekskiezer kon sluiten.
* De lijst met beschikbare functies in de expressieeditor is bijgewerkt. De **FormatCurrency** en **ConvertCurrency** functies zijn verwijderd.
