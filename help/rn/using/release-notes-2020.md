---
title: Opmerkingen bij de releases in 2020
description: Deze pagina bevat een overzicht van alle releases van Adobe Campaign Standard in 2020.
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
feature: Overview
role: User
level: Beginner
hidefromtoc: true
exl-id: b6cf7152-2200-43d7-8d0a-d65752bb2c9b
source-git-commit: 1d8baca669235be10d373d985ea62f6f014c16f8
workflow-type: tm+mt
source-wordcount: '5267'
ht-degree: 97%

---

# Aanvullende informatie 2020{#release-notes-2020}

![](assets/do-not-localize/cp-icon.png) **Release van nieuw configuratiescherm in juni** met controle van actieve profielen, controle van de leverbaarheid van subdomeinen en beheer van GPG-sleutels. [Meer informatie](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html?lang=nl).

![](assets/do-not-localize/cp-icon.png) **Release van nieuw Configuratiescherm in oktober** met domeinconfiguratie met CNAME-records en nieuwe mogelijkheden voor databasecontrole. [Meer informatie](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html?lang=nl).

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
<p>Raadpleeg de <a href="../../sending/using/control-group.md">gedetailleerde documentatie</a> en de <a href="https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/communication-channels/email/control-groups.html">instructievideo</a> voor meer informatie.
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
  <p>Journey AI maakt gebruik van Advanced Machine Learning (ML) om bedrijven in staat te stellen het ontwerp en de levering van klantreizen te optimaliseren door de voorkeur van elk individu voor de service te voorspellen.</p>
  <P>Journey AI bestaat uit twee ML-kenmerken:</p>
