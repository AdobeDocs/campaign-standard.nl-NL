---
title: Opmerkingen bij de release 2019
description: Deze pagina bevat een lijst met alle versies van Adobe Campaign Standard van 2019.
page-status-flag: never-activated
uuid: 99f92a54-4b3d-48b9-b08d-e98b24e75f62
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
discoiquuid: e54f8305-7e32-4193-8e5a-b5d87b03038c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7775e1d95e6a7e08b38fc65b44a061eda7ff079
workflow-type: tm+mt
source-wordcount: '7626'
ht-degree: 2%

---


# Release Notes 2019{#release-notes-2019}

[Release-planning](https://helpx.adobe.com/campaign/kb/acs-release-planning.html) | [Release van het regelpaneel](https://docs.adobe.com/content/help/en/control-panel/using/release-notes.html) | [Documentatie-updates](../../rn/using/documentation-updates.md) | [Opmerkingen bij de laatste release](../../rn/using/release-notes.md) | [Verouderde functies](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html)

## Release 19.4 - december 2019 {#release-19-4---october-2019}

**Nieuwe functies?**

<table> 
 <thead> 
  <tr> 
   <th> <strong>California Consumer Privacy Act (CCPA)</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>CCPA is de nieuwe privacywet van de staat Californië die de vereisten inzake gegevensbescherming harmoniseert en moderniseert en van kracht wordt op 1 januari 2020. CCPA is op de klanten van Adobe Campaign van toepassing die gegevens voor de Onderwerpen van Gegevens in Californië verblijven.</p>
   <p>Naast de privacy mogelijkheden reeds beschikbaar in Adobe Campaign (met inbegrip van toestemmingsbeheer, de montages van het gegevensbehoud, en gebruikersrollen), nemen wij deze kans aan om extra mogelijkheden te omvatten, helpen uw bereidheid voor CCPA vergemakkelijken:</p>
   <ul>
    <li>Recht op toegang en recht op verwijdering: We benutten de capaciteiten die voor GDPR zijn toegevoegd. <a href="https://helpx.adobe.com/content/help/en/campaign/kb/acs-privacy.html#righttoaccess">Meer informatie</a> </li>
    <li><p>Bij het maken van een privacyverzoek is het regulatietype (GDPR of CCPA) toegevoegd aan de Privacy Core Service. Dit is de methode u voor alle toegang en schrappingsverzoeken zou moeten gebruiken. Het gebruik van de campagne-API en -interface voor toegangs- en verwijderingsverzoeken is afgekeurd.  Zie het artikel <a href="https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html"></a>Vervangen en verwijderde functies.</p></li>
    <li>Er is een <strong>Opt-Out</strong> -veld CCPA toegevoegd aan de profielbron zodat Adobe Campaign-gebruikers kunnen controleren of een consument heeft gekozen voor de verkoop van persoonlijke gegevens. <a href="https://helpx.adobe.com/content/help/en/campaign/kb/acs-privacy.html#ccpa">Meer</a>informatie.</li>
  </ul>
    <p>Raadpleeg de <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/privacy/privacy-overview.html">Hoe kan ik-video</a>.</p>
</td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Integratie van Microsoft Dynamics 365 (GA)</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 
    <p>De integratie tussen Adobe Campaign Standard en Microsoft Dynamics 365 is nu beschikbaar. U kunt uw contact- en aangepaste entiteitsrecords van Dynamics 365 naar Campagne overbrengen en e-mailgebeurtenisgegevens terugkrijgen van Campagne naar Dynamics 365 voor een betere uitlijning van verkoop/marketing.</p>
    <p>Raadpleeg de <a href="../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md">gedetailleerde documentatie</a> om deze integratie in te stellen en de <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/integrating-with-adobe-cloud/campaign-and-microsoft-dynamics-365/working-with-campaign-standard-and-microsoft-dynamics-365.html">hoe kan ik-video</a>te bekijken.</p>
  </td>
  </tr> 
 </tbody> 
</table>

**Verbeteringen**

* De toestemmings pop-up voor Dynamische rapportering is bijgewerkt om integratie van de Dynamica van Adobe Campaign Standard en van Microsoft 365 te omvatten. Door de voorwaarden te accepteren, worden profielgegevens opgenomen wanneer de integratie Adobe Campaign Standard / Microsoft Dynamics 365 en Dynamic Reporting worden gebruikt. [Lees meer](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement) (CAMP-29766)
* Probleem verholpen waarbij onjuiste contactdata werden weergegeven bij ontvangst van leveringswaarschuwingen.
* Wanneer een transactieberichtgebeurtenis met een onbekende contextparameter wordt voorgelegd, keert de Campagne nu een &quot;400&quot;foutenmelding in plaats van &quot;500&quot;terug. (CAMP-28632)
* Er is een nieuw proefdruksegment **uitsluiten** toegevoegd aan Dynamische rapportage. Dit segment is nu standaard geselecteerd om uw rapporten te filteren. [Meer informatie](../../reporting/using/list-of-components-.md#segments)
* De optie **Bericht bij verlopen** is toegevoegd aan pushmelding. Hiermee kunt u een vervaldatum opgeven waarop het bericht niet meer wordt verzonden door Apple (APNS) of Android (FCM). [Meer informatie](../../channels/using/customizing-a-push-notification.md#add-expiration-date)
* Er zijn verbeteringen aangebracht in de activiteit **Bestand** laden: workflowlogboeken zijn duidelijker en gedetailleerder gemaakt over de fout die optreedt wanneer een bestand niet kan worden geladen. De uitgaande overgang die is gegenereerd bij het activeren van de optie **Afwijzingen behouden in een bestand** , heeft de naam **Afwijzen** gewijzigd. [Meer informatie](../../automating/using/load-file.md)
* Meertalige verwante logbestanden zijn toegevoegd aan de verzendende logboeken om beter te begrijpen dat verzendfouten optreden omdat de geüploade CSV-bestanden ontbrekende talen bevatten.

**Verbeterde beveiliging**

* Probleem verholpen waarbij bij het verwijderen van de gegevens van een gekwantificeerd profiel via een privacyaanvraag alle gegevens werden verwijderd, behalve het e-mailadres in de quarantainelijst.
* De beveiliging is verbeterd voor bescherming tegen injecties in e-mailkoppen.
* De veiligheid is verbeterd voor bescherming tegen aanvallen SSRF waar de uitdrukkingen van xtk kunnen worden gebruikt (e-mail HTML, tekstinhoud en onderwerp, sms en duw berichtinhoud).

**Verbeteringen voor e-mailontwerper**

* Probleem verholpen waardoor koppelingen naar abonnements-, abonnements- en landingspagina&#39;s niet konden worden bijgehouden wanneer deze in een e-mail werden ingevoegd. (CAMP-37809)
* Probleem verholpen dat tot fouten kon leiden bij het maken van een nieuwe e-mail en het selecteren van een sjabloon. (CAMP-38000)
* Als u een koppeling bewerkt met de e-mailontwerper, kunt u nu de optie **Onderstrepen** gebruiken. Bovendien is een **Target** -eigenschap toegevoegd met de standaardwaarde ingesteld op **Geen**. [Meer informatie](../../designing/using/styles.md#about-styling-links)
* Probleem verholpen met kleuren van koppelingen in tekstcomponenten in de tekst van een e-mailbericht. (CAMP-37330)
* Probleem verholpen waarbij gekoppelde koppelingen niet konden worden verwijderd wanneer een afbeelding werd verwijderd. (CAMP-37234)
* Probleem verholpen waarbij het opslaan van wijzigingen in de **Orde** -instellingen van dynamische inhoud in een voorwaarde werd voorkomen. (CAMP-36883)
* Probleem verholpen bij het zoeken naar bestemmingspagina&#39;s. De zoekopdracht is uitgebreid van de 50 die voor het eerst zijn gemaakt naar alle databases. (CAMP-36839)
* Probleem verholpen bij het opslaan van wijzigingen op de e-mailafzender in het dialoogvenster **Van: Veld naam** . (CAMP-36606)
* De compatibiliteitswaarschuwing voor de carrouselcomponent is gewijzigd om ondersteunde e-mailclients weer te geven.
* Probleem met weergave op mobiel netwerk is opgelost. Het kenmerk height is nu altijd ingesteld op height: auto&quot; wanneer u een nieuwe afbeelding in een e-mailbericht toevoegt of uploadt. (CAMP-35497)
* Probleem verholpen waarbij stijl en metatags voor links in de HTML werden gebruikt wanneer een fragment uit een structuurcomponent werd verwijderd. (CAMP-35390)
* Probleem met fragmenten verholpen tijdens het bijwerken van herbruikbare inhoud. (CAMP-35186)
* Probleem verholpen bij weergave van voorwaardelijke inhoud voor mobiele apparaten in e-mails. (CAMP-35155)
* Probleem verholpen waarbij op willekeurige wijze vaste spaties met een breedte van nul werden weergegeven. (CAMP-35116)
* Correctie van een probleem met de positie van knoppen in het dialoogvenster **Opslaan als fragment** .
* Probleem verholpen waarbij een voorvertoning werd weergegeven wanneer een HTML-tag in een afbeeldingstitel en alternatieve tekst werd toegevoegd.
* Probleem verholpen tijdens het bewerken van koppelingen die in e-mailberichten van de verouderde editor zijn gemaakt in de e-mailontwerper van e-mail.
* Probleem verholpen waarbij gedupliceerde stijllabels in de inhoud werden achtergelaten.
* Probleem verholpen met de datumnotatie bij het invoegen van een personalisatieveld in een e-mail.
* Oplossing voor een opslagprobleem bij het overschakelen van de HTML-modus naar normale tekst.
* Probleem verholpen door te klikken op de optie voor vergrendelen en ontgrendelen waarmee margewaarden zijn toegevoegd in het deelvenster met inline-stijleigenschappen.
* Probleem verholpen met de grootte van de mobiele voorvertoning voor een betere rendering.
* Probleem verholpen met de grootte van knoppen in sjablonen en fragmenten.
* Probleem verholpen met de grootte van afbeeldingen wanneer deze in een knopcomponent worden ingevoegd.

**Overige wijzigingen**

* De standaardtijdwaaier waarvoor de gegevens op de levering KPI pagina&#39;s en op de Dynamische Rapporterende pagina worden getoond is gericht om discrepantie in het melden van resultaten te verhinderen. (CAMP-35148)
* Er is een foutbericht toegevoegd aan logboeken wanneer het toepassingscertificaat verlopen is.
* De voorvertoning van de payload-berekening bevat nu een aangepaste veldgrootte om mislukte pushmeldingen te voorkomen. (CAMP-35303)
* De naam van het bestand **** Weigts in de activiteit **Bestand** laden kan nu worden gewijzigd in dezelfde naam als in de activiteit **Bestand exporteren** .
* Alle aangepaste entiteiten die niet zijn gekoppeld aan een entiteit buiten de box, zijn nu toegankelijk via de API.
* Verbeterde databaseprestaties bij grote bronnen.
* De beschrijvingen van sommige fouten die bij het verzenden van SMS-berichten zijn opgetreden, zijn duidelijker. (CAMP-36558)
* Er wordt nu een foutbericht weergegeven wanneer de **planneractiviteit** van een werkstroom wordt uitgevoerd die met zichzelf is verbonden, rechtstreeks of via verschillende activiteiten, omdat dit ertoe kan leiden dat de werkstroomserver van de instantie vastloopt.
* De verbeteringen zijn aangebracht helpen transactioneel overseinen problemen oplossen: De &quot;Gegevens&quot;verbinding is anders genoemd &quot;Laatste transactionele gebeurtenissen&quot;in het scherm van de gebeurtenisconfiguratie, maakt nu een lijst van de ontvangen gebeurtenissen die in een dalende orde worden gesorteerd. Er is ook een nieuwe status voor een transactiegebeurtenis gemaakt: &quot;targetingFailed&quot;. Wanneer de transactionele overseinenmodule er niet in slaagt om een verbinding te verrijken die voor bericht het richten wordt gebruikt, zal de transactionele gebeurtenis nu in deze nieuwe staat (in plaats van de &quot;routingFailed&quot;status) zijn.
* Er zijn verbeteringen aangebracht in de interface bij het beperken van de toegang tot landingspagina&#39;s tot specifieke geografische of organisatorische eenheden. Het doel is te waarschuwen dat de landingspagina aan zichtbaarheidsvoorwaarden kan worden onderworpen: de selectie van een geografische en organisatorische eenheid bij het creëren van een landingspagina is nu verplicht . Een banner met verwante informatie wordt nu weergegeven zodra een eenheid is geselecteerd. Het foutbericht dat wordt weergegeven tijdens het testen van de landingspagina is duidelijker.
* In Campaign Standard API&#39;s kunnen aangepaste sleutels niet worden gewijzigd met behulp van een PATCH-bewerking als de sleutelwaarde afwijkt van de oorspronkelijke sleutel of als u uw eigen zakelijke sleutel gebruikt als URI in plaats van de sleutel die door Adobe wordt geleverd.
* De taal &quot;Albanees - Macedonië&quot; is toegevoegd aan de keuzelijst met voorkeurstalen. (CAMP-35396)

**Patches**

* Probleem verholpen waardoor geplande rapporten niet konden worden gesorteerd of doorzocht.
* Probleem verholpen met triggerregels die ertoe leidden dat de AND- en OR-regels werden gemengd.
* Oplossing voor een probleem waarbij de eigenschap Mobile werd weergegeven als Verwijderd in Launch. (CAMP-35382)
* Probleem verholpen waarbij synchronisatie van mobiele eigenschappen van Adobe Launch in Adobe Campaign werd voorkomen. (CAMP-35411, CAMP-35089, CAMP-35014, CAMP-35487)
* Probleem verholpen waarbij transactionele pushberichten mislukten wanneer gebeurtenissen werden verrijkt met profielgegevens. (CAMP-34385)
* Probleem verholpen waarbij mobiele eigenschappen niet werden gesynchroniseerd in meerdere omgevingen. (CAMP-37060)
* Probleem verholpen bij het selecteren, in een pushmelding, van een sjabloon met een contactdatumformule. (CAMP-35300)
* Probleem opgelost waarbij het bericht dat de service verzendt mogelijk vastloopt. (CAMP-35287)
* Probleem verholpen met terugkerende directe mails die allemaal zijn gedefinieerd met de eerste gebeurtenisdatum. (CAMP-35139)
* Probleem verholpen met onlangs uitgebreide aangepaste **profielen** die niet beschikbaar waren voor query&#39;s. (CAMP-35119)
* Oplossing voor de structuurmodus **van de database** Repareren voor instanties waarvoor de configuratie voor delen is geactiveerd. (CAMP-35118)
* Probleem verholpen die leidde tot een SQL-logfout bij het toevoegen van geaggregeerde gegevens over logboeken. (CAMP-35034)
* Probleem verholpen met overgangen tijdens het maken van een **segmenteringsactiviteit** . (CAMP-35033)
* Probleem verholpen in de activiteit van de **Vraag** die de functie **encryption_aescbcDecrypt** verhinderde de **encryptie_aescbcEncrypt** functie te decrypteren. (CAMP-34952)
* Probleem verholpen waardoor de logboeken **voor** bijhouden niet konden worden weergegeven in leveringen. (CAMP-34855)
* Probleem verholpen bij het gebruik van een aangepaste datumformule voor optimalisatie **** van de verzendtijd, die kan voorkomen dat pushmeldingen worden verzonden als gevolg van fouten met de aanvullende gegevens in de workflow. (CAMP-30336)
* Probleem verholpen waardoor aangepaste bronnen niet konden worden gepubliceerd. (CAMP-37425)
* Probleem verholpen waardoor gebruikers van Admin geen importpakketten konden wijzigen.  (CAMP-37176)
* Probleem verholpen in workflows die ervoor zorgden dat geen proefdrukken konden worden verzonden als de leveringsactiviteit was verbonden met een leeg **leespubliek** -activiteit. (CAMP-37164)
* Probleem verholpen waardoor aangepaste bronnen niet konden worden geïmporteerd in een nieuwe omgeving. (CAMP-36506)
* Probleem verholpen in hot-click-rapporten die ertoe kunnen leiden dat percentages door afbeeldingen worden verborgen (CAMP-36407)
* Probleem verholpen die optrad tijdens het exporteren van een beschrijvingsveld voor de levering. (CAMP-35467)
* Probleem verholpen waarbij de status van een levering als &quot;In behandeling beginnen&quot; kon worden weergegeven, hoewel de levering was voltooid. (CAMP-35355)
* Probleem verholpen waarbij werd voorkomen dat workflowlogboeken werden weergegeven nadat ze waren ingeschakeld, en vervolgens SQL-logbestanden werden uitgeschakeld.

## Release 19.3 - juli 2019 {#release-19-3---july-2019}

**Nieuwe functies?**

<table> 
 <thead> 
  <tr> 
   <th> Functionaliteit<br /> </th> 
   <th> Beschrijving<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Externe API-activiteit (openbare bètaversie)<br /> </td> 
   <td> <p>Voor een diepere verpersoonlijking, staat de Externe API Activiteit u toe om gegevens van externe systemen in een werkschema via een REST API vraag te brengen. De REST-eindpunten kunnen een Klantbeheersysteem, Adobe I/O-runtime of Adobe Experience Cloud REST-eindpunt zijn (bijvoorbeeld Data Platform, Target, Analytics, Campaign).</p><p>Deze mogelijkheid is momenteel beschikbaar in een openbare bètaversie.</p><p>Raadpleeg voor meer informatie de <a href="../../automating/using/external-api.md">gedetailleerde documentatie</a> en de <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/managing-processes-and-data/data-management-activities/external-api-activity.html">Hoe kan ik-video</a>.</p></td> 
  </tr> 
  <tr> 
   <td> Rapport over workflowsegment<br /> </td> 
   <td> <p>Met deze functie kunnen marketers hun leveringsprestaties opsplitsen per segmentcode. Wanneer u een werkschema creeert en een segmentatieactiviteit gebruikt om segmenten aan de leveringspopulatie toe te wijzen, kunnen deze segmenten nu in de zelfde levering gaan. Dit staat u toe om te tonen opent/klikt statistieken die op veelvoudige segmenten binnen één enkele levering worden gebaseerd.</p><p>Raadpleeg voor meer informatie de <a href="../../reporting/using/creating-a-report-workflow-segment.md">gedetailleerde documentatie</a> en de <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/reporting/report-on-workflow-segments.html">Hoe kan ik-video</a>.</p></td>
  </tr> 
 </tbody> 
</table>

**Verbeterde beveiliging**

* Oplossing voor een beveiligingsprobleem om te voorkomen dat DoS-aanvallen (Denial of Service) worden uitgevoerd op ongeldige aanvragen om afbeeldingen op te halen. (CAMP-33454)

**Verbeteringen voor e-mailontwerper**

* Probleem verholpen waarbij telkens wanneer een component werd toegevoegd, extra HTML-stijltags aan een HTML-sjabloon werden toegevoegd, waardoor de grootte van de sjabloon aanzienlijk zou kunnen toenemen. (CAMP-34694)
* Probleem verholpen waarbij sommige opties in het bovenste werkbalkmenu niet beschikbaar waren. (CAMP-34577)
* Probleem verholpen die optrad wanneer het URL-inhoudsblok van de pagina Mirror was ingevoegd in een e-mailinhoud. (CAMP-34779)
* Probleem verholpen dat optrad bij het gebruik van JSPP-code in een e-mail, waardoor het moeilijk werd de inhoud te bewerken. (CAMP-34574)
* Probleem verholpen waarbij afbeeldingen bovenaan werden afgekapt wanneer er een hyperlink aan werd toegevoegd. (CAMP-34382)
* Probleem met weergave verholpen bij gebruik van e-mailontwerper met Firefox. (CAMP-34364)
* Verschillende problemen met de modus Geavanceerd bij het definiëren van dynamische inhoud in een e-mail zijn opgelost. (CAMP-34351, CAMP-34333, CAMP-34331)
* Oplossing voor verschillende problemen met de editor voor dynamische inhoudsregels (CAMP-34304, CAMP-34303).
* Probleem verholpen waardoor het veld Koppeling niet kan worden weergegeven in het deelvenster Instellingen voor e-mailontwerper (CAMP-33749).
* Probleem verholpen met het YouTube-pictogram dat te groot was in verzonden e-mailberichten. (CAMP-33726)
* Probleem verholpen waarbij de inhoud van de spiegel bewerkbaar werd gemaakt. (CAMP-33691)
* Probleem verholpen waarbij de HTML-uitvoer werd verbroken wanneer het symbool groter dan het symbool in dynamische inhoud werd gebruikt. (CAMP-33688)
* Oplossing voor een probleem dat optrad bij het gebruik van de optie Ongedaan maken bij het bewerken van tekst in E-mailontwerper. (CAMP-32565)
* Probleem verholpen waarbij extra labels werden gemaakt tijdens het ongedaan maken van stijlen in plaats van deze te verwijderen. (CAMP-32359)
* U kunt nu definiëren of elk onderdeel dat in een e-mailbericht wordt gebruikt, alleen wordt weergegeven op desktopapparaten of alleen op mobiele apparaten.
* U kunt nu de breedte en hoogte van een onderdeel van de sociale inhoud instellen.
* Probleem verholpen waardoor oude broncode voor dynamische inhoud niet kon worden verwijderd nadat de dynamische inhoud was verwijderd.
* Probleem verholpen waardoor het onderwerp van een e-mailbericht niet kon worden bijgewerkt nadat het was gewijzigd.
* Probleem verholpen waardoor een n:n-kolomstructuur niet kon worden geselecteerd nadat deze in de werkruimte was neergezet.
* Probleem verholpen waardoor de miniatuur van het bericht vaag werd weergegeven op het dashboard voor e-mail.
* Probleem verholpen waardoor de achtergrond niet correct kon worden weergegeven voor e-mails die in Outlook werden ontvangen.
* Oplossing voor enkele sorteerproblemen op de startpagina van e-mailontwerper.
* Probleem verholpen dat optrad bij het dupliceren van varianten bij het gebruik van dynamische inhoud.
* Enkele ongewenste velden zijn verwijderd uit het deelvenster Instellingen van e-mailontwerper.

**Overige verbeteringen**

* Dankzij de integratie met Adobe Experience Platform Location Services is Adobe Campaign nu compatibel met het versturen van op locatie gebaseerde marketingberichten naar de abonnees van uw mobiele toepassing via de SDK van het Experience Platform. Raadpleeg de [gedetailleerde documentatie](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md)voor meer informatie.
* De rapportfunctie is verbeterd voor een betere ervaring. Om deze eigenschap te gebruiken, moet u de Dynamische Overeenkomst van het Gebruik van de Rapportering goedkeuren. For more on this, refer to the [detailed documentation](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).
* In workflows is een nieuwe optie toegevoegd om een voorvertoning te bekijken van de volgende tien uitvoeringen van een workflow. For more on this, refer to the [detailed documentation](../../automating/using/scheduler.md).
* In de activiteit van de Planner, staat een nieuwe optie u toe om een specifieke dag van een specifieke week voor maandelijkse leveringen te selecteren. For more on this, refer to the [detailed documentation](../../automating/using/scheduler.md).
* Bij het maken van terugkerende leveringen zonder aggregatieperiode kunt u op het dashboard voor de levering nu een bevestiging aanvragen voordat de levering wordt verzonden. For more on this, refer to the [detailed documentation](../../sending/using/confirming-the-send.md).
* U kunt het label van een levering nu personaliseren met gebeurtenisvariabelen die zijn gedeclareerd in de externe signaalactiviteit van de workflow. For more on this, refer to the [detailed documentation](../../automating/using/calling-a-workflow-with-external-parameters.md).
* De GDPR-verwijderquery is verbeterd ten behoeve van betere prestaties. (CAMP-33504)
* De optie &quot;ftp&quot; is verwijderd uit de interface voor externe accountconfiguratie. (CAMP-34472)
* U kunt de optie van de SMTP testwijze voor elk e-mailbericht nu toelaten en onbruikbaar maken. For more on this, refer to the [detailed documentation](../../administration/using/configuring-email-channel.md#smtp-test-mode). (CAMP-34602)

**Overige wijzigingen**

* Er is een waarschuwing toegevoegd aan de interface met leveringseigenschappen. Hiermee geeft u op dat leveringen worden voorbereid op basis van hun aggregatieperiode en ontdooid om de workflow meerdere keren per dag aan te roepen. Zorg ervoor dat ze geen periode hebben. (CAMP-34393)
* Een waarschuwing is toegevoegd in de schermen van de douaneconfiguratie van het middel. We raden u aan maximaal 30 tekens te gebruiken voor aangepaste bron-id&#39;s. Dit geldt ook voor aangepaste bronvelden, sleutels, indexen en koppelingen.
* Er wordt nu een bericht weergegeven wanneer u probeert een transactiebericht te verwijderen dat door een landingspagina wordt gebruikt als een bevestigingsbericht.
* Er verschijnt nu een waarschuwing in workflows wanneer een activiteit langer dan 6 uur wordt uitgevoerd. Dit is niet van toepassing op de activiteiten Push notification, Delivery, Signal, Start, End, Fork, AND-joint, Schedule, and Wait.
* Er verschijnt nu een waarschuwing in workflows wanneer u het maximumaantal werkstromen bereikt dat gelijktijdig wordt uitgevoerd.
* Workflows die langer dan 7 dagen zijn gepauzeerd of gezakt, worden nu gestopt om minder schijfruimte te verbruiken. De reinigingstaak wordt weergegeven in de werkstroomlogboeken.
* Als u een activiteit &quot;Bestand overbrengen&quot; gebruikt, wordt een fout nu geregistreerd als de bestandsgrootte de beschikbare schijfruimte overschrijdt.
* De handeling Omleiden naar doel-URL kan niet meer worden geselecteerd voor de secundaire knop in In-App-berichten.

**Patches**

* Probleem verholpen waarbij aanvragen voor GDPR-toegang zouden kunnen mislukken.
* Probleem verholpen waarbij triggers konden worden genegeerd wanneer meerdere triggers voor een uniek profiel werden ontvangen.
* Probleem verholpen dat na aanmelding tot een foutbericht voor de publicatie van een aangepaste bron kon leiden.
* Probleem verholpen waarbij een lege pagina werd weergegeven bij het maken of uitbreiden van een aangepaste bron.
* Probleem verholpen waardoor een publiek met appSubscriptioncp als doeldimensie niet kon kiezen voor een mobiele levering.
* Probleem verholpen waarbij vaste e-mailadressen niet in quarantaine konden worden geplaatst. (CAMP-24587)
* Probleem verholpen dat optrad bij het toevoegen van een typologieregel en vervolgens deze regel verwijderen voordat de typologie werd opgeslagen. (CAMP-32789)
* Probleem verholpen waardoor het niet mogelijk was om pagina-inhoud te landen wanneer dynamische inhoud werd uitgeschakeld. (CAMP-32924)
* Probleem verholpen met terugkerende leveringen die optraden bij het gebruik van personalisatie voor de kenmerken van een primaire levering. (CAMP-32983)
* Probleem verholpen in workflows die het lezen van resultaten van een overgang met inkomende sms-berichtengegevens beletten. (CAMP-33134)
* Probleem opgelost in workflows die optraden bij het combineren van vork- en uitsluitingsactiviteiten om een publiek te maken. (CAMP-33401)
* Probleem verholpen waardoor de inhoud van de spiegelpagina niet kan worden weergegeven en er geen proefdrukberichten kunnen worden verzonden voor terugkerende leveringen. (CAMP-33413)
* Probleem verholpen dat tot een fout leidde bij het gebruik van een activiteit van de Unie tussen profielen en publiek. Dit probleem werd veroorzaakt door een incompatibiliteit van de identificatietoetsen in invoerovergangen. (CAMP-33713)
* Probleem verholpen in de testactiviteiten die ervoor zorgden dat de expressie &quot;recCount&quot; de juiste syntaxis niet kon gebruiken wanneer erop werd dubbelgeklikt. (CAMP-33756)
* Probleem verholpen dat tot een foutbericht kon leiden wanneer de logbestanden van de technische workflow voor facturering werden geopend. (CAMP-34313)
* Probleem verholpen in bestemmingspagina&#39;s die kon voorkomen wanneer het vormen van checkbox gebieden met abonnementen. (CAMP-34369)
* Oplossing voor een probleem dat optrad tijdens het configureren van een lijst en het toevoegen van het veld &quot;icon&quot;. (CAMP-34585)
* Probleem verholpen waarbij de symbolen &quot;|&quot; en &quot;%&quot; niet konden worden gebruikt als datum- of tijdscheidingstekens bij workflowactiviteiten voor bestand laden. (CAMP-34706)
* Probleem verholpen dat optrad bij het gebruik van zichtbaarheidsvoorwaarden met selectievakjes op bestemmingspagina&#39;s. (CAMP-34802)
* Probleem verholpen in de verrijkingsactiviteit waardoor velden niet konden worden weergegeven op het tabblad &quot;Aanvullende gegevens&quot; als de filterdimensie was ingesteld op het bijhouden van logbestanden en de doeldimensie op profiel.
* Probleem verholpen die tot een foutbericht leidde bij het exporteren van een &#39;workflowTemplate&#39;-bron.
* Probleem verholpen tijdens het maken van een nieuw profiel. Hierdoor kon het veld Landcode/regiocode niet worden opgeslagen als dit was geselecteerd in het dialoogvenster.
* Oplossing voor verschillende problemen die optraden bij het gebruik van de importsjabloon Direct Mail (updateQuarantinesDeliveryLogsDirectMail).
* Probleem opgelost met betrekking tot de integratie van activa op aanvraag.
* Oplossing voor een probleem dat optrad bij het inzoomen op de tijdlijnweergave. (CAMP-33628)
* Probleem verholpen waarbij proofs niet direct konden worden verzonden voor e-mailberichten met een geplande datum en tijd. (CAMP-33723)
* Probleem verholpen met betrekking tot transactiemeldingen die foutmeldingen genereerden wanneer een gebruiker zich afmeldde. (CAMP-31698)
* Oplossing voor een fout die in specifieke omgevingen kan optreden bij het plannen van een e-mailbericht.
* Probleem opgelost waarbij de workflow voor het uitvoeren van de update is mislukt.
* Probleem verholpen met beveiliging waarbij de e-mailinhoud werd verbroken wanneer het onderwerp meerdere regels bevatte.


## Release 19.2.7 - juli 2019 {#release-19-2-7---july-2019}

**Verbeteringen**

* De GDPR-verwijderquery is verbeterd ten behoeve van betere prestaties.
* Probleem opgelost waarbij het web vastloopt na de upgrade van 19.2. (CAMP-34862)
* Probleem verholpen waardoor niet-beheerders rapporten kunnen opslaan of plannen. (CAMP-31133)
* Correctie van een probleem bij het gebruik van &quot;|&quot; als datumscheidingsteken in de werkstroom Bestand laden. (CAMP-34706)

## Release 19.2.4 - juni 2019 {#release-19-2-4---june-2019}

**E-mailontwerper**

* Probleem verholpen waardoor gebruikers fragmenten niet konden bewerken wanneer lege stijltags werden gebruikt in de HTML. Dit is een follow-up fix voor CAMP-33778 in 19.2.3.

## Release 19.2.3 - juni 2019 {#release-19-2-3---june-2019}

**E-mailontwerper**

Introduceerde een reeks verbeteringen en correcties om fragmenten te optimaliseren in de release 19.2. Nieuw gemaakte fragmenten werken naadloos. Fragmenten die eerder zijn gemaakt, zijn grijs weergegeven en moeten naar de nieuwe indeling worden gemigreerd. Klik hiertoe op elk fragment en valideer de migratie ervan naar de nieuwe indeling. We raden u aan enkele fragmenten te testen voordat u ze allemaal migreert.

* Probleem verholpen waardoor gebruikers een fragment niet konden bewerken nadat het was ontgrendeld. Dit had invloed op bestaande fragmenten bij het bijwerken naar versie 19.2. (CAMP-33778)
* Probleem verholpen bij gebruik van dynamische inhoud. Er zijn extra spaties toegevoegd aan de HTML.

**Overige verbeteringen**

* Probleem verholpen waarbij het verzenden van SMS-berichten na het verbreken van de verbinding met de SMS-connector kon worden hervat.
* Probleem opgelost waarbij SMPP-verbindingen konden worden gesloten wanneer TLS was ingeschakeld.
* Probleem opgelost waarbij SMPP-verbindingen konden worden gesloten wanneer TLS was ingeschakeld.
* De optie &quot;Launch_URL_Campaign&quot; is toegevoegd in Campagne om eigenschappen van mobiele toepassingen te beheren die zijn gemaakt met Adobe Experience Platform Mobile SDK.
* Correctie van een fout die ertoe leidde dat de de milieuoptie van de Sandbox na het uploaden van het certificaat van een nieuw gecreeerd mobiel bezit en het weggaan van de mobiele pagina van het toepassingsbezit werd ongecontroleerd.
* Probleem verholpen waardoor u een transactiemelding voor berichtinhoud niet kon verrijken met informatie uit het servicemiddel. (CAMP-33707)
* Probleem verholpen op de pagina&#39;s waarop de lijst van afgewezen personen werd gepost en die optrad toen werd geprobeerd profielen af te melden bij een service.

## Release 19.2 - mei 2019 {#release-19-2---may-2019}

**Nieuwe functies?**

<table> 
 <thead> 
  <tr> 
   <th> Functionaliteit<br /> </th> 
   <th> Beschrijving<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Configuratiescherm<br /> </td> 
   <td> <p>Om uw werk als Admin-gebruiker efficiënter te maken, kunt u eenvoudig de capaciteit controleren en de instellingen van uw instanties beheren (te beginnen met SFTP-serverbeheer).</p><p>Raadpleeg voor meer informatie de <a href="https://docs.adobe.com/content/help/en/control-panel/using/control-panel-home.html">gedetailleerde documentatie</a> en de <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/administrating/control-panel/control-panel-overview.html">Hoe kan ik-video</a>.</p></td> 
  </tr> 
  <tr> 
   <td> Lokale meldingen<br /> </td> 
   <td> <p>Met een lokaal meldingsbericht kunt u uw gebruikers informeren wanneer nieuwe gegevens beschikbaar komen in hun mobiele toepassingen, zelfs zonder toegang tot internet of de mobiele toepassing die op de voorgrond wordt uitgevoerd. Lokale meldingen worden geactiveerd door een mobiele toepassing op een bepaald tijdstip en afhankelijk van een gebeurtenis.</p><p>Raadpleeg de <a href="../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type">gedetailleerde documentatie</a>voor meer informatie.</p></td> 
  </tr> 
  <tr> 
   <td> Workflowverbetering - Een lading toevoegen aan externe signaalactiviteit<br /> </td> 
   <td> <p>Start een workflow met een payload als aan bepaalde voorwaarden is voldaan vanuit een andere workflow of een REST API-aanroep om te integreren met uw externe systemen. Dit omvat ook een nieuwe <strong>testactiviteit</strong> waar u tests op deze functionaliteit kunt in werking stellen.</p><p>Raadpleeg voor meer informatie de <a href="../../automating/using/calling-a-workflow-with-external-parameters.md">gedetailleerde documentatie</a> en de <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/managing-processes-and-data/execution-activities/external-signal-activity.html">Hoe kan ik-video</a>.</p></td> 
  </tr> 
  <tr> 
   <td> Verbetering van bestemmingspagina's - Google reCAPTCHA<br /> </td> 
   <td> <p>Gebruik Google reCAPTCHA om spam op uw landingspagina's te voorkomen zonder dat uw klanten iets moeten doen.</p><p>Raadpleeg de <a href="../../channels/using/configuring-landing-page.md#setting-google-recaptcha">gedetailleerde documentatie</a>voor meer informatie.</p></td> 
  </tr> 
 </tbody> 
</table>

**Verbeterde beveiliging**

* Oplossing voor een mogelijk probleem met de clickjackingbeveiliging in de rapportwerkruimte.

**Verbeteringen voor e-mailontwerper**

* Oplossing voor een probleem dat optrad bij het dupliceren van fragmenten en het proberen deze te gebruiken in de e-mailontwerper. (CAMP-33193)
* Probleem verholpen waarbij ongewenste spaties werden gemaakt bij gebruik van inline-elementen in de e-mailDesigner-interface. (CAMP-32163)
* Probleem verholpen waarbij enkele extra HTML-tagkenmerken werden verwijderd die de gebruiker had toegevoegd nadat e-mailinhoud in de e-mailontwerper was opgeslagen. (CAMP-32162)
* Probleem verholpen waarbij een Microsoft Office-tag in de HTML-modus van E-mailontwerper werd weergegeven, zelfs nadat deze was verwijderd. (CAMP-32141)
* Als u een e-mailbericht hebt gemaakt met een eerdere versie van de e-mailontwerper, wordt de gebruiker in een pop-upvenster gevraagd om de laatste versie bij te werken als deze e-mailinhoud is geopend. (CAMP-31529)
* Probleem verholpen waarbij afbeeldingen konden worden vervormd uit een e-mailbericht dat met de e-mailontwerper is gemaakt bij levering aan bepaalde berichtklanten. (CAMP-31407)
* Probleem verholpen waardoor bepaalde elementen, zoals lijsten of knoppen, niet correct konden worden weergegeven in de modus platte tekst wanneer ze werden gemaakt in de HTML-modus. (CAMP-32582, CAMP-32542)
* Probleem verholpen waarbij meer dan 50 organisatorische eenheden niet konden worden weergegeven in een inhoudssjabloon of fragmenteigenschappen. (CAMP-32932)
* Probleem verholpen met de achtergrondkleur van de viewport bij het ontvangen van een e-mail die is gemaakt met de e-mailontwerper in Outlook. (CAMP-31402)
* Probleem verholpen waardoor e-mailinhoud die met de e-mailontwerper is gemaakt, niet reageert wanneer deze wordt geopend in Outlook. (CAMP-31400)
* Probleem verholpen waardoor dynamische inhoud niet goed kon werken bij gebruik in een e-mailonderwerp. (CAMP-32837)
* Probleem verholpen met betrekking tot het onderwerp van de e-mail dat niet correct is beschermd.
* Probleem verholpen waarbij fragmenten niet konden worden geladen in het linkerpalet E-mailontwerper.
* Probleem verholpen waarbij werd voorkomen dat fragmenten die zijn gemaakt tijdens de editie van e-mailinhoud, werden weergegeven in het linkerpalet E-mailontwerp bij het vernieuwen van de fragmentlijst.
* Verschillende problemen verholpen die optraden bij het gebruik van dynamische inhoud in een e-mail.
* Probleem verholpen dat optrad met de kleurkiezer tijdens een poging een kleur te definiëren met RGB-waarden.
* Probleem verholpen waardoor de spiegel niet kon reageren wanneer de e-mail op een mobiel apparaat werd ontvangen.

**Verbeteringen op het gebied van transactief berichtenverkeer**

Er zijn verschillende verbeteringen toegevoegd aan het Transactionele berichtenkanaal om de werking en prestaties te optimaliseren.

* De transactionele berichtduur is uitgebreid om ervoor te zorgen dat alle berichten worden verzonden alvorens zij verlopen, vooral wanneer opnieuw probeert wordt uitgevoerd.
* De transactionele overseinenprestaties zijn verhoogd door de lading op verschillende verzendende draden te verdelen.
* Het transactionele overseinenproces is geoptimaliseerd om in parallelle veelvoudige analyse van het zelfde bericht te kunnen beginnen.
* Probleem verholpen die tot inconsistente doorvoer en latentie bij pushberichten over transacties kon leiden.
* Probleem verholpen waarbij een onjuist doelpubliek werd weergegeven voor levering van transactieberichten.
* Probleem verholpen die optrad bij het importeren van een pakket met een gebeurtenisconfiguratie en het bijbehorende transactiemelding. For more on this, refer to the [detailed documentation](../../channels/using/about-transactional-messaging.md#exporting-and-importing-transactional-messages).
* Probleem verholpen waarbij de verzamelingsgegevens werden verwijderd uit de testprofielen die zijn gemaakt voor een transactiebericht met productaanbiedingen.

**Overige wijzigingen**

* Er is een nieuwe optie toegevoegd aan de externe SMS-account. Het laat toe om het maximumaantal MTA processen te beperken die SMS verzenden om het aantal parallelle verbindingen beter te controleren. Raadpleeg het [SMS-connectorprotocol en het instellingentechnologie](https://helpx.adobe.com/campaign/kb/sms-connector-protocol-and-settings.html) voor meer informatie.
* Als een bron met API-extensie wordt gepubliceerd en de API al is gepubliceerd, wordt deze nu automatisch bijgewerkt wanneer deze opnieuw wordt gepubliceerd. Eerder was deze handeling handmatig en als de API niet werd bijgewerkt, kon het profiel of de servicebron van deze API worden verbroken. For more on this, refer to the [detailed documentation](../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension).
* De dimensie van de code van het postcode is verwijderd uit Dynamische Rapportering. We raden je aan in plaats daarvan de afmetingen Plaats, Land en Staat te gebruiken.
* De gebeurtenisactivering &#39;First Launch&#39; van de levenscyclus van In-App-berichten is verwijderd.
* Wanneer het uitvoeren van een pakket met veiligheidsgroepen, bevat het nu de rollen die aan elke groep worden toegewezen. (CAMP-32960)
* In de activiteit van het Dossier van de Lading, laat een nieuwe optie u controleren dat de kolommen van het dossier u uploadt de kolomdefinitie aanpassen. Raadpleeg de [gedetailleerde documentatie](../../automating/using/load-file.md)voor meer informatie. (CAMP-3229)
* Workflows kunnen nu worden gestart met een payload, zodat u externe parameters kunt gebruiken en delen tussen activiteiten in de workflow. Raadpleeg de [gedetailleerde documentatie](../../automating/using/calling-a-workflow-with-external-parameters.md)voor meer informatie. (CAMP-29412 &amp; CAMP-29413)
* Met Campaign Standard API&#39;s kunt u nu de geografische en organisatorische eenheden van profielen bijwerken met een payload. Raadpleeg de [gedetailleerde documentatie](../../api/using/get-started-apis.md)voor meer informatie.
* Foutberichten waarin een object uit de database niet toegankelijk is, zijn duidelijker om te begrijpen.
* In de activiteit van het Extraheren dossier, zijn de mogelijkheden JavaScript bijgewerkt toen het bepalen van de naam van een dossier om uit te voeren. Alleen de functie formatDate is nu beschikbaar voor gebruik in het veld Uitvoer. Raadpleeg de [gedetailleerde documentatie](../../automating/using/extract-file.md)voor meer informatie.
* Het genereren van automatische sequentie-id&#39;s is verbeterd voor aangepaste bronnen. De primaire sleutels voor nieuwe douanemiddelen zijn nu in 64 beetjes door gebrek.
* De testmodus voor het publiceren van aangepaste bronnen is verbeterd. Er wordt nu een waarschuwingsbericht weergegeven aan gebruikers als de laatste publicatie van de aangepaste bron is mislukt en niet is hersteld. Nadat de publicatie van een aangepaste bron is mislukt, kunt u terugdraaien naar de laatste werkversie. Raadpleeg de [gedetailleerde documentatie](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource)voor meer informatie.
* Er is een nieuwe optie toegevoegd aan de bestandsactiviteit voor overbrengen. Hiermee kunt u de bestanden sorteren wanneer u de handeling File downloaden gebruikt, in de SFTP-modus. Raadpleeg de [gedetailleerde documentatie](../../automating/using/transfer-file.md)voor meer informatie. (CAMP-33109)

**Patches**

* Probleem verholpen waarbij geheugenlek naar de MTA kon optreden toen de SMS-instellingen opnieuw werden geladen.
* Probleem opgelost waarbij updates van databases niet konden worden gepubliceerd in de herstelmodus.
* Probleem verholpen dat een verschil veroorzaakte tussen Adobe Analytics Reports en Adobe Campaign Dynamic Reporting. (CAMP-25393)
* Oplossing van een fout die ervoor zorgde dat de workflow voor het delen van rapporten mislukte.
* Probleem verholpen waardoor gebruikers geen berichten in de app konden verzenden met alleen de media-URL.
* Probleem verholpen waarbij een mobiele toepassing werd weergegeven, zelfs als het certificaat niet naar de instantie is geüpload.
* Correctie van een fout die ervoor zorgde dat aanpassingsvelden niet werkten wanneer alle gebruikers van een **Target-toepassingssjabloon** de velden konden gebruiken.
* Er zijn nieuwe instanties van de Campagnestandaard ingericht. (CAMP-32635 &amp; CAMP-32344)
* Probleem verholpen waarbij de aanpassing van de datumformule in een workflow werd voorkomen. (CAMP-30336)
* Probleem verholpen bij het definiëren van een aangepaste datumformule die kan voorkomen dat de velden &quot;Aanvullende gegevens&quot; en &quot;Segmentcode&quot; beschikbaar zijn in de vervolgkeuzelijst. (CAMP-32383)
* Probleem verholpen waarbij de activiteiten &quot;Overdrachtsbestand&quot; en &quot;Bestand uitpakken&quot; er niet in konden slagen de bestanden te zoeken die worden afgewezen als ze werden versleuteld. (CAMP-32377)
* Probleem verholpen in API&#39;s waardoor het lineCount-filter niet het exacte totale aantal kan weergeven. (CAMP-31424)
* Probleem verholpen in bestemmingspagina&#39;s die konden verhinderen dat invoervelden de bijgewerkte waarde konden weergeven nadat deze was gewijzigd. (CAMP-31401)
* Probleem verholpen waarbij een signaalactiviteit onverwacht kon worden geactiveerd.
* Probleem verholpen waarbij e-mailvoorvertoning niet kon worden weergegeven wanneer het publiek leeg is.
* Probleem verholpen in de activiteit &#39;Bestand uitpakken&#39; die een bestand kon genereren terwijl de optie &#39;Geen bestand genereren als de binnenkomende overgang leeg is&#39; was geactiveerd.
* Probleem verholpen waardoor de workflow voor aflevering werd uitgeschakeld als deze niet succesvol was voltooid.
* Probleem verholpen waardoor gebruikers rapporten niet konden opslaan of plannen. (CAMP-31133)

## Release 19.1.3 - maart 2019 {#release-19-1-3---march-2019}

**Verbeteringen voor e-mailontwerper**

* Probleem verholpen waardoor een sjabloon niet kon worden gewijzigd nadat deze was opgeslagen.
* Verschillende problemen verholpen bij het gebruik van een eerder gemaakte sjabloon in een e-mail.
* Probleem verholpen waarbij componenten niet konden worden verborgen in geïmporteerde sjablonen.

**Overige verbeteringen**

* Correctie van een fout bij het weergeven van typologische regels. (CAMP-32059 &amp; CAMP-31849)
* Probleem verholpen waardoor typologische regels niet konden worden bewerkt. (CAMP-31750)
* Probleem verholpen met het InMail-proces dat onverwachts kon stoppen. (CAMP-31238)

## Release 19.1 - februari 2019 {#release-19-1---february-2019}

**Nieuwe functies?**

<table> 
 <thead> 
  <tr> 
   <th> Functionaliteit<br /> </th> 
   <th> Beschrijving<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Verbeteringen voor Push Channel Reporting<br /> </td> 
   <td> <p>Er zijn verschillende verbeteringen toegevoegd aan de Push Channel-rapportage, zodat u de betrokkenheid van gebruikers intuïtiever kunt meten. Met deze release breiden we de lijst met metriek van het drukkkanaal uit tot drie verschillende meetwaarden: Impressies, klikken, Openen (App Open) om u te helpen de interactie van gebruikers met pushberichten beter te meten en te analyseren. Daarnaast standaardiseren we ook de definitie en implementatie van deze meetwaarden. Het ingebouwde rapport voor pushmeldingen is ook verbeterd met veelgebruikte visualisaties en metriek.</p><p> Raadpleeg de <a href="../../reporting/using/push-notification-report.md">gedetailleerde documentatie</a>voor meer informatie.</p> </td> 
  </tr> 
  <tr> 
   <td> Integratie starten voor mobiele toepassing<br /> </td> 
   <td> <p>Deze release bevat de integratie van Adobe Campaign met de GA-versies van Android en iOS-extensies voor Adobe Campaign Standard in Adobe Experience Platform Launch en Mobile SDK's. Deze extensies ondersteunen pushberichten, berichten in de app en updates van het profiel voor mobiele apps.</p><p> Raadpleeg de <a href="https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html">gedetailleerde documentatie</a>voor meer informatie.</p> </td> 
  </tr> 
  <tr> 
   <td> Mobiele berichten in de app<br /> </td> 
   <td> <p>Deze release bevat de GA-versie van In-App-kanaal in Campagne. Vanuit functioneel oogpunt zijn de meest opvallende toevoegingen aan de bètaversie dynamische rapporten voor het kanaal in de app en veilige handshake tussen Mobile SDK en MCIAS (Marketing Cloud In-App Messaging Service die de regels in de app aan de SDK aanbiedt). De veilige handshake zorgt ervoor dat de PII-gegevens van uw gebruikers niet in kwaadwillige handen vallen en stelt u in staat de privacy van gebruikers op een gedeeld apparaat te handhaven door berichtcache uit te wissen telkens als de gebruiker zich afmeldt.</p><p>Raadpleeg voor meer informatie de <a href="../../channels/using/about-in-app-messaging.md">gedetailleerde documentatie</a> en de speciale zelfstudie <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/communication-channels/mobile/in-app/in-app-message-overview.html">in de app</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Workflowverbeteringen<br /> </td> 
   <td> <p>De volgende workflowmogelijkheden zijn toegevoegd:</p> 
    <ul> 
     <li> U kunt nu activiteiten kopiëren en plakken binnen een workflow of een andere workflow vanuit dezelfde Campagne-instantie. Op deze manier kunt u eenvoudig een volledige workflow of specifieke activiteiten dupliceren en de instellingen behouden die oorspronkelijk zijn gedefinieerd. Raadpleeg de <a href="../../automating/using/workflow-interface.md#duplicating-workflow-activities">gedetailleerde documentatie</a>voor meer informatie. (CAMP-2014) </li> 
     <li> Wanneer u de activiteit Bestand <strong></strong> laden gebruikt, kunt u nu een tijdstempel toevoegen aan de naam van het bestand dat de geweigerde records bevat. Raadpleeg de <a href="../../automating/using/load-file.md#configuration">gedetailleerde documentatie</a>voor meer informatie. </li> 
     <li> <strong>De activiteiten van de vraag</strong> en van de <strong>Segmentatie</strong> laten u nu een uitgaande overgang toelaten als de activiteiten geen gegevens terugwinnen. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

**Verbeterde beveiliging**

* De gegenereerde HTML-code van de bestemmingspagina is bijgewerkt om indexering van zoekprogramma&#39;s te voorkomen.

**Verbeteringen voor e-mailontwerper**

* Er is nu een set van vier e-mailsjablonen met de beste responsieve functies die door Behance-artiesten zijn ontworpen.

   Raadpleeg de [gedetailleerde documentatie](../../designing/using/using-reusable-content.md#content-templates)voor meer informatie.

* Dankzij onze nieuwe instapervaring kunt u sneller e-mails maken en eenvoudiger toegang krijgen tot documentatie en zelfstudies.

   Raadpleeg de [gedetailleerde documentatie](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-home-page)voor meer informatie.

* U hebt nu de flexibiliteit om het aantal kolommen en breedte te vormen die op uw behoeften worden gebaseerd.

   Raadpleeg de [gedetailleerde documentatie](../../designing/using/designing-from-scratch.md#defining-the-email-structure)voor meer informatie.

* Wanneer u bewerkingen uitvoert in de mobiele weergave, kunt u bepaalde componenten alleen verbergen in de mobiele weergave voor een effectief ruimtegebruik.

   Raadpleeg de [gedetailleerde documentatie](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view)voor meer informatie.

* U kunt nu aangepaste sociale kanalen toevoegen aan uw e-mailsjabloon boven op de kanalen die al beschikbaar zijn.
* Probleem verholpen waarbij niet kon worden geschoven in het structuurmenu bij gebruik van meer dan 18 structuren. (CAMP-31173)
* Probleem verholpen waarbij de voorheader boven op de inhoud werd weergegeven wanneer een e-mail met een voorheader die met Adobe Campaign is verzonden, werd verzonden. (CAMP-30736)
* Probleem verholpen waardoor de onderwerpregel niet kon worden bijgewerkt wanneer werd geklikt op de optie AEM-inhoud **** vernieuwen nadat het onderwerp in de Adobe Experience Manager was gewijzigd. (CAMP-29984)
* Correctie van verschillende problemen die het gebruik van dynamische afbeeldingen van Adobe Target verhinderden.
* Probleem verholpen waardoor de voorvertoning niet kon worden bijgewerkt wanneer tijdens het voorbereiden inhoud werd opgehaald als de inhoud eerder uit een URL was geïmporteerd.
* Het YouTube-pictogram is toegevoegd aan de component **Sociale** inhoud.
* De **lijstweergave** is toegevoegd voor inhoudscomponenten en fragmenten die worden weergegeven in het palet E-mailontwerper.

**Overige verbeteringen**

* Adobe Campaign is nu volledig FCM-compatibel voor zowel SDK V4- als AEP SDK-apps.
* Adobe Campaign biedt ondersteuning voor pushberichten op het besturingssysteem Wear door Android en voor watchOS door Apple.
* Waarschuwings- en foutberichten die kunnen worden weergegeven wanneer u in de interface navigeert, zijn duidelijker en begrijpelijker gemaakt.
* U kunt nu kolommen toevoegen aan de profielenlijst met betrekking tot opt-in en opt-out (&quot;Niet meer contact..&quot; velden).
* De drop-down lijst van de tijdzone in het de aanmaakscherm van het Profiel is bewogen van de sectie van het Adres aan de hogere sectie van de interface.
* U kunt nu scheidingstekens toevoegen wanneer u aangepaste bronschermen configureert, zodat u uw velden in categorieën kunt indelen.

   Raadpleeg de [gedetailleerde documentatie](../../developing/using/configuring-the-screen-definition.md#defining-the-detail-screen-configuration)voor meer informatie.

**Overige wijzigingen**

* Adobe Campaign en Adobe Experience Cloud zullen vanaf het voorjaar van 2019 de ondersteuning voor Microsoft Internet Explorer 11 en de Campaign Standard 19.2-release stopzetten. Schakel over naar Microsoft Edge of een andere ondersteunde browser. Zie pagina [Vervangen en verwijderde functies](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html) .
* Het veld **Landcode** van de profielbron is hernoemd naar de code **** Land/regio.

**Patches**

* Probleem verholpen waardoor het bericht niet kon worden verzonden wanneer een testprofiel werd toegevoegd aan een e-mailtransactiebericht. (CAMP-29854)
* Probleem verholpen waarbij het verzenden van berichten van andere kanalen vertraagde als het verzenden voor één kanaal laag was toen het verzenden van berichten van alle kanalen gelijktijdig werd geactiveerd.
* Probleem verholpen waarbij de MTA sms-berichten begon te verzenden wanneer de externe accountverbinding nog niet tot stand was gebracht.
* Probleem verholpen die optrad met de uitvoeringsfrequentie en begintijd van de planningsactiviteit. (CAMP-30745)
* Probleem verholpen dat zich kon voordoen bij het genereren van PKEY bij het gebruik van uitgebreide profielbronnen. (CAMP-30285)
* Probleem verholpen dat zich kon voordoen met op kalenderdag gebaseerde vermoeidheidsregels. (CAMP-30136)
* Probleem verholpen die kon optreden wanneer werd geprobeerd toegang te krijgen tot aangepaste bronnen met namen die eindigen op &quot;Basis&quot;. (CAMP-30109)
* Probleem verholpen waarbij een PATCH-aanroep niet kon worden gebruikt om een profiel in te schrijven op een service. (CAMP-29728)
* Probleem verholpen waarbij een workflow kon worden beschadigd tijdens het importeren van een XML-bestand via de activiteit Bestand laden. (CAMP-29208 en CAMP-28205)
* Probleem verholpen bij het koppelen van aangepaste bronnen die het genereren van omgekeerde cardinaliteitskoppelingen kunnen voorkomen. (CAMP-30476)
* Probleem verholpen waarbij leveringslogboeken niet konden worden uitgebreid wanneer alleen de segmentcode werd gebruikt.
* Probleem verholpen waarbij rijen konden worden gedupliceerd wanneer de bestandsoverdrachtactiviteit in workflows werd gebruikt.
* Probleem opgelost waarbij geplande rapporten niet op het gekozen tijdstip konden worden verzonden.
* Probleem verholpen waarbij een discrepantie optrad tussen de KPI&#39;s &quot;Te leveren&quot; en &quot;Verzonden&quot; voor levering in de app in een workflow.
* Probleem verholpen waardoor tracering niet werkte voor een In-App-bericht dat met een aangepaste HTML is gemaakt.
* Probleem verholpen waarbij werd voorkomen dat leveringsinhoud in de app werd opgeslagen bij gebruik in een workflow.
* Probleem verholpen waardoor mobiele toepassingen niet konden worden weergegeven voor beheerders.
* Probleem opgelost waarbij de technische workflow voor het bijwerken van de levering mislukte. (CAMP-26387)
* Probleem verholpen waarbij een verschil werd veroorzaakt tussen de profielen die tijdens het maken van een levering in de app als doel werden gebruikt en de profielen die op het dashboard voor levering werden weergegeven. (CAMP-28722)
* Probleem verholpen met de integratie van Campagne en Assets Core Service, waardoor u mogelijk geen gedeeld middel in een e-mail kunt selecteren.

## Release 19.0 - januari 2019 {#release-19-0---january-2019}

**Nieuwe functies?**

<table> 
 <colgroup><col style="width: 30%"><col style="width: 70%"></colgroup>
 <thead> 
  <tr> 
   <th> Functionaliteit<br /> </th> 
   <th> Beschrijving<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Algemene beschikbaarheid van e-mailontwerper<br /> </td> 
   <td> <p>De nieuwe intuïtieve e-mailontwerper (voorheen Creative Designer genoemd) is verplaatst naar GA. De klasse biedt nu ondersteuning voor alle functies van de verouderde inhoudeditor, waaronder:</p> 
    <ul> 
     <li> Het gebruik van <a href="../../integrating/using/adding-target-dynamic-content.md">dynamische afbeeldingen uit Adobe Target</a> </li> 
     <li> De mogelijkheid om inhoud automatisch tijdens de voorbereiding van een URL op te <a href="../../designing/using/using-existing-content.md#retrieving-content-from-a-url-automatically-at-preparation-time">halen</a> </li> 
     <li> Volledig compatibele sjablonen voor inhoud <a href="../../designing/using/using-reusable-content.md#content-templates">buiten het vak</a>. </li> 
    </ul> 
    <p>Raadpleeg voor meer informatie de <a href="../../designing/using/designing-content-in-adobe-campaign.md">gedetailleerde documentatie</a> en de <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/email-designer-overview.html">Hoe kan ik-video</a>. Hieronder vindt u verbeteringen en correcties.</p><p>Als gevolg hiervan is de oude e-mailinhoudeditor nu afgekeurd. Raadpleeg deze <a href="https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html">pagina</a>voor meer informatie.</p> </td> 
  </tr> 
  <tr> 
   <td> Productaanbiedingen in Transactiee-mails<br /> </td> 
   <td> <p>U kunt nu verwijzen naar een of meer productverzamelingen in een transactie-e-mailbericht. U kunt bijvoorbeeld automatisch een e-mailbericht met een winkelwagentje verzenden waarin alle producten worden vermeld die zich in de winkelwagentje van de gebruiker bevonden met een afbeelding, prijs en koppeling naar elk product.</p><p>Raadpleeg voor meer informatie de <a href="../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message">gedetailleerde documentatie</a> en de <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/designing-content/product-listings-in-transactional-email.html">Hoe kan ik-video</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Mobiele weergave in de e-mailontwerper<br /> </td> 
   <td> <p>U kunt nu overschakelen naar een speciale mobiele weergave wanneer u e-mailinhoud bewerkt. Op deze manier kunt u het responsieve ontwerp van een e-mail perfectioneren door alle stijlopties voor mobiele weergave afzonderlijk te bewerken, zoals het aanpassen van marges, kleinere tekengrootte, verschillende achtergrondkleur enzovoort.</p><p> Raadpleeg de <a href="../../designing/using/plain-text-html-modes.md#switching-to-mobile-view">gedetailleerde documentatie</a>voor meer informatie.</p> </td> 
  </tr> 
  <tr> 
   <td> Verbeteringen in bètaberichten in de app<br /> </td> 
   <td> <p>De bètafunctie voor berichten in de app is uitgebreid met de volgende mogelijkheden:</p> 
    <ul> 
     <li> Bètakanaal in de app is GDPR-compatibel </li> 
     <li> Integratie met Analytics API's om dropdowns van Triggers te vullen </li> 
     <li> Intuïtieve vormgeving en beschrijving van leveringssjablonen </li> 
     <li> Verbeteringen van de ontwerpinterface vanuit het oogpunt van bruikbaarheid </li> 
    </ul> <p>Raadpleeg de <a href="../../channels/using/about-in-app-messaging.md">gedetailleerde documentatie</a>voor meer informatie.</p> </td> 
  </tr> 
 </tbody> 
</table>

**Verbeteringen**

* Met een nieuwe optie in de activiteit Gegevens laden kunt u nu een nabewerkingsfase toepassen op het bestand dat de afgewezen records bevat (bijvoorbeeld Compressie Zip-indeling). (CAMP-24521)
* Een nieuwe optie in de de gegevensactiviteit van de Update staat u nu toe om de maximumpartijgrootte voor de te uploaden gegevens te vormen. (CAMP-28400)
* Verbeterde selectie van de adresstatus van profielen. Wanneer u een land selecteert, wordt de vervolgkeuzelijst Staat nu automatisch bijgewerkt met de relevante statuswaarden. (CAMP-28874)
* Een nieuwe optie in de activiteit van het Extraheren dossier verhindert nu om een dossier te produceren als de binnenkomende overgang leeg is. Zo voorkomt u het maken en uploaden van lege bestanden op SFTP-servers.
* Het overzichtsverslag over de levering is verbeterd.
* De lijst met landen die beschikbaar zijn wanneer het adres van een profiel wordt gedefinieerd, is verrijkt. (CAMP-26707)
* Er wordt nu een foutbericht weergegeven wanneer u een ingebouwde workflow probeert te importeren.

**E-mailontwerper**

* Probleem verholpen waarbij de geografische eenheid kon worden gebruikt voor een e-mailsjabloon of een inhoudsfragment dat met de e-mailontwerper is gemaakt, ook al was deze functie uitgeschakeld in Adobe Campaign, waardoor de sjabloon of het fragment niet beschikbaar was toen u opnieuw probeerde toegang te krijgen tot de sjabloon. (CAMP-28174)
* Probleem verholpen waardoor dynamische inhoudsvoorwaarden niet konden worden opgeslagen tijdens het bewerken van inhoud met de e-mailontwerper. (CAMP-27905)
* Probleem verholpen waarbij de HTML-versie uit de e-mailinhoud werd verwijderd nadat de onbewerkte tekstversie van een bericht was bewerkt en de HTML-synchronisatie in de e-mailontwerper was verbroken. (CAMP-28507)
* Probleem verholpen waardoor de interface van E-mailDesigner niet kon worden geopend in Internet Explorer 11. (CAMP-28273)
* Probleem verholpen waarbij de Microsoft Outlook-rendering van stijlinstellingen die op knoppen met de e-mailontwerper zijn toegepast, werd vervormd.
* Probleem verholpen in de e-mailontwerper die een URL bewerkbaar maakte vanuit een inhoudsfragment dat in een e-mail werd gebruikt. Dit probleem werd niet verwacht omdat het fragment standaard vergrendeld is.
* Probleem verholpen waardoor de scheidingscomponent van de e-mailontwerper niet in Microsoft Office kon worden weergegeven.
* Probleem verholpen waarbij een pagina in bepaalde internetbrowsers vastliep tijdens het weergeven van inhoud die via AEM was gesynchroniseerd met de oude e-mailinhoudeditor. (CAMP-29068)
* Oplossing voor een fout die optrad wanneer op een afbeelding in een e-mailbericht werd geklikt wanneer de oude e-mailinhoudeditor werd gebruikt. (CAMP-30424)
* Probleem verholpen waarbij de nieuwe fragmenten niet konden worden weergegeven tijdens het bewerken van een e-mailbericht met de e-mailontwerper. (CAMP-29928)
* Probleem verholpen waardoor knoptekst niet correct kon worden weergegeven in e-mailberichten die waren gemaakt met de e-mailontwerper en die werden ontvangen met de Outlook-webmailclient.
* Het is nu mogelijk om transactieberichten voor profielen te maken met de e-mailontwerper. (CAMP-28900)
* Correctie van een fout in de e-mailontwerper die de inhoud bewerkbaar heeft gemaakt tijdens het automatisch ophalen van inhoud van een URL tijdens de voorbereiding, terwijl de inhoud vergrendeld moest worden.

**Patches**

* Probleem verholpen waarbij onjuiste leveringslogboeken werden weergegeven bij Dynamische rapportage. (CAMP-23446)
* Probleem opgelost dat van invloed zou kunnen zijn op de nummers in het rapport met de stuiterende samenvatting (CAMP-28703)
* Probleem verholpen met de integratie van Campagne en Assets Core Service, waardoor elementen niet kunnen worden weergegeven wanneer u een e-mailbericht selecteert (CAMP-28732). **[!UICONTROL Image shared from Adobe Experience Cloud]**
* Probleem verholpen waarbij werd voorkomen dat sms-berichten met het &quot;ene&quot; teken werden verzonden, ook al was de vertaling toegestaan in de externe rekening van SMPP. (CAMP-29041)
* Probleem verholpen waarbij dubbele records konden worden weergegeven wanneer een segmentatieactiviteit in workflows werd gebruikt. (CAMP-28743)
* Probleem verholpen waarbij een van de waardetoewijzingen in een kolom in een werkstroomactiviteit niet kon worden verwijderd. (CAMP-28708)
* Probleem verholpen in de bestandsoverdrachtactiviteit bij het gebruik van jokertekens met de optie Testen om te controleren of het bestand bestaat. (CAMP-28977)
* Probleem verholpen in de bestandsoverdrachtactiviteit die zich kon voordoen bij het bijwerken van instellingen voor externe accounts. (CAMP-28894)
* Probleem verholpen met aangepaste filters in de query-editor wanneer de voorwaarde &#39;E-mail is niet leeg&#39; wordt gebruikt. (CAMP-28741)
* Probleem verholpen die zich kon voordoen wanneer aangepaste bronnentabellen met meer dan 100 k records werden geëxporteerd. (CAMP-28150)
* Probleem verholpen waarbij transactierepunten die gekoppeld zijn aan triggers, niet konden worden verwijderd. (CAMP-28385)
* Verwijderde wachtwoorden die onveilig in sommige logboeken van SMS werden getoond.
* Probleem verholpen waarbij de verbinding met de SMPP-simulator is verbroken als gevolg van een leeg wachtwoord dat door Adobe Campaign is verzonden.
* Probleem opgelost waarbij het verzenden van campagnes werd verhinderd wanneer de sms-verbindingen instabiel zijn.
* Probleem verholpen waarbij verwijderde leveringen werden weergegeven in Dynamic Reporting.
* Probleem verholpen waarbij geen aanvullende gegevens konden worden opgehaald uit leveringslogboeken, logboekbestanden werden bijgehouden en logboektabellen werden uitgesloten bij gebruik van een verrijkingsactiviteit in een workflow.
* Probleem verholpen met GDPR-verwijderingsverzoeken die konden optreden bij het gebruik van een koppelingstype &quot;N cardinality collection link&quot; en het koppelingstype &quot;Deleting the target record impliceert delete records references by the link&quot;.
* Probleem opgelost met delen van rapporten.
* Probleem verholpen dat tot problemen met de doorvoer kan leiden wanneer een pushmelding wordt verzonden.
* Probleem verholpen waarbij velden voor direct-mailuitvoer ontbreken.
* Probleem verholpen waarbij gebruikers ingebouwde workflows konden wijzigen.
* Probleem verholpen tijdens het maken van een campagne op basis van een campagnemalplaatje, inclusief een workflow met een geconfigureerde extractieactiviteit. (CAMP-29198)
* Probleem verholpen met de extractie-activiteit voor bestanden waardoor dezelfde expressie niet kon worden gebruikt voor verschillende elementen. (CAMP-29182)
* Oplossing voor een probleem in de queryeditor met de voorwaarde voor samenvoeging tussen log en trackinglogbestand voor rtEvent. (CAMP-28780)
* Probleem verholpen waardoor wijzigingen in de landingspagina van &quot;Specifieke actie&quot; niet konden worden opgeslagen. (CAMP-29422)
* Probleem verholpen waarbij het laden van een gebeurtenislading in een werkstroom werd verhinderd. (CAMP-29029)
* Probleem verholpen waarbij SMS-nummers op de lijst van afgewezen personen niet in een SMS-bericht werden uitgesloten. (CAMP-28898)
* Probleem verholpen waardoor SMPP-providers niet op de hoogte konden worden gesteld van een fout tijdens de verwerking van binnenkomende berichten. (CAMP-29804)
* Probleem verholpen waarbij externe accounts met bijbehorende leveringen konden worden verwijderd. (CAMP-29738)
* De verzendende doorvoer is verbeterd en gestabiliseerd voor SMS-berichten.
* Probleem verholpen waardoor het teken &#39;~&#39; niet in een SMS-bericht kon worden gebruikt. (CAMP-29172)
* Probleem verholpen in leveringen met de optie Tijd verzenden. (CAMP-29231)

