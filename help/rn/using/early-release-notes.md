---
solution: Campaign Standard
product: campaign
title: Opmerkingen bij de eerste release
description: Opmerkingen bij de eerste release
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
hide: true
hidefromtoc: true
translation-type: tm+mt
source-git-commit: c5807da6bc9a33adcba6fc9825b0496bb5dc609b
workflow-type: tm+mt
source-wordcount: '2587'
ht-degree: 3%

---


# Opmerkingen bij de eerste release {#new-release}

[Release-planning](../../rn/using/release-planning.md) |  [Configuratiescherm](https://docs.adobe.com/content/help/nl-NL/control-panel/using/release-notes.html) |  [Documentatie-updates](../../rn/using/documentation-updates.md) |  [Nieuwste releaseopmerkingen](../../rn/using/release-notes.md) |  [Verouderde functies](../../rn/using/deprecated-features.md)

Op deze pagina worden nieuwe functies, verbeteringen en oplossingen beschreven die in de volgende release van Campaign Standard zijn opgenomen.

>[!CAUTION]
>
> Deze inhoud kan zonder voorafgaande kennisgeving worden gewijzigd tot de upgradedatum van de werkgebiedomgevingen. Meer informatie vindt u op de [releaseplanningspagina](../../rn/using/release-planning.md).


## Release 21.1 - februari 2021 {#release-21-1---febuary-2021}

**Nieuwe functies**

<table> 
<thead> 
<tr> 
<th> <strong>E-mailfeedbackservice</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>De E-mailfeedbackservice (EFS) is een schaalbare service die de rapportnauwkeurigheid verbetert door de e-mailfeedback rechtstreeks van de Enhanced MTA vast te leggen.</p>
<ul>
<li>Alle categorieën gebeurtenissen worden vastgelegd: Vertragingen, afgeleverd, te verzenden, af te schrijven (Verbinding, Lijst), Terugkoppeling (Spam- klachten, asynchrone gebeurtenissen).</li>
<li>De berekening van de verzonden/geleverde indicatoren is nu gebaseerd op real-time feedback van de verbeterde MTA voor verbeterde nauwkeurigheid en reactiviteit.</li>
<li>EFS lost het probleem van synchrone grenzen meldend vertragingen op en neemt 80% van lading van het inMail proces weg.</li>
</ul>
<p>Deze mogelijkheid wordt vrijgegeven als een <strong>persoonlijke bèta</strong> en zal in toekomstige versies geleidelijk beschikbaar zijn voor alle klanten.</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>Verbeteringen in Adobe Experience Manager-integratie</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>De integratie van de campagne met Adobe Experience Manager is verbeterd: u kunt meertalige inhoud nu gemakkelijker importeren vanuit Adobe Experience Manager. <p>
<p>Adobe Campaign Standard detecteert nu automatisch taalvarianten van Adobe Experience Manager-inhoud en maakt het mogelijk om grote varianten te importeren en te maken. Hierdoor wordt het aantal stappen vereenvoudigd dat een arts moet doorlopen om een meertalige campagne te maken op basis van Adobe Experience Manager-inhoud.</p>
</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>Unified Experience Cloud Interface</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>De kopbalbar van Adobe Campaign is veranderd om uw ervaring over alle producten en de diensten van de Experience Cloud te verenigen en te verbeteren. Deze wijzigingen zijn ontworpen om uw leven eenvoudiger te maken, zoals:</p>
<ul>
<li>Eenvoudiger overschakelen tussen uw organisaties of op een andere toepassing.</li>
<li>Verbeterde gebruikershulp - De Experience League in het product opnemen, de zoekresultaten omvatten ook resultaten van communityforums en meer video-inhoud, zodat u gemakkelijker toegang hebt tot meer inhoud om optimaal te profiteren van de toepassing. We hebben ook een feedbackmechanisme toegevoegd in het menu Help, waardoor het gemakkelijker wordt om problemen te melden of uw ideeën te delen.</li>
<li>Verbeterde meldingen - De vervolgkeuzelijst Meldingen bevat nu twee tabbladen: één voor uw eigen productberichten, en één voor meer globale productaankondigingen.</li>
</ul>
</td> 
</tr> 
</tbody> 
</table>

**Verbeteringen**

* **De** integratie van de Dynamica 365 van Microsoft is verbeterd met een specifieke zelfbedienings integratieapp en een verbeterd implementatieproces. [Meer informatie](../../integrating/using/d365-acs-get-started.md)

* Er is een verbetering aangebracht om het oplossen van problemen bij het oplossen van problemen met het **Transactioneel overseinenproces** te vergemakkelijken. De technische beheerders van Adobe kunnen het vinden op om het even welk proces nu gebruiken zonder het opnieuw te beginnen.

* Met de lijst **Profielen** kunt u nu zoeken naar records die op een van deze velden zijn gebaseerd: e-mail, voornaam, achternaam of aangepaste velden die zijn toegevoegd bij geavanceerd filteren tijdens het uitbreiden van de profielbron. Deze functie is ook beschikbaar in Campaign Standard API&#39;s die de parameter filterType gebruiken.

* Een parameter is aangepast aan het aantal containers die **Transactioneel overseinen** gegevensbestand het groeperen proces in werking stellen. Hierdoor kan de belasting gelijkmatig over alle gebruikte containers worden verdeeld en worden de optimale prestaties bereikt.

* Een nieuwe functie **GetOption** is nu beschikbaar in activiteiten die gebeurtenisvariabelen gebruiken na het roepen van een werkschema met externe parameters. Hiermee kunt u de waarde van een opgegeven functie retourneren.

* Met een nieuwe optie kan Campaign Standard tot **fysieke geheugen** op uw systeem controleren voordat een workflow wordt gestart. Als de hoeveelheid geheugen te laag is, wordt de uitvoering van de workflow uitgesteld totdat het systeemgeheugen deze drempel bereikt. Dit voorkomt verdere verslechtering van de prestaties en beperkt het risico van een stroomstoring. De workflow wordt automatisch hervat zodra het laden op de server is mislukt en het geheugen is vergroot. Deze optie is alleen-lezen en kan niet worden gewijzigd.


**Overige wijzigingen**

* Er is een fout gewijzigd in een waarschuwing tijdens de voorbereiding van berichten wanneer de limiet van 100 downloaduren van inhoud per roluur is bereikt. Er wordt nu een waarschuwing weergegeven wanneer de limiet is bereikt, zodat u verder kunt gaan met de levering.

* Wanneer het verrijken van een inhoud van een transactiebericht, worden de verbindingen niet meer teruggewonnen wanneer het halen van gegevens van de lijst van het Profiel, die latentie tijdens berichtvoorbereiding vermindert en lege profielgegevens vermijdt toe te schrijven aan een onjuiste verhouding die met de profiellijst wordt bepaald.

* De technische configuratie van de instantie is geoptimaliseerd om stabiliteit te verzekeren. (CAMP-45681)

* Sessiebeheer is verbeterd om geheugen te optimaliseren. (CAMP-45901, CAMP-46767)

* De activiteit **Transfer file** produceert nu een extra variabele (filesCount) die het aantal geüploade of gedownloade dossiers bevat. (CAMP-45842)

* De **sms-connector** kan nu meerdere optionele parameters verzenden met elk bericht.

* Gebruikers met de rol DATAMODEL kunnen nu extensies voor het leveringslogboek publiceren. (CAMP-46604)

* Het foutbericht dat werd weergegeven toen u een resource probeerde te publiceren die een aangepaste bron had die niet meer bestaat, is duidelijker geworden. (CAMP-46893)

* De volgende talen zijn toegevoegd aan de lijst **Voorkeurstaal**: Indonesisch - Indonesië (in-id), Engels - Zweden (en-se), Engels - Azië Pacific (en-ap), Engels - Japan (en-jp), Spaans - Latijns-Amerika (es-la). (CAMP-46351)

* De kiezer voor het selecteren van profielen tijdens het testen van een bestemmingspagina gebruikt nu de ProfileBase-bron in plaats van het profiel om time-out te voorkomen.

* De indeling van het SMPP-logbestand is verbeterd.

* Optionele parameters voor cryptString- en decryptString JS-functies zijn toegevoegd aan Adobe Campaign Classic API&#39;s.

* Verbeterde waarschuwings- of foutberichten in leveringsvoorbereidingslogboeken.

* Verbeterde foutlogboeken bij poging verbinding te maken met Adobe Identity Management Service (IMS).

* U kunt de afmetingen van de Aflevering en van de Campagne nu verder filtreren gebruikend de onderzoeksbar in **Dynamische rapportering**.

* De transactionele datum van de berichtgeldigheid van SMS kan nu door de waarde worden bepaald die voor de vervalparameter in **Transactionele Berichten API** wordt geplaatst. (CAMP-36600)

* In Dynamische rapportering, toonde het **Overzicht van de Levering** ingebouwde rapport onjuiste gegevens voor de unsubscribed tarief metrisch. Er is een nieuwe metrische waarde met de naam **Unique unsubscription** toegevoegd om dit te herstellen. (CAMP-46445)

**Patches**

* Probleem verholpen waarbij leveringen zeer traag verliepen als gevolg van bepaalde processen. Dit is te wijten aan onjuiste eenheden die zijn gedefinieerd voor verschillende parameters (bijvoorbeeld milliseconden in plaats van seconden).
* Probleem verholpen in workflows die konden optreden wanneer een **deduplicatie**-activiteit die eenmaal was uitgevoerd, werd gekopieerd en waarbij een tijdelijke bron werd gebruikt. Nadat de bron van de activiteit is gedupliceerd, wordt deze automatisch ingesteld op leeg, wat leidt tot problemen in andere activiteiten van de workflow. Nadat de bron van de activiteit is geplakt, blijft de bron van de activiteit nu gelijk, zodat de fout zo snel mogelijk en niet later in de workflow wordt geactiveerd. (CAMP-46903)
* Probleem verholpen waarbij de Mobile SDK een open traceringsverzoek heeft verzonden op basis van de voorwaarde dat deliveryID/MessageID niet null is. Dit zou resulteren in 404 fouten voor leveringen met tracking uitgeschakeld. Een extra variabele (acsDeliveryTracking) met informatie over het volgen status van de levering wordt nu verzonden in de lading. Deze variabele kan twee waarden in- of uitschakelen, afhankelijk van de status voor het bijhouden van de set.
* Probleem verholpen waardoor leveringsrapporten niet konden worden uitgevoerd wanneer 5000 rijen werden weergegeven.
* Probleem verholpen met A/B-tests waarbij de inhoud van variant B niet kon worden bijgewerkt nadat de leveringstemplate was gewijzigd. (CAMP-45235)
* Oplossing van een kwestie die het Transactionele overseinenproces veroorzaakte vast te komen, verhinderend berichten worden verzonden.
* Probleem opgelost waarbij de leveringsanalyse mislukte bij het verzenden van een transactioneel pushbericht met de profieldoeldimensie. Er is nu een nieuwe leveringstoewijzing (mapRtEventAppSubRcp) beschikbaar voor transactionele pushberichten die op profielen zijn getarget. De leverings-, uitsluitings- en trackinglogboeken voor deze leveringen zijn nu beschikbaar in de broadLogAppSubRcp-, excludeLogAppSubRcp- en trackingLogAppSubRcp-tabellen.
* Probleem verholpen dat tot navigatieproblemen kan leiden nadat op een interne koppeling is geklikt (bijvoorbeeld wanneer de bovenliggende levering wordt geopend via een overzichtsscherm met proefdrukken).
* Probleem verholpen waarbij alle beschikbare sjablonen voor inhoud van de Experience Manager niet konden worden weergegeven bij het maken van een levering. (CAMP-45990)
* Probleem verholpen in workflows die kunnen voorkomen dat foutberichten worden weergegeven in de leveringslogboeken nadat de kolom **Reden** aan het tabblad Extra gegevens is toegevoegd. (CAMP-45139)
* Probleem verholpen die zich kon voordoen wanneer twee aanroepen met een app-abonnement dezelfde Marketing Cloud-id hadden (&#39;dubbele sleutelwaarde schendt unieke beperkingsfout&#39;).
* Probleem verholpen dat trage problemen zou kunnen veroorzaken wanneer activiteiten naar een werkstroom worden gesleept die een grote hoeveelheid **Query** en **Leespubliek** activiteiten bevat. (CAMP-44511)
* Oplossing voor een fout die aan het einde van de voorbereiding van het transactiebericht zou kunnen optreden, zodat gegevens voor omleiding niet naar de trackingservers kunnen worden geüpload.
* Probleem verholpen waarbij foutberichten konden worden weergegeven wanneer werd geprobeerd importsjablonen of eerdere importtaken te openen nadat de werkstroombron was aangepast. (CAMP-46183)
* Probleem verholpen waardoor een **Leespubliek** activiteit niet kon worden uitgevoerd als deze was geconfigureerd met een dynamische publieksnaam. (CAMP-46047)
* Probleem verholpen waardoor de knop **Lijst exporteren** niet kon worden weergegeven
* Probleem verholpen dat tot het mislukken van de **Workflow voor het rapporteren van aggregaten** zou kunnen leiden. (CAMP-45979)
* Probleem verholpen bij het maken van een aangepaste bron met een aangepaste samengestelde sleutel (dynamische inhoud voor tekst/datum).
* Probleem verholpen waarbij gegevens over queryovergangen niet konden worden weergegeven. (CAMP-45669)
* Problemen met het geheugenverbruik met betrekking tot publicatie van aangepaste bronnen opgelost.
* Probleem verholpen die optrad tijdens het configureren van een levering die op een bepaalde datum moet worden verzonden. Indien de levering onmiddellijk na bevestiging werd verzonden, is de bereiding van de levering mislukt en is de oorspronkelijk vastgestelde datum nog steeds in aanmerking genomen. (CAMP-44107)
* Probleem verholpen waardoor transactiesjablonen niet konden worden geopend. (CAMP-47181)
* Probleem verholpen tijdens het publicatieproces van transactionele berichten die tot dubbele typologieën en typologische regels met namen die de toegestane tekenreeksgrootte overschrijden, konden leiden. (CAMP-47104)
* Probleem verholpen in de activiteit **External API** die optrad wanneer een invoerparameter een record retourneerde die niet bestond. (CAMP-47023)
* Probleem verholpen waardoor de SMPP-aansluiting niet opnieuw kan worden aangesloten.
* Probleem verholpen die optrad in de **Bestandsoverdracht** activiteit tijdens het downloaden van een bestand dat een punt in de naam bevatte. De tekens na de punt werden beschouwd als de bestandsextensie. (CAMP-46624)
* Oplossing een kwestie die gegevensbestand het groeperen van werd uitgevoerd verhinderde, die transactionele berichten om in de routerrij veroorzaakte te worden geplakt.
* Correctie van een fout waardoor de geannuleerde leveringslogs niet konden worden verzonden.
* Probleem verholpen waarbij een workflow zou kunnen mislukken bij gebruik van een **AND-join**-activiteit. De activiteit veranderde automatisch de Primaire reeks aan de laatste overgang die aan het wordt getelegrafeerd, zelfs als het de eerste getelegrafeerde overgang visueel toonde. (CAMP-46900)
* Probleem verholpen waarbij adressen die correct in quarantaine zijn geplaatst onjuist op Geldig werden ingesteld, waardoor ze uit quarantaine werden verwijderd.
* Probleem verholpen waardoor gepersonaliseerde velden niet konden worden weergegeven als ze speciale tekens bevatten. (CAMP-46805)
* Probleem verholpen waarbij een specifieke gedetailleerde weergave voor een profiel niet kon worden weergegeven. Dit kwam voor als de profielbron met douanevelden met **Add een gepersonaliseerde toegelaten gebiedssectie** optie was uitgebreid.
* Probleem verholpen waarbij een foutcode 500 kon worden geretourneerd bij het verzenden van transactiegebeurtenissen. (CAMP-46811)
* Probleem verholpen waardoor u geen geplande e-mailrapporten meer kunt ontvangen. (CAMP-46891)
* Probleem verholpen die optrad wanneer een douanemiddel aan het profielmiddel met een 1 kardinaliteit eenvoudige verbinding werd verbonden. Wanneer u een profiel opent met het veld Aangepaste bron leeg, wordt nu een foutbericht weergegeven in plaats van een lege lijst.
* Probleem verholpen bij het gebruik van profielvervanging in een werkstroom waarbij de pagina de leveringsprofielen niet kon laden bij het selecteren van het te vervangen profiel. (CAMP-46522)
* Oplossing voor een regressie waarbij de technische workflow **Database Cleanup** probeerde verlopen werktabellen voor levering te laten vallen met als gevolg de volgende fouten: (CAMP-46536)

```
   PGS-220000 PostgreSQL error: ERROR: table ""wkdlv_24439460_data"" does not exist and WDB-200001 SQL statement 'DROP TABLE wkdlv_24448131_data' could not be executed.
```

* Oplossing voor de volgende fout die in sommige gevallen optrad bij het gebruik van een aangepast filter op aangepaste bronnen: (CAMP-46509)

```
   The 'profile/xxxx' field used in the filter 'xxxxx' does not exist in custom resource 'xxx'
```

* Probleem verholpen waarbij het voorbereiden van pushmeldingen te veel tijd in beslag nam om te worden voltooid. Dit werd veroorzaakt door een ontbrekende index op de tijdelijke werktabellen.
* Oplossing voor een fout die kan optreden wanneer de optie **Dimension wordt gebruikt om de combinatie van** in een **Afstemming**-activiteit in een werkstroom tot stand te brengen als er al een relatie is gedefinieerd tussen een aangepaste bron en een profielbron.
* Oplossing voor een probleem dat optrad bij het toevoegen van koppelingen via een **Afstemming** of **Verrijking**-activiteit. Gekozen koppelingen werden niet weergegeven in de uitvoerovergang.
* Probleem verholpen bij het gebruik van een **Segmentatie**-activiteit met terugkerende leveringen in een workflow die ertoe heeft geleid dat de levering naar het verkeerde publiek werd verzonden. (CAMP-46275, CAMP-46470)
* Probleem verholpen waarbij publicatie van aangepaste bronnen is mislukt tijdens het uitbreiden van de profielbron om aangepaste profielafmetingen voor dynamische rapportage te maken. (CAMP-46266)
* Oplossing voor een fout die optrad bij het toevoegen van een koppeling naar een tabel voor het importeren van bestanden. Na het toevoegen van **Verrijking** activiteit aan **de invoer van het Dossier** activiteit, de eerder gevormde verbinding verdween. (CAMP-46557)
* Probleem verholpen bij het gebruik van aangepaste bronnen gekoppeld aan profielgegevens waarbij de weergavevolgorde in het detailconfiguratiescherm tijdens het opslaan werd gewijzigd. (CAMP-46312)
* Probleem verholpen waarbij gegevens niet konden worden weergegeven in dynamische rapportage als gevolg van leveringen op basis van een aangepaste leveringstoewijzing.
* Probleem verholpen waardoor u een verzameling met een onjuist brondoel niet kon selecteren in een workflowqueryactiviteit.
* Probleem verholpen waarbij harde tegenstellingen onjuist konden worden gevalideerd tijdens het InMail-proces.
* Oplossing voor een fout die optrad bij het openen van een profielscherm als gevolg van een koppelingsfout.
* Probleem verholpen waarbij GDPR-gegevens niet konden worden verwijderd uit de opschoningsworkflow.
* Oplossing voor een fout die optrad wanneer de planningsconfiguratie handmatig met het type toetsenbord werd bijgewerkt in de parameters van het e-mailleveringsschema.
* Probleem verholpen waardoor u een profiel niet kon bewerken vanwege onjuiste parameters in de Organizer-eenheid.
* Probleem verholpen waarbij het veld Service extension leeg en onmogelijk in de e-maileigenschappen kon worden ingesteld, zelfs als dit in de leveringssjabloon was ingesteld.
* Probleem verholpen waarbij proefdrukken langer duren om te worden verwerkt. (CAMP-45048)
* Probleem verholpen waarbij u kolommen niet kon sorteren in een profieloverzichtsscherm.
* Probleem verholpen waarbij een miniatuur werd gegenereerd dat in Azure kon voorkomen in e-mailvarianten met Chinese tekens. (CAMP-47152)
* Oplossing voor een regressie die in 20.4 werd geïntroduceerd en die tot onjuiste open tarieven voor Gmail wegens het filtreren van het volgen van gebeurtenissen kon leiden die van Gmail- rekeningen werden ontvangen. (CAMP-46504)
* Probleem verholpen waarbij HTML-inhoud niet kon worden geïmporteerd in een transactiemalplaatje voor berichten. (CAMP-47318)
* Probleem verholpen waarbij de weergave van de renderingen in het e-mailrenderrapport trager kon worden. (CAMP-46226)
* Probleem verholpen waardoor u geen aangepaste bronnen kon publiceren die zijn geconfigureerd met een List-type element in de schermdefinitie. (CAMP-47217)
* Probleem verholpen in de e-mailontwerper die ervoor zorgde dat regelscheidingen niet correct konden worden weergegeven in Microsoft Outlook wanneer ze boven aan de e-mailinhoud werden geplaatst. (CAMP-46294)
* Probleem opgelost waarbij de KPI&#39;s-combinatie met de technische workflow van Adobe Analytics vastliep. (CAMP-46576)
* Probleem verholpen in de e-mailontwerper dat ervoor zorgde dat fragmenten niet automatisch werden weergegeven in zoekvakken wanneer inhoudsblokken werden ingevoegd. (CAMP-44205)
* Probleem verholpen in de e-mailontwerper dat ertoe leidde dat ongewenste tekens in verzonden e-mailberichten werden weergegeven wanneer emojis in fragmenten werd gebruikt. (CAMP-46621)
* Correctie van regressie die in 20.4 werd geïntroduceerd in de E-mailontwerper en die invloed had op de component Divider. Dit resulteerde in extra regelhoogten en afbeeldingsvervormingen in de inhoud. (CAMP-46663)
* Probleem verholpen dat de uit-van-de-doos knopen dwong om gecentreerd te blijven wanneer het bericht werd verzonden naar een brievenbus van Vooruitzichten, alhoewel deze knopen aan het recht of links in E-mailontwerper werden gericht. (CAMP-46466)
* Probleem verholpen waarbij de lijst met testprofielen niet kon worden vernieuwd tijdens het zoeken naar profielen in de voorvertoning van E-mailontwerper. (CAMP-45265)
* Probleem verholpen waarbij aangepaste testprofielen niet konden worden weergegeven in de lijst bij het zoeken naar profielen in de voorvertoning van E-mailontwerper. (CAMP-45589)
* Probleem verholpen waarbij onjuiste datums werden weergegeven wanneer trendafbeeldingen werden gegenereerd op basis van het samenvattingsrapport van de levering. (CAMP-45521)