<ul> 
     <li> <strong>Voorspellende betrokkenheidsscores</strong> - Intelligente identificatie van het geprefereerde betrokkenheidsniveau van klanten om berichten beter te kunnen targeten en personaliseren voor meer conversies en retentie. Bekijk de <a href="https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/communication-channels/email/journey-ai/predictive-engagement-scoring.html">instructievideo</a>.</li> 
     <li> <strong>Voorspellende optimalisatie van verzendtijd</strong> - Voorspelt voor elk individu het beste tijdstip om in een campagne e-mails te verzenden voor maximale betrokkenheid en een beter rendement van de e-mailcampagne. Bekijk de <a href="https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/communication-channels/email/journey-ai/predictive-send-time-optimization.html">instructievideo</a>.</li>
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
* Er zijn [nieuwe filters](../../channels/using/configuring-transactional-event.md#searching-transactional-events) toegevoegd aan de lijst met transactiegebeurtenissen. Hiermee kunt u de gebeurtenisconfiguraties filteren op basis van hun status en de laatste keer dat een gebeurtenis is ontvangen.
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



## Release 20.3 - mei 2020 {#release-20-3---may-2020}

**Nieuwe functies**

<table> 
<thead> 
<tr> 
<th> <strong>Thaise wetgeving inzake de bescherming van persoonsgegevens (PDPA)</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>De Thaise wet inzake de bescherming van persoonsgegevens (PDPA) is de nieuwe privacywet die de vereisten inzake databescherming voor Thailand harmoniseert en moderniseert. Deze verordening is van toepassing op Adobe Campaign-klanten die data beheren voor 'datasubjecten' die inwoner zijn van Thailand.</p>
<p>Naast de privacyopties die al beschikbaar zijn in Adobe Campaign (met inbegrip van toestemmingsbeheer, instellingen voor databehoud en gebruikersrollen), gebruiken we deze gelegenheid om extra functies op te nemen, zodat de gereedheid voor PDPA voor u als klant nog makkelijker wordt:</p>
<ul>
<li>Recht op toegang en recht op verwijdering: we maken gebruik van de functies die voor de AVG (GDPR) en CCPA zijn toegevoegd. <a href="https://helpx.adobe.com/content/help/nl/campaign/kb/acs-privacy.html#righttoaccess">Meer informatie</a> </li>
<li><p>Als u een verzoek om toegang tot persoonsgegevens wilt maken, is het PDPA-wetgevingstype toegevoegd in de Privacy-kernservice. Dit is de enige methode die u moet gebruiken voor alle verzoeken voor toegang en verwijderen. Het gebruik van de Campaign-API en -interface voor toegangs- en verwijderingsverzoeken is verouderd. Zie het artikel <a href="../../rn/using/deprecated-features.md">Vervangen en verwijderde functies</a>.</p></li>
</ul>
<p>Bekijk ook de <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/privacy/privacy-overview.html">Hoe kan ik-video</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>External API-activiteit (GA)</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
  <td> <p>De activiteit <strong>External API</strong> gaat van bèta naar GA. Deze release biedt extra flexibiliteit voor de parser van de JSON-responsstructuur. U kunt nu het volgende:</p>
<ul>
<li>Een geneste JSON met een maximale diepte van 10 niveaus parseren. </li>
<li>Een selectie van eigenschappen parseren als leaf-nodes van een JSON en deze in één tabelrij weergeven.</li>
<li>Een array-object van een JSON selecteren zonder de objectdata te benoemen, en zonder dat deze data op het hoogste niveau moeten staan.</li>
</ul>
<p><strong>Let op:</strong> Klanten moeten <strong>alle External API-activiteiten van de bètaversie in hun workflows vervangen door</strong> External API-activiteiten van de GA-versie. Workflows die de bètaversie van de External API gebruiken, werken niet meer in 20.3.</p>
<p>Raadpleeg voor meer informatie de <a href="../../automating/using/external-api.md">gedetailleerde documentatie</a> en de <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/managing-processes-and-data/data-management-activities/external-api-activity.html">Hoe kan ik-video</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

**Aanvullende mogelijkheden** (vanaf 13 juli)

* **AI-aangestuurde optimalisering van verzendingstijd en profielscore** - U kunt nu het ontwerp en de levering van klantjourneys optimaliseren om de betrokkenheidsvoorkeur van elke persoon te voorspellen. Adobe Campaign wordt aangestuurd door Journey AI en kan openingsfrequenties, optimale verzendtijden en waarschijnlijk verloop analyseren en voorspellen op basis van historische betrokkenheidscijfers. [Meer informatie](../../sending/using/predictive.md)
* **De nieuwe privacyverordening van Brazilië** - Naast de privacy-mogelijkheden die al beschikbaar zijn in Campaign, helpt Adobe u te helpen bij het voorbereiden van de Braziliaanse Lei Geral de Proteçao de Datos (LGPD). Bij het maken van een verzoek om toegang tot persoonsgegevens is het LGPD-wetgevingstype toegevoegd in de Adobe Privacy-kernservice. [Meer informatie](https://helpx.adobe.com/nl/campaign/kb/campaign-privacy-overview.html)

**Verbeteringen**

* Het aantal tekens dat in het veld **Prefix** kan worden gebruikt om [berichten te testen met behulp van doelprofielen](../../sending/using/testing-messages-using-target.md), is verhoogd van 32 naar 500 tekens.
* Het maximale aantal real-time gebeurtenissen dat op een instantie kan worden gepubliceerd, is verhoogd van 350 naar 2000. (CAMP-41608)
* De synchronisatie tussen Adobe Launch en Campaign Standard is verbeterd dankzij de technische workflow SyncWithLaunch. Met deze workflow kunt u alle mobiele eigenschappen van Adobe Launch automatisch importeren in Adobe Campaign Standard. Raadpleeg [deze sectie](../../administration/using/technical-workflows.md) voor meer informatie.

  U moet een ticket indienen bij de klantenservice van Adobe (rechtstreeks of via uw Adobe-contactpersoon) om de technische workflow syncWithLaunch in uw Campaign-instantie te activeren. (CAMP-40082)

**Verbeteringen voor Email Designer**

* Email Designer verwerkt nu een flexibelere HTML-indeling dan strikte W3C. (CAMP-42529)
* Probleem verholpen met [klikbare afbeeldingen](../../designing/using/links.md#inserting-a-link) om te voorkomen dat koppelingen naast de afbeelding in contentblokken worden weergegeven. (CAMP-41586)
* Probleem verholpen waarbij het doorsturen naar een landingspagina niet mogelijk is wanneer een categorie voor de [gevolgde URL](../../designing/using/links.md#about-tracked-urls) is toegevoegd in de sjabloon. (CAMP-41537)
* Probleem verholpen met opvulling van knoppen in Outlook.
* Probleem verholpen waarbij HTML-tags in onbewerkte tekst worden weergegeven.
* Bij zoeken in contentblokken worden nu zowel de zoekresultaten van de server als de vooraf geladen resultaten weergegeven. (CAMP-41870)

**Overige wijzigingen**

* De interface voor het publiceren van aangepaste bronnen is verbeterd met duidelijkere foutberichten.
* Ongebruikte leveringstoewijzingen zijn verwijderd uit de interface.
* Onnodige beheerderrollen zijn verwijderd uit de interface.
* Selectievakjes op een landingspagina kunnen nu verplicht zijn.
* Bij het downloaden van het CSV-bestand van een Dynamic-rapport is de limiet van 200 rijen verwijderd. U kunt nu elke rij van uw rapport opnemen. (CAMP-40810)
* De taal ES-VS is toegevoegd aan de lijst met kant-en-klare talen voor meertalige e-mails. (CAMP-42279)
* Bestanden die met de activiteit Transfer File voor bestandsoverdracht zijn gedownload, worden nu na X dagen verwijderd. Het aantal dagen (X) wordt bepaald door het veld **History in days** in het menu **Execution** in de workfloweigenschappen. [Meer informatie](../../automating/using/managing-execution-options.md)

**Experience Platform-integraties**

* Activering van het Adobe Experience Platform-publiek vanuit de **Lees publiek** de activiteit is verbeterd om betere prestaties en stabiliteit te bieden . Bovendien zijn de logbestanden van workflows nu overzichtelijker en gedetailleerder ten aanzien van activeringstaken, met als resultaat eenvoudigere monitoring en probleemoplossing bij het lezen van Adobe Experience Platform-doelgroepen.

**Patches**

* Probleem verholpen waarbij een ghostbron werd gemaakt tijdens de publicatietaak van een aangepaste bron.
* Probleem verholpen waarbij de marketinghistorie van profielen niet kon worden weergegeven als de profielbron was uitgebreid met een aangepaste bron. (CAMP-41009)
* Probleem verholpen met kant-en-klare sjablonen voor de landingspagina die Franse tekst bevatten bij het openen van de editor. (CAMP-41639)
* Probleem in pushberichten met dynamische content verholpen waardoor emoji&#39;s niet werden weergegeven. (CAMP-40715)
* Probleem verholpen voor de activiteit **Deduplication** dat ertoe kon leiden dat een onjuiste segmentcode werd toegewezen aan een van de uitgaande complement-overgangen. (CAMP-41400)
* Probleem verholpen waardoor geplande rapporten niet konden worden verwijderd. (CAMP-41302)
* Probleem opgelost waarbij een discrepantie optrad tussen het dashboard voor levering en het rapport **Delivery Summary**. (CAMP-41145)
* Probleem verholpen dat leidde tot de overlapping van tekens in gedownloade rapporten.
* Probleem verholpen waardoor de voorvertoning van een levering niet kon werken bij het vervangen van proefversies.
* Correctie van een fout bij het verwijderen van aangepaste velden van een lokaal in-app-bericht.
* Probleem verholpen waardoor de charIndex-functie niet kon werken met een **End**- of **File transfer**-activiteit in een workflow.
* Probleem verholpen in workflows die kon optreden bij het gebruik van een **Enrichtment**-activiteit met twee invoeractiviteiten en targetbronnen die zijn gekoppeld. (CAMP-42133)
* Probleem verholpen waarbij een workflow niet kon worden uitgevoerd wanneer onbekende functies werden gebruikt. (CAMP-41873)
* Probleem verholpen in workflows die kon optreden bij het maken van doelgroepen met gebruik van meerdere **Save audience**-activiteiten met aanvullende uitgaande overgangen. (CAMP-39992)
* Probleem verholpen dat tot datadiscrepantie leidde bij het gebruik van personalisatie in transactie-e-mails. (CAMP-41842)
* Correctie van problemen die optraden bij het verwijderen van aangepaste velden in pushberichtleveringen. (CAMP-37586)
* Probleem verholpen waardoor gebruikers geen wijzigingen konden aanbrengen in rapporten. (CAMP-42505)


![](assets/do-not-localize/cp-icon.png) **Nieuw configuratiescherm in de release van mei** met certificaatverlenging voor CNAME-subdomeinen. [Meer informatie](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html?lang=nl).

## Release 20.2 - april 2020 {#release-20-2---april-2020}

**Nieuwe functies**

<table> 
 <thead> 
  <tr> 
   <th> <strong>Azure Blob-integratie</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>De Azure Blob Storage-connector kan nu worden gebruikt voor het importeren of exporteren van data naar Adobe Campaign met behulp van een workflowactiviteit <strong>Bestandsoverdracht</strong>. </p>
    <p>Raadpleeg de <a href="../../administration/using/external-accounts.md#microsoft-azure-external-account">gedetailleerde documentatie</a> voor meer informatie.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>E-mails testen met doelprofielen</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Naast testprofielen kunt u nu uw e-mails testen op echte doelprofielen. Zo krijgt u een exacte weergave van het bericht dat het profiel ontvangt: aangepaste velden, dynamische en gepersonaliseerde informatie, inclusief aanvullende data van workflows, enz. </p>
    <p>Raadpleeg de <a href="../../sending/using/testing-messages-using-target.md">gedetailleerde documentatie</a> en de <a href="https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/communication-channels/email/profile-substitution.html">videotutorial</a>voor meer informatie. </p>
   </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Nieuwe mogelijkheden worden in april beschikbaar gesteld in het Configuratiescherm van Campaign, waaronder Google TXT-recordbeheer, bewaking van de databaseruimte en e-mailwaarschuwingen. Raadpleeg de [Opmerking bij de release van het Configuratiescherm](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html?lang=nl) voor meer informatie over deze functies.

**Verbeteringen**

* De gebruikerservaring met transactionele berichten is uitgebreid en de interfaceconsistentie is verbeterd. [Meer informatie](../../channels/using/getting-started-with-transactional-msg.md)
* U kunt nu in Campaign Standard proeven naar testprofielen verzenden met behulp van aanvullende data uit workflows.
* Beveiligingen voor de activiteit Externe API zijn bijgewerkt. [Meer informatie](../../automating/using/external-api.md)

**Verbeteringen voor Email Designer**

* Probleem verholpen dat invloed had op escape-tekens wanneer meerdere keren op een gepersonaliseerde afbeelding werd geklikt.
* Probleem verholpen bij het dupliceren van dynamische tekstcomponenten waarbij de verkeerde regel werd gedupliceerd. (CAMP-41249)
* Probleem met opvulling in Outlook verholpen bij het definiëren van opvulling op tabelniveau in plaats van op div-niveau.
* Probleem verholpen waarbij de breedte van een afbeelding werd gewijzigd wanneer naar de HTML-modus werd overgeschakeld. (CAMP-41116)
* Probleem verholpen waarbij de sociale-mediacomponent niet toegankelijk was wanneer alternatieve tekst voor de pictogrammen werd opgegeven. (CAMP-41345)
* Probleem verholpen waarbij zichtbare `<br>`-tags werden weergegeven bij gebruik van kopiëren en plakken in Email Designer.
* Probleem verholpen waarbij HTML-tags in de e-mail werden weergegeven nadat er van HTML-content naar tekst zonder opmaak werd overgeschakeld. (CAMP-41138)
* Probleem verholpen waarbij het weergeven van knoppen met slechts één gedefinieerde rand werd voorkomen.
* Probleem verholpen in HTML-inspringing waardoor de voettekst van e-mails in Microsoft Outlook naar links werd verplaatst. (CAMP-40987)
* Probleem verholpen waarbij personalisatievelden die verwijzen naar een verzamelingskenmerk dat is gedefinieerd in HTML, in de normale tekstcontent werden gekopieerd wanneer naar de modus voor tekst zonder opmaak werd geschakeld. (CAMP-40365)
* Probleem verholpen waarbij werd voorkomen dat koppelingen werden ingevoegd op een tekstsegment dat is geselecteerd. (CAMP-41406)
* Probleem verholpen waarbij de datum werd gewijzigd wanneer een tijdzone werd geselecteerd in de query-editor. (CAMP-38277)

**Overige wijzigingen**

* De kant-en-klare workflow voor **KPI-afstemming met Adobe Analytics** loopt nu tot de huidige datum in plaats van één dag.
* De MCPNS biedt geen ondersteuning voor het toevoegen van zowel APNS als APNS-SANDBOX als platforms in een app. Nadat u het certificaat hebt toegevoegd in Adobe Campaign Standard, kunt u de instellingen nu niet meer terugzetten omdat er slechts één APNS-platform (productie of sandbox) aan de MCPNS-app kan worden toegevoegd.

**Experience Platform-integraties**

>[!NOTE]
>
>De functies van het Adobe Experience Platform in de Campaign Standard worden momenteel in bèta weergegeven en kunnen vaak en zonder kennisgeving worden bijgewerkt. Raadpleeg de gedetailleerde documentatie: Experience Platform Data Connector, Publiek Doelen

* In workflowlogboeken wordt om de 10 minuten het aantal records weergegeven dat al is verwerkt door de taak die momenteel wordt uitgevoerd in Campaign.
* Probleem verholpen dat kon optreden bij het importeren van een Adobe Experience Platform-profiel dat uit de database was verwijderd.
* Probleem verholpen in workflowlogboeken waarbij een onjuist resultaat kon worden weergegeven voor het totale aantal geïmporteerde records.

**Patches**

* Probleem verholpen met de workflowactiviteit **Verrijking** dat kon optreden wanneer spaties werden toegevoegd in het veld **Alias** en waarbij vervolgens een nieuw rij-item werd gemaakt. (CAMP-39229)
* Probleem verholpen waarbij elk testprofiel als doel kon worden ingesteld bij het verzenden van een proefbericht.
* Probleem verholpen dat optrad na het ongedaan maken van de publicatie van een gebeurtenisconfiguratie en het verwijderen ervan. [Meer informatie](../../channels/using/publishing-transactional-event.md#deleting-an-event)
* Probleem verholpen waarbij de knop **Opslaan** verdween bij het aanbrengen van wijzigingen in workflows.
* Probleem verholpen bij het handmatig verwijderen van een privacyaanvraag in Campaign nadat deze was verwerkt. Hierdoor konden data die aan de aanvraag waren gekoppeld, niet worden verwijderd, zelfs niet na opschoning.
* Probleem verholpen dat kon optreden tijdens het voorvertonen of verzenden van berichten met speciale tekens uit Adobe Experience Manager.
* Probleem verholpen dat in workflows kon voorkomen wanneer een activiteit met verschillende binnenkomende overgangen werd uitgevoerd.
* Probleem verholpen waarbij standaardgebruikers de abonnementen op een applicatie niet konden gebruiken als de doeldimensie in een workflowquery of een levering. (CAMP-37618)

## Release 20.1.4 - februari 2020 {#release-20-1-4---february-2020}

* Probleem verholpen bij het openen van een activiteit **Doelgroep lezen** voor bestaande workflows. (CAMP-41002)

## Release 20.1.3 - februari 2020 {#release-20-1-3---february-2020}

* Probleem met regressie verholpen dat in 20.1 door CAMP-39273 werd geïntroduceerd voor klanten die de loophole gebruikten. CAMP-39273 werd teruggedraaid.

## Release 20.1.2 - februari 2020 {#release-20-1-2---february-2020}

**Verbeteringen voor Email Designer**

* Probleem verholpen waarbij een HTML-code-element in een verouderd fragment werd toegevoegd bij het toevoegen van patches aan het element en het opslaan van de content. (CAMP-40685)
* Probleem verholpen waarbij een spatie werd toegevoegd bij het gebruik van dynamische content. (CAMP-40605)
* Probleem verholpen bij het configureren van een transactionele e-mailsjabloon. (CAMP-40604)

## Release 20.1 - februari 2020 {#release-20-1---february-2020}

**Nieuwe functies**


<table> 
 <thead> 
  <tr> 
   <th> <strong>Adobe Experience Platform-gegevensconnector (bèta)</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>De Adobe Experience Platform-gegevensconnector is nu geïntegreerd met Adobe Campaign Standard. U kunt uw Campaign-data ter beschikking stellen op het Adobe Experience Platform door de XTK-data (data die in Campaign worden opgenomen) toe te wijzen aan het Adobe Experience Platform-datamodel (XDM). </p>
    <p>Houd er rekening mee dat deze mogelijkheid alleen beschikbaar is voor klanten die in Azure worden gehost.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Audience Destinations (bèta) </strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Met Audience Destinations kunt u segmenten van het Adobe Experience Platform delen met Adobe Campaign.</p>
    <p>Houd er rekening mee dat deze mogelijkheid alleen beschikbaar is voor klanten die in Azure worden gehost.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

**Verbeteringen**

* Algemene beschikbaarheid van de verbeterde MTA: berichten (inclusief transactionele berichten) worden nu verzonden door de Adobe Campaign Enhanced MTA, die een geüpgrade verzendinfrastructuur biedt die verbeterde leverbaarheid, doorvoer en afhandeling van niet-bezorgde berichten mogelijk maakt. [Meer informatie](https://helpx.adobe.com/nl/campaign/kb/campaign-enhanced-mta.html)

* Tijdzonebeheer is verbeterd. U kunt nu een [specifieke tijdzone](../../automating/using/building-a-workflow.md) definiëren voor een volledige workflow. De geselecteerde tijdzone is van toepassing op alle activiteiten van de workflow. De informatie over de tijdzone die voor de operator of de server is geconfigureerd, wordt nu weergegeven in de interface (in logboeken, en na het selecteren van een tijdzone). (CAMP-37672)

* Met Campaign Standard-API&#39;s kunt u nu paginering uitvoeren bij het gebruik van grote tabellen, door de parameter `_forcePagination=true` aan uw aanroep-URL toe te voegen. [Meer informatie](../../api/using/pagination.md)

* De id van het leveringslogboek (een unieke identificatie voor elk logboek) is nu beschikbaar in de resources Leveringslogboeken en Trackinglogboeken voor alle targetingdimensies. Hierdoor kunnen verzend- of trackinglogboeken bijvoorbeeld tijdens het exporteren worden geïdentificeerd. [Meer informatie](../../automating/using/exporting-logs.md)

**Verbeteringen voor Email Designer**

* Ontbrekende verplichte tekstinstructies toegevoegd bij het maken van een doelgroep.
* Probleem verholpen bij het klikken op de knop **Change content** in de wizard van de verouderde e-maileditor.
* Probleem verholpen waarbij kopteksten niet konden worden uitgelijnd met de content in het rapport Service Summary. (CAMP-38103)
* Probleem verholpen waardoor dynamische contentvarianten niet konden worden verwijderd zonder dat dit een impact had op de rest van de onderwerpregel. (CAMP-40096)
* Probleem met A/B-tests verholpen bij gebruik van de B-variant op de onderwerpregel. (CAMP-40327)
* Probleem verholpen waarbij bestanden niet konden worden gesleept en neergezet wanneer de functie voor het uploaden van HTML-import werd gebruikt. (CAMP-39326)
* Probleem verholpen waarbij tekst uit een teksteditor niet kon worden gekopieerd en geplakt. (CAMP-39028)
* Probleem verholpen waardoor de woordsuggesties niet konden worden weergegeven. (CAMP-38970)
* Probleem verholpen waardoor gebruikers fragmenten niet konden opslaan. (ATU-2447)
* Probleem verholpen waarbij werd voorkomen dat dynamische structuren werden gedupliceerd. (CAMP-38367)
* Probleem verholpen waarbij dynamische content de voorwaarden niet kon behouden tijdens het dupliceren. (CAMP-39051)

**Overige wijzigingen**

* Het filter voor leveringen met mislukte voorbereiding houdt nu rekening met de aanmaakdatum van de leveringen in plaats van met de laatste wijzigingsdatum.
* De organisatorische eenheid van de beveiligingsgroep Beheerders kan niet meer worden veranderd.
* Wanneer u een profiel maakt, moet u het veld Organisatorische eenheid nu invullen.
* Een Experience Cloud Trigger kan nu alleen worden verwijderd als zowel de gebeurtenis als de transactionele sjabloon die eraan gekoppeld is, worden verwijderd.
* [!DNL Adobe Creative SDK] is buiten gebruik gesteld. Deze kan niet meer worden gebruikt in Campaign Standard. Zie de pagina [Verouderde en verwijderde functies](../../rn/using/deprecated-features.md).


**Patches**

* Probleem verholpen tijdens het uitvoeren van een privacyaanvraag voor verwijderen waardoor gebruikersgegevens niet konden worden verwijderd in uitsluitingslogboeken. (CAMP-39003)
* Probleem verholpen dat tot toegankelijkheidsproblemen leidde bij het wijzigen van het formaat van tekst in een containerelement.
* Probleem verholpen waarbij gebruikers het pop-upmenu voor de agenda dat bij het aanwijzen van marketingactiviteiten wordt weergegeven, niet konden negeren.
* Probleem verholpen in de activiteit **[!UICONTROL External API]** waarbij de knop **[!UICONTROL Confirm]** werd weergegeven, zelfs als er geen data waren gewijzigd.
* Probleem verholpen bij het gebruik van een activiteit **[!UICONTROL Union]** op query&#39;s met verschillende doeldimensies. De overgangsdata gaven alleen records weer van de doeldimensie van de hoofdreeks. (CAMP-36831)
* Probleem verholpen dat tot een fout kon leiden wanneer een activiteit **[!UICONTROL Reconciliation]** in specifieke contexten werd gebruikt, bijvoorbeeld bij twee binnenkomende activiteiten, waarvan één een uitsluitingsactiviteit was. (CAMP-37490)
* Problemen met de prestaties verholpen die konden optreden bij het selecteren en bijwerken van testprofielen. (CAMP-37976)
* Probleem verholpen waarbij foutpagina&#39;s konden worden weergegeven bij het inschrijven of uitschrijven via landingspagina&#39;s. (CAMP-37771)
* Probleem verholpen dat optrad bij het uploaden van content in zip-indeling, waarbij in de HTML naar PNG-bestanden werd verwezen met de extensie ervan in hoofdletters. (CAMP-37913)
* Er is een probleem verholpen waardoor in-app-berichten niet konden worden verzonden wanneer een testprofiel aan de levering was toegevoegd.
* Probleem verholpen met de workflowactiviteit Externe API die mislukte wanneer deze was gekoppeld aan verrijkingsactiviteiten.
* Probleem verholpen waarbij de status van sms-berichten onjuist kon worden weergegeven.
* Probleem verholpen met aangepaste resources die ervoor zorgden dat dubbele vermeldingen onder verschillende API-eindpunten werden weergegeven.
* Probleem verholpen waardoor landingspagina&#39;s na publicatie niet beschikbaar waren. (CAMP-38695)
* Probleem verholpen dat optrad bij het weergeven van data van een overgang Doorsnede die uit twee verschillende resources afkomstig was. (CAMP-38974)
* Probleem verholpen waarbij de opsommingswaarde in een leveringssjabloon onjuist werd ingesteld. (CAMP-38388)
* Probleem verholpen met bulkleveringen via e-mail waarbij de status van de leveringen als In behandeling en de status Verzonden als Voltooid werden weergegeven. (CAMP-35355)
* Probleem verholpen waarbij het domein van de afzender onjuist werd weergegeven in Dynamische rapportage. (CAMP-33123)
* Probleem verholpen dat discrepantie veroorzaakte in tellingen van uitschrijvingen in Dynamische rapportage. (CAMP-39949)
* Probleem verholpen waarbij adressen niet konden worden weergegeven in het scherm Sending logs bij het verzenden van in-app-berichten.
* Probleem verholpen waarbij sms-verzendlogboeken niet konden worden bijgewerkt met het juiste aantal niet-bezorgde berichten. (CAMP-38395)
* Loophole verholpen waarbij de tokens voor pushberichten konden worden bijgewerkt met POST-aanroepen van abonnementen op de applicatie. (CAMP-39273)
