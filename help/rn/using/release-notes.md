---
title: Laatste release
description: Op deze pagina vindt u informatie over de inhoud van de nieuwste release van Campaign Standard.
page-status-flag: never-activated
uuid: 1cf2e40c-beca-43db-8261-a1820ee86ad3
contentOwner: vignes
products: SG_CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
discoiquuid: 5c7bfb74-4002-4ffe-87e8-bddb41d34b41
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 8d55a92deeccabcb6970de6cce4b5e297bc431d8
workflow-type: tm+mt
source-wordcount: '2441'
ht-degree: 4%

---


# Laatste release{#latest-release}

[Releaseplanning](../../rn/using/release-planning.md) | [Releases van het Configuratiescherm](https://docs.adobe.com/content/help/nl-NL/control-panel/using/release-notes.html) | [Updates van documentatie](../../rn/using/documentation-updates.md) | [Opmerkingen bij eerdere releases](../../rn/using/release-notes-2020.md) | [Verouderde functies](../../rn/using/deprecated-features.md)

## Release 20.4 - oktober 2020 {#release-20-4---october-2020}

**Nieuwe functies**

<table> 
<thead> 
<tr> 
<th> <strong>Controlegroepen</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
  <td> <p>U kunt nu <strong>Controlegroepen</strong> gebruiken om de impact van uw campagnes te meten door een deel van hun publiek uit te sluiten. Vervolgens kunt u het gedrag van de doelgroep die de boodschap heeft ontvangen, vergelijken met het gedrag van contacten die niet als doelgroep werden beschouwd. Gebaseerd op de verzendende logboeken, kunt u een controlegroep in toekomstige campagnes ook richten.
</p>
<p>For more information refer to the <a href="../../sending/using/control-group.md">detailed documentation</a> and <a href="https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/communication-channels/email/control-groups.html">how-to video</a>.
</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>Externe API - OAuth-ondersteuning</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
  <td> <p>Adobe Campaign ondersteunt nu OAuth voor verificatie in de <strong>externe API</strong> -workflowactiviteit. Dit nieuwe vermogen opent de capaciteit voor deze activiteit om met systemen te communiceren die OAuth steun vereisen.
</p>
<p>For more information refer to the <a href="../../automating/using/external-api.md">detailed documentation</a>.
</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>Integratie van AIR op reis</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
  <td> <p>We zijn erg blij dat we Journey AI voor alle Adobe Campaign Standard-klanten bekendmaken.</p>
  <p>Journey AI maakt gebruik van Advanced Machine Learning (ML) om bedrijven in staat te stellen het ontwerp en de levering van klantreizen te optimaliseren door de voorkeur van elk individu voor de service te voorspellen.</p>
  <P>Reis AI bestaat uit twee ML-kenmerken:</p>
<ul> 
     <li> <strong>Predictive Engagement Scoring</strong> - Intelligent identificeert het voorkeursniveau van klanten om berichten beter te richten en te personaliseren om omzettingen en behoud te verhogen. Bekijk de <a href="https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/communication-channels/email/journey-ai/predictive-engagement-scoring.html">Hoe kan ik-video</a>.</li> 
     <li> <strong>Voorspellende optimalisatie</strong> van verzendtijd - Verwacht de beste tijd om e-mails naar elk individu te verzenden in een campagne om de betrokkenheidspercentages te maximaliseren en het investeringsrendement van de e-mailcampagne te verbeteren. Bekijk de <a href="https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/communication-channels/email/journey-ai/predictive-send-time-optimization.html">Hoe kan ik-video</a>.</li>
    </ul>
  <p>Als u wilt leren hoe u aan de slag gaat met Journey AI, raadpleegt u de <a href="../../sending/using/predictive.md">gedetailleerde documentatie</a> en neemt u contact op met uw accountmanager. Hoewel Journey AI gratis beschikbaar is voor bestaande campagneklanten, zijn er implementatiekosten van ongeveer 50 uur.</p>
    </td> 
</tr> 
</tbody> 
</table>

**Verbeteringen**

* **Privacybeheer**: Het **CCPA-veld Opt-Out** , dat beschikbaar was via de Campagne-interface en API, wordt nu ook ondersteund via de Privacy Core Service. In dit veld kunnen Adobe Campaign-gebruikers bijhouden of een consument heeft gekozen voor de verkoop van persoonlijke gegevens. [Meer informatie](https://helpx.adobe.com/content/help/en/campaign/kb/acs-privacy.html#ccpa)
* **Verbeteringen** voor workflowuitvoering (bèta): in het kader van een wereldwijd initiatief inzake workflows zijn enkele belangrijke verbeteringen ontwikkeld om het geheugenbeheer te stabiliseren , de latentie te verminderen en het geheugen dat werkstromen tijdens de uitvoering verbruiken te optimaliseren . Deze verbeteringen zijn momenteel in bèta, en slechts beschikbaar aan een reeks klanten. De algemene beschikbaarheid is gepland voor begin 2021.
* Voor een betere beveiliging gebruikt Campagne nu een **handtekeningmechanisme** voor het bijhouden van koppelingen in e-mails.
* De configuratie van mobiele apps is verbeterd dankzij **duidelijkere foutmeldingen** tijdens het uploaden van iOS-certificaten of Android-sleutels.
* Er is nu een **nieuwe leveringstoewijzing** (mapRtEventAppSubRcp) beschikbaar voor transactieberichten die zich richten op profielen. De leverings-, uitsluitings- en trackinglogboeken voor deze leveringen zijn nu beschikbaar in de tabellen wideLogAppSubRcp, excludeLogAppSubRcp en trackingLogAppSubRcp. Dit lost een kwestie op die leveringsanalyse om veroorzaakte te ontbreken wanneer het verzenden van een transactie duw bericht gebruikend de het doeldimensie van het **Profiel** .
* **Het beheer van** SMS-fouten is verbeterd om te voorkomen dat te veel profielen worden toegevoegd aan de quarantainelijst. Door gebrek, worden de fouten van SMS nu gevormd als zachte fouten in plaats van harde fouten. Zie [deze pagina](https://helpx.adobe.com/nl/campaign/kb/sms-connector-protocol-and-settings.html).

**Verbeteringen voor de Email Designer**

* We hebben de gebruikerservaring in de e-mailontwerper verbeterd met de **nieuwe dynamische contextafhankelijke Help** die de gebruikersinterface en documentatie volledig met elkaar verbindt en eenvoudige toegang biedt tot de nieuwste Help-inhoud.
* Probleem verholpen waarbij regeleinden in een bericht werden verwijderd tijdens het bewerken van de tekstversie. (CAMP-44483)
* Probleem verholpen waarbij de automatische tekstversie van een HTML-sjabloon niet kon worden gegenereerd en gesynchroniseerd. (CAMP-44195)
* Probleem verholpen dat zich kon voordoen bij het wijzigen van het formaat van afbeeldingen. Nadat de berichten waren verzonden, werden de afbeeldingen niet correct weergegeven in Microsoft Outlook. (CAMP-44656)
* Oplossing voor een probleem dat optrad bij het invoegen van een knop en het instellen van de breedte op &quot;auto&quot;. Nadat het bericht was verzonden, werd de inhoud van de knop niet volledig weergegeven. (CAMP-44560)
* Probleem verholpen die optrad bij het uploaden van inhoud uit een gekoppeld HTML-bestand. Nadat het bericht naar een Gmail-adres was verzonden, werd de CSS niet toegepast, waardoor een renderingprobleem ontstond. (CAMP-44085)
* Probleem verholpen waardoor inhoudsfragmenten die eerder in een bericht werden gebruikt, niet konden worden bijgewerkt toen ze rechtstreeks in de inhoudssjabloon werden gewijzigd. (CAMP-43973)
* Probleem verholpen met de zoekbalk **Fragments** . Bij het zoeken naar een bestaand fragment heeft de zoekbalk geen resultaat opgeleverd. (CAMP-44223)
* Probleem verholpen met de zoekbalken voor **inhoudsblokken** en **fragmenten** . Als u een van de zoekbalken gebruikt, worden de resultaten alleen weergegeven als u op Meer resultaten **tonen hebt geklikt...**. (CAMP-44205)
* Probleem verholpen waarbij opvulling tussen tekst en afbeeldingen niet kon worden toegepast in Microsoft Outlook. (CAMP-45370)
* Probleem verholpen bij het dupliceren van een fragment. Nadat het fragment is gedupliceerd, bevat het oorspronkelijke fragment ontbrekende HTML-lijnen. (CAMP-45207)
* Oplossing voor een fout die weergaveproblemen in Microsoft Outlook veroorzaakte. (CAMP-44749)
* Oplossing voor een fout die optrad bij het wijzigen van de opvulling van de **structuurcomponent** in een leveringssjabloon. CSS-tags hebben de wijzigingen die zijn aangebracht in de opvulling die een renderingprobleem veroorzaakt, niet overgenomen. (CAMP-45381)
* Probleem verholpen tijdens het uploaden van een afbeelding. De hoogte van de afbeelding wordt automatisch ingesteld op 0, waardoor een renderingprobleem ontstaat. (CAMP-45366)

**Overige wijzigingen**

* Er zijn nieuwe mechanismen toegevoegd bij een fout tijdens het importeren van een publiek in een Experience Platform via een **Lees publiek** -activiteit. (CAMP-43947, CAMP-43366)
* De eenheden van de organisatie worden nu automatisch geplaatst om de organisatorische eenheid van de gebruiker te passen die het profiel of de entiteit creeert. Organisatorische eenheden kunnen niet meer worden verwijderd en leeg blijven.
* Wanneer u een aangepaste bron publiceert, wordt na de voorbereiding een bevestigingspop-up weergegeven.
* Het pop-upbericht dat wordt weergegeven wanneer een aangepaste bron mislukt, is verbeterd voor meer duidelijkheid.
* De expressie-editor in workflows is verbeterd om uitvoeringsfouten te voorkomen. [Er zijn nieuwe functies](../../automating/using/customizing-workflow-external-parameters.md) beschikbaar: ze kunnen worden gebruikt in alle activiteiten waarmee u gebeurtenisvariabelen kunt gebruiken nadat u een workflow met externe parameters hebt aangeroepen. Bovendien wordt knopinfo nu weergegeven in de expressie-editor met de functiebeschrijving.
* [Er zijn nieuwe filters](../../administration/using/configuring-transactional-messaging.md#searching-transactional-events) toegevoegd aan de lijst met transactiegebeurtenissen. Hiermee kunt u de gebeurtenisconfiguraties filteren op basis van hun status en de laatste keer dat een gebeurtenis is ontvangen.
* De logboeken die worden weergegeven bij het exporteren van pakketten, zijn specifieker en gedetailleerder weergegeven over de fouten die zijn aangetroffen bij een fout.
* Nadat u een bericht hebt verzonden, kunt u nu de lijst met [bijgehouden URL&#39;s zoeken, filteren en exporteren](../../sending/using/tracking-messages.md).
* Automatische [synchronisatie tussen Starten en Campagne](../../administration/using/configuring-a-mobile-application.md#aepsdk-workflow) is nu GA en standaard ingeschakeld.
* Transactieberichten kunnen met hoge prioriteit worden verzonden zelfs in geval van significante bulkleveringswerkbelasting.
* De grootte van workflowexportpakketten is geoptimaliseerd door de verzending van proefdrukexportpakketten te verwijderen.
* Er is een nieuw bericht toegevoegd om de grootte van het gedownloade bestand weer te geven in de activiteit **Bestandsoverdracht** .
* Foutberichten voor ongeldige sessietokens zijn verbeterd.
* Een nieuw mechanisme voorkomt nu dat volggebeurtenissen worden toegevoegd aan logboeken en rapporten.
* Er is een nieuw waarschuwingsbericht toegevoegd om het opsporen van fouten in gegevensbeheeractiviteiten te ondersteunen die zijn verbonden met een leveringsactiviteit.
* De labels in de rapportwerkruimte zijn verbeterd.
* Er is een nieuwe validatiestap toegevoegd om te voorkomen dat technische objecten worden verwijderd in transactieberichten.
* Er is een nieuw filter voor de leveringsstatus toegevoegd aan het tabblad **Uitvoerlijst** van een transactiemelding om het oplossen van problemen te verbeteren.
* Om de prestaties te verbeteren en de uitvoeringstijd te optimaliseren, zijn de ongebruikte indexen verwijderd, gebaseerd op gebruiksstatussen van lijsten die in voorlopige analyse voor 350+ klanten worden geïdentificeerd. Betrokken tabellen zijn: nmsaddressStatus, nmscampaign, nmsdelivery, nmslandingpage, nmsprogram, nmsontvanger, nmsseedmember, nmsservice, nmssubhistorycp, nmspubliek, xtkworkflow

**Patches**

* Probleem verholpen waardoor u geen doelkoppeling voor pushberichten of In-App-berichten kon gebruiken wanneer reeksspatiëring was ingeschakeld.
* Probleem verholpen waardoor u mogelijk geen merknamen kunt toewijzen aan een transactie-e-mail. Verschillende foutberichten kunnen tijdens de publicatiestap worden weergegeven. (CAMP-44988)
* Probleem verholpen in de gebruikersinterface van de workflow waardoor gegevens niet konden worden opgeslagen in velden waarvoor numerieke waarden werden aangevraagd. (CAMP-44025)
* Probleem verholpen waarbij een foutbericht kon worden weergegeven wanneer een **testactiviteit** werd gebruikt in een workflow van een importsjabloon. (CAMP-42910)
* Probleem verholpen die optrad bij het gebruik van een **Lees-publiek** -activiteit die een opsommingstype veld bevat en verbonden is met **activiteiten van de Unie** of **Verrijking** . (CAMP-42795)
* Probleem verholpen in dynamische rapporten wanneer de out-of-the-box segmenten werden gebruikt om gegevens in rapporten te filteren. (CAMP-42627)
* Probleem verholpen waardoor u een **planneractiviteit** niet kon instellen op 12.00 uur. (CAMP-42674)
* Probleem verholpen waarbij het verzenden van SMS-berichten kon worden onderbroken wanneer de SMPP-verbinding instabiel was. (CAMP-42789)
* Probleem verholpen waardoor de knop **Stoppen met voorbereiden** niet kon worden weergegeven nadat de pagina was vernieuwd. (CAMP-42721)
* Probleem verholpen waarbij via een hot-klik geen percentages konden worden weergegeven wanneer inhoud uit een URL werd geïmporteerd. (CAMP-44468)
* Probleem verholpen waarbij een time-outfout kon worden weergegeven wanneer een profiel werd geselecteerd voor gebruik in de context van profielvervanging. (CAMP-44746)
* Probleem verholpen waardoor instanties mogelijk niet werken nadat aangepaste bronnen met onjuiste koppelingsdefinities zijn geïmplementeerd. (CAMP-44406)
* Probleem opgelost waarbij lege gekoppelde entiteiten werden gemaakt (typologieën, merken, enz.) na het kopiëren en plakken van een levering in een campagnemalplaatje. (CAMP-44765)
* Probleem verholpen waarbij proofs niet konden worden verzonden vanwege een onjuiste verwerking van de tabellen voor het voorbereiden van de levering in het geval van een database die vastloopt of een eenvoudige database die in Azure opnieuw wordt opgestart.
* Probleem verholpen waarbij koppelingen met Experience Manager-inhoud in een levering die is geconfigureerd met meertalige inhoud niet konden worden verwijderd. (CAMP-44029)
* Probleem verholpen in dynamische rapporten die een foutbericht konden weergeven wanneer werd geprobeerd afmetingen te filteren.  (CAMP-43097)
* Probleem verholpen waarbij een leeg scherm kon worden weergegeven wanneer werd geprobeerd toegang te krijgen tot profielen voor een instantie die is geconfigureerd met aangepaste bronnen die specifieke koppelingsdefinities bevatten. (CAMP-41009)
* Probleem verholpen in workflows die kunnen optreden wanneer een **verrijkingsactiviteit** wordt gebruikt met twee invoeractiviteiten die beide doelbronnen met elkaar verbinden. (CAMP-42133)
* Probleem verholpen waarbij workflows voor importeren werden herhaald bij gebruik van een **bestandsoverdracht** . (CAMP-43754)
* Probleem verholpen waarbij duplicaten niet in aanmerking werden genomen bij het maken van een profiel met geëxporteerde logboeken. (CAMP-45031)
* Probleem verholpen waarbij gegevensdiscrepantie optrad tussen rapporten in Adobe Campaign en rapporten die werden geëxporteerd in PDF-bestanden. (CAMP-43010)
* Correctie van een fout die ervoor zorgde dat de workflow voor directe verzending mislukte wanneer bestaande gegevensvelden in functies werden gebruikt. (CAMP-42737)
* Probleem verholpen bij het importeren van pakketten, waaronder transactiegebeurtenissen en berichtsjablonen. Het importproces is gestopt bij 5%. (CAMP-42544)
* Probleem verholpen waarbij een fout (Uncaught TypeError) werd veroorzaakt na het wijzigen van de **verrijkingsactiviteit** en het toevoegen van aanvullende gegevens in een workflow. (CAMP-41877)
* Probleem verholpen waarbij het verwijderen van de workflow werd voorkomen. Logbestanden moesten worden gewist om de workflow te verwijderen. (CAMP-44144)
* Probleem verholpen bij het maken van een openingspagina met HTML-code. Verplichte selectievakjes werden niet herkend in de campagne en waren niet beschikbaar op de gepubliceerde landingspagina. (CAMP-44181)
* Probleem verholpen waarbij workflows werden herhaald tijdens het gebruik van de activiteit **Wacht** . (CAMP-43981)
* Probleem verholpen bij het verzenden van transactiemeldingen die ertoe leidden dat meerdere e-mailadressen in dezelfde levering meerdere keren als doel werden gekozen. (CAMP-44202)
* Correctie van een fout bij het gebruik van profielvervanging met targetData personalization. (CAMP-44996)
* Probleem opgelost waarbij de voorvertoning van de levering mislukte bij het exporteren van een leveringssjabloon in een pakket. (CAMP-44084)
* Probleem verholpen waarbij proefdrukken niet naar testprofielen konden worden verzonden bij gebruik van aangepaste doeltoewijzingen. (CAMP-43701)
* Oplossing voor een fout die in workflows optrad bij het gebruik van de activiteit **Lezen publiek** en bij het kiezen voor een publiek dat is geconfigureerd met een andere doeldimensie dan **Profiel**.  (CAMP-41885)
* Probleem verholpen dat tot fouten leidde wanneer de technische workflow **updateEventsStatus** te veel tijd in beslag nam om de gebeurtenisgeschiedenis op te halen (toen de workflow werd gestopt). Het ongebruikte geaggregeerde veld &quot;sumQueueTime&quot; is uit de workflow verwijderd om het probleem op te lossen. (CAMP-43920)
* Oplossing voor een geheugenprobleem bij de implementatie van aangepaste bronnen. (CAMP-42909)
* Probleem verholpen in transactiemeldingen waarbij kenmerken in verzamelingen ontbraken. Alle ontbrekende kenmerken worden nu gedefinieerd met een standaardwaarde en opgenomen in de payload. (CAMP-42882)
* Probleem verholpen die van invloed kon zijn op de prestaties bij het opvragen van real-time logbestanden voor gebeurtenisaflevering. (CAMP-42759)
* Oplossing voor een fout die optrad bij het gebruik van bestandsextensies met hoofdletters en kleine letters bij Gedeelde elementen. (CAMP-44159)
* Probleem verholpen waarbij een foutbericht werd weergegeven tijdens het testen van de verbinding met een externe account voordat deze werd gemaakt. De knop Verbinding **** testen wordt nu pas weergegeven nadat het externe account is gemaakt.
* Probleem verholpen waarbij berichten werden achtergelaten als in behandeling nadat de verbeterde MTA opnieuw werd gestart op instanties die met het delen waren geconfigureerd.
* Probleem verholpen waarbij het aantal actieve profielen ertoe kon leiden dat het effectieve aantal verzonden items niet overeenkwam.
* Probleem verholpen dat tot vertraging kon leiden bij het zoeken naar bronnen in de query-editor in een workflow.
* Probleem verholpen bij het selecteren van de optie **Geef de velden op waarmee rekening moet worden gehouden bij het zoeken** van tekst in een aangepaste bron. Als de veldlijst leeg was gelaten, is de publicatie van de aangepaste bron mislukt.
* Oplossing voor een prestatieprobleem bij het weergeven van het overzicht van aangepaste bronnen met een groot gegevensvolume.
* Probleem verholpen waardoor een levering niet kon worden geïmporteerd met gebruik van vervangende profielen.
* Probleem verholpen bij het gebruik van profielvervanging waardoor proofs niet meteen konden worden verzonden als de levering gepland was.
* Het probleem dat optrad bij het uploaden van een Android-toets voor een mobiele toepassing, is opgelost. Het bericht dat werd weergegeven nadat de toets was geüpload, toonde de waarde van de voormalige toets.
* Probleem verholpen waarbij testprofielen niet konden worden gemaakt van transactieberichten nadat een gebeurtenisconfiguratie met een verzameling zonder kenmerk was gemaakt.
* Probleem verholpen waarbij het publiceren van aangepaste bronnen kon worden voorkomen nadat een nieuw filter met een aggregaat was gemaakt.
* Probleem verholpen waarbij een fout is opgetreden bij het bijhouden van de open snelheid voor Gmail-ontvangers die is veroorzaakt door de Gmail-proxy voor de afbeelding.
* Probleem verholpen waarbij tijdens het importeren van een pakket fouten in het geheugen werden veroorzaakt.
* Probleem opgelost waarbij de ontkoppelactie van de Experience Manager mislukte wanneer de inhoud van de Experience Manager een pad met het teken &quot;%20&quot; bevatte.
* Oplossing voor een fout op labels tijdens het dupliceren van workflowactiviteiten.
* Probleem verholpen met de transactiemeldkiezer op een landingspagina toen de optie Bericht **verzenden** starten was geselecteerd.
* Probleem verholpen met transactieberichten of terugkerende leveringen die ervoor zorgden dat de leveringsstatus niet met de juiste standaardwaarde kon worden geïnitialiseerd. Foutlogboeken zijn ook verbeterd.
* Probleem verholpen waarbij het **abonnement werd uitgebreid naar een toepassingsschema** (appSubscriptionRcp) met een profielkoppeling met behulp van een aangepast veld. De index is niet automatisch gemaakt, wat invloed kan hebben op de verzendtijd van de drukker. (CAMP-41120)

