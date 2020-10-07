---
title: Opmerkingen bij de releases in 2017
description: Deze pagina bevat een overzicht van alle releases van Adobe Campaign Standard in 2017.
page-status-flag: never-activated
uuid: d73f8186-e309-441b-969d-71d0a1c33cf4
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
discoiquuid: 1cfd9b3b-9b3e-4587-9c46-b6fb02131654
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '4627'
ht-degree: 8%

---


# Opmerkingen bij de releases in 2017{#release-notes}

Op zoek naar een specifieke release van Adobe Campaign Standard in 2017?

Elke release bevat nieuwe functies en patches. Klik op een release om de inhoud ervan weer te geven.

Bekijk de nieuwste [documentatieupdates](../../rn/using/documentation-updates.md) voor Adobe Campaign Standard. Raadpleeg deze [pagina](../../rn/using/release-notes.md)als u op zoek bent naar een nieuwere versie.

## Release 17.10 - oktober 2017 {#release-17-10---october-2017}

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
   <td> Beheer van moeheidsregels<br /> </td> 
   <td> Met vermoeidheidsbeheer kunt u vermoeidheidsregels maken om overcommunicatie met profielen te beheren. De regels van de vermoeidheid worden gemakkelijk gebouwd, maar zijn uiterst flexibel met mogelijkheden zoals het tellen van berichten over veelvoudige kanalen (met inbegrip van transactionele berichten), slechts het tellen van specifieke leveringen, of het toepassen van regels op specifieke profielen.<br /> Raadpleeg de <a href="../../sending/using/fatigue-rules.md">gedetailleerde documentatie</a> voor meer informatie.<br /> </td> 
  </tr> 
  <tr> 
   <td> Content creation: Import from a URL<br /> </td> 
   <td> Importeren vanaf een URL biedt u de mogelijkheid om uw creatieve inhoud snel van een website op te halen en e-mails samen te stellen voor elke levering. Bovendien kunt u uw creatieve proces stroomlijnen door derden in staat te stellen inhoud rechtstreeks via een URL te delen. Geïmporteerde inhoud kan op flexibele wijze worden gebruikt als onderdeel van één levering of op sjabloonniveau, zodat alle gerelateerde campagnes, ongeacht of het workflowberichten of transactiemeldingen betreft, consistent blijven en A/B- of multivariate tests bevatten. Importeren van een URL converteert en volgt automatisch alle koppelingen om de e-mailprestaties te controleren via Dynamic Reporting.<br /> Raadpleeg de <a href="../../designing/using/using-existing-content.md#importing-content-from-a-url">gedetailleerde documentatie</a> voor meer informatie.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Patches**

_Platform_

