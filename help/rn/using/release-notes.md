---
solution: Campaign Standard
product: campaign
title: Laatste release
description: Op deze pagina vindt u content van de nieuwste release van Campaign Standard
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
translation-type: tm+mt
source-git-commit: a0ad969c86a5047f3f967a21fdc2d6040d7d939f
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Laatste release{#latest-release}

[Releaseplanning](../../rn/using/release-planning.md) | [Releases van het Configuratiescherm](https://docs.adobe.com/content/help/nl-NL/control-panel/using/release-notes.html) | [Updates van documentatie](../../rn/using/documentation-updates.md) | [Opmerkingen bij eerdere releases](../../rn/using/release-notes-2020.md) | [Verouderde functies](../../rn/using/deprecated-features.md)

![](assets/do-not-localize/cp-icon.png) **Release van nieuw Configuratiescherm in oktober** met domeinconfiguratie met CNAME-records en nieuwe mogelijkheden voor databasecontrole. [Meer informatie](https://docs.adobe.com/content/help/en/control-panel/using/release-notes.html).

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
  <td> <p>U kunt nu <strong>Controlegroepen</strong> gebruiken om de invloed van uw campagnes te meten door een deel van hun doelgroep uit te sluiten. Vervolgens kunt u de gedragingen van de doelgroep die het bericht heeft ontvangen, vergelijken met de gedragingen van contactpersonen die niet zijn getarget. Op basis van de verzendlogboeken kunt u in toekomstige campagnes ook een controlegroep targeten.
</p>
<p>Raadpleeg de <a href="../../sending/using/control-group.md">gedetailleerde documentatie</a> en de <a href="https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/communication-channels/email/control-groups.html?lang=nl#communication-channels">instructievideo</a> voor meer informatie.
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
  <td> <p>Adobe Campaign ondersteunt nu OAuth voor verificatie in de <strong>Externe API</strong>-workflowactiviteit. Dankzij deze nieuwe mogelijkheid kan deze activiteit communiceren met systemen die OAuth-ondersteuning vereisen.
</p>
<p>Raadpleeg de <a href="../../automating/using/external-api.md">gedetailleerde documentatie</a> voor meer informatie.
</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>Journey AI-integratie</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
  <td> <p>Met veel plezier kondigen we Journey AI aan voor alle Adobe Campaign Standard-klanten.</p>
  <p>Journey AI maakt gebruik van geavanceerde Machine Learning (ML) waarmee bedrijven het ontwerp en de levering van klantjourneys kunnen optimaliseren door de betrokkenheidsvoorkeur van elk individu te voorspellen.</p>
  <P>Journey AI bestaat uit twee ML-kenmerken:</p>
<ul> 
     <li> <strong>Voorspellende betrokkenheidsscores</strong> - Intelligente identificatie van het geprefereerde betrokkenheidsniveau van klanten om berichten beter te kunnen targeten en personaliseren voor meer conversies en retentie. Bekijk de <a href="https://docs.adobe.com/content/help/nl-NL/campaign-standard-learn/tutorials/communication-channels/email/journey-ai/predictive-engagement-scoring.html">instructievideo</a>.</li> 
     <li> <strong>Voorspellende optimalisatie van verzendtijd</strong> - Voorspelt voor elk individu het beste tijdstip om in een campagne e-mails te verzenden voor maximale betrokkenheid en een beter rendement van de e-mailcampagne. Bekijk de <a href="https://docs.adobe.com/content/help/nl-NL/campaign-standard-learn/tutorials/communication-channels/email/journey-ai/predictive-send-time-optimization.html">instructievideo</a>.</li>
    </ul>
  <p>Als u wilt weten hoe u aan de slag kunt met Journey AI, raadpleegt u de <a href="../../sending/using/predictive.md">gedetailleerde documentatie</a> en neemt u contact op met uw accountmanager. Hoewel Journey AI gratis beschikbaar is voor bestaande Campaign-klanten, zijn er implementatiekosten van ongeveer 50 uur.</p>
    </td> 
</tr> 
</tbody> 
</table>

**Verbeteringen**

* **Privacybeheer**: Het veld **CCPA-opt-out**, dat beschikbaar was via de Campaign-interface en -API, wordt nu ook ondersteund door de Privacy-kernservice. In dit veld kunnen Adobe Campaign-gebruikers bijhouden of een consument zich heeft afgemeld voor de verkoop van persoonlijke gegevens. [Meer informatie](https://helpx.adobe.com/nl/campaign/kb/acs-privacy.html#ccpa)
* **Verbeteringen voor workflowuitvoering** (bèta): in het kader van een wereldwijd initiatief inzake workflows zijn een paar belangrijke verbeteringen ontwikkeld om het geheugenbeheer te stabiliseren, latentie te verminderen en het geheugen dat door workflows tijdens de uitvoering wordt verbruikt te optimaliseren. Deze verbeteringen zijn momenteel in bètaversie beschikbaar en alleen voor een beperkt aantal klanten. Algemene beschikbaarheid staat gepland voor begin 2021.
* Voor een betere beveiliging gebruikt Campaign nu een **handtekeningmechanisme** voor het bijhouden van koppelingen in e-mails.
* De configuratie van mobiele apps is verbeterd dankzij **duidelijkere foutmeldingen** tijdens het uploaden van iOS-certificaten of Android-sleutels.
* **Sms-foutbeheer** is verbeterd om te voorkomen dat te veel profielen worden toegevoegd aan de quarantainelijst. Sms-fouten worden nu standaard geconfigureerd als ‘zachte’ fouten in plaats van ‘harde’ fouten. Zie [deze pagina](https://helpx.adobe.com/nl/campaign/kb/sms-connector-protocol-and-settings.html).

**Verbeteringen voor Email Designer**

* We hebben de gebruikerservaring in Email Designer verbeterd met de **nieuwe dynamische contextafhankelijke Help**, die de gebruikersinterface en documentatie volledig met elkaar verbindt en eenvoudig toegang biedt tot de nieuwste Help-content.
* Er is een probleem opgelost waardoor regeleinden in een bericht werden verwijderd tijdens het bewerken van de tekstversie. (CAMP-44483)
* Er is een probleem opgelost waardoor de gewone tekstversie van een HTML-sjabloon niet automatisch kon worden gegenereerd en gesynchroniseerd. (CAMP-44195)
* Er is een probleem opgelost dat kon optreden bij het wijzigen van de grootte van afbeeldingen. Nadat de berichten waren verzonden, werden de afbeeldingen in Microsoft Outlook niet correct weergegeven. (CAMP-44656)
* Er is een probleem opgelost dat optrad als er een knop werd ingevoegd waarvan de breedte werd ingesteld op ‘auto’. Nadat het bericht was verzonden, werd de inhoud van de knop niet volledig weergegeven. (CAMP-44560)
* Er is een probleem opgelost dat optrad bij het uploaden van content vanuit een gekoppeld HTML-bestand. Nadat het bericht naar een Gmail-adres was verzonden, werd de CSS niet toegepast, waardoor een renderingprobleem ontstond. (CAMP-44085)
* Er is een probleem opgelost waardoor contentfragmenten die eerder in een bericht werden gebruikt, niet konden worden bijgewerkt als ze rechtstreeks in de contentsjabloon waren gewijzigd. (CAMP-43973)
* Er is een probleem opgelost met de zoekbalk **Fragmenten**. Bij het zoeken naar een bestaand fragment toonde de zoekbalk geen resultaat. (CAMP-44223)
* Er is een probleem opgelost met de zoekbalken **Contentblokken** en **Fragmenten**. Bij gebruik van een van de zoekbalken werden de resultaten alleen weergegeven als u klikte op **Meer resultaten tonen**. (CAMP-44205)
* Er is een probleem opgelost waardoor opvulling tussen tekst en afbeeldingen in Microsoft Outlook niet kon worden toegepast. (CAMP-45370)
* Er is een probleem opgelost bij het dupliceren van een fragment. Na de duplicatie van het fragment ontbraken er HTML-regels in het oorspronkelijke fragment. (CAMP-45207)
* Er is een fout opgelost die weergaveproblemen in Microsoft Outlook veroorzaakte. (CAMP-44749)
* Er is een fout opgelost die optrad bij het wijzigen van de opvulling van het **structuuronderdeel** in een leveringssjabloon. CSS-tags hebben de wijzigingen die zijn aangebracht in de opvulling niet overgenomen, wat een renderingprobleem veroorzaakt. (CAMP-45381)
* Er is een probleem opgelost bij het uploaden van een afbeelding. De hoogte van de afbeelding werd automatisch ingesteld op 0, waardoor een renderingprobleem ontstond. (CAMP-45366)

**Overige wijzigingen**

* Er zijn mechanismen toegevoegd voor een nieuwe poging voor het geval een fout optreedt tijdens het importeren van een Experience Platform-doelgroep met een **Doelgroep lezen**-activiteit. (CAMP-43947, CAMP-43366)
* Organisatie-eenheden worden nu automatisch zo ingesteld dat ze overeenkomen met de organisatie-eenheid van de gebruiker die het profiel of de entiteit maakt. Organisatie-eenheden kunnen niet meer worden verwijderd en leeg blijven.
* Bij het publiceren van een aangepaste bron wordt nu na de voorbereiding ter bevestiging een pop-upvenster weergegeven.
* Het pop-upbericht dat wordt weergegeven wanneer een aangepaste bron mislukt, verschaft nu meer duidelijkheid.
* De expressie-editor in workflows is verbeterd om uitvoeringsfouten te voorkomen. Er zijn [nieuwe functies](../../automating/using/customizing-workflow-external-parameters.md) beschikbaar: deze kunnen worden gebruikt in alle activiteiten waarmee u gebeurtenisvariabelen kunt gebruiken na het aanroepen van een workflow met externe parameters. Bovendien wordt in de expressie-editor nu knopinfo weergegeven met de functiebeschrijving.
* Er zijn [nieuwe filters](../../administration/using/configuring-transactional-messaging.md#searching-transactional-events) toegevoegd aan de lijst met transactiegebeurtenissen. Hiermee kunt u de gebeurtenisconfiguraties filteren op basis van hun status en de laatste keer dat een gebeurtenis is ontvangen.
* De logboeken die worden weergegeven bij het exporteren van pakketten bevatten nu meer specifieke en gedetailleerde informatie over de fouten die zijn aangetroffen bij een mislukking.
* Na verzending van een bericht kunt u nu de lijst met [bijgehouden URL’s](../../sending/using/tracking-messages.md) doorzoeken, filteren en exporteren.
* Automatische [synchronisatie tussen Launch en Campaign](../../administration/using/configuring-a-mobile-application.md#aepsdk-workflow) is nu algemeen verkrijgbaar en standaard ingeschakeld.
* De grootte van workflowexportpakketten is geoptimaliseerd door de verzending van proefexportpakketten te verwijderen.
* Er is een nieuw bericht toegevoegd om de grootte van het gedownloade bestand in de activiteit **Bestandsoverdracht** weer te geven.
* Foutberichten voor ongeldige sessietokens zijn verbeterd.
* Er is nu een nieuw mechanisme dat voorkomt dat trackinggebeurtenissen van proxy’s worden toegevoegd aan trackinglogboeken en rapporten.
* Er is een nieuw waarschuwingsbericht toegevoegd om te helpen bij het opsporen van fouten in databeheeractiviteiten die zijn verbonden met een leveringsactiviteit.
* De labels in de rapportagewerkruimte zijn verbeterd.
* Er is een nieuwe validatiestap toegevoegd om te voorkomen dat technische objecten in transactionele berichten worden verwijderd.
* Er is een nieuw filter voor de leveringsstatus toegevoegd aan het tabblad **Uitvoeringslijst** van een transactioneel bericht om het oplossen van problemen te verbeteren.
* Voor het verbeteren van de prestaties en het optimaliseren van de uitvoeringstijd zijn ongebruikte indexen verwijderd, op basis van gebruiksstatistieken van tabellen die in voorlopige analyses van meer dan 350 klanten zijn geïdentificeerd. De betreffende tabellen zijn: nmsaddressStatus, nmscampaign, nmsdelivery, nmslandingpage, nmsprogram, nmsrecipient, nmsseedmember, nmsservice, nmssubhistorcp, nmsaudience en xtkworkflow

**Patches**

* Er is een probleem opgelost waardoor u geen bestemmingskoppeling voor pushmeldingen of in-app-berichten kon gebruiken wanneer tracking was ingeschakeld.
* Er is een probleem verholpen waarbij hoge prioriteit in transactieberichten niet in acht werd genomen bij grote bulkleveringen.
* Er is een probleem opgelost waardoor u mogelijk geen merken kon toewijzen aan een transactionele e-mail. Tijdens de publicatiestap werden verschillende foutberichten weergegeven. (CAMP-44988)
* Er is een probleem opgelost in de gebruikersinterface van de workflow waardoor data mogelijk niet konden worden opgeslagen in velden waarvoor numerieke waarden vereist waren. (CAMP-44025)
* Er is een probleem opgelost waardoor mogelijk een foutbericht werd weergegeven wanneer een **test** activiteit werd gebruikt in een workflow van een importsjabloon. (CAMP-42910)
* Er is een probleem opgelost dat optrad bij het gebruik van een **Doelgroep lezen**-activiteit die een opsommingsveld bevatte en verbonden was met activiteiten voor **Samenvoeging** of **Verrijking**. (CAMP-42795)
* Er is een probleem opgelost in dynamische rapporten bij het gebruik van kant-en-klare segmenten om data in rapporten te filteren. (CAMP-42627)
* Er is een probleem opgelost waardoor u een **Planner**-activiteit niet kon instellen op 12.00 uur. (CAMP-42674)
* Er is een probleem opgelost waardoor het verzenden van sms-berichten kon worden onderbroken wanneer de SMPP-verbinding instabiel was. (CAMP-42789)
* Er is een probleem opgelost waardoor de knop **Stoppen met voorbereiden** niet werd weergegeven na het vernieuwen van de pagina. (CAMP-42721)
* Er is een probleem opgelost waardoor via een hot-klik geen percentages konden worden weergegeven wanneer content uit een URL werd geïmporteerd. (CAMP-44468)
* Er is een probleem opgelost waardoor mogelijk een time-outfout werd weergegeven bij het selecteren van een profiel voor gebruik in de context van profielvervanging. (CAMP-44746)
* Er is een probleem opgelost waardoor instanties mogelijk niet werkten nadat aangepaste bronnen met onjuiste koppelingsdefinities waren geïmplementeerd. (CAMP-44406)
* Er is een probleem opgelost waardoor lege gekoppelde entiteiten werden gemaakt (typologieën, merken, enz.) na het kopiëren en plakken van een levering in een campagnesjabloon. (CAMP-44765)
* Er is een probleem opgelost waardoor proeven niet konden worden verzonden vanwege een onjuiste verwerking van de tabellen voor leveringsvoorbereiding in het geval van een vastlopende database of een eenvoudige herstart van de database in Azure.
* Er is een probleem opgelost waardoor koppelingen met Experience Manager-content in een levering die was geconfigureerd met meertalige content niet konden worden verwijderd. (CAMP-44029)
* Er is een probleem opgelost in dynamische rapporten die een foutbericht konden weergeven wanneer werd geprobeerd op dimensies te filteren.  (CAMP-43097)
* Er is een probleem opgelost waardoor mogelijk een leeg scherm werd weergegeven wanneer werd geprobeerd toegang te krijgen tot profielen op een instantie die was geconfigureerd met aangepaste bronnen die specifieke koppelingsdefinities bevatten. (CAMP-41009)
* Er is een probleem opgelost in workflows dat kon optreden wanneer een **Verrijking**-activiteit werd gebruikt met twee invoeractiviteiten waarvan beide targetbronnen aan elkaar waren gekoppeld. (CAMP-42133)
* Er is een probleem opgelost waardoor workflows voor importeren werden herhaald bij gebruik van een **Bestandsoverdracht**-activiteit. (CAMP-43754)
* Er is een probleem opgelost waardoor duplicaten niet in aanmerking werden genomen bij het maken van een profiel met geëxporteerde logboeken. (CAMP-45031)
* Er is een probleem opgelost waardoor gegevensdiscrepantie optrad tussen rapporten in Adobe Campaign en rapporten die werden geëxporteerd in PDF-bestanden. (CAMP-43010)
* Er is een fout opgelost waardoor de workflow voor levering van direct mail mislukte wanneer bestaande gegevensvelden in functies werden gebruikt. (CAMP-42737)
* Er is een probleem opgelost bij het importeren van pakketten, waaronder transactiegebeurtenissen en berichtsjablonen. Het importproces stopte bij 5%. (CAMP-42544)
* Er is een probleem opgelost waarbij een fout (Uncaught TypeError) werd veroorzaakt na het wijzigen van de **Verrijking**-activiteit en het toevoegen van aanvullende data in een workflow. (CAMP-41877)
* Er is een probleem opgelost waardoor het verwijderen van de workflow werd verhinderd. Er moesten logbestanden worden gewist om de workflow te verwijderen. (CAMP-44144)
* Er is een probleem opgelost bij het maken van een landingspagina met HTML-code. Verplichte selectievakjes werden in Campaign niet herkend en waren niet beschikbaar op de gepubliceerde landingspagina. (CAMP-44181)
* Er is een probleem opgelost waardoor workflows werden herhaald tijdens het gebruik van de **Wachten**-activiteit. (CAMP-43981)
* Er is een probleem opgelost bij het verzenden van transactionele berichten waardoor meerdere e-mailadressen in dezelfde levering meerdere keren als target werden gekozen. (CAMP-44202)
* Er is een fout opgelost bij het gebruik van profielvervanging met targetData-personalisatie. (CAMP-44996)
* Er is een probleem opgelost waardoor de voorvertoning van de levering mislukte bij het exporteren van een leveringssjabloon in een pakket. (CAMP-44084)
* Er is een probleem opgelost waardoor proeven niet naar testprofielen konden worden verzonden bij gebruik van aangepaste targettoewijzingen. (CAMP-43701)
* Er is een fout opgelost die optrad in workflows bij het gebruik van de **Doelgroep lezen**-activiteit en bij het targeten van een doelgroep die was geconfigureerd met een andere targetingdimensie dan **Profiel**.  (CAMP-41885)
* Er is een probleem opgelost dat tot fouten leidde wanneer de technische workflow **updateEventsStatus** te veel tijd nodig had om de gebeurtenisgeschiedenis op te halen (als de workflow was gestopt). Het ongebruikte aggregaatveld ‘sumQueueTime’ is uit de workflow verwijderd om het probleem op te lossen. (CAMP-43920)
* Er is een geheugenprobleem opgelost bij de implementatie van aangepaste bronnen. (CAMP-42909)
* Er is een probleem opgelost voor transactionele berichten waarbij kenmerken in verzamelingen ontbraken. Alle ontbrekende kenmerken worden nu gedefinieerd met een standaardwaarde en opgenomen in de payload. (CAMP-42882)
* Er is een probleem opgelost dat van invloed kon zijn op de prestaties bij het opvragen van leveringslogboeken van realtimegebeurtenissen. (CAMP-42759)
* Er is een fout opgelost die optrad bij het gebruik van bestandsextensies met hoofdletters bij Gedeelde assets. (CAMP-44159)
* Er is een probleem opgelost waardoor een foutbericht werd weergegeven tijdens het testen van de verbinding met een extern account voordat dit was gemaakt. De knop **Verbinding testen** wordt nu pas weergegeven nadat het externe account is gemaakt.
* Er is een probleem opgelost waardoor berichten werden achtergelaten als in behandeling nadat de verbeterde MTA opnieuw was gestart op instanties die voor sharding waren geconfigureerd.
* Er is een probleem opgelost waardoor het aantal actieve profielen kon leiden tot een onjuiste telling van het effectieve aantal verzonden leveringen.
* Er is een probleem opgelost dat tot latentie kon leiden bij het zoeken naar bronnen in de query-editor in een workflow.
* Er is een probleem opgelost bij het selecteren van de optie **Velden opgeven waarmee rekening moet worden gehouden bij het zoeken van tekst** in een aangepaste bron. Als de veldlijst werd leeggelaten, mislukte de publicatie van de aangepaste bron.
* Er is een prestatieprobleem opgelost bij het weergeven van het overzicht van aangepaste bronnen met een hoog datavolume.
* Er is een probleem opgelost waardoor een levering niet kon worden geïmporteerd met gebruik van vervangende profielen.
* Er is een probleem opgelost met het gebruik van profielvervanging waardoor proeven niet meteen konden worden verzonden als de levering was gepland.
* Er is een probleem opgelost dat optrad bij het uploaden van een Android-sleutel voor een mobiele applicatie. Het bericht dat werd weergegeven nadat de sleutel was geüpload, gaf de waarde van de vorige sleutel weer.
* Er is een probleem opgelost waardoor geen testprofielen konden worden gemaakt van transactionele berichten nadat een gebeurtenisconfiguratie was gemaakt met een verzameling zonder kenmerk.
* Er is een probleem opgelost waardoor u geen aangepaste bronnen kon publiceren nadat u een nieuw filter met een aggregaat had gemaakt.
* Er is een probleem opgelost waardoor een fout optrad bij het bijhouden van het aantal keren openen voor Gmail-ontvangers, die werd veroorzaakt door de Gmail-afbeeldingsproxy.
* Er is een probleem opgelost dat tijdens het importeren van een pakket fouten met betrekking tot onvoldoende geheugen veroorzaakte.
* Er is een probleem opgelost waardoor de ontkoppelactie van Experience Manager mislukte wanneer de content van Experience Manager een pad met het teken ‘%20’ bevatte.
* Er is een fout opgelost op labels tijdens het dupliceren van workflowactiviteiten.
* Er is een probleem opgelost met de kiezer voor transactionele berichten op een landingspagina wanneer de optie **Berichtverzending starten** was geselecteerd.
* Er is een probleem opgelost met transactionele berichten of terugkerende leveringen waardoor de leveringsstatus niet met de juiste standaardwaarde kon worden geïnitialiseerd. Foutlogboeken zijn eveneens verbeterd.
* Er is een probleem opgelost bij het uitbreiden van de **Aanmelding bij een applicatie**-planning (appSubscriptionRcp) met een profielkoppeling die gebruikmaakte van een aangepast veld. De index werd niet automatisch gemaakt, wat invloed kon hebben op de verzendtijd van de pushmelding. (CAMP-41120)

