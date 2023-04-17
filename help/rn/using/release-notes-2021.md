---
title: Aanvullende informatie 2021
description: Deze pagina bevat een overzicht van alle releases van Adobe Campaign Standard in 2021.
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
feature: Overview
role: User
level: Beginner
exl-id: 225c65cc-2964-4b71-84a9-30fcd22d75bf
source-git-commit: 1a2b2ab8b6d23ca021d196909dc3ebdc02fe4e9e
workflow-type: tm+mt
source-wordcount: '4569'
ht-degree: 100%

---

# Aanvullende informatie 2021{#release-notes-2021}

## Release 21.3 - september 2021 {#release-21-3---sept-2021}

De nieuwe functies, verbeteringen en oplossingen die in de laatste release van Campaign Standard zijn opgenomen, worden hieronder weergegeven.

**Nieuwe functies**

<table> 
<thead> 
<tr> 
<th> <strong>Uniforme Experience Cloud-interface</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>De kopbalk van Adobe Campaign is veranderd voor een uniforme, verbeterde ervaring voor alle Experience Cloud-producten en -services. Deze wijzigingen maken het u als volgt gemakkelijker:</p>
<ul>
<li>Eenvoudiger overschakelen tussen uw organisaties of naar een andere applicatie.</li>
<li>Verbeterde Help voor gebruikers - De Experience League is in het product opgenomen, zodat de zoekresultaten ook resultaten van communityforums en meer videocontent omvatten; hierdoor krijgt u gemakkelijker toegang tot meer content om optimaal te profiteren van de applicatie. We hebben ook een feedbackmechanisme toegevoegd aan het menu Help, waardoor het gemakkelijker is om problemen te melden of uw ideeën te delen.</li>
<li>Verbeterde meldingen - De vervolgkeuzelijst Meldingen bevat nu twee tabbladen: één voor uw eigen productmeldingen en één voor meer algemene productmeldingen.</li>
</ul>
<p>Raadpleeg de <a href="../../start/using/interface-description.md#top-bar">gedetailleerde documentatie</a> voor meer informatie.
</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>Audittrail</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>Met de nieuwe functie Audittrail wordt in real time een uitgebreide lijst met acties en gebeurtenissen in Adobe Campaign vastgelegd. Het bevat een manier om zelf toegang te krijgen tot een geschiedenis van gegevens om vragen te beantwoorden zoals:</p>
<ul>
<li>Wat is er gebeurd met deze workflow en wie heeft deze voor het laatst bijgewerkt?</li>
<li>Wie heeft de laatste wijzigingen doorgevoerd?</li>
<li>Wat was de vorige staat?</li>
</ul>
<p>Adobe Campaign controleert nu de acties voor het maken, bewerken en verwijderen van: workflows, opties, aangepaste bronnen. Wijzigingen van deze items worden ook bijgehouden.</p>
<p>Raadpleeg de <a href="../../administration/using/audit.md">gedetailleerde documentatie</a> voor meer informatie.</p>
</td> 
</tr> 
</tbody> 
</table>


<table> 
<thead> 
<tr> 
<th> <strong>Diagnostische modus voor workflows</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>U kunt de workflows van Campaign nu uitvoeren in de diagnostische modus. In deze modus wordt informatie geregistreerd om problemen met de uitvoering van probleemoplossingen te helpen oplossen. Het volledige uitvoeringsplan wordt geregistreerd als een workflowquery standaard meer dan één minuut duurt.</p>
<p>Raadpleeg de <a href="../../automating/using/managing-execution-options.md">gedetailleerde documentatie</a> voor meer informatie.</p>
</td> 
</tr> 
</tbody> 
</table>

**Beveiligingsverbeteringen**

* De beveiliging is verbeterd voor bescherming tegen SSRF-aanvallen. (CAMP-47836)
* De lijst met gebruikers is nu beperkt tot alleen beheerders. (CAMP-47260)
* Omgevingsvariabelen kunnen niet meer worden gebruikt als onderdeel van parameteruitbreiding in een URL. (CAMP-47268)

**Verbeteringen**

* Wanneer u een terugkerende levering maakt in een workflow die is gekoppeld aan inhoud van Adobe Experience Manager, wordt de goedkeuringsstatus van de inhoud nu gecontroleerd voordat deze wordt verzonden.
* De verbindingslimiet voor databases wordt nu uitgelijnd met het Campaign-pakket om verbindingsfouten te voorkomen.
* Een nieuwe consistentiecontrole in de publicatie van aangepaste bronnen voorkomt dat gebruikers dubbele indexen maken, waardoor de publicatie mislukt. Een verbeterd foutbericht vraagt de gebruiker de naam van de index indien nodig te wijzigen. [Meer informatie](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource)

**Andere wijzigingen**