* Probleem verholpen waarbij grote gecomprimeerde bestanden niet correct werden uitgepakt.
* De beveiliging van merkbeheer is verbeterd. Het wijzigen van de naam en het afzenderadres van een merk is nu gereserveerd voor Adobe technische beheerders.
* Om de beveiliging te verbeteren, door de gebruiker gegenereerde inhoud (afbeeldingen, spiegelpagina&#39;s, bestemmingspagina&#39;s, enz.) kan niet meer worden aangeboden door het domein adobe.com. Het is nu verplicht om uw eigen domein te gebruiken om deze bronnen te verwerken via branding.
* Oplossing voor een interfaceprobleem bij het weergeven en filteren van marketingactiviteiten.
* Probleem verholpen waardoor velden met abonnementsdatum niet konden worden bijgewerkt met een aanroep van de POST Rest API.

_E-mail, SMS-berichten en direct mail_

* Probleem verholpen waarbij het maken van een melding voor een publiek met een lijsttype niet kon worden geactiveerd, waardoor de voorbereiding mislukte.
* Ontbrekende talen die zijn toegevoegd aan de meertalige functies voor het leveren van e-mail.
* De miniatuur van de inhoud, weergegeven op het bezorgdashboard, wordt nu automatisch bijgewerkt wanneer de gebruiker inhoud wijzigt en opslaat.
* Probleem met betrekking tot tijdzone verholpen waardoor een levering niet kon worden geopend.

_Pushmeldingen_

* Wanneer u het pushmeldingskanaal configureert, moet het pushprovider voor iOS **apns** en voor Android **gcm** zijn.
* Correctie van een fout die ervoor zorgde dat mobiele iOS-app niet kon worden toegevoegd aan de Adobe Campaign-interface.
* Pushmeldingen worden nu ondersteund op mobiele Android-toepassingen die geschikt zijn voor GCM en FCM.
* Oplossing voor een fout die ervoor zorgde dat er geen inhoud kon worden opgeslagen tijdens het dupliceren van een pushberichtsjabloon.
* Het is nu mogelijk om een profiel te maken of bij te werken vanuit de Adobe Campaign-database door de gegevens van gebruikers van mobiele toepassingen met elkaar in overeenstemming te brengen.
* Adobe Campaign geeft nu prioriteit aan het verwerken van de transactionele pushmeldingen boven standaardpushmeldingen.

_Rapporten_

* Probleem verholpen waardoor de percentages voor klikken met hot in de e-mailinhoud niet konden worden weergegeven.
* Probleem verholpen met de lijst van afgewezen personen metrisch die als harde stuit in plaats van stuit werd geteld.
* Probleem verholpen waarbij negatieve tellingen werden weergegeven in samenvattingsgegevens.
* Probleem verholpen waarbij profielen in het verkeerde leeftijdssegment werden geteld.
* De zachte en harde berekeningsformules zijn veranderd.

_Workflows_

* Probleem verholpen in de **[!UICONTROL Load file]** activiteit die tot fouten zou kunnen leiden na het handmatig toevoegen en verwijderen van kolommen in de activiteit.
* De **[!UICONTROL deliverabilityUpdate]** technische workflow is nu gepland om 2 uur &#39;s nachts, op de server.
* Probleem verholpen waarbij een beveiligingsprobleem is verholpen waarbij een lijst zonder de exportrol kon worden geëxporteerd.
* Probleem met de **[!UICONTROL Reconciliation]** activiteit opgelost.
* Probleem verholpen met het gebruik van jokertekens in de **[!UICONTROL File Transfer]** activiteit.

_Profielen en doelgroepen_

* Probleem verholpen waardoor in bepaalde specifieke gevallen geen correcte rekening kon worden gehouden met een voorwaarde voor een query, wat tot onjuiste resultaten zou kunnen leiden.
* Probleem verholpen waardoor profielen niet konden worden geopend als ze waren bestemd voor een bericht dat was voorbereid, maar dat nooit was verzonden en verlopen.

_Integraties_

* Probleem verholpen waarbij bepaalde voor Triggers gemaakte gegevensbronnen niet correct konden worden weergegeven en geselecteerd.

_Aangepaste resources_

* Probleem verholpen die optrad in lijstschermen waar aangepaste bronrijen konden worden weergegeven zonder gegevens.
* Probleem verholpen waarbij werd voorkomen dat Booleaanse tekstvelden met de waarde Onwaar werden weergegeven in aangepaste bronnen.

## Release 17.9 - september 2017 {#release-17-9---september-2017}

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
   <td> Bibliotheek van e-mailsjablonen<br /> </td> 
   <td> Maak kennis met achttien gloednieuwe responsieve sjablonen die zijn ontworpen in twee prachtige thema's: Astro en Doezelaar. Deze aanpasbare sjablonen zijn in de branche agnostisch en kunnen meteen worden gebruikt. Sjablonen bevatten inhoud voor verschillende gebruiksgevallen, zodat uw e-mailmarketingcampagnes sneller, efficiënter en mooier dan ooit kunnen worden ontworpen en geleverd.<br /> Raadpleeg de <a href="../../designing/using/using-reusable-content.md#content-templates">gedetailleerde documentatie</a> voor meer informatie.<br /> </td> 
  </tr> 
  <tr> 
   <td> Dynamische rapportage met profielgegevens<br /> </td> 
   <td> De dynamische Rapportering verstrekt volledig klantgerichte en bedrijfsrapporten in real time. Met deze release biedt een krachtige uitbreiding van Dynamic Reporting toegang tot profielgegevens, waardoor demografische analyse mogelijk wordt op basis van profieldimensies zoals geslacht, stad, postcode en leeftijd, en naast functionele e-mailcampagnecampagne, zoals geopend en geklikt. Met de zelfde makkelijk te gebruiken belemmering-en-dalingsinterface, bepalend hoe uw e-mailcampagne tegen uw belangrijkste klantensegmenten wordt uitgevoerd gemakkelijker dan ooit.<br /> Raadpleeg de <a href="../../reporting/using/about-dynamic-reports.md">gedetailleerde documentatie</a> voor meer informatie.<br /> </td> 
  </tr> 
  <tr> 
   <td> Abonnement voor massa met oorsprong en datum<br /> </td> 
   <td> Met deze Mass Subscription-uitbreiding kunt u nu abonnementsgegevens (oorsprong en datum) rechtstreeks in de Adobe Campaign Standard-database opslaan via de activiteit Subscription Services in een workflow.<br /> Raadpleeg de <a href="../../automating/using/subscription-services.md">gedetailleerde documentatie</a> voor meer informatie.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Patches**

_Platform_

* Sommige klanten moeten een id van Adobe Campaign Standard kunnen gebruiken omdat ze geen unieke sleutel beheren om hun eigen records te identificeren. Deze id (**ACS-id**) kan worden geëxporteerd en als een afstemmingssleutel worden gebruikt bij het bijwerken van de gegevens. Raadpleeg de [gedetailleerde documentatie](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources) voor meer informatie.
* Het FTP-protocol wordt afgekeurd. Gebruik nu SFTP. Om bestaande implementaties niet te blokkeren, werken bestaande configuraties op FTP nog steeds zoals voorheen, maar de optie wordt niet weergegeven voor nieuwe activiteiten.

_E-mail, SMS-berichten en direct mail_

* Het is nu mogelijk nieuwe waarschuwingscriteria te maken om deze te gebruiken in waarschuwingsberichten voor leveringen. Raadpleeg de [gedetailleerde documentatie](../../sending/using/receiving-alerts-when-failures-happen.md#creating-a-delivery-alerting-criterion) voor meer informatie.
* De berichten van de levering alarmerend hebben een nieuw ontwerp en de levering alarmerende dashboardgebruikerservaring is verbeterd.
* Wanneer een verpletterende externe rekening nu onbruikbaar wordt gemaakt, wordt een waarschuwing getoond in de beïnvloede leveringen (e-mail, SMS en duw) en de knoop van de **Voorproef** wordt verborgen in deze leveringen.
* Probleem verholpen dat een fout veroorzaakte in de voorvertoning van een A/B-test op de e-mailinhoud toen dynamische tekst werd ingeschakeld op de onderwerpregel.

_Transactionele berichten_

* Het is nu mogelijk om te bepalen wanneer u een vervolgbericht wilt verzenden, bijvoorbeeld 3 dagen nadat een transactiebericht is verzonden. Raadpleeg de [gedetailleerde documentatie](../../channels/using/follow-up-messages.md#sending-a-follow-up-message) voor meer informatie.
* Het is nu mogelijk om de datum te bepalen vanaf wanneer de aan een gebeurtenis gekoppelde transactieberichten moeten worden verzonden.
* Probleem verholpen waarbij een SQL-fout optrad tijdens het uitvoeren van een workflow met een vervolgbericht nadat profielen waren verwijderd die gekoppeld waren aan ontvangen en verwerkte gebeurtenissen.
* Probleem verholpen waarbij een aan een gebeurtenis gekoppeld profiel niet kon worden verwijderd.
* Probleem verholpen waardoor het omleiden van bijgehouden koppelingen niet meer werkt.
* Probleem verholpen waarbij het bijhouden van wijzigingen voor bepaalde koppelingen in een e-mail- of SMS-bericht niet kon worden uitgeschakeld.

_Rapporten_

* Het rapport **Hot kliks** is verbeterd. Ook, is het nu mogelijk om heet kliks volgens elke voorwaardelijke inhoud te tonen die in een levering werd bepaald en hete kliks voor elke uitvoering van terugkomende leveringen of transactionele berichten te tonen. Raadpleeg de [gedetailleerde documentatie](../../sending/using/receiving-alerts-when-failures-happen.md#creating-a-delivery-alerting-criterion) voor meer informatie.
* Probleem verholpen waarbij de quarantaineminimetrische gegevens niet werden opgehaald.
* Er is een nieuw vooraf ingesteld tijdframe toegevoegd aan de kalenderwidget.
* De [dynamische rapportmetriek](../../reporting/using/indicator-calculation.md) en KPIs van [campagnes](../../sending/using/confirming-the-send.md) (die op het dashboard van verzonden berichten worden getoond) zijn gericht voor meer coherentie.
* Probleem verholpen waarbij een pijpleiding ertoe kon leiden dat er een crash optrad bij debian 7.

_Workflows_

* Probleem verholpen waarbij het bewaren van het geïmporteerde bestand niet kon werken.

_Integraties_

* Vars en gebeurtenissen worden nu ondersteund voor de integratie van Analytics &amp; Campagne.
* Wanneer u een e-mail verzendt met de inhoud van de verlaten winkelwagen, is de parameter voor het laden van elementen die uit winkelwagentje zijn verwijderd nu optioneel.

_Profielen en doelgroepen_

* Adobe Campaign biedt nu een rapport waarin het aantal actieve profielen wordt weergegeven. Dit rapport is slechts informatief, het heeft geen directe invloed op het factureren. Raadpleeg de [gedetailleerde documentatie](../../audiences/using/active-profiles.md) voor meer informatie.
* Probleem verholpen waardoor profielen niet op een service konden worden geabonneerd wanneer de API voor profielen en services werd gebruikt.

## Release 17.7 - juli 2017 {#release-17-7---july-2017}

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
   <td> Meertalige e-mail- en sms-leveringen<br /> </td> 
   <td> Bepaal en voer meertalige e-mail &amp; SMS-leveringen uit door één enkele levering op basis van de voorkeurstaal van uw automatisch gesegmenteerde klanten. Rapporteer over de prestaties van elke levering, inclusief de taal en individuele niveaus.<br /> Steeds meer bedrijven worden geconfronteerd met de uitdaging om content in meerdere talen te leveren terwijl ze in eigen land en in het buitenland groeien. Als zodanig vormt het stroomlijnen van gelokaliseerde berichtlevering een essentieel onderdeel van een effectieve strategie voor klantcommunicatie voor multinationale ondernemingen; ondernemingen in landen met meerdere talen; en bedrijven die hun inhoud op taalkundig niveau verder willen aanpassen, ongeacht waar de klanten zich bevinden. Raadpleeg de <a href="../../channels/using/creating-a-multilingual-email.md">gedetailleerde documentatie</a> voor meer informatie.<br /> </td> 
  </tr> 
  <tr> 
   <td> Adobe Campaign-meldingen<br /> </td> 
   <td> Ontvang meldingen met betrekking tot belangrijke systeemactiviteiten rechtstreeks in Adobe Campaign Standard. U wordt bijvoorbeeld op de hoogte gesteld van de voortgang van de lopende leveringen of wanneer een workflow een fout bevat.<br /> Kennisgevingen in realtime houden relevante belanghebbenden op de hoogte en bieden gebruikers de mogelijkheid om onmiddellijk en rechtstreeks te reageren op activiteitenmeldingen vanuit de toepassing. Het resultaat voor teams is geavanceerde behendigheid, efficiency en vlottere uitvoering van campagnes. Raadpleeg de <a href="../../administration/using/sending-internal-notifications.md">gedetailleerde documentatie</a> voor meer informatie.<br /> </td> 
  </tr> 
  <tr> 
   <td> Leveringswaarschuwing<br /> </td> 
   <td> Naast het rechtstreeks bekijken van berichten in Adobe Campaign Standard, biedt Adobe Campaign nu ook een e-mailwaarschuwingssysteem om e-mailwaarschuwingen aan gebruikers of externe belanghebbenden over belangrijke systeemactiviteiten te activeren. Maak, beheer en ontvang aanpasbare waarschuwingen en dashboards om de resultaten of mislukkingen van de levering bij te houden.<br /> Adobe Campaign Delivery Alerting verhoogt de efficiëntie door alle betrokken Adobe Campaign-gebruikers automatisch via e-mail en dashboard op de hoogte te houden van de uitvoeringsstatus van de levering. Raadpleeg de <a href="../../sending/using/receiving-alerts-when-failures-happen.md">gedetailleerde documentatie</a> voor meer informatie.<br /> </td> 
  </tr> 
  <tr> 
   <td> Versleutelde gedeclareerde id in gegevensbronnen<br /> </td> 
   <td> Verzend e-mail en de trekkers van SMS zonder de behoefte aan een bestaand profiel in Campagne door gecodeerde contactinformatie (e-mailadres of telefoonaantal) als Verklaarde identiteitskaart te gebruiken Omdat gecodeerde opgegeven id's door Adobe Campaign Standard kunnen worden gedecodeerd, kan Campagne nu nieuwe verhandelbare profielen maken wanneer gebruikers van andere Experience Cloud-oplossingen met eerder onbekende contactpersonen worden benaderd.<br /> De klanten van het doel en onbekende vooruitzichten in real time door zowel e-mail als SMS om loyaliteit in uw bestaande klantenbasis te verbeteren en nieuwe klanten te verwerven. Maak optimaal gebruik van uw first-party cookie data (vanuit Adobe Audience Manager*) wanneer perspectief verifieert en gebruik deze inzichten in Adobe Campaign. <br /> *Adobe Audience Manager is vereist. Raadpleeg de <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">gedetailleerde documentatie</a> voor meer informatie.<br /> </td> 
  </tr> 
  <tr> 
   <td> KPI sharing from Campaign to Analytics<br /> </td> 
   <td> Deel campagnegegevens met Adobe Analytics om de cijfers voor e-mailmarketing van Campaign te meten in combinatie met andere marketing- en reclameactiviteiten door middel van conversie, waarbij het gedrag voor en na het klikken wordt verenigd.<br /> De algemene prestaties rechtstreeks volgen en synergieën met externe programma's in Analytics aan het licht brengen. Pas uw leren van deze geconsolideerde mening terug in uw campagnes toe; verbeteren van de open, doorklikings- en conversiekoersen, waardoor de omzet en de algehele campagneprestaties toenemen. <br /> Adobe Analytics is vereist. Raadpleeg de <a href="../../integrating/using/about-campaign-analytics-integration.md">gedetailleerde documentatie</a> voor meer informatie.<br /> </td> 
  </tr> 
  <tr> 
   <td> Direct Mail Channel - Return To Sender<br /> </td> 
   <td> Platte bestandsuitwisselingen met Direct Mail-providers die informatie over terugsturen bevatten, worden nu ondersteund. Dankzij deze uitbreiding van het Direct Mail-kanaal kunnen de overeenkomstige postadressen van toekomstige communicatie worden uitgesloten.<br /> Op deze manier kunnen marketers op de hoogte worden gesteld van een onjuist adres en via andere kanalen contact opnemen met de klant of worden aangemoedigd zijn postadres bij te werken. Dit vermindert ook het aantal verspilde marketingdollars aangezien de marketers vermijden verzendend post naar onjuiste adressen. <br /> Direct Mail is beschikbaar als een add-on kanaal. Raadpleeg de <a href="../../channels/using/return-to-sender.md">gedetailleerde documentatie</a> voor meer informatie.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Patches**

_Algemeen_

* Probleem verholpen waarbij lijsten met gebruikers konden worden geëxporteerd. Alleen gebruikers met de **[!UICONTROL Export]** rol mogen deze nu doen.

_E-mail, SMS-berichten en direct mail_

* Probleem verholpen met de **updateDeliveryExecInfo** -workflow die de optie **Om de indicator te leveren** op 0 instelt voor SMS-leveringen.
* In de **Geavanceerde parameters** van de eigenschappen van het leveringsmalplaatje, toont de **Verpletterende** drop-down lijst nu slechts externe rekeningen die aan het type van malplaatjebericht beantwoorden. Een sjabloon voor e-maillevering geeft bijvoorbeeld alleen e-mailexterne accounts weer.
* Probleem verholpen waarbij de e-mailindeling van de **[!UICONTROL Text]** voorkeur werd gedefinieerd voor testprofielen.
* Probleem verholpen die tot een fout Javascript binnen leidde wanneer het selecteren van de standaardtijdzone in het scherm van de programmadefinitie van een levering.
* Probleem verholpen waarbij overvullingen niet konden worden weergegeven in de verzendende logboeken.
* In het scherm van de malplaatjeselectie van de tovenaar van de leveringsverwezenlijking, follow-up en A/B testmalplaatjes worden nu verborgen door gebrek. For more information, refer to the [detailed documention](../../channels/using/creating-an-email.md).
* Probleem verholpen waarbij gebruikers leveringen konden verzenden. Alleen gebruikers met de **[!UICONTROL Start deliveries]** rol mogen deze nu doen. For more information, refer to the [detailed documention](../../sending/using/confirming-the-send.md).

_Pushmeldingen_

* Probleem verholpen met de URL voor eindpunten **voor bijhouden van** campagne die rapportage verhinderde.
* Probleem verholpen waarbij de titel voor pushmeldingen niet kon worden weergegeven op Android-apparaten.
* Probleem verholpen waarbij de pushmelding niet op iOS-apparaten kon worden weergegeven wanneer de pushmelding alleen een titel bevatte (en niets in de hoofdtekst van het bericht).
* Probleem verholpen waarbij URL&#39;s van mediaverslagbijlagen in een te volgen levering werden geforceerd, waardoor video&#39;s en afbeeldingen niet konden worden ingesloten in de levering. Het bijhouden van URL&#39;s van het type mediaAttachmentURL wordt nu standaard gedeactiveerd voor pushberichten.

_Rapporten_

* Correctie van een probleem waarbij waarden in diagrammen en tabellen anders werden weergegeven.
* Correctie van een probleem waarbij waarden voor pushmeldingen werden weergegeven als e-mailwaarden.
* Probleem verholpen waarbij waarden onbekend werden weergegeven toen een levering buiten een campagne werd gemaakt.
* Correctie van een probleem waarbij SMS-rapportgegevens werden weergegeven als gegevens van mobiele toepassingen.

_Workflows_

* U kunt werkstroomlogboeken (tijd- en tekstzoektijd) nu filteren. For more information, refer to the [detailed documention](../../automating/using/monitoring-workflow-execution.md).
* Er is nu een optie beschikbaar in workflowleveringen om de bevestiging te deactiveren voordat deze wordt verzonden.
* Probleem verholpen waardoor u geen uitgaande overgang kon instellen in de wizard voor het maken van terugkerende leveringen.
* Probleem verholpen die optrad wanneer een activiteit van de werkschemaquery die op een gebied van het douanemiddel met een opsomming wordt gebaseerd die veel waarden had

## Release 17.5 - mei 2017 {#release-17-5---may-2017}

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
   <td> Direct mail<br /> </td> 
   <td> Doorbreek de digitale barrière en verbind met de fysieke wereld met het eerste off-line kanaal van Adobe Campaign Standard, Direct Mail. Met deze functie kunt u het bestand dat door directe-mailproviders wordt vereist, aanpassen en genereren als onderdeel van de campagnes voor meerdere kanalen. Gebruik Direct Mail om klanten opnieuw aan te trekken of om de klantervaring te verbeteren met een aansprekend aanraakpunt dat klanten naar uw app, website of winkel stuurt.<br /> Raadpleeg de <a href="../../channels/using/about-direct-mail.md">gedetailleerde documentatie</a> voor meer informatie.<br /> </td> 
  </tr> 
  <tr> 
   <td> BCC e-mailen<br /> </td> 
   <td> Met e-mail BCC kunt u unieke e-mailberichten opslaan die naar individuele ontvangers zijn verzonden, zodat het merk deze berichten kan archiveren. Door een BCC e-mailadres aan alle e-mails toe te voegen, kunnen Adobe Campaign Standard-klanten een exacte kopie van elke e-mail bewaren met deze functie. Dit is een algemene wettelijke vereiste voor de financiële dienstenindustrie en is nuttig in het helpen van de centra van de klantendienst bij het oplossen van conflicten in echt - tijd.<br /> Raadpleeg de <a href="../../sending/using/archiving.md">gedetailleerde documentatie</a> voor meer informatie.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Patches**

_Interface-updates_

* In de bovenste balk is de **[!UICONTROL Timeline]** koppeling verwijderd en vervangen door een koppeling naar **[!UICONTROL Programs & Campaigns]** .

_E-mails en SMS-berichten_

* Probleem verholpen waarbij de verkeerde kleur voor de **[!UICONTROL Retry in progress]** leveringsstatus werd weergegeven. De kleur was grijs in plaats van blauw.

_Workflows_

* Probleem verholpen dat optrad bij het wijzigen van de handeling om uit te voeren in een **[!UICONTROL Transfer file]** activiteit.

_Rapporten_

* De berekeningen **[!UICONTROL Spam]** **[!UICONTROL Spam rate]** en de indicatoren zijn gewijzigd.
* De **[!UICONTROL Bounce]** meetgegevens zijn verbeterd, zodat het resultaat nauwkeuriger is.

_Pushmeldingen_

* Probleem verholpen waarbij u niet op een pushgebeurtenis in de marketinggeschiedenis van een profiel kon klikken.
* Het gebruik van pushberichten in workflows is verbeterd.

## Release 17.4 - april 2017 {#release-17-4---april-2017}

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
   <td> Enhanced Image edition capabilities with the Creative SDK<br /> </td> 
   <td> U hebt nu toegang tot een volledige set functies die door de Creative SDK worden gevoed om uw afbeeldingen direct in de inhoudeditor te verbeteren tijdens het bewerken van e-mails of het landen van pagina's.<br /> Voor deze functie hoeft u geen extra Creative Cloud-oplossingen aan te schaffen.<br /> Raadpleeg de <a href="../../designing/using/images.md#modifying-images-with-the-adobe-creative-sdk">gedetailleerde documentatie</a> voor meer informatie.<br /> </td> 
  </tr> 
  <tr> 
   <td> Transactionele pushmeldingen<br /> </td> 
   <td> Het mobiele toepassingskanaal is toegevoegd aan de mogelijkheden voor transactiemeldingen van Adobe Campaign. Er worden nu drie kanalen ondersteund voor transactieberichten: e-mail-, SMS- en pushberichten.<br /> Raadpleeg de <a href="../../channels/using/transactional-push-notifications.md">gedetailleerde documentatie</a> voor meer informatie.<br /> </td> 
  </tr> 
  <tr> 
   <td> Pushmeldingen herstellen<br /> </td> 
   <td> U kunt terugkerende pushmeldingen nu configureren in een workflow. U kunt terugkerende pushmeldingen gebruiken in situaties waarin uw klanten periodieke updates zoals wekelijkse herinneringen verwachten om nieuwe inhoud of promoties uit te checken.<br /> Raadpleeg de <a href="../../automating/using/push-notification-delivery.md">gedetailleerde documentatie</a> voor meer informatie.<br /> </td> 
  </tr> 
  <tr> 
   <td> Amazon Simple Storage Service (S3) connector<br /> </td> 
   <td> De Amazon Simple Storage Service (S3)-connector kan nu worden gebruikt voor het importeren of exporteren van gegevens naar Adobe Campaign. Deze kan worden ingesteld in een workflowactiviteit. De configuratie wordt uitgevoerd in een externe account.<br /> Raadpleeg de <a href="../../administration/using/external-accounts.md">gedetailleerde documentatie</a> voor meer informatie.<br /> </td> 
  </tr> 
  <tr> 
   <td> Dreamweaver-integratie live<br /> </td> 
   <td> De integratie tussen Adobe Campaign en Dreamweaver is nu live. Het werkt nu met de officiële laatst vrijgegeven versie van Dreamweaver (17.0.2).<br /> Hiervoor is de installatie van de Adobe Campaign Integration-extensie vanaf hier vereist: <a href="https://adobe.ly/acdw_addon">https://adobe.ly/acdw_addon</a><br /> Raadpleeg deze <a href="https://docs.adobe.com/content/help/nl-NL/campaign-standard-learn/tutorials/designing-content/email-designer/dreamweaver-integration.html">video</a>voor meer informatie.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Patches**

_Platform_

* Probleem met geheugenverbruik verholpen.

_E-mails en SMS-berichten_

* Probleem verholpen waarbij de inhoud niet correct kon worden gesynchroniseerd met de meest recente wijzigingen tijdens de voorvertoning van een bericht.
* Probleem verholpen waarbij het maken of verwijderen van een MX- of Domain-regel voor e-mailverwerking werd voorkomen.
* Probleem opgelost waarbij e-mailberichten met meerdere aliassen niet konden worden verzonden.
* Probleem verholpen waarbij het voorkomen was dat leveringslogboeken voor overvulling werden weergegeven in de verzendende logboeken van de levering.
* Probleem verholpen dat tot een fout leidde bij de weergave van bijgehouden URL&#39;s van een levering zonder URL in de inhoud.
* Probleem verholpen waarbij de groottekenmerken van een afbeelding niet correct werden toegepast in het verzonden bericht.

_Transactionele berichten_

* Het veld rtEventHistoId wordt niet meer weergegeven als een personalisatieveld in een transactiemalplaatje.

_Landingspagina’s_

* We hebben het **[!UICONTROL by email]** filter dat wordt gebruikt bij het openen van pagina&#39;s geoptimaliseerd om nieuwe abonnees te combineren met databaseprofielen.
* Probleem verholpen waarbij bij het gebruik van Booleaanse velden in een formulierconfiguratie vrije tekstinvoer in plaats van selectievakjes werd weergegeven.
* Probleem verholpen waardoor geen miniaturen op de openingspagina konden worden gegenereerd.

_Workflows_

* Oplossing voor een weergavefout tijdens het bewerken van een **[!UICONTROL End]** of **[!UICONTROL External Signal]** activiteit (alleen in Safari).
* Het weergegeven foutbericht is verbeterd tijdens het bewerken van een **[!UICONTROL Read Audience]** activiteit met een onjuist publiek.
* Probleem verholpen die tot een SQL-fout kan leiden bij het uitvoeren van een abonnement.

_Integraties_

* Gegevens over punten van belang: heeft een fout gecorrigeerd die optrad bij het tellen van abonnees van locaties.

_Soorten publiek en vragen_

* Probleem verholpen waarbij som en gemiddelde aggregaten niet konden worden gebruikt voor een verzameling in de queryeditor.
* Probleem verholpen waardoor de query-editor niet opnieuw kon worden geladen nadat de bron van het filter was gewijzigd.

_Rapporten_

* Probleem verholpen waarbij Open rate metriek niet correct berekend kon worden wanneer het selecteren van veelvoudige rijen in een lijst.
* Probleem verholpen waarbij alleen meetgegevens als gehele getallen werden weergegeven. Metrische gegevens kunnen nu met decimalen worden weergegeven.

_Pushmeldingen_

* Probleem verholpen waarbij geen foutbericht werd weergegeven bij het maken van een Android-toepassing die gekoppeld was aan een mobiele app die niet op MCPNS was gemaakt.
* Probleem verholpen waarbij een gebruiker geluiden kon toevoegen aan een stille melding.

## Release 17.2 - maart 2017 {#release-17-2---march-2017}

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
   <td> Dynamische rapportage<br /> </td> 
   <td> De dynamische Rapportering verstrekt een nieuwe generatie volledig klantgerichte en bedrijfsrapporten in real time. Met deze functie, die is gebaseerd op visuele dynamische draaitabellen en afbeeldingen, kunt u variabelen en dimensies slepen en neerzetten om de efficiëntie en effectiviteit van uw marketingcampagnes te analyseren. Dynamische rapportering stelt u ook in staat om uw eigen bedrijfsrapporten helemaal zelf te maken en deze op te slaan voor later gebruik.<br /> Raadpleeg de <a href="../../reporting/using/about-dynamic-reports.md">gedetailleerde documentatie</a> voor meer informatie.<br /> </td> 
  </tr> 
  <tr> 
   <td> Dreamweaver-integratie (Labs)<br /> </td> 
   <td> Dankzij de integratie met Adobe Campaign en Dreamweaver hebt u nu een geïntegreerd proces voor het maken van e-mailcampagnes met Adobe-oplossingen.<br /> U kunt Adobe Campaign-e-mailberichten bewerken in Dreamweaver en de inhoud naadloos laten synchroniseren tussen beide oplossingen.<br /> Voor de eerste release is de integratie beschikbaar als een 'Labs'-functie en werkt deze alleen met Dreamweaver Pre Release Beta. Neem contact op met AC-DW-integration@adobe.com als u dit wilt activeren.<br /> Raadpleeg deze <a href="https://docs.adobe.com/content/help/nl-NL/campaign-standard-learn/tutorials/designing-content/email-designer/dreamweaver-integration.html">video</a>voor meer informatie.<br /> </td> 
  </tr> 
  <tr> 
   <td> Manual send time optimization<br /> </td> 
   <td> U kunt nu handmatig een aangepaste verzendtijd per ontvanger definiëren - op leveringsniveau of met behulp van een workflow. <br /> Er zijn twee nieuwe opties beschikbaar: <br /> 
    <ul> 
     <li> Alle ontvangers ontvangen het bericht met hun tijdzone in rekening gebracht. </li> 
     <li> Elke ontvanger ontvangt het bericht op een gegevens verwerkte datum en tijd die door een formule wordt bepaald. </li> 
    </ul> Raadpleeg de <a href="../../sending/using/optimizing-the-sending-time.md">gedetailleerde documentatie</a> voor meer informatie.<br /> </td> 
  </tr> 
  <tr> 
   <td> Nieuwe mogelijkheden voor pushmeldingen<br /> </td> 
   <td> Het pushmeldingskanaal is uitgebreid met verschillende nieuwe mogelijkheden:<br /> 
    <ul> 
     <li> Nieuwe ontwerpinterface </li> 
     <li> Stil meldingen </li> 
     <li> Interactieve push </li> 
     <li> Ondersteuning voor rijke inhoud </li> 
     <li> calculator voor downloadgrootte </li> 
    </ul> Raadpleeg de <a href="../../channels/using/about-push-notifications.md">gedetailleerde documentatie</a> voor meer informatie.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: nieuwe signaalactiviteit<br /> </td> 
   <td> Trigger een werkschema van een andere werkschema gebruikend de nieuwe activiteit van het <span class="uicontrol">Signaal</span> .<br /> Met de capaciteit om één werkschema van een andere te beginnen, kunt u complexere klantenreizen nu steunen. U kunt de reizen van de klant beter controleren en reageren voor het geval er problemen zijn.<br /> Verschillende workflowactiviteiten zijn bijgewerkt:<br /> 
    <ul> 
     <li> <span class="uicontrol">Eindactiviteit</span> : op een nieuw tabblad kunt u een workflow opgeven die wordt geactiveerd nadat deze activiteit is uitgevoerd. </li> 
     <li> <span class="uicontrol">Gegevensactiviteit</span> bijwerken: gebruik de nieuwe lege uitgaande overgang om een activiteit van het <strong>Eind</strong> toe te voegen die een andere werkschema teweegbrengt. Lege uitgaande overgangen bevatten geen gegevens en nemen geen overbodige ruimte in het systeem in beslag </li> 
    </ul> Raadpleeg de <a href="../../automating/using/external-signal.md">gedetailleerde documentatie</a> voor meer informatie.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: nieuwe activiteit voor publiek lezen<br /> </td> 
   <td> Start uw doelproces met een bestaand publiek dat u eenvoudig kunt selecteren en verfijnen in één activiteit.<br /> Raadpleeg de <a href="../../automating/using/read-audience.md">gedetailleerde documentatie</a> voor meer informatie.<br /> </td> 
  </tr> 
  <tr> 
   <td> Gegevens over punten van belangstelling<br /> </td> 
   <td> Punten van interessegegevens integreren Adobe Campaign met Adobe Analytics for Mobile. Een merk kan gegevens verzamelen van de mobiele locaties van gebruikers - de zogenaamde <strong>punten van interesse</strong> - wanneer gebruikers de app van het merk openen. Hierdoor kan het merk Adobe Campaign-workflows gebruiken om persoonlijke berichten te verzenden op basis van de locatie van de gebruiker. Dit kanaal gebruikt SDK van de Mobiele kerndienst.<br /> Voor deze functie is Analytics for Mobile vereist. Dit is een betaalde oplossing.<br /> Raadpleeg de <a href="../../integrating/using/about-campaign-points-of-interest-data-integration.md">gedetailleerde documentatie</a> voor meer informatie.<br /> </td> 
  </tr> 
  <tr> 
   <td> REST API's<br /> </td> 
   <td> Bronnen die op elk niveau zijn gekoppeld aan de profielen of services, zijn nu beschikbaar in de API.<br /> Raadpleeg de <a href="../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension">gedetailleerde documentatie</a> voor meer informatie.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Patches**

_Algemeen_

* Het is nu mogelijk om profielgegevens toe te voegen wanneer het uitvoeren van leveringslogboeken.

_E-mails en SMS-berichten_

* Probleem verholpen waarbij de **[!UICONTROL Request confirmation before sending messages]** optie geselecteerd bleef, zelfs nadat deze was uitgeschakeld en de levering was opgeslagen.
* Probleem verholpen waarbij het verwijderen van e-mailberichten over transacties kon worden voorkomen.
* Probleem verholpen waarbij de inhoud niet correct kon worden gesynchroniseerd met de laatste wijzigingen voordat een voorvertoning van een levering werd weergegeven.

_Landingspagina’s_

* Probleem verholpen waarbij een gebruiker niet kon bewerken door in de inhoud van een openingspagina te klikken.

_Workflows_

* Probleem verholpen waarbij de inhoud van de verworpen overgang van een **[!UICONTROL Load file]** activiteit niet kon worden gelezen.
* Probleem verholpen waarbij werd voorkomen dat verwisselde kolommen correct in aanmerking werden genomen bij het configureren van een **[!UICONTROL Load file]** activiteit.

## Release 17.1 - januari 2017 {#release-17-1---january-2017}

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
   <td> Logexport voor externe rapportage<br /> </td> 
   <td> Logboeken exporteren, zoals bezorgings- en trackinglogboeken, om deze te verwerken in de rapportage- of BI-gereedschappen van uw voorkeur. U kunt eenvoudige werkschema's met stijgende vragen gebruiken om regelmatige uitvoer van nieuwe logboeken te automatiseren.<br /> Naast de beschikbaarheid van de logboekmiddelen van de middelplukker, werden verhogingen aangebracht aan de <a href="../../automating/using/incremental-query.md">Incrementele vraag</a> en de activiteiten van het <a href="../../automating/using/extract-file.md">Extraheren dossier</a> :<br /> 
    <ul> 
     <li> <span class="uicontrol">Met incrementele query</span> kunt u nu een datumveld gebruiken om nieuwe of bijgewerkte gegevens op te halen. Eerder werden alle resultaten van eerdere executies automatisch uitgesloten, zelfs als deze werden bijgewerkt sinds de laatste executie. </li> 
     <li> <span class="uicontrol">Met Extraheren kunt u nu labels exporteren voor opsommingswaarden in plaats van id's.</span> </li> 
    </ul> Deze activiteiten zijn beschikbaar voor beheerders met toegang tot alle geo- en org-eenheden.<br /> Raadpleeg de <a href="../../automating/using/exporting-logs.md">gedetailleerde documentatie</a>voor meer informatie over het exporteren van logbestanden.<br /> </td> 
  </tr> 
  <tr> 
   <td> Marketingmogelijkheden voor transactieberichten<br /> </td> 
   <td> Marktdeelnemers kunnen nu transactieberichten verzenden op basis van marketingprofielen van klanten. Hierdoor kunnen zij:<br /> 
    <ul> 
     <li> Pas marketingtypologische regels toe, zoals <span class="uicontrol">Adres op lijst van afgewezen personen</span> . </li> 
     <li> De koppeling voor het opzeggen van abonnementen in de berichten opnemen. </li> 
     <li> De transactionele berichten aan de globale leveringsrapportage toevoegen. </li> 
     <li> De transactionele berichten in het klanttraject gebruiken. </li> 
    </ul> Raadpleeg de <a href="../../channels/using/profile-transactional-messages.md">gedetailleerde documentatie</a> voor meer informatie.<br /> </td> 
  </tr> 
  <tr> 
   <td> Transactieberichten-API<br /> </td> 
   <td> De API voor transactief berichtenverkeer is nu beschikbaar via <a href="https://docs.campaign.adobe.com/doc/standard/en/adobeio.html">adobe.io</a>, zodat u deze eenvoudiger kunt gebruiken en controleren:<br /> 
    <ul> 
     <li> U kunt profiteren van de rapportage- en monitoringfuncties van het platform adobe.io. </li> 
     <li> De verificatie wordt nu uitgevoerd met de op adobe.io-token gebaseerde verificatie in plaats van IP-toevoegende op lijst van gewenste personen, waardoor het beveiligingsproces eenvoudiger wordt. </li> 
     <li> Alle API's zijn nu geïntegreerd op één platform, waardoor het eenvoudiger dan ooit is om transactionele communicatiemogelijkheden toe te voegen aan uw integratie als u de profiel- en services-API al ondersteunt. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

**Patches**

_Algemeen_

* De **[!UICONTROL Access authorization]** opties zijn geretourneerd naar de eigenschappen van de bestemmingspagina.
* Probleem verholpen waarbij mogelijk een oude afbeelding werd gerenderd in plaats van de juiste afbeelding. Dit gebeurde als het bronbeeld in de inhoudsdefinitie van een levering of een landingspagina was bijgewerkt.
* Probleem verholpen waardoor gebruikers bepaalde velden in een bestaande SFTP externe account niet konden bewerken.
* Verschillende problemen met de gebruikersinterface zijn opgelost. Gebruikers kunnen nu bijvoorbeeld profielkenmerken bewerken en wijzigingen opslaan zonder problemen met de gebruikersinterface.

_E-mails en SMS-berichten_

* Probleem verholpen met betrekking tot leveringssjablonen met HTML-inhoud die een

_Pushmeldingen_

* Probleem verholpen waarbij het terugsturen van een toepassing naar de Adobe Campaign-server mogelijk is voorkomen.
* Probleem verholpen dat mogelijk voorkwam **[!UICONTROL Play a sound]** **[!UICONTROL Custom fields]** en waarmee rekening moest worden gehouden voor Android.
* Probleem verholpen waarbij een extra escapeteken zijn toegevoegd aan Unicode-tekens die voor Emojis worden gebruikt.
* Wanneer de registratietoken van een abonnee aan de lijst van afgewezen personen wordt toegevoegd, wordt de overeenkomstige status nu onmiddellijk bijgewerkt in de lijst van abonnees van de toepassing in Adobe Campaign.

_Workflows_

* Probleem verholpen waarbij voorvertoningen van query&#39;s over gebeurtenisbronnen mogelijk zijn voorkomen (bijvoorbeeld rtEvent).
* Het bestand dat door een **[!UICONTROL Load file]** activiteit wordt gegenereerd, kan nu in de uitgaande overgang worden opgehaald en in de volgende activiteit worden verwerkt. Upload bijvoorbeeld het afwijzende bestand via een SFTP-server met **[!UICONTROL Transfer file]** .
* Probleem verholpen waardoor een gebruiker de populatie van een segment mogelijk niet kon beperken als dit op het **[!UICONTROL Temporary resource]** tabblad **[!UICONTROL General]** **[!UICONTROL Segmentation]** was geselecteerd.
* **[!UICONTROL Scheduler]** activiteiten kunnen niet meer worden ingesteld om een workflow meer dan eenmaal per 10 minuten te activeren.
* Probleem verholpen waarbij het werken **[!UICONTROL Use common columns]** van een **[!UICONTROL Union]** activiteit mogelijk niet goed ging.

_Integraties_

* Probleem verholpen dat een fout kan veroorzaken bij het implementeren van een gebeurtenistrigger in Adobe Campaign. Deze fout trad op wanneer de metagegevens &quot;Waarschijnlijkheid om in 30 dagen terug te keren&quot; waren toegevoegd aan de trigger voor afschrijving in Adobe Marketing Cloud.
* Probleem verholpen waardoor het veld Doel Dimension tijdens het importeren van soorten publiek uit de kernservice van Personen mogelijk werd gewist door de technische workflow. De volgende vragen konden niet het ingevoerde publiek terugwinnen.
* Probleem verholpen waarbij de **[!UICONTROL Save audience]** activiteit van een workflow mogelijk mislukte wanneer de optie **[!UICONTROL Share in Adobe Marketing Cloud]** werd ingeschakeld.