* Adobe Experience Platform Data Connector en de service Doelgroepbestemmingen zijn nu verouderd met Campaign Standard. Als u deze functies gebruikt moet u naar Bronnen en bestemmingen van Adobe gaan en uw implementatie aanpassen. [Meer informatie](../../integrating/using/get-started-sources-destinations.md)
* Verouderde en verwijderde functies worden op [deze pagina](deprecated-features.md) weergegeven.
* Er is een nieuwe samenvoegingsfunctie &#39;StringAgg&#39; geïntroduceerd om de waarden van een kolom met het type tekenreeks samen te voegen. (CAMP-47077) [Meer informatie](../../automating/using/list-of-functions.md#aggregates)
* De technische workflow **Leveringsindicatoren bijwerken** (updateDeliveryIndicators) is verbeterd voor betere prestaties.
* Sjablonen voor berichten in de app zijn nu beschikbaar voor alle talen die worden ondersteund in Campaign Standard.
* De voorbereidingstijd van de levering is geoptimaliseerd voor transactionele berichten door het aantal oproepen aan de trackingserver tijdens de analyse van de levering te verminderen.
* Gebruikers worden met een nieuw waarschuwingsbericht op de hoogte gebracht van een hoog bouncepercentage.
* Verbeterde foutmeldingen en waarschuwingen in het logboekbestand om foutopsporing eenvoudiger te maken wanneer de trackinglogbestanden niet correct zijn opgehaald. (CAMP-48939, CAMP-47360)
* U kunt URL&#39;s nu volledig aanpassen, inclusief de domeinnaam. [Meer informatie](../../designing/using/personalization.md#personalizing-urls)
* Proef- en overvulprofielen zijn nu uitgesloten van de berekening van leveringsprestaties in dynamische rapporten. (CAMP-47338)

**Patches**

* Er is een probleem met time-out verholpen bij het importeren van e-mailinhoud van een URL. (CAMP-49054)
* Er is een fout (-69) verholpen die werd veroorzaakt door een einde van de sessie bij het openen van een URL gemarkeerd met een bladwijzer of bij het vernieuwen van een pagina vanuit de browser. (CAMP-49003, CAMP-48930, CAMP-48894)
* Er is een probleem verholpen bij het synchroniseren van regels van de verouderde bezorgingsserver naar de nieuwe bezorgingsserver. (CAMP-48923)
* Er is een probleem verholpen bij het laden van een e-mailsjabloon met HTML-tags in de e-mailontwerper. (CAMP-48243)
* Er is een probleem verholpen waarbij de content van Adobe Experience Manager niet werd geladen tijdens het maken van transactieberichten met de e-mailontwerper. (CAMP-49075)
* Er is een probleem verholpen in de interface waarbij te veel opvulling werd toegevoegd tussen de bovenste balk en de content.
* Er is een probleem verholpen met transactieberichten die tot een publicatiefout konden leiden bij het gebruik van Campaign-contentblokken in de content van Adobe Experience Manager. (CAMP-49233)
* Er is een probleem verholpen dat tot een foutbericht kon leiden wanneer de verificatie mislukte. De gebruiker wordt nu omgeleid naar de aanmeldingspagina.
* Er is een tokenweergaveprobleem verholpen waardoor gebruikers een rapport niet konden bewerken of delen.
* Er is een probleem verholpen tijdens de publicatie van een aangepaste bron met behulp van een filterexpressie met 1-n tabelrelaties. (CAMP-48740)
* Er is een probleem verholpen met de datumopmaak waardoor er geen contactdatums van de levering konden worden opgehaald in workflowovergangen. (CAMP-48871)
* Er is een probleem verholpen waardoor de extensie geen logbestanden kon verzenden tijdens het maken van een aangepaste profieldimensie.
* Er is een probleem verholpen waarbij leveringen met meerdere taalvarianten soms mislukten. Als een gebruiker de standaardtaalvariant verwijdert, moet voortaan een andere taalvariant als de standaardvariant worden ingesteld voordat u de talenkopieën maakt. (CAMP-48235)
* Er is een probleem verholpen waarbij e-mailberichten in Outlook extra witruimten bevatten als de gebruiker de optie **Alleen weergeven op mobiele apparaten** had geselecteerd tijdens het ontwerpen van het bericht. (CAMP-48902)
* Er is een probleem verholpen waardoor de laatste uitvoeringsdatum van het veld met incrementele queryactiviteiten ontbrak op het tabblad **Verwerkte gegevens** na het uitvoeren van de incrementele queryworkflow. (CAMP-48879)
* Er is een probleem verholpen waardoor u een dynamische segmentcode in de workflowactiviteit **Segmentatie** niet correct kon definiëren. (CAMP-48727)
* Er is een probleem verholpen dat willekeurig optrad tijdens het opslaan van een workflow na bewerking. (CAMP-48695)
* Er is een probleem verholpen waardoor u geen aangepaste bronnen kon publiceren omdat het gegevensschema van een trigger nog steeds aanwezig was, zelfs nadat de trigger was verwijderd. (CAMP-48523)
* Er is een probleem verholpen waardoor de aanvragen voor feedbackherhalingen niet werden uitgevoerd omdat het InMail-proces de bij te werken leveringslogboeken niet kon ophalen. (CAMP-48705)
* Er is een probleem verholpen waardoor u de uitsluitingsopties in de workflowactiviteit **Exclusie** niet correct kon definiëren.(CAMP-48355)
* Er is een probleem verholpen dat optrad wanneer verrijkingsactiviteiten in workflows betrekking hadden op lidmaatschappen of afmeldingen van services. Dit probleem leidde tot vastlopen.
* Er is een probleem verholpen waardoor workflows niet konden worden uitgevoerd.
* Er is een probleem verholpen waarbij gebruikers de gebruiksklare beveiligingsgroepen in de gebruikersinterface niet kon hernoemen of verwijderen.
* Er is een probleem verholpen waardoor gebruikers een onvolledige publicatietaak voor gebeurtenissen niet konden verwijderen.
* Er is een probleem verholpen waarbij de workflow voor het opschonen van de database mislukte met een fout. (CAMP-49097)


## Release 21.2 - juni 2021 {#release-21-2---june-2021}

De nieuwe functies, verbeteringen en oplossingen die zijn opgenomen in de volgende release van Campaign Standard, worden hieronder weergegeven. De nieuwe functies, verbeteringen en oplossingen die zijn opgenomen in deze release van Campaign Standard, worden hieronder weergegeven.

**Verbeteringen**

* Bij het ontwerpen van een landingspagina kunt u nu een verplicht selectievakje toevoegen dat profielen moeten selecteren voordat het formulier wordt verzonden. Raadpleeg de [gedetailleerde documentatie](../../channels/using/managing-landing-page-form-data.md#agreement-checkbox) voor meer informatie.

* Voor de integratie van Triggers is het foutbericht dat wordt weergegeven wanneer er geen afstemmingsgegevens in de lading van de trigger komen, verbeterd: &#39;Aliasgegevens ontbreken in de lading&#39;.

* De prestaties voor het ophalen van pushmeldingen uit de wachtrij zijn verbeterd.

**Overige wijzigingen**

* Het URL-handtekeningmechanisme voor het bijhouden van koppelingen is uitgeschakeld om te voorkomen dat er een probleem optrad waardoor bepaalde geldige, ondertekende trackingskoppelingen ten onrechte werden geblokkeerd nadat deze waren gewijzigd door beveiligingstools van derden.

* Bij leveringen met meerdere varianten kunnen gebruikers niet langer taalkopieën maken als de standaardvariant is verwijderd. Er wordt nu een bericht weergegeven tijdens het maken van een taalkopie. (CAMP-48235)

* Het proces in twee stappen voor het verwijderen van profielen (verouderde versie van Campaign 19.4) is nu standaard uitgeschakeld. Eerder moest het handmatig in de interface van Campaign worden uitgeschakeld alvorens de Privacy Core-service te gebruiken. Als u dit niet deed, bleven aanvragen voor verwijderen in behandeling zonder ze te voltooien.

* In Dynamische rapporten is het segment van het **Bewijs van uitsluiting** verwijderd. (CAMP-46161)

* Er is een nieuw waarschuwingsbericht toegevoegd om de gebruiker te waarschuwen wanneer een iOS-certificaat zonder de waarde platformPrincipal in de Campaign-applicatie wordt geüpload.

* De maximale grootte van een e-mailbericht is nu standaard ingesteld op 100 MB. Met deze limiet kunt u fouten voorkomen die een e-mailbericht oneindig groter kunnen maken, waardoor het systeem kan vastlopen. (CAMP-47445) [Meer informatie](../../sending/using/design-and-personalize.md#email-size)

* De integratie van de Asset Core-service met de e-mailontwerper kan nu worden gebruikt door standaardgebruikers.

* Er is een nieuw bericht toegevoegd ter bevestiging van een geslaagde migratie van een v4-pushapplicatie naar een v5-pushapplicatie.

* Tijdens het maken van JSONWeb-tokens om te verifiëren bij de Campaign Standard-API voor authentiek te verklaren, zijn nu de productprofielen **overwogen**. Dit betekent dat de organisatorische eenheden en rollen die zijn toegewezen aan de beveiligingsgroep (die overeenkomt met het productprofiel op AdobeIO), worden toegepast op de technische IMS-account die nodig is voor oproepen van de Campaign Standard Rest-API. (CAMP-47479)

**Patches**

* Probleem verholpen waardoor de verloopoptie voor de logtabel van het batchproces (**xtkjoblog**) niet kon worden toegepast. Hierdoor kon de tabel niet correct worden gewist.

* Probleem verholpen waardoor u de volgorde van filters in een **Segmentatie**-workflowactiviteit niet kon wijzigen. (CAMP-48357)

* Probleem verholpen waarbij een regressie van 20.4 resulteerde in een fout met de waarde null. (CAMP-48591)

* Probleem verholpen waarbij u een rapport niet kon verzenden via de menu&#39;s **Delen** > **Rapport nu verzenden** of **Rapport volgens planning verzenden**. (CAMP-47798)

* Probleem verholpen waarbij een regressie werd gecorrigeerd die kon leiden tot onjuiste openingspercentages voor Gmail wegens het filteren van trackinggebeurtenissen die van Gmail-accounts werden ontvangen. (CAMP-46504)

* Verschillende problemen verholpen die leidde tot gegevensdiscrepanties tussen rapporten in Adobe Campaign Standard en rapporten in Adobe Analytics. (CAMP-47671, CAMP-47296)

* Probleem verholpen waardoor u geen toegang meer kreeg tot de leveringslogboeken nadat de voorbereiding was mislukt. (CAMP-48296)

* Probleem verholpen waarbij een foutbericht kon worden weergegeven wanneer werd geprobeerd een aangepast rapport te bewerken, te verwijderen of te verzenden. (CAMP-47789, CAMP-47798)

* Probleem verholpen waarbij oproepen van API&#39;s mislukten wanneer een nieuwe aangepaste bron werd gemaakt en de optie **Niet synchroniseren** werd ingeschakeld. (CAMP-48014)

* Probleem verholpen waarbij aangepaste bronnen met de ingeschakelde optie **Niet synchroniseren** konden verwijzen naar een schema dat opnieuw was geformuleerd of verwijderd. Dit probleem veroorzaakte een fout bij het publiceren van de aangepaste bronnen.

* Probleem verholpen met een sms-opt-out bij het gebruik van meerdere korte codes op hetzelfde externe account.

* Probleem verholpen waardoor u geen toegang kreeg tot een nieuw leveringswaarschuwingscriterium (&quot;de bron die u probeert te bereiken is onbereikbaar&quot;) na publicatie van de database. (CAMP-48221)

* Probleem verholpen waarbij trackinglogboeken in sommige Campaign-instanties met dynamische rapportage ontbraken. Er is een nieuwe [technische workflow](../../administration/using/technical-workflows.md) toegevoegd om deze trackinglogboeken te herstellen. (CAMP-47885)

* Probleem verholpen waarbij geen leveringsdata in dynamische rapporten werden weergegeven. De rapporten zijn ingesteld op 0. (CAMP-47480)

* Probleem verholpen waardoor de Server JavaScript HTTP Client geen verbinding kon maken met externe URL.

* Probleem verholpen waarbij een **Incrementele query**-activiteit werd hersteld nadat de interne naam van de workflow werd gewijzigd. Dit gebeurde wanneer een datumveld werd gebruikt als incrementele modus. (CAMP-47674)

* Probleem verholpen waarbij de voorvertoningsminiatuur niet kon worden weergegeven in het leveringsoverzicht bij het maken van een meertalige e-mail met de integratie van Adobe Experience Manager. Dit probleem trad op bij het gebruik van de knop **Taalkopie maken** om de e-mailvarianten te maken. (CAMP-47810)

* Probleem verholpen waardoor gebruikers geen toegang kregen tot de bovenliggende levering via onderliggende levering van e-mail of sms. (CAMP-47986)

* Probleem verholpen waarbij het CPU- en geheugenverbruik te hoog zou kunnen zijn bij het verzenden van transactieberichten via de REST-API met een ontbrekende aangepaste gebeurtenis. (CAMP-47147)

* Probleem verholpen met de API voor Transactieberichten waardoor realtimeberichten soms niet konden worden verzonden.

* Probleem verholpen waarbij geen rapporten werden ontvangen na het gebruik van de optie **Rapport volgens planning verzenden**. (CAMP-48583, CAMP-47786)

* Probleem verholpen waarbij rapporten die werden ontvangen na het gebruik van de optie **Rapport nu verzenden**, onvolledig waren en gegevens ontbraken. (CAMP-48583)

* Probleem verholpen met de e-mailontwerper waarbij de afmetingen van een afbeelding tijdens het uploaden van een afbeelding werden verkleind. (CAMP-47017)

* Probleem verholpen waarbij elke beschikbare sjabloon van Experience Manager niet kon worden weergegeven bij het maken van een levering. (CAMP-48132)

* Probleem verholpen waardoor de koppeling Campaign in de overzichtspagina van een verzonden levering de gebruikers niet kon doorsturen naar de gerelateerde campagne. (CAMP-48012)

* Probleem verholpen in de e-mailontwerper waarbij de integratie van de Asset Core-service bleef mislukken bij het selecteren van een asset. (CAMP-47446)

* Probleem verholpen waarbij sommige Journey Orchestration-leveringen werden geblokkeerd doordat Campaign geen tijdstempels met een exacte waarde ondersteunde (dat wil zeggen eindigend met 00) die door gebeurtenissen van Journey Orchestration werden verzonden.

## Release 21.1 - februari 2021 {#release-21-1---february-2021}

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
<p>De E-mailfeedbackservice (EFS) is een schaalbare service die rechtstreeks feedback van de Enhanced MTA vastlegt, zodat de rapporteringsnauwkeurigheid wordt verbeterd. Deze functie wordt uitgebracht als een persoonlijke bètaversie en wordt in toekomstige versies geleidelijk beschikbaar gemaakt voor alle klanten.</p>
<ul>
<li>Alle categorieën feedback worden nu vastgelegd voor volledige en nauwkeurige rapportage.</li>
<li>De berekening van de <b>Geleverd</b>-indicator is nu gebaseerd op realtimefeedback van de Enhanced MTA voor verbeterde nauwkeurigheid en reactiviteit.</li>
<li>EFS lost het probleem van vertragingen bij het rapporteren van synchrone soft bounces op.</li>
</ul>
<p>Raadpleeg de <a href="../../sending/using/confirming-the-send.md">gedetailleerde documentatie</a> voor meer informatie.
</p>
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
<p>De integratie van Campaign met Adobe Experience Manager is verbeterd: u kunt meertalige content nu gemakkelijker importeren vanuit Adobe Experience Manager. <p>
<p>Adobe Campaign Standard detecteert nu automatisch taalvarianten in Adobe Experience Manager-content en maakt het mogelijk om bulksgewijs content in verschillende talen te importeren en te maken. Hierdoor hoeven gebruikers minder stappen te doorlopen om een meertalige campagne te maken op basis van Adobe Experience Manager-content.</p>
<p>Raadpleeg de <a href="../../integrating/using/creating-multilingual-email-aem.md">gedetailleerde documentatie</a> voor meer informatie.
</p>
</td> 
</tr> 
</tbody> 
</table>

<!--
<table> 
<thead> 
<tr> 
<th> <strong>Unified Experience Cloud interface</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>Adobe Campaign header bar has been changed to unify and improve your experience across all Experience Cloud products and services. These changes are designed to make your life easier, including:</p>
<ul>
<li>Easier switching between your organizations or to a different application.</li>
<li>Improved User Help – Bringing the Experience League into the product, search results also include results from community forums and more video content, giving you easier access to more content to help get the most out of the application. We've also added a feedback mechanism right in the Help menu, making it easier to report issues or share your ideas.</li>
<li>Improved Notifications – Notifications drop-down now has two tabs: one for your own product notifications, and one for more global product announcements.</li>
</ul>
<p>For more information refer to the <a href="../../start/using/interface-description.md#top-bar">detailed documentation</a>.
</p>
<p>NOTE: This change will be progressively rolled out to all customer environments between Feb 10 and March 1st.
</p>
</td> 
</tr> 
</tbody> 
</table>
-->

**Verbeteringen**

* De **integratie van Microsoft Dynamics 365** is verbeterd met een speciale app voor zelfbedieningsintegratie en een beter implementatieproces. [Meer informatie](../../integrating/using/d365-acs-get-started.md)

* Er is een verbetering aangebracht om het oplossen van problemen bij het verzenden van transactionele berichten te vergemakkelijken. De technische beheerders van Adobe kunnen nu voor elk proces tracering gebruiken zonder het opnieuw te starten.

* Met de lijst **Profielen** kunt u nu zoeken naar records die op een van deze velden zijn gebaseerd: e-mail, voornaam, achternaam of aangepaste velden die zijn toegevoegd bij geavanceerd filteren tijdens het uitbreiden van de profielresource. Deze functie is ook beschikbaar in Campaign Standard-API’s die de parameter filterType gebruiken. [Meer informatie](../../audiences/using/integrated-customer-profile.md)

* Een parameter is aangepast aan het aantal containers die het groeperingsproces van de database voor transactionele berichten uitvoeren. Hierdoor kan de belasting gelijkmatig over alle gebruikte containers worden verdeeld voor optimale prestaties.

* Er is nu een nieuwe **GetOption**-functie beschikbaar in activiteiten die gebruikmaken van gebeurtenisvariabelen na het aanroepen van een workflow met externe parameters. Hiermee kunt u de waarde van een opgegeven functie retourneren. [Meer informatie](../../automating/using/customizing-workflow-external-parameters.md)

* Met een nieuwe optie kan Campaign Standard de beschikbaarheid van **fysiek geheugen op uw systeem controleren** voordat een workflow wordt gestart. Als de hoeveelheid geheugen te klein is, wordt de uitvoering van de workflow uitgesteld totdat het systeemgeheugen het minimum bereikt. Dit voorkomt verdere verslechtering van de prestaties en beperkt het risico van een storing. De workflow wordt automatisch voortgezet zodra de serverbelasting is gereduceerd en er meer geheugen beschikbaar is. Deze optie is alleen-lezen en kan niet worden gewijzigd. [Meer informatie](../../automating/using/best-practices-workflows.md#execution)

* Er is een nieuw proces beschikbaar in Adobe Campaign Standard, waarmee u eenvoudiger kunt migreren van de verouderde mobiele applicatie SDK v4 naar **Adobe Experience Platform Mobile SDK**. Zie [deze pagina](../../administration/using/sdkv4-migration.md).

**Overige wijzigingen**

* Een fout is gewijzigd in een waarschuwing tijdens de voorbereiding van berichten, wanneer de limiet van 100 contentdownloads per doorlopend uur is bereikt. Er wordt nu een waarschuwing weergegeven wanneer de limiet is bereikt, zodat u verder kunt gaan met de levering.

* Wanneer de content van een transactiebericht wordt verrijkt, worden de koppelingen niet meer opgehaald bij het ophalen van gegevens uit de profieltabel. Hierdoor wordt latentie tijdens berichtvoorbereiding verminderd en worden lege profielgegevens vermeden die het gevolg zijn van een onjuiste relatie die met de profieltabel is gedefinieerd.

* De technische configuratie van de instantie is geoptimaliseerd om stabiliteit te verzekeren. (CAMP-45681)

* Sessiebeheer is verbeterd om geheugen te optimaliseren. (CAMP-45901, CAMP-46767)

* De activiteit **Bestand overdragen** genereert nu een extra variabele (filesCount) die het aantal geüploade of gedownloade bestanden bevat. (CAMP-45842) [Meer informatie](../../automating/using/transfer-file.md#output-variables)

* De SMS-connector kan nu meerdere optionele parameters bij elk bericht verzenden. [Meer informatie](../../administration/using/sms-protocol.md)

* Gebruikers met de rol DATAMODEL kunnen nu extensies voor leveringslogboeken publiceren. (CAMP-46604)

* Het foutbericht dat werd weergegeven bij pogingen om een resource te publiceren die gericht is op een niet meer bestaande aangepaste resource, is duidelijker gemaakt. (CAMP-46893)

* De volgende talen zijn toegevoegd aan de lijst **Voorkeurstaal**: Indonesisch - Indonesië (in-id), Engels - Zweden (en-se), Engels - Azië en Stille Oceaan (en-ap), Engels - Japan (en-jp) en Spaans - Latijns-Amerika (es-la). (CAMP-46351)

* De functie voor het selecteren van profielen tijdens het testen van een introductiepagina gebruikt nu de ProfileBase-resource in plaats van het profiel, om een time-out te voorkomen.

* De indeling van het SMPP-logboek is verbeterd.

* Optionele parameters voor cryptString- en decryptString JS-functies zijn toegevoegd in overeenstemming met Adobe Campaign Classic-API’s.

* Verbeterde waarschuwings- of foutberichten in logboeken voor leveringsvoorbereiding.

* Verbeterde foutenlogboeken bij pogingen om verbinding te maken met Adobe IMS (Identity Management Service).

* U kunt nu de dimensies **Levering** en **Campagne** verder filteren met de zoekbalk in Dynamische rapportage.

* De geldigheidsdatum van transactionele sms-berichten kan nu worden gedefinieerd door de waarde die is ingesteld voor de vervalparameter in de API voor transactionele berichten. (CAMP-36600)

* In Dynamische rapportage toonde het ingebouwde rapport **Leveringsoverzicht** onjuiste gegevens voor de metrische waarde voor het uitschrijvingspercentage. Er is een nieuwe metrische waarde met de naam **Unieke uitschrijving** toegevoegd om dit te herstellen. (CAMP-46445)

**Patches**

* Probleem verholpen waarbij leveringen zeer traag verliepen als gevolg van bepaalde processen. Dit was te wijten aan het feit dat onjuiste eenheden werden gedefinieerd voor verschillende parameters (bijvoorbeeld milliseconden in plaats van seconden).

* Probleem verholpen waarbij de Mobile SDK een open trackingverzoek verzond op basis van de voorwaarde dat deliveryId/MessageID niet null is. Dit resulteerde in 404-fouten voor leveringen waarvoor tracking uitgeschakeld was. Een extra variabele (acsDeliveryTracking) met informatie over de trackingstatus van de levering wordt nu verzonden in de payload. Afhankelijk van de ingestelde trackingstatus kan deze variabele twee waarden hebben: ‘on’ of ‘off’. [Meer informatie](../../administration/using/push-tracking.md).

* Oplossing van een probleem in workflows bij het kopiëren en plakken van een **deduplicatie**-activiteit die eenmaal was uitgevoerd en die gebruikmaakte van een tijdelijke resource. Na duplicatie werd de resource van de activiteit automatisch ingesteld op leeg, wat leidde tot problemen in andere activiteiten van de workflow. Na het plakken blijft de resource van de activiteit nu gelijk, zodat de fout zo snel mogelijk en niet later in de workflow wordt geactiveerd. (CAMP-46903)

* Probleem verholpen waarbij de leveringsanalyse mislukte bij het verzenden van een transactioneel pushbericht gericht op profielen. Het probleem is opgelost door een nieuwe [doeltoewijzing](../../administration/using/target-mappings-in-campaign.md) te introduceren: **Profiel - realtimegebeurtenis voor Push** (*mapRtEventAppSubRcp*). De leverings-, uitsluitings- en trackinglogboeken voor [transactionele pushmeldingen die gericht zijn op een profiel](../../channels/using/transactional-push-notifications.md#transactional-push-notifications-targeting-a-profile), worden nu opgeslagen in de tabellen *broadLogAppSubRcp*, *excludeLogAppSubRcp* and *trackingLogAppSubRcp*.

   >[!IMPORTANT]
   >
   >Als u daarom een bestaand, op profielen gebaseerde pushmelding gebruikt (gemaakt vóór de upgrade naar Adobe Campaign 21.1), wordt u wegens deze verandering aangeraden de doeltoewijzing bij te werken naar de nieuwe en het bericht opnieuw te publiceren. Raadpleeg de gedetailleerde stappen [hier](../../channels/using/transactional-push-notifications.md#change-target-mapping). Als u de vorige doeltoewijzing **Profiel - Realtimegebeurtenis** (*mapRtEventRcp*) gebruikt, kan dit leiden tot langere voorbereidingstijden van de levering en een verslechtering van de prestaties.

* Probleem verholpen waardoor leveringsrapporten niet konden worden uitgevoerd wanneer 5000 rijen werden weergegeven.
* Probleem verholpen met A/B-tests waarbij de content van variant B niet kon worden bijgewerkt nadat de leveringssjabloon was gewijzigd. (CAMP-45235)
* Probleem verholpen waarbij het proces voor verzending van transactionele berichten vastliep, zodat berichten niet werden verzonden.
* Probleem verholpen waardoor navigatieproblemen optraden na het aanklikken van een interne koppeling (bijvoorbeeld wanneer de bovenliggende levering werd geopend via een proefoverzichtsscherm).
* Probleem verholpen waardoor geen beschikbare Experience Manager-contentsjablonen werden weergegeven bij het maken van een levering. (CAMP-45990)
* Probleem in workflows verholpen waardoor foutberichten niet in de leveringslogboeken werden weergegeven nadat de kolom **Reden** aan het tabblad met aanvullende data was toegevoegd. (CAMP-45139)
* Probleem verholpen dat zich voordeed wanneer twee app-abonnementaanroepen dezelfde Marketing Cloud-id hadden (‘dubbele sleutelwaarde schendt unieke beperking’-fout).
* Probleem verholpen waardoor vertraging optrad wanneer activiteiten naar een workflow met een grote hoeveelheid **Query**- en **Doelgroep lezen**-activiteiten werden gesleept. (CAMP-44511)
* Probleem verholpen dat aan het einde van de voorbereiding van een transactioneel bericht optrad, waardoor gegevens voor omleiding niet naar de trackingservers konden worden geüpload.
* Probleem verholpen waardoor foutberichten werden weergegeven bij pogingen om importsjablonen of eerdere importtaken te openen nadat de workflowresource was aangepast. (CAMP-46183)
* Probleem verholpen waardoor de activiteit **Doelgroep lezen** niet kon worden uitgevoerd als deze was geconfigureerd met de naam van een dynamische doelgroep. (CAMP-46047)
* Probleem verholpen waardoor de knop **Lijst exporteren** niet werd weergegeven
* Probleem verholpen waardoor de workflow **Rapportage-aggregaten** mislukte. (CAMP-45979)
* Probleem verholpen bij het maken van een aangepaste resource met een aangepaste samengestelde sleutel (dynamische content voor tekst/datum).
* Probleem verholpen waardoor gegevens over queryovergangen niet werden weergegeven. (CAMP-45669)
* Geheugengebruikproblemen met betrekking tot publicatie van aangepaste resources opgelost.
* Probleem verholpen dat optrad tijdens het configureren van een levering die op een bepaalde datum moest worden verzonden. Indien de levering vervolgens werd ingesteld op verzending direct na bevestiging, mislukte de voorbereiding van de levering en werd de oorspronkelijk opgegeven datum aangehouden. (CAMP-44107)
* Probleem verholpen waardoor transactionele sjablonen niet konden worden geopend. (CAMP-47181)
* Oplossing van een probleem in het proces voor het publiceren van transactionele berichten, dat tot dubbele typologieën en typologieregels leidde bij namen die de toegestane tekenreeksgrootte overschreden. (CAMP-47104)
* Probleem verholpen in de activiteit **Externe API**, dat optrad wanneer een invoerparameter een record retourneerde die niet bestond. (CAMP-47023)
* Probleem verholpen waardoor de SMPP-connector niet opnieuw verbinding kon maken.
* Probleem verholpen dat optrad in de activiteit **Bestandsoverdracht** tijdens het downloaden van een bestand dat een punt in de naam bevatte. De tekens na de punt werden beschouwd als de bestandsextensie. (CAMP-46624)
* Probleem verholpen waardoor databasegroepering niet kon worden uitgevoerd, zodat transactionele berichten vast kwamen te zitten in de routerwachtrij.
* Fout gecorrigeerd waardoor geannuleerde leveringslogboeken werden verzonden.
* Probleem verholpen waardoor een workflow mislukte bij gebruik van de activiteit **AND-join**. De primaire set werd door de activiteit automatisch ingesteld op de laatste overgang die eraan was gekoppeld, zelfs als voor deze set de eerste gekoppelde overgang werd weergegeven. (CAMP-46900)
* Probleem verholpen waarbij in quarantaine geplaatste adressen foutief op Geldig werden ingesteld, waardoor ze uit quarantaine werden gehaald.
* Probleem verholpen waardoor gepersonaliseerde velden niet werden weergegeven als ze speciale tekens bevatten. (CAMP-46805)
* Probleem verholpen waardoor een specifieke gedetailleerde weergave voor een profiel niet kon worden weergegeven. Dit gebeurde als de profielresource was uitgebreid met aangepaste velden terwijl de optie **Sectie met gepersonaliseerde velden toevoegen** ingeschakeld was.
* Probleem verholpen waardoor een foutcode 500 werd geretourneerd bij het verzenden van transactionele gebeurtenissen. (CAMP-46811)
* Probleem verholpen waardoor u geen geplande e-mailrapporten kon ontvangen. (CAMP-46891)
* Probleem verholpen dat optrad wanneer een aangepaste resource aan de profielresource werd gekoppeld via een eenvoudige koppeling met kardinaliteit 1. Bij het openen van een profiel waarin het veld voor de aangepaste resource leeg is, wordt nu een foutbericht weergegeven in plaats van een lege lijst.
* Probleem verholpen bij het gebruik van profielvervanging in een workflow, waardoor de leveringsprofielen niet in de pagina werden geladen bij het selecteren van het te vervangen profiel. (CAMP-46522)
* Regressie gecorrigeerd waarbij de technische workflow **Database opschonen** probeerde werktabellen voor verlopen levering te verwijderen met als gevolg de volgende fouten: (CAMP-46536)

```
   PGS-220000 PostgreSQL error: ERROR: table ""wkdlv_24439460_data"" does not exist and WDB-200001 SQL statement 'DROP TABLE wkdlv_24448131_data' could not be executed.
```

* De volgende fout is gecorrigeerd die in sommige gevallen optrad bij het gebruik van een aangepast filter op aangepaste resources: (CAMP-46509)

```
   The 'profile/xxxx' field used in the filter 'xxxxx' does not exist in custom resource 'xxx'
```

* Probleem verholpen waarbij **het voorbereiden van pushmeldingen** te veel tijd kostte en niet kon worden voltooid. Dit was te wijten aan een ontbrekende index voor de tijdelijke werktabellen.
* Fout gecorrigeerd die optrad bij gebruik van de optie **Dimensie om af te stemmen** in een **Afstemming**-activiteit in een workflow als er al een relatie was gedefinieerd tussen een aangepaste resource en een profielresource.
* Probleem verholpen dat optrad bij het toevoegen van koppelingen via een **Afstemming**- of **Verrijking**-activiteit. Gekozen koppelingen werden niet weergegeven in de uitvoerovergang.
* Probleem verholpen bij het gebruik van een **Segmentatie**-activiteit met terugkerende leveringen in een workflow, waardoor de levering naar de verkeerde doelgroep werd verzonden. (CAMP-46275, CAMP-46470)
* Probleem verholpen waarbij publicatie van aangepaste resources mislukte tijdens het uitbreiden van de profielresource om aangepaste profieldimensies voor dynamische rapportage te maken. (CAMP-46266)
* Fout gecorrigeerd die optrad bij het toevoegen van een koppeling aan een tabel voor het importeren van bestanden. Na het toevoegen van een **Verrijking**-activiteit aan de activiteit **Bestand importeren** verdween de eerder geconfigureerde koppeling. (CAMP-46557)
* Probleem verholpen bij het gebruik van aangepaste resources die aan profielgegevens zijn gekoppeld, waardoor de weergavevolgorde in het configuratiescherm **Details** tijdens het opslaan werd gewijzigd. (CAMP-46312)
* Probleem verholpen waarbij gegevens niet konden worden weergegeven in dynamische rapportage vanwege leveringen op basis van een aangepaste leveringstoewijzing.
* Fout gecorrigeerd waardoor u een verzameling met een onjuist resourcedoel niet kon selecteren in de **Query**-activiteit van een workflow.
* Probleem verholpen waarbij hard bounces onjuist werden gevalideerd tijdens het InMail-proces.
* Fout gecorrigeerd die optrad bij het openen van een profielscherm als gevolg van een koppelingsfout.
* Probleem verholpen waarbij AVG-gegevens niet konden worden verwijderd uit de opschoningsworkflow.
* Fout gecorrigeerd die optrad wanneer de planningsconfiguratie handmatig met het toetsenbord werd bijgewerkt in de planningparameters van e-mailleveringen.
* Probleem verholpen waardoor u een profiel niet kon bewerken vanwege onjuiste parameters in de organisatorische eenheid.
* Probleem verholpen waardoor het extensieveld **Service** leeg bleef en niet kon worden ingesteld in de **e-maileigenschappen**, zelfs als het in de leveringssjabloon was ingesteld.
* Probleem verholpen waardoor proeven trager werden verwerkt. (CAMP-45048)
* Probleem verholpen waarbij u kolommen niet kon sorteren in een profieloverzichtsscherm.
* Probleem bij het genereren van een miniatuur verholpen, dat in Azure optrad in e-mailvarianten met Chinese tekens. (CAMP-47152)
* Regressie gecorrigeerd die werd geïntroduceerd in Campaign 20.4 en die resulteerde in onjuiste openingspercentages voor Gmail wegens het filteren van trackinggebeurtenissen die van Gmail-accounts werden ontvangen. (CAMP-46504)
* Probleem verholpen waarbij HTML-content niet kon worden geïmporteerd in een sjabloon voor transactionele berichten. (CAMP-47318)
* Probleem verholpen waardoor de weergave van de renderings in het **rapport over e-mailweergave** werd vertraagd. (CAMP-46226)
* Probleem verholpen waardoor u geen aangepaste resources kon publiceren die zijn geconfigureerd met een element van het type Lijst in de schermdefinitie. (CAMP-47217)
* Probleem in Email Designer verholpen waardoor scheidingslijnen niet correct werden weergegeven in **Microsoft Outlook** wanneer ze bovenaan de e-mailcontent werden geplaatst. (CAMP-46294)
* Probleem verholpen waardoor de afstemming van KPI’s op de technische workflow van **Adobe Analytics** vastliep. (CAMP-46576)
* Probleem in **Email Designer** verholpen waardoor fragmenten niet automatisch werden weergegeven in zoekvakken wanneer contentblokken werden ingevoegd. (CAMP-44205)
* Probleem in **Email Designer** verholpen waardoor ongewenste tekens in verzonden e-mailberichten werden weergegeven wanneer emoji’s in fragmenten werden gebruikt. (CAMP-46621)
* Regressie gecorrigeerd die in 20.4 werd geïntroduceerd in **Email Designer** en die invloed had op de component Scheidingslijn, resulterend in extra lijnhoogten en afbeeldingsvervormingen in content. (CAMP-46663)
* Probleem verholpen waardoor de kant-en-klare knoppen gecentreerd bleven wanneer het bericht werd verzonden naar een Outlook-postvak, hoewel deze knoppen rechts of links waren uitgelijnd in **Email Designer**. (CAMP-46466)
* Probleem verholpen waardoor de lijst met testprofielen niet kon worden vernieuwd tijdens het zoeken naar profielen in de voorvertoning van **Email Designer**. (CAMP-45265)
* Probleem verholpen waardoor aangepaste testprofielen niet in de lijst werden weergegeven bij het zoeken naar profielen in de voorvertoning van **Email Designer**. (CAMP-45589)
* Probleem verholpen waarbij onjuiste datums werden weergegeven bij het genereren van trendafbeeldingen op basis van het **rapport Leveringsoverzicht**. (CAMP-45521)
