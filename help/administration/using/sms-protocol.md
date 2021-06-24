---
solution: Campaign Standard
product: campaign
title: Protocol en instellingen voor sms-connector
description: Leer meer op de schakelaar van SMS en hoe te om het te vormen.
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Instantie-instellingen
role: Administrator
level: Experienced
exl-id: ea936128-1c51-483d-914c-6d06708456d6
source-git-commit: f849e668cffaaca05261f0b91726a350a47676e4
workflow-type: tm+mt
source-wordcount: '8666'
ht-degree: 0%

---

# Protocol en instellingen voor sms-connector {#sms-connector-protocol}

>[!NOTE]
>
>Het **SMS-connectorprotocol en de instellingen** voor Adobe Campaign Classic vindt u op deze [pagina](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-protocol.html).
>
>In dit document verwijzen alle verwijzingen naar details over het protocol, veldnamen en waarden naar de [SMPP 3.4-specificatie](https://smpp.org/SMPP_v3_4_Issue1_2.pdf).

## Overzicht {#overview}

SMS kan beperkt zijn tot het verzenden van korte tekstberichten zonder opmaak, maar de eenvoud ervan maakt het een waardevol communicatiekanaal.

Er zijn twee belangrijke manieren om SMS te verzenden:

* Verzend het manueel van een telefoon, de gebruikelijke manier om rechtstreeks tussen mensen te communiceren.

* Verzend het via internet, zoals Adobe Campaign berichten verzendt. Hiervoor hebt u een SMS-serviceprovider nodig die verbinding maakt met het mobiele netwerk.
Adobe Campaign gebruikt het protocol SMPP om SMS naar een dienstverlener te verzenden.

Dit document doorloopt u de verbindingsinstelling tussen Adobe Campaign en een SMPP-provider.

SMPP-aanbieders kunnen soms afwijken van de officiële specificaties, maar de SMS-connector in Adobe Campaign biedt veel mogelijkheden om het gedrag aan te passen zodat het compatibel is met de meeste aanbieders.

>[!IMPORTANT]
>
>De vestiging een verbinding aan een nieuwe leverancier kan sommige technische vaardigheden, kennis van TCP, binaire, hexadecimale vertegenwoordiging en tekstcoderingen vereisen. Het zal ook actieve samenwerking met de leverancier vereisen.

### Typen SMS {#sms-types}

Wanneer u SMS-berichten verzendt via een SMS-provider, worden er drie verschillende soorten SMS-berichten weergegeven:

* **SMS MT (mobiel beëindigd)**: een SMS dat door Adobe Campaign via de SMPP-provider naar mobiele telefoons wordt gezonden.

* **SMS MO (mobiele oorsprong)**: een SMS dat door een mobiele telefoon via de SMPP-provider naar Adobe Campaign wordt verzonden.

* **SMS SR (Status Report) of DR of DLR (Delivery Receipt)**: een door de mobiele telefoon via de SMPP-provider aan Adobe Campaign verzonden ontvangstbewijs waaruit blijkt dat het SMS met succes is ontvangen. Adobe Campaign kan ook SR ontvangen om aan te geven dat het bericht niet kan worden verzonden, vaak met een beschrijving van de fout.

U moet tussen erkenningen (RESP PDU, een deel van het protocol SMPP) en SR onderscheiden: SR is een soort SMS dat door het netwerk van begin tot eind wordt verzonden, terwijl een erkenning slechts een bevestiging is dat één overdracht succesvol is geweest.

Zowel erkenningen als SR kunnen fouten teweegbrengen, die tussen twee onderscheiden zal helpen het oplossen van problemen.

### Informatie die via een SMS wordt verzonden {#information-sms}

Een SMS bevat meer informatie dan tekst. Hier een lijst van wat u in SMS kunt verwachten te vinden:

* De tekst, die is beperkt tot 140 bytes, wat betekent tussen 70 en 160 karakters afhankelijk van de codering. Zie [SMS-tekstcodering](../../administration/using/sms-protocol.md#sms-text-encoding) hieronder voor details en beperkingen.

* Een ontvankelijk adres, soms genoemd `ADC` of `MSISDN`. Dat is het nummer van de mobiele telefoon die het SMS zal ontvangen.

* Een afzenderadres, dat `oADC` of soms `sender id` kan worden geroepen. Dat kan een telefoonaantal in daggebruik, een korte code zijn wanneer verzonden door een leverancier of een naam. Naam is een facultatieve eigenschap, in dat geval kunt u niet op SMS antwoorden.

* Een markering die aangeeft of het bericht een Flash-bericht is. Een flitsbericht is een pop-up die niet in geheugen wordt opgeslagen.

* Een vlag die aangeeft of een SR wordt verwacht of niet.

* Een geldigheidsdatum, waarna geen netwerkmateriaal wordt toegestaan om opnieuw te proberen.

* Een veld `data_coding` dat de codering van de tekst aangeeft.

## SMPP-protocol {#smpp-protocol}

Adobe Campaign Standard ondersteunt versie 3.4 van het SMPP-protocol. Dit is een wijdverbreid protocol dat het verzenden van SMS naar een leverancier (SMSC) en het ontvangen van SMS evenals ontvangstbewijzen toestaat. Raadpleeg voor meer informatie de [SMPP-documentatie](https://smpp.org/SMPP_v3_4_Issue1_2.pdf).

Het netwerkmateriaal op de dienstverlener van SMS wordt vaak genoemd SMSC.

### SMPP-verbindingen {#smpp-connections}

Adobe Campaign maakt via TCP verbinding met de netwerkapparatuur van de SMS-serviceprovider. Het protocol SMPP plaatst permanente verbindingen van TCP van Adobe Campaign aan de leverancier. TCP-verbindingen worden altijd geïnitieerd door Adobe Campaign, zelfs om berichten te ontvangen.
SMPP opent 1 of 2 verbindingen van TCP, afhankelijk van zijn wijze. Alle verbindingen worden altijd geïnitieerd door Adobe Campaign.

Het protocol SMPP kan in twee wijzen werken:

* **Transmitter+ontvanger (of TX+RX)**: twee afzonderlijke verbindingen van TCP worden gebruikt voor het overbrengen van en het ontvangen van berichten.
* **Transceiver (abor TRX)**: één enkele verbinding van TCP wordt gebruikt voor het overbrengen van en het ontvangen van berichten.

>[!NOTE]
>
>TRX heeft de voorkeur voor Adobe Campaign Standard omdat het het aantal verbindingen vermindert en verbindingsterugwinning in het geval van mislukking vereenvoudigt.

### SMPP PDU {#smpp-pdu}

De transmissieeenheden van SMPP (&quot;pakketten&quot;) worden genoemd PDUs. A **PDU** bevat een bevel, een status, een opeenvolgingsaantal en gegevens.

Elke PDU moet worden erkend door een `SMPP RESP PDU` (synchrone reactie). De verzoeken kunnen worden gestroomlijnd: de afzender kan vele bevelen verzenden zonder op `RESP` te wachten, wordt het aantal verzoeken die op elk ogenblik kunnen in een pijpleiding worden gezet genoemd het venster. `RESP PDU` kan in om het even welke orde aankomen, los van de orde van hun overeenkomstige initiator PDU.

In gescheiden **Transmitter+receiver** wijze, hangt de gebruikte verbinding van het soort verzonden bericht af. De transmissieverbinding wordt gebruikt voor MT, en de ontvangerverbinding wordt gebruikt voor MO en SR. De verzoeken en de reacties voor elk soort bericht worden verzonden over de zelfde verbinding van TCP.

Bijvoorbeeld, wanneer het verzenden van MT, wordt de transmissieverbinding gebruikt en `RESP` die erkent wordt MT ook verzonden door het transmissiekanaal. Wanneer u een MO (of een SR) ontvangt, wordt de ontvangerverbinding gebruikt om MO te ontvangen en `RESP` te verzenden die MO erkent.

![](assets/do-not-localize/sms_protocol_1.png)

In Adobe Campaign Standard is de verzoening tussen MT en SR eigen aan de MTA, dus is er geen speciaal SMS-proces.

Een geslaagde `SUBMIT_SM_RESP PDU` activeert de &quot;verzonden&quot;berichtstatus in het verzendende logboek terwijl een succesvolle `DELIVER_SM (SR) PDU` de &quot;ontvangen&quot;berichtstatus teweegbrengt.

### Beveiligingsaspecten {#security-aspects}

Het protocol zelf is niet gecodeerd. De meeste leveranciers voeren een variant van IP op lijst van gewenste personen uit zodat moeten de serverIP van Adobe Campaign adressen aan de leverancier worden verklaard.

Adobe Campaign ondersteunt het doorgeven van een aanmelding en een wachtwoord tijdens de bind fase. Ook SMPP via TLS wordt ondersteund. Er zij op gewezen dat certificaten vereist zijn voor een goede beveiliging. Hoewel met de SMPP-connector certificaatcontroles kunnen worden overgeslagen, mag deze alleen worden gebruikt voor tests, aangezien TLS zonder certificaten een aanzienlijk lager beveiligingsniveau biedt.

De schakelaar gebruikt de standaardcertificaten die door de systeem `openssl` bibliotheek worden verstrekt. Meestal wordt deze opgegeven door de map `/etc/ssl/certs` op Debian. Deze map wordt standaard geleverd door het pakket &quot;ca-certificates&quot;, maar kan worden aangepast.

### Informatie in elke soort PDU {#information-pdu}

Elk type PDU heeft verschillende gebieden die verschillende stukken van informatie dragen. Deze PDU worden gedetailleerd in [SMPP 3.4 specificatie](https://smpp.org/SMPP_v3_4_Issue1_2.pdf).

Elke sectie beschrijft zowel PDU als zijn synchrone reactie (`*_RESP PDU`). Alle PDU&#39;s moeten worden herkend door een corresponderende `RESP`, dit is een verplicht onderdeel van de specificatie.

PDU&#39;s kunnen optionele velden hebben. Alleen de meest voorkomende velden worden hier beschreven. Raadpleeg de [SMPP 3.4-specificatie](https://smpp.org/SMPP_v3_4_Issue1_2.pdf) voor meer informatie.

#### BIND_TRANSMITTER / BIND_RECEIVER / BIND_TRANSCEIVER {#bind-transmitter}

Deze PDU wordt gebruikt om een verbinding met SMSC in werking te stellen. **Transmitter**,  **** Receiverand en  **** Transceivermdes veranderen slechts het soort SMS dat over deze verbinding mag worden overgebracht, specifiek:

| Modus | Typen SMS toegestaan |
|:-:|:-:|
| Transmitter | MT |
| Ontvanger | MO + SR |
| Transceiver | MT + MO + SR |

Noteerbare velden in een `BIND_* PDU`:

* **system_id**: Aanmelding gebruikt voor verificatie. Instellen in de externe account.

* **wachtwoord**: Wachtwoord voor verificatie. Instellen in de externe account.

* **system_type**: Vereist om voor sommige providers op een specifieke waarde te worden ingesteld. Instellen in de externe account, beschikbaar in alle versies. Vaak wordt onderscheid gemaakt tussen verschillende soorten contracten, kanalen, landen, enz.

* **addr_** tonand  **addr_npi**: Vereist door sommige providers. Wordt ingesteld door de instellingen `Bind TON` en `Bind NPI` in de externe account.

* **address_range**: Vereist door sommige providers. Meestal is dit een lijst met toegestane snelcodes voor deze verbinding. Instellen in de externe account.

`BIND_*_RESP` heeft geen specifiek veld, wordt bevestigd of de verbinding is gelukt of niet.

#### ONBINDEN {#unbind}

Deze PDU moet door het systeem worden verzonden alvorens los te maken van. De overeenkomst moet `UNBIND_RESP PDU` wachten voordat de verbinding wordt gesloten.

Als u SMSC in overeenstemming acht, mag de verbinding niet worden gesloten, wordt de TCP-verbinding bestuurd door de Adobe Campaign-connector.

#### VERZENDEN_SM {#submit-sm}

Deze PDU verzendt een MT naar SMSC. Zijn reactie PDU geeft identiteitskaart van MT.

Noteerbare velden in een `SUBMIT_SM PDU`:

* **service_type**: vereist door sommige aanbieders. Instellen in de eigenschappen van de levering.

* **source_addr_** tonand  **source_addr_npi**: Hiermee wordt aangegeven welk type bronadres wordt verzonden. De betekenis van deze gebieden wordt gestandaardiseerd, maar aangezien sommige leveranciers het verschillend gebruiken, zou u de leverancier om zijn correcte waarde moeten vragen. Instellen in de externe account.

* **source_addr**: het bronadres/de oADC van de MT. Het wordt weergegeven op de mobiele telefoon. De waarde in de levering wordt in de externe account en in de levering ingesteld en heeft voorrang op de waarde van de externe account.

* **dest_addr_** tonand  **dest_addr_npi**: geeft aan welk soort bestemmingsadres wordt verzonden (bijvoorbeeld lokale of internationale indeling). De betekenis van deze gebieden wordt gestandaardiseerd, maar aangezien sommige leveranciers het verschillend gebruiken, zou u de leverancier om zijn correcte waarde moeten vragen. Instellen in de externe account.

* **doel_adres**: ontvankelijk adres, telefoonaantal of MSISDN.

* **esm_class**: gebruikt om te zien of UDH wordt gebruikt of niet in het tekstveld. Deze optie wordt automatisch ingeschakeld door de connector voor gesplitste SMS als de modus `message_payload` niet wordt gebruikt.

* **priority_flag**: voorrang van deze boodschap boven andere. Dit hangt samen met de prioriteit van de levering zelf.

* **validity_period**: tijdstempel waarna geen poging mag worden gedaan. In de levering zelf instellen.

* **registered_delivery**: geeft aan of een SR is aangevraagd of niet. Adobe Campaign stelt deze markering altijd in, behalve voor automatische reacties. Bij multipart-berichten wordt de markering alleen ingesteld voor het eerste deel. Alle versies hebben hetzelfde gedrag.

* **data_coding**: Hiermee wordt de codering aangegeven die in het tekstveld wordt gebruikt. Zie de sectie [SMS-tekstcodering](../../administration/using/sms-protocol.md#sms-text-encoding) voor meer informatie.

* **short_message**: de tekst van het bericht. Als UDH wordt gebruikt, bevat dit ook de UHD-header.

Adobe Campaign ondersteunt de volgende optionele velden:

* **dest_addr_subunit**: gebruikt om het doel van het SMS te specificeren: flash, mobile of SIM-kaart. Instellen in de eigenschappen van de levering.

* **message_payload**: als deze optie is ingeschakeld in de externe account, worden lange berichten verzonden in één PDU en wordt de tekst in dit veld verzonden in plaats van in het  `short_message` veld.

#### SUBMIT_SM_RESP {#submit-sm-resp}

Deze PDU zal identiteitskaart van MT bevatten. Dit is handig om deze aan te passen aan de binnenkomende SR.

>[!IMPORTANT]
>
>Vele leveranciers brengen identiteitskaart MT in hexadecimaal over. Zorg ervoor dat u de **ID-indeling in MT-erkenning** correct instelt in de externe account.

Sommige providers verzenden `SUBMIT_SM_RESP` nadat de SR is verzonden. Adobe Campaign wacht 30 seconden op het beantwoorden van **Ongeldige bericht-id** aan een SR met een onbekende id om dat gedrag te verantwoorden.

#### DELIVER_SM {#delivery-sm}

Deze PDU wordt door SMSC naar Adobe Campaign verzonden. Het bevat een MO of een SR.

De meeste velden hebben dezelfde betekenis als hun `SUBMIT_SM`-tegenhanger. Hier volgt een lijst met nuttige velden:

* **source_addr**: bronadres van de MO/SR. Meestal is dit een telefoonnummer.

* **doel_adres**: korte code die de MO of de SR heeft ontvangen.

* **esm_class**: gebruikt om te bepalen of PDU een MO of een SR is.

* **short_message**: tekst van het bericht. Voor SR bevat dit de gegevens die worden beschreven in aanhangsel B van de specificatie van het SMPP-protocol. Zie [SR-foutbeheer](../../administration/using/sms-protocol.md#sr-error-management) voor meer informatie.

Adobe Campaign kan bericht-id lezen in het optionele veld `receipted_message_id` met enige configuratie-instelling.

#### DELIVER_SM_RESP {#deliver-sm-resp}

Deze PDU wordt door Adobe Campaign verzonden om SR en MO te erkennen.

Adobe Campaign Standard verzendt alleen een `DELIVER_SM_RESP` wanneer alle verwerkingsstappen zijn voltooid. Dit garandeert dat geen SR of MO wordt erkend terwijl er nog steeds een risico van verwerkingsfouten bestaat.

#### INQUIRE_LINK {#enquire-links}

Deze PDU wordt alleen gebruikt om te controleren of de verbinding live is. De frequentie moet worden vastgesteld op basis van de behoeften van de aanbieder.

De standaardconfiguratie 60 seconden moet overeenkomen met de meeste configuraties die zijn ingesteld in de externe account.

#### INQUIRE_LINK_RESP {#enquire-links-resp}

Deze PDU erkent dat de verbinding levend is.

### Multipart SMS (lang SMS) {#multipart}

Multipart SMS, of lange SMS, zijn SMS die in veelvoudige delen worden verzonden. Vanwege technische beperkingen in het mobiele netwerkprotocol kan een SMS niet groter zijn dan 140 bytes of moet het worden gesplitst. Zie [SMS-tekstcodering](../../administration/using/sms-protocol.md#sms-text-encoding) voor meer informatie over het aantal tekens dat in een SMS kan worden gebruikt.

Elk deel van een lang bericht is een individueel SMS. Deze onderdelen reizen onafhankelijk op het netwerk en worden door de ontvangende mobiele telefoon gemonteerd. Om herpogingen en connectiviteitsproblemen te behandelen, verzendt Adobe Campaign deze delen in omgekeerde orde en verzoekt slechts om SR op het eerste deel van het bericht, het laatst verzonden. Aangezien de mobiele telefoon alleen een bericht weergeeft wanneer het eerste deel ervan is ontvangen, worden bij nieuwe pogingen op extra onderdelen geen duplicaten op de mobiele telefoon gegenereerd.

Het maximumaantal SMS per bericht kan per levering worden geplaatst gebruikend **Maximum aantal SMS per bericht** het plaatsen in **leveringsmalplaatje**. Berichten die deze limiet overschrijden, mislukken tijdens het verzenden met een te lange reden voor SMS-fout.

Er zijn twee manieren om lange SMS te verzenden:

* **UDH**: De standaard en aanbevolen manier om lange berichten te verzenden. In deze modus splitst de connector het bericht in meerdere `SUBMIT_SM PDU`s met UDH-informatie erin. Dit protocol wordt gebruikt door mobiele telefoons zelf. Dit betekent dat Adobe Campaign de meeste controle heeft over het genereren van berichten, waardoor het precies kan berekenen hoeveel onderdelen zijn verzonden en hoe ze zijn gesplitst.

* **message_payload**: de manier om de hele lange boodschap in één keer te verzenden  `SUBMIT_SM PDU`. De aanbieder moet het opsplitsen, wat betekent dat het voor Adobe Campaign onmogelijk is precies te weten hoeveel onderdelen zijn verzonden. Sommige providers vereisen deze modus, maar we raden u aan deze alleen te gebruiken als ze UDH niet ondersteunen.

Zie de beschrijving van `esm_class`, `short_message` en `message_payload` gebieden van [SUBMIT_SM PDU](../../administration/using/sms-protocol.md#information-pdu) voor meer details over het protocol en formaten.

### Vastzetten en ramen van doorvoer {#throughput-capping}

De meeste leveranciers vereisen een productielimiet voor elke verbinding SMPP. Dit kan worden bereikt door een aantal SMS in te stellen in de externe account. Merk op dat de productiesnelheid per verbinding gebeurt, is de totale efficiënte productie de grens per verbinding vermenigvuldigd met het totale aantal verbindingen. Dit wordt beschreven in de [sectie Gelijktijdige verbindingen](../../administration/using/sms-protocol.md#connection-settings).

Om maximum mogelijke productie te bereiken, zult u het maximum verzendende venster moeten verfijnen. Het verzendende venster is het aantal `SUBMIT_SM PDU`s dat zonder het wachten op `SUBMIT_SM_RESP` kan worden verzonden. Zie de sectie [Venster verzenden als instelling](../../administration/using/sms-protocol.md#throughput-timeouts) voor meer informatie.

### SR- en foutbeheer (&quot;Bijlage B&quot;) {#sr-error-management}

Het protocol SMPP bepaalt standaard synchrone fouten in `RESP PDU`s, maar het bepaalt geen foutencodes voor SR. Elke provider gebruikt zijn eigen foutcodes met hun betekenis.

Een aanbeveling wordt gedaan in de sectie van Bijlage B van [SMPP protocolspecificatie](https://smpp.org/SMPP_v3_4_Issue1_2.pdf) (pagina 167) maar dit maakt geen lijst van de daadwerkelijke foutencodes noch hun betekenis.

Om zich aan foutenbeheer aan te passen, is het systeem van het uitzendingsbericht van Adobe Campaign gebruikt aan behoorlijk leveringsfouten en hun strengheid (hard, zacht, enz.).

Zoals hierboven vermeld, zijn er twee verschillende soorten fouten:

* synchrone antwoorden in `SUBMIT_SM_RESP` die onmiddellijk voorkomen nadat het bericht aan SMSC werd verzonden
* ontvangstbewijzen die veel later kunnen komen wanneer de mobiele telefoon het bericht ontving of wanneer uit het bericht timed. In dat geval wordt de fout gevonden in een SR.

Wanneer een SR wordt ontvangen, kunnen de status en de fout in zijn `short_message` gebied (voorbeeld voor Bijlage B conformerende implementaties) worden gevonden. Het `short_message` gebied van PDU wordt vaak genoemd **tekstgebied** aangezien het tekst in MT bevat. In het geval van SR bevat het technische informatie plus een subveld met de naam **Text**. Deze twee velden zijn verschillend en `short_message` bevat feitelijk het veld **Text** en andere informatie.

#### Indeling van tekstveld SR {#sr-text-field-format}

De specificatie raadt u aan deze indeling te gebruiken voor het tekstveld SR. Het is een lijst van subvelden, spaties gescheiden met een dubbele punt om de veldnaam en de waarde ervan te scheiden. Veldnamen zijn niet hoofdlettergevoelig.

Voorbeeld van een SR-tekstveld dat overeenkomt met de aanbeveling in aanhangsel B:

```
id:1234567890 sub:001 dlvrd:001 submit date:1608011415 done date:1608011417 stat:DELIVRD err:000 Text:Hello Adobe world
```

Het id-veld is de id die is ontvangen in de `SUBMIT_SM_RESP PDU`, de bevestiging van de MT.

`sub` en  `dlvrd` worden verondersteld de hoeveelheid geleverde delen en geleverde berichten te tellen, maar dit wordt niet gebruikt door Adobe Campaign aangezien het breedbandsysteem een betere, en meer geïntegreerde informatie geeft.

`submit date` en  `done date` velden zijn indicatieve tijdstempels van wanneer de MT is verzonden en wanneer de SR door de mobiele telefoon is verzonden. Verwacht enkele problemen met tijdzones of zelfs onjuiste tijdstempels die worden gegeven door mobiele apparaten met een onjuiste datumset.

Het statusveld is belangrijk omdat het de status van het bericht aangeeft. De enige belangrijke status zijn `DELIVRD`, `UNDELIV` en `REJECTD`. De status `DELIVRD` geeft aan dat de bewerking is geslaagd, de andere twee geven een fout aan. Andere waarden zijn mogelijk, maar doorgaans zijn het tussentijdse meldingen, zoals de MT die de mobiele provider heeft bereikt, maar niet de mobiele telefoon. Deze tussentijdse meldingen worden genegeerd door Adobe Campaign.

Het foutveld bevat de providerspecifieke foutcode. De provider moet een tabel met mogelijke foutcodes en de betekenis ervan opgeven om deze waarde te kunnen interpreteren.

Ten slotte bevat het tekstveld gewoonlijk het begin van de tekst van de MT. Dit wordt genegeerd door Adobe Campaign en sommige providers verzenden het niet om PII-lekkage en netwerkbandbreedteverbruik te voorkomen. Het kan tijdens het oplossen van problemen worden gebruikt om SR te vlekken die een test MT door dit gebied gemakkelijker aanpast te lezen.

### Voorbeeld van SR-verwerking in Adobe Campaign Standard Extended algemeen SMPP {#sr-processing}

In dit voorbeeld wordt het geval van een implementatie weergegeven volgens de aanbeveling in appendix B, de standaardwaarden in de externe account en een geslaagde SMS MT.

```
id:1234567890 sub:001 dlvrd:001 submit date:1608011415 done date:1608011417 stat:DELIVRD err:000 Text:Hello Adobe world
```

Eerst, wordt `id extraction` regex toegepast om identiteitskaart te halen en het met overeenkomstige MT in overeenstemming te brengen.

Vervolgens worden de `status extraction` regex en `error code extraction` regex toegepast om deze velden te extraheren en worden deze aan de tekenreeks toegevoegd.

Het breedbandbericht wordt geconstrueerd met deze informatie, en het originele onveranderde koord wordt toegevoegd voor verwijzing:

```
SR ExampleProvider DELIVRD 000|MESSAGE=id:1234567890 sub:001 dlvrd:001 submit date:1608011415 done date:1608011417 stat:DELIVRD err:000 Text:Hello Adobe world
```

Het bericht wordt dan genormaliseerd, verwijderend het deel van het BERICHT om veelvoudige berichten met de zelfde staat en err codes te kunnen aanpassen.

```
SR ExampleProvider DELIVRD 000|#MESSAGE#
```

Als het bericht niet reeds provisioned in de lijst van het uitzendingsbericht is, zal een nieuwe ingang worden gecreeerd, gebruikend het volledige bericht als **firstText** en het genormaliseerde bericht. Dan, gebruikt de schakelaar het succes en `error` regex om te bepalen als het een succes of een mislukking was:

* Als het `success` regex aanpast, zal het als succes worden beschouwd.

* Als het `error` regex aanpast, wordt het bericht gekwalificeerd als fout.

* Als geen van deze twee regex-overeenkomsten overeenkomen, wordt de SR genegeerd. Het zou een tussenmelding kunnen zijn, die niet door Adobe Campaign wordt behandeld.

Standaard worden alle fouten weergegeven als schermfouten. Dit betekent dat harde fouten handmatig moeten worden opgelost.

### SMS-tekstcodering {#sms-text-encoding}

**moet altijd contact opnemen met de SMSC-provider in het geval van coderingsproblemen**. Alleen de SMSC-aanbieders beschikken over nauwkeurige kennis van de codering die zij ondersteunen en over speciale regels die van toepassing kunnen zijn vanwege beperkingen in hun technische platform.

SMS-berichten gebruiken een speciale 7-bits codering, die vaak de GSM7-codering wordt genoemd.

In het protocol SMPP, zal de tekst GSM7 tot 8 beetjes per karakter voor het gemakkelijkere oplossen van problemen worden uitgebreid. Het SMSC zal het in 7 beetjes per karakter verpakken alvorens het naar mobiel wordt verzonden. Dit betekent dat het `short_message` gebied van SMS tot 160 bytes lang in het kader SMPP kan zijn terwijl het tot 140 bytes wanneer verzonden op het mobiele netwerk beperkt is.

In het geval van coderingsproblemen moet u een aantal belangrijke zaken controleren:

* Zorg ervoor dat u weet tot welke tekens codering behoort. GSM7 steunt niet volledig diakritische tekens (accenten). Vooral in het Frans, waar é en è deel uitmaken van GSM7, maar ê, â of ï niet. Hetzelfde geldt voor het Spaans.

* De C met cedilla (ç) is alleen in hoofdletters aanwezig in het GSM7 alfabet, maar sommige telefoons geven het in kleine letters of &quot;slimme&quot; gevallen terug. De algemene aanbeveling is om dit volledig te vermijden en het cedilla of de overschakeling op UCS-2 te verwijderen.

* **Gebruik ASCII niet in** SMS, tenzij de SMSC-provider daar uitdrukkelijk om verzoekt. Deze codering verspilt ruimte omdat deze 8-bits tekens bevat en minder dekking heeft dan GSM7. Deze codering kan vereist zijn voor CDMA-netwerken die in Noord-Amerika worden gebruikt.

* Latin-1 wordt niet altijd ondersteund. Controleer de compatibiliteit met uw SMSC-provider voordat u Latin-1 gaat gebruiken.

* Tabellen voor nationale taalverschuiving worden niet ondersteund door de Adobe Campaign-connector. U moet UCS-2 of andere `data_coding` in plaats daarvan gebruiken.

* UCS-2 en UTF-16 worden vaak gemengd door telefoons. Dit is een probleem wanneer emojis en andere karakters worden gebruikt niet aanwezig in UCS-2.

* De meeste telefoons hebben doopvontglyphs niet voor alle karakters UCS-2. Smartphones kunnen zeldzame karakters vrij gemakkelijk tonen, maar eigenschaptelefoons hebben over het algemeen beperkte steun aan wat in de inheemse tong van het land nuttig is zij werden gekocht. Als u emoji of ASCII-kunst wilt gebruiken, test het op een grote verscheidenheid van telefoons alvorens te verzenden. In de Adobe Campaign-voorvertoning worden ontbrekende glyphs niet gesimuleerd en worden symbolen weergegeven die beschikbaar zijn in de webbrowser.

In het veld `data_coding` wordt aangegeven welke codering wordt gebruikt. Een groot probleem is dat de waarde 0 standaard SMSC-codering in de specificatie betekent, die meestal naar GSM7 verwijst. Controleer bij de SMSC-partner welke codering is gekoppeld aan `data_coding` = 0 die alleen door Adobe Campaign wordt ondersteund. Andere `data_coding`-waarden volgen doorgaans de specificatie, maar de enige manier om zeker te zijn is om contact op te nemen met de SMSC-provider.

De maximumgrootte van een bericht hangt van zijn codering af. In deze tabel worden alle relevante gegevens samengevat:

| Codering | Gebruikelijke gegevens_codering | Berichtgrootte (tekens) | Onderdeelformaat voor SMS met meerdere onderdelen | Beschikbare tekens |
|:-:|:-:|:-:|:-:|:-:|
| GSM7 | 0 | 160 | 152 | GSM7 basis tekenset + extensie (uitgebreide tekens nemen 2 tekens in beslag) |
| Latin-1 | 3 | 140 | 134 | ISO-8859-1 |
| UCS-2 <br>UTF-16 | 8 | 70 | 67 | Unicode (verschilt per telefoon) |

## SMPP-parameters voor externe accounts {#SMPP-parameters-external}

Elke implementatie van het protocol SMPP heeft vele variaties. Om de compatibiliteit en het aanpassingsvermogen te verbeteren, zijn er veel instellingen beschikbaar om het gedrag van de SMPP-connector te wijzigen. Deze sectie beschrijft elke parameter en zijn gevolgen op de schakelaar.

### Algemene parameters en routering {#general-parameters-routing}

**MTA-instanties voor deze account beperken**

Het is mogelijk om een grens aan het aantal MTA instanties te plaatsen die met de leverancier SMPP mogen verbinden. Wanneer gecontroleerd, kunt u specificeren hoeveel MTAs maximaal kan worden gebruikt.

Met deze optie kunt u het aantal verbindingen nauwkeuriger bepalen. Zie [Gelijktijdige verbindingen](../../administration/using/sms-protocol.md#connection-settings).

Als u een waarde hoger dan het aantal lopende MTAs plaatst, zullen alle MTAs normaal lopen: deze optie is slechts een limiet en kan geen extra MTA&#39;s kweken.

Als u het aantal verbindingen, b.v. leveranciersvereiste moet nauwkeurig controleren, wordt het geadviseerd om deze optie altijd te plaatsen zelfs als de huidige plaatsing het juiste aantal lopende MTAs heeft. Als extra MTAs daarna wordt toegevoegd, zal de verbindingsgrens nog worden geëerbiedigd.

### Verbindingsinstellingen {#connection-settings}

#### SMPP-verbindingsmodus {#smpp-connection-mode}

Hiermee wordt de verbinding ingesteld in de modus **transceiver** of in de gescheiden modus **zender+receiver**. Wanneer u overschakelt naar de gescheiden **zender+receiver** modus, zijn de instellingen in de sectie **SMPP-verbindingsmodus** van toepassing op de zender en de instellingen in de sectie **Ontvangerverbindingsinstellingen** van toepassing op de ontvangerverbinding, alleen als u het selectievakje **Verschillende parameters gebruiken voor de ontvanger** hebt ingeschakeld.

#### Naam SMSC-implementatie {#smsc-implementation-name}

Hier geeft u de naam van de SMSC-implementatie op. U moet de naam van de provider instellen. Neem contact op met de beheerder of het leveringsteam om te weten wat u in dit veld wilt toevoegen. De rol van dit gebied wordt beschreven in [SR foutenbeheer](../../administration/using/sms-protocol.md#sr-error-management) sectie.

#### Server {#server}

De DNS-naam of het IP-adres van de server waarmee verbinding moet worden gemaakt.

#### Poort {#port}

De TCP-poort waarmee verbinding moet worden gemaakt.

#### Account {#account}

De aanmelding van de verbinding. Wordt doorgegeven in het veld `system_id` van de PDU BIND.

#### Wachtwoord {#password}

Wachtwoord van de SMPP-verbinding. Wordt doorgegeven in het wachtwoordveld van de PDU BIND.

#### Systeemtype {#system-type}

Waarde die in het `system_id` gebied van de BIND PDU wordt overgegaan. Sommige providers hebben hier een specifieke waarde nodig.

#### Gelijktijdige verbindingen {#simultaneous-connections}

In Adobe Campaign Standard, bepaalt het het aantal verbindingen per de draad van SMS en per proces MTA.
Het aantal MTA-processen wordt bepaald door de implementatie: gewoonlijk zijn er 2 MTAs en 1 draad. Het aantal draden kan in het config-instance.xml- dossier worden veranderd gebruikend het plaatsen smppConnectorThreads. Gewoonlijk is er 1 MTA proces per container en 1 draad per MTA proces.

Totale aansluitingsformule voor Adobe Campaign Standard:

* **Totale verbindingen = Gelijktijdige verbindingen * aantal draden * aantal MTAs**

De gelijktijdige verbindingen worden geplaatst in de externe rekening, wordt het aantal draden geplaatst in het config-instance.xml- dossier (smppConnectorThreads) en het aantal MTAs kan in de externe rekening worden beperkt.

In gescheiden **zender/ontvanger** wijze, vertegenwoordigt het aantal verbindingen hierboven het aantal **zender/ontvanger** paren betekenend dat er tweemaal het aantal verbindingen in totaal zal zijn.

#### TLS inschakelen via SMPP {#enable-TLS}

Gebruik TLS om verbinding te maken met de provider. De verbinding wordt versleuteld. De TLS-verbinding wordt beheerd door de OpenSSL-bibliotheek en alles wat op OpenSSL van toepassing is, geldt voor deze verbinding.

#### Brede SMPP-sporen inschakelen in het logbestand {#enable-verbose-log-file}

Deze instelling dumpt al SMPP-verkeer in logbestanden. Het wordt vaak vereist om parameters tijdens aanvankelijke opstelling aan te passen. Dit moet worden toegelaten wanneer het oplossen van problemen de schakelaar en vergeleken met het verkeer dat door de leverancier wordt gezien.

### Verbindingsinstelling ontvanger {#receiver-connection}

Deze sectie is alleen zichtbaar in de gescheiden modus **zender+ontvanger**.

#### Verschillende parameters gebruiken voor de ontvanger {#receiver-parameters}

Als het selectievakje is uitgeschakeld, worden dezelfde instellingen gebruikt voor zender en ontvanger.

Als het selectievakje is ingeschakeld, worden instellingen in de sectie **Verbindingsinstellingen** toegepast op de zender en worden de instellingen in de instellingen **Ontvangerverbinding** toegepast op de ontvanger.

**Ontvangerserver, poort, account, wachtwoord, systeemtype**

Deze instellingen zijn van toepassing op de ontvanger in de modus **zender+ontvanger**. Ze werken als het zenderdeel, zie hierboven voor meer details.

### SMPP-kanaalinstellingen {#smpp-channel-settings}

#### Tekentransliteratie toestaan {#allow-character-transliteration}

Transliteratie is het zoeken naar tekens die equivalent zijn aan ontbrekende tekens. Het Franse &quot;ê&quot;-teken (e met omstreeks accent) ontbreekt bijvoorbeeld in GSM-codering, maar kan worden vervangen door &quot;e&quot; zonder dat dit de leesbaarheid nadelig beïnvloedt.

Als dit selectievakje is uitgeschakeld, mislukt de tekstcodering als de tekenreeks niet exact zo kan worden gecodeerd.

Als dit selectievakje is ingeschakeld, probeert de tekstcodering de tekenreeks om te zetten in een versie die bij benadering overeenkomt in plaats van te mislukken. Als sommige tekens geen equivalent hebben in de doelcodering, mislukt de tekstcodering.

Zie [Een specifieke toewijzing van coderingsinstellingen definiëren](../../administration/using/sms-protocol.md#SMSC-specifics) voor een meer algemene uitleg van het coderingsproces.

#### Inkomende MO opslaan in de database {#incoming-mo-storing}

Als deze optie is ingeschakeld, wordt de inkomende MO opgeslagen in de inSMS-tabel van de database. Deze lijst kan worden gevraagd gebruikend de vraagactiviteit van om het even welke werkschema.

#### Real-time KPI-updates inschakelen tijdens SR-verwerking {#real-time-kpi}

Indien toegelaten, KPIs zal in real time op de belangrijkste leveringspagina worden bijgewerkt wanneer het ontvangen van foutSR.

Het nadeel kan lage prestaties wegens het gegevensbestandgeschil zijn het produceert. Als deze optie is uitgeschakeld, worden de statistieken elke 20 minuten bijgewerkt met de **syncfromexec**-workflow.

#### Bronnummer {#source-number}

Bepaalt het standaardbronadres voor berichten. Deze instelling is alleen van toepassing als het bronnummer leeg is gelaten in de levering.

Het veld Bronnummer wordt standaard niet doorgegeven, zodat de provider dit veld vervangt door de korte code.

Dit laat de de opheffingseigenschap van het afzenderadres/oADC toe.

#### Korte code {#short-code}

Geeft de korte hoofdcode van de account aan. Als er meerdere korte codes worden gebruikt voor deze account of als de korte code onbekend is, laat u dit veld leeg.

Het opgeven van korte code is handig voor twee functies:

* In de voorvertoning wordt de korte code weergegeven als er geen bronnummer is opgegeven. Het zal het echte gedrag op de mobiele telefoon weerspiegelen.

* De lijst van gewezen personen die van de auto antwoordeigenschap plaatst verzendt slechts naar quarantaine de gebruiker voor een specifieke korte code.

#### Bron TON/NPI, bestemming TON/NPI {#ton-npi}

TON (Type van Aantal) en NPI (de Indicator van het Nummeringsplan) worden beschreven in sectie 5.2.5 van [SMPP 3.4 specificatie](https://smpp.org/SMPP_v3_4_Issue1_2.pdf) (pagina 117). Deze waarden moeten op de behoeften van de leverancier worden ingesteld.

Ze worden &#39;as-is&#39; verzonden in `source_addr_ton`-, `source_addr_npi`-, `dest_addr_ton`- en `dest_addr_npi`-velden van `SUBMIT_SM PDU`.

#### Servicetype {#service-type}

Dit veld wordt &#39;as-is&#39; verzonden in het veld `service_type` van `SUBMIT_SM PDU`. Stel dit in op de behoeften van de provider.

### Doorvoer en time-outs {#throughput-timeouts}

Deze montages controleren alle timingsaspecten van het kanaal SMPP. Sommige leveranciers vereisen zeer nauwkeurige controle van het berichttarief, venster en retry timings. Deze instellingen moeten worden ingesteld op waarden die overeenkomen met de capaciteit van de aanbieder en de voorwaarden die in het contract zijn vermeld.

#### Venster verzenden {#sending-window}

Het venster is het aantal `SUBMIT_SM PDU`s dat kan worden verzonden zonder te wachten op een overeenkomst `SUBMIT_SM_RESP`.

Voorbeeld van een transmissie met een maximum venster van 4:

![](assets/do-not-localize/sms_protocol_2.png)

De vensterhulp verhoogt de productie wanneer de netwerkverbinding een hoge latentie heeft.  De waarde van het venster moet minstens het aantal SMS/s zijn die met de latentie van de verbinding in seconden wordt vermenigvuldigd zodat de schakelaar nooit op `SUBMIT_SM_RESP` alvorens het volgende bericht wacht te verzenden.
Als het venster te groot is, kunt u meer dubbele berichten verzenden in het geval van verbindingsproblemen. Bovendien hebben de meeste providers een zeer strikte limiet voor het venster en weigeren berichten die de limiet overschrijden.

Hoe te om de optimale verzendende vensterformule te berekenen:

* Meet de maximale latentie tussen `SUBMIT_SM` en `SUBMIT_SM_RESP`.

* Vermenigvuldig deze waarde in seconden tot de maximale MT-doorvoer. Dit geeft de optimale waarde voor het verzendende venster.

Voorbeeld: Als u 300 SMS/s in maximum MT productie en er is 100ms latentie tussen `SUBMIT_SM` en `SUBMIT_SM_RESP` gemiddeld, zou de optimale waarde `300×0.1 = 30` zijn.

#### Maximale MT-doorvoer {#max-mt-throughput}

Maximum aantal MT per seconde en per verbinding. Deze instelling wordt strikt gehandhaafd, de MTA zal nooit berichten sneller dan deze grens duwen. Het is nuttig voor leveranciers die nauwkeurige vertraging vereisen.

Om de totale productielimiet te kennen, vermenigvuldig dit aantal met het totale aantal verbindingen zoals die in de bovenstaande formule worden beschreven.

0 betekent geen limiet, de MTA zal MT zo snel mogelijk verzenden.

Het wordt over het algemeen aanbevolen deze instelling onder de 1000 te houden, aangezien het onmogelijk is een exacte doorvoer boven dit aantal te garanderen, tenzij deze op de uiteindelijke architectuur is gebaseerd. Neem contact op met uw provider als u een doorvoer van meer dan 1000 nodig hebt. Het kan beter zijn om het aantal verbindingen te verhogen om boven 1000 MT/s te gaan.

#### Tijd vóór opnieuw verbinden {#time-reconnection}

Wanneer de verbinding van TCP wordt verloren, zal de schakelaar dit aantal seconden wachten alvorens te proberen om een verbinding te maken.

#### Vervalperiode van de MT {#expiration-period}

Time-out tussen `SUBMIT_SM` en overeenkomende `SUBMIT_SM_RESP`. Als `RESP` niet op tijd wordt ontvangen, zal het bericht als ontbroken worden beschouwd en zal het globale hertestbeleid van MTA van toepassing zijn.

#### Time-out binden {#bind-timeout}

Time-out tussen de poging van TCP verbinden en het `BIND_*_RESP` antwoord. Wanneer de verbinding uitvalt, wordt deze door de Adobe Campaign-connector gesloten en wacht deze op Tijd voordat u opnieuw verbinding maakt. Probeer het opnieuw.

#### request_link period {#enquire-link-period}

`enquire_link` is een speciaal soort PDU die wordt verzonden om de verbinding levend te houden. Deze periode is in seconden. De campagneconnector verzendt alleen `enquire_link` wanneer de verbinding niet-actief is om bandbreedte te besparen. Als geen RESP na tweemaal deze periode wordt ontvangen, zal de verbinding als dood worden beschouwd en zal een reconnectieproces worden teweeggebracht.

### SMSC-specificaties {#SMSC-specifics}

Deze instellingen zijn geavanceerde instellingen die de Adobe Campaign-aansluiting aanpassen aan de meeste specifieke kenmerken van de SMPP-implementatie.

#### Een specifieke toewijzing van coderingen definiëren {#encoding-specific-mapping}

Zie de sectie [SMS-tekstcodering](../../administration/using/sms-protocol.md#sms-text-encoding) voor meer informatie over tekstcodering.

Met deze instelling kunt u een aangepaste coderingstoewijzing definiëren die afwijkt van de specificatie. U kunt een lijst met coderingen declareren, samen met de waarde `data_coding`.

De MTA zal proberen te coderen gebruikend het eerste coderen in de lijst. Als dit mislukt, probeert het de volgende codering in de lijst te gebruiken, enzovoort. Als het bericht niet kan worden gecodeerd, treedt er een fout op. Nadat de codering is gevonden, maakt de MTA `SUBMIT_SM PDU` met de gecodeerde tekst en het veld `data_coding` met de waarde die in de tabel is opgegeven.

De volgorde van items in de tabel is belangrijk: coderingen zijn pogingen van boven naar beneden. Plaats de goedkoopste of meest aanbevolen codering boven aan de lijst, gevolgd door meer en duurdere coderingen.

Houd er rekening mee dat UCS-2 nooit zal mislukken omdat het alle tekens kan coderen die in Adobe Campaign worden ondersteund en dat de maximale lengte van een UCS-2 SMS veel kleiner is: Alleen 70 tekens.

U kunt deze instelling ook gebruiken om een specifieke codering te forceren die altijd moet worden gebruikt door slechts 1 regel in de toewijzingstabel te declareren.

De standaardtoewijzing die wordt gebruikt wanneer het selectievakje niet is ingeschakeld, is gelijk aan de volgende tabel:

| data_coding | Codering |
|---|---|
| 0 | GSM |
| 9 | UCS-2 |

Dit betekent dat de MTA zal proberen de boodschap in GSM te coderen. Als het slaagt zal het het verzenden met `data_coding` plaatste aan 0.

Als het bericht niet in GSM kan worden gecodeerd, zal het in UCS-2 worden gecodeerd en zal `data_coding` aan 8 plaatsen.

#### message_payload inschakelen {#enable-message-payload}

Als deze optie is uitgeschakeld, wordt lange SMS gesplitst door de MTA en verzonden in meerdere `SUBMIT_SM PDU`s met UDH. Het bericht wordt opnieuw samengesteld door de mobiele telefoon na UDH-gegevens.

Wanneer gecontroleerd, lange SMS zal in één SUBMIT_SM PDU worden verzonden, die de tekst in het bericht_payload facultatieve gebied zetten. Zie de [SMPP specificatie](../../administration/using/sms-protocol.md#ACS-SMPP-connector) voor details over dit.

Als deze functie is ingeschakeld, kan Adobe Campaign de SMS-onderdelen niet afzonderlijk tellen: alle berichten worden als verzonden in één deel geteld .

#### Het volledige telefoonnummer verzenden {#send-full-phone-number}

Als dit selectievakje niet is ingeschakeld, worden alleen cijfers van het telefoonnummer verzonden naar de provider (`destination_addr` veld van het veld `SUBMIT_SM`). Dit is het standaardgedrag aangezien de internationale aantalindicator, gewoonlijk a + prefix, door TON en NPI gebieden in SMPP wordt vervangen.

Als het selectievakje is ingeschakeld, wordt het telefoonnummer ongewijzigd verzonden, zonder voorbehandeling en mogelijke spaties, plus voorvoegsel- of hekje-/sterborden.

Deze functie heeft ook een effect op het gedrag van de functie lijst van gewezen personen voor automatisch reageren: wanneer checkbox niet wordt gecontroleerd, zal a + prefix aan telefoonaantallen worden toegevoegd die in de quarantainelijst worden opgenomen om te compenseren + prefix die van het telefoonaantal door het protocol SMPP zelf wordt verwijderd.

#### TLS-certificaatcontrole overslaan {#skip-tls}

Wanneer TLS is ingeschakeld, slaat u alle certificaatcontroles over.

Wanneer gecontroleerd, is de verbinding niet veilig meer, zou het niet in productie moeten worden toegelaten.

Het kan nuttig voor het zuiveren of testdoeleinden zijn.

#### Binden TON/NPI {#bind-ton-npi}

TON (Type van Aantal) en NPI (Indicator van het Nummeringsplan) beschreven in paragraaf 5.2.5 van de [SMPP 3.4 specificatie](https://smpp.org/SMPP_v3_4_Issue1_2.pdf) (pagina 117). Deze waarden moeten worden ingesteld op wat de provider nodig heeft.

Zij worden overgebracht zoals-is in `addr_ton` en `addr_npi` gebieden van BIND PDU.

#### Adresbereik {#address-range}

Verzonden as-is op het address_range gebied van BIND PDU. Deze waarde moet worden ingesteld op wat de provider nodig heeft.

#### Aantal voor ongeldige id-erkenning {#invalid-id}

Beperkt het aantal **Bericht ID ongeldig** `DELIVER_SM_RESP` dat voor één enkele SR kan worden verzonden.

**Dit zou slechts voor het oplossen van problemendoel als** alternator moeten worden gebruikt en aan 0 in normale omstandigheden worden geplaatst.

Voorbeeld bij instelling op 2:

* De leverancier verzendt een SR (`DELIVER_SM`) met identiteitskaart &quot;1234&quot;.

* ID &quot;1234&quot; is niet gevonden in de database.

* De schakelaar telt 1 **Ongeldige identiteitskaart** fout voor die identiteitskaart, zodat verzendt het `DELIVER_SM_RESP` met de &quot;ongeldige&quot;foutencode van identiteitskaart van het Bericht&quot;(normaal gedrag).

* De provider probeert dezelfde SR opnieuw met ID &quot;1234&quot;.

* De id &quot;1234&quot; is nog steeds niet gevonden in de database.

* De schakelaar telt 2 **Ongeldige identiteitskaart** fout voor die identiteitskaart, zodat verzendt het `DELIVER_SM_RESP` &quot;OK&quot;, zelfs als het niet correct werd verwerkt.

* Deze functie is bedoeld om SR-buffers op de providerzijde te verwijderen wanneer een ongeldig SR-blok legitiem is dat berichten niet kunnen worden verwerkt.

Als u dit veld instelt op 0, wordt het mechanisme uitgeschakeld waarbij **Message ID invalid** altijd wordt geretourneerd, dit is normaal gedrag.

Als u dit veld instelt op 1, reageert de connector altijd op OK, zelfs als de id ongeldig is. Dit zou slechts aan 1 moeten worden geplaatst onder toezicht, voor het oplossen van problemen en voor de minimumhoeveelheid tijd, bijvoorbeeld om van een leverancier-zijkwestie terug te krijgen.

#### Extractieregex van de id in de SR {#regex-extraction}

SR-indeling wordt niet strikt afgedwongen door de specificatie van het SMPP-protocol. Dit is slechts een aanbeveling die wordt beschreven in [Aanhangsel B](../../administration/using/sms-protocol.md#sr-error-management) (pagina 167) van het productdossier. Sommige implementatoren van SMPP formatteren dit gebied verschillend, zodat heeft Adobe Campaign een manier nodig om het correcte gebied te halen.

Standaard worden maximaal 10 alfanumerieke tekens na `id:` vastgelegd.

De regex moet precies één vastleggroep hebben met een onderdeel tussen haakjes. Haakjes moeten rond het id-onderdeel staan. De regex-indeling is PCRE.

Wanneer u deze instelling aanpast, moet u zoveel mogelijk context opnemen om onjuiste triggers te voorkomen. Als er specifieke voorvoegsels, zoals `id:` in de norm zijn, omvat hen in regex. Gebruik ook woordscheidingstekens (\b) zoveel mogelijk om te voorkomen dat tekst in het midden van een woord wordt vastgelegd.

Als u niet genoeg context in de regex opneemt, kan er een klein veiligheidsprobleem ontstaan: de feitelijke inhoud van het bericht kan in de SR worden opgenomen. Als u alleen een specifieke id-indeling aanpast zonder context, bijvoorbeeld een UUID, wordt de werkelijke tekstinhoud mogelijk geparseerd, bijvoorbeeld een UUID die is ingesloten in het tekstveld, in plaats van de ID.

#### Regex is toegepast om de status van geslaagd/fout te bepalen {#regex-applied}

Wanneer berichten met een onbekende stat/err gebiedscombinatie worden ontmoet, worden deze regex toegepast op het staatsgebied om te bepalen of SR een succes of een fout was. SR met statuswaarden die niet overeenkomen met een van deze regexes wordt genegeerd.

Stelt standaard waarden in die met `DELIV` beginnen, bijvoorbeeld `DELIVRD` in [Bijlage B](../../administration/using/sms-protocol.md#sr-error-management) wordt beschouwd als succesvol afgeleverd en alle statuswaarden die overeenkomen met fouten, bijvoorbeeld `REJECTED`, `UNDELIV`, worden beschouwd als fouten.

#### ID-indeling in MT-bevestiging {#id-format-mt}

Dit geeft de indeling van de id aan die wordt geretourneerd in het veld `message_id` van `SUBMIT_SM_RESP PDU`.

* **Niet wijzigen**: De id wordt als zodanig opgeslagen in de database, als ASCII-gecodeerde tekst. Er vindt geen voorbewerking of filtering plaats.

* **Decimaal getal**: Van de id wordt een decimaal getal in ASCII-vorm verwacht. Voorloopspaties, volgspaties en voorloopnullen worden verwijderd wanneer deze instelling wordt gebruikt.

* **Hexadecimaal getal**: Van de id wordt verwacht dat het een hexadecimaal getal in ASCII-vorm is, zonder voorlooppunt 0x of navolgend h. De id wordt vervolgens omgezet in een decimaal getal voordat deze in de database wordt opgeslagen.

* **Hexadecimale tekenreeks**: Van de id wordt verwacht dat het een ASCII-gecodeerde tekst is die zelf een tekenreeks is met bytes die als hexadecimaal zijn gecodeerd. In de PDU vindt u bijvoorbeeld `0x34 0x31 0x34 0x32 0x34 0x33`, die wordt vertaald naar ASCII &quot;414243&quot;. Deze tekenreeks wordt vervolgens gedecodeerd als een hexadecimale reeks bytes en u krijgt als resultaat &quot;ABC&quot;: u zult identiteitskaart &quot;ABC&quot;in het gegevensbestand opslaan.

#### ID-indeling in SR {#id-format-sr}

Dit geeft de indeling aan van de id die wordt vastgelegd door de `Extraction`-regex van de id in de SR. Waarden hebben dezelfde betekenis en hetzelfde gedrag als de notatie in MT hierboven.

**SR-id of foutcode in optioneel veld**

Als deze optie is ingeschakeld, wordt de inhoud van optionele velden toegevoegd aan de tekst die wordt verwerkt door bovenstaande regexes. De tekst heeft de notatie `0xTAG:VALUE`, `0xTAG` is de hexadecimale waarde van 4 cijfers van de tag in hoofdletters, bijvoorbeeld `0x002E`.

U kunt bijvoorbeeld de id vastleggen in het veld `receipted_message_id`. Hiervoor schakelt u dit selectievakje in en wordt de volgende tekst aan de status toegevoegd:

```
0x001E:05e3299e-8d37-49d0-97c6-8e4fe60c7739
```

In dit voorbeeld is 0x001E de tag van het optionele veld en is UUID de waarde van het veld.

Als u deze waarde wilt vastleggen, kunt u nu de volgende regex instellen in het vak Extractie van de id in het veld SR:

```
\b0x001E:([0-9a-f]{8}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{12})\b
```

>[!IMPORTANT]
>
>U kunt alleen optionele velden vastleggen die tekstwaarden (ASCII/UTF-8) hebben. Specifiek, kunnen de binaire gebieden niet betrouwbaar met het huidige regex systeem worden gevangen.

**SR-id of foutcode in tekstveld**

Als deze optie is ingeschakeld, wordt het veld **Tekst** bewaard tijdens de verwerking van de statustekst van de SR.

Dit is handig als de provider belangrijke gegevens in dit veld plaatst, zoals de id of de status. Dit veld kan gewoonlijk veilig worden verwijderd, omdat het tekst met een niet-ASCII-codering kan bevatten en de verwerking van regex kan verstoren.

Als u deze optie inschakelt, kan dit leiden tot een zeer klein beveiligingsprobleem als de `Extraction`-regex van de id in het veld SR niet specifiek genoeg is. De inhoud van het veld **Text** kan als een id worden geparseerd en een aanvaller kan deze gebruiken om vervalste id&#39;s te injecteren, wat kan leiden tot een gedeeltelijke ontkenning van de servicesituatie.

**Tag voor service-id**

Hiermee kunt u een aangepast TLV-bestand toevoegen. In dit veld wordt het taggedeelte ingesteld. De waarde kan per levering in **de waarde van de Dienst of van programma ID** in de geavanceerde parameters van de levering worden aangepast.

Met deze instelling kunt u slechts één TLV-optie per bericht toevoegen.

>[!NOTE]
>
>Vanaf de release 21.1 is het nu mogelijk meer dan één optionele parameter toe te voegen. Raadpleeg deze [sectie](../../administration/using/sms-protocol.md#automatic-reply-tlv) voor meer informatie.

### Automatisch antwoord verzonden naar het MO-bericht {#automatic-reply}

Met deze functie kunt u snel tekst op de MO beantwoorden en per korte code naar de lijst van gewezen personen verzenden.

Met de kolommen **Trefwoord** en **Korte code** worden voorwaarden gedefinieerd om de automatische reactie te activeren. Als beide velden overeenkomen, wordt de MO verzonden en wordt de aanvullende actie geactiveerd. Als u een jokerteken wilt opgeven, laat u het veld leeg. Trefwoorden komen overeen met het eerste alfanumerieke woord in de MO-tekst, waarbij leestekens en voorloopruimten worden genegeerd. Het betekent dat het **Trefwoord** gebied geen ruimten kan bevatten en één enkel woord moet zijn.

De instelling **Trefwoord** is een voorvoegsel. Als u bijvoorbeeld &quot;AD&quot; opgeeft, komt deze overeen met &quot;AD&quot;, &quot;ADAPT&quot; en &quot;ADOBE&quot;. Als u meerdere trefwoorden met een algemeen voorvoegsel hebt, moet u rekening houden met de volgorde, aangezien de trefwoorden van boven naar beneden worden verwerkt.

De kolom **Reageren** is de tekst die moet worden beantwoord. Er is geen personalisatie beschikbaar op dit gebied. Als u dit veld leeg laat, wordt er geen bericht geantwoord, maar wordt de aanvullende actie toch geactiveerd.

De **Aanvullende actie** kolom verstrekt een extra actie wanneer zowel **Trefwoord** als **Korte code** gelijke, lege korte code alle korte codes aanpast. U kunt naar quarantaine verzenden of uit quarantaine verwijderen, waarde geen antwoorden op de tekst. Als u een **Aanvullende actie** maar het veld **Reageren** leeg laat, wordt de actie uitgevoerd maar wordt geen antwoord verzonden. Quarantaine wordt alleen toegepast voor de opgegeven korte code of voor alle korte codes als het veld leeg blijft.

>[!IMPORTANT]
>
>De instelling voor het verzenden van het volledige telefoonnummer heeft invloed op het gedrag van het quarantainemechanisme voor automatische antwoorden: als het verzenden van het volledige telefoonaantal niet wordt gecontroleerd, zal het telefoonaantal dat in quarantaine wordt geplaatst door een plusteken (&quot;+&quot;) worden vooraf bepaald om het met het internationale formaat van het telefoonaantal compatibel te maken.

Alle items in de tabel worden in de opgegeven volgorde verwerkt, totdat één regel overeenkomt. Als de veelvoudige regels een MO aanpassen, slechts zal de hoogste regel worden toegepast.

### Optionele parameters voor automatisch antwoord (TLV) {#automatic-reply-tlv}

Vanaf release 21.1 kunt u optionele parameters toevoegen aan automatische reactie MT. Ze worden als optionele TLV-parameters toegevoegd aan de `SUBMIT_SM PDU` van de reactie, zoals beschreven in sectie 5.3 van de [SMPP-specificatie](https://smpp.org/SMPP_v3_4_Issue1_2.pdf)(pagina 131).

Voor meer informatie over facultatieve parameters, verwijs naar dit [sectie](../../administration/using/sms-protocol.md#smpp-optional-parameters).

## Sjabloonparameters voor verzending via SMS {#sms-delivery-template-parameters}

Sommige parameters kunnen per leveringsmalplaatje worden geplaatst.

### Van veld {#from-field}

Dit veld is optioneel. Het staat het met voeten treden van afzenderadres (oADC) toe. De inhoud van dit veld wordt in het veld `source_addr` van `SUBMIT_SM PDU` geplaatst.

Het veld is door de SMPP-specificatie beperkt tot 21 tekens, maar sommige providers staan mogelijk langere waarden toe. Houd er rekening mee dat in sommige landen zeer strikte beperkingen kunnen worden toegepast, zoals lengte, inhoud en toegestane tekens.

### Bezorgingsparameters {#delivery-parameters}

#### Maximum aantal SMS per bericht {#maximum-sms}

Deze instelling werkt alleen als de instelling **Berichtlading** is uitgeschakeld. Raadpleeg deze [pagina](../../administration/using/configuring-sms-channel.md) voor meer informatie hierover. Als het bericht meer SMS dan deze waarde vereist, zal een fout worden teweeggebracht.

Het protocol van SMS beperkt SMS tot 255 delen, maar sommige mobiele telefoons hebben moeite samenstellend lange berichten met meer dan 10 delen zo, hangt de grens van het nauwkeurige model af. We raden u aan niet meer dan 5 delen per bericht te verzenden.

Vanwege de manier waarop gepersonaliseerde berichten in Adobe Campaign werken, kan de grootte van berichten variëren. Een grote hoeveelheid lange berichten zou de verzendkosten kunnen verhogen.

#### Transmissiemodus {#transmission-mode}

In dit veld wordt aangegeven welk soort SMS u wilt verzenden: normale of Flash-berichten, die op de mobiele kaart of de simkaart worden opgeslagen.

Deze instelling wordt verzonden in het optionele veld `dest_addr_subunit` in `SUBMIT_SM PDU`.

* **** Unspecified verzendt geen facultatief gebied in PDU.

* **Hiermee** wordt de waarde ingesteld op 1. Er wordt een Flash-bericht verzonden dat op de mobiele telefoon verschijnt en niet in het geheugen is opgeslagen.

* **Hiermee** wordt de waarde ingesteld op 0. Het stuurt een normaal bericht.

* **Opslaan op** mobiele apparaten stelt de waarde in op 2. Het vertelt de telefoon om SMS in intern geheugen op te slaan.

* **Met Opslaan op** terminals stelt u de waarde in op 3. Het vertelt de telefoon om SMS in de kaart op te slaan SIM.

#### Geldigheidsperiode {#validity-period}

De geldigheidsperiode wordt doorgegeven in het veld `validity_period` van `SUBMIT_SM PDU`. De datum wordt altijd opgemaakt als een absolute UTC-tijdnotatie (het datumveld eindigt met &quot;00+&quot;).

#### Optionele SMPP-parameters (TLV) {#smpp-optional-parameters}

Vanaf versie 21.1 kunt u meerdere optionele parameters toevoegen aan elke MT die voor deze levering wordt verzonden. Deze optionele parameters worden toegevoegd aan de `SUBMIT_SM PDU` van de reactie, zoals beschreven in sectie 5.3 van de [SMPP-specificatie](https://smpp.org/SMPP_v3_4_Issue1_2.pdf)(pagina 131).

Elke rij in de tabel vertegenwoordigt een optionele parameter:

* **Parameter**: Beschrijving van de parameter. Niet verzonden naar de provider.
* **Tag-id**: Tag van de optionele parameter. Moet geldig hexadecimaal zijn, gebruikend formaat 0x1234. Ongeldige waarden leiden tot een voorbereidingsfout voor de levering.
* **Waarde**: Waarde van het optionele veld. Gecodeerd als UTF-8 wanneer het aan de leverancier wordt overgebracht. Coderingsindeling kan niet worden gewijzigd, het is niet mogelijk binaire waarden te verzenden of verschillende coderingen te gebruiken, zoals UTF-16 of GSM7.

Als een optionele parameter dezelfde **Tag-id** heeft als de **Service-tag-id** die in de externe account is gedefinieerd, heeft de waarde die in deze tabel is gedefinieerd, voorrang.

## SMPP-aansluiting {#ACS-SMPP-connector}

![](assets/do-not-localize/sms_protocol_3.png)

Pijlen geven de gegevensstroom aan.

Het belangrijkste ding om hier nota van te nemen is dat er veelvoudige SMPP schakelaardraden zijn. Deze draden zijn allen identiek en delen de zelfde configuratie. Daarom wordt het aantal verbindingen altijd vermenigvuldigd met het aantal draden.

Het aantal draden kan niet door de klant worden veranderd aangezien het veranderende configuratiedossiers vereist.

### Beschrijving van het gedrag van de SMPP-connector {#behavior-smpp-connector}

#### Overeenkomende MT-, SR- en Broadlog-vermeldingen {#matching-mt-sr}

In Adobe Campaign is een bericht een broadlog-vermelding. In Adobe Campaign Standard, moeten de externe schakelaars slechts over de het werk uitzenden lijst weten: `nmsBroadLogExec`. Een werkstroom is verantwoordelijk voor het kopiëren van uitzendingangen naar hun specifieke doeldimensies (nmsBroadLogXXX).

Jammer genoeg, staat SMPP niet toe om een identiteitskaart samen met een bericht te verzenden: de leverancier geeft een MT identiteitskaart aan elke MT, dan verstrekt één of meerdere SR met zelfde identiteitskaart

De id die door de provider wordt gegeven, wordt opgeslagen in de kolom `sProviderId` van de tabel `nmsBroadLogExec`. SR arriveert altijd nadat de MT met succes is verzonden en erkend, maar kan soms buiten de orde aankomen, in Adobe Campaign bekend als uitstaande SR. De verwerkingsdraad slaat deze SR tijdelijk in RAM op tot de volledige informatie aankomt.

Wanneer een MT wordt erkend (`SUBMIT_SM_RESP`), `sProviderId` wordt onmiddellijk bijgewerkt in gegevensbestand.

Elke SR wordt verwerkt individueel door SMPP verwerkingsdraden. Dit proces is pseudo-synchroon: het wordt gezien als synchroon van de buitenkant, maar intern uitgevoerd met gebeurtenis-gedreven implementaties. SR worden erkend slechts wanneer de uitzendingen met succes zijn bijgewerkt, als een fout wordt ontmoet SR wordt verworpen.

Hier volgt het proces dat op elke SR wordt toegepast:

* De id van de SR wordt geëxtraheerd met een regex.
* De id wordt doorzocht in `nmsBroadLogExec:sProviderId`.
* De status + foutcode worden met behulp van regexes uit de SR geëxtraheerd.
* Het mechanisme van het uitzendingsbericht wordt gebruikt om de fout te kwalificeren en uitzendingsidentiteitskaart te vinden
* De uitzending wordt bijgewerkt met alle bovenstaande informatie.
* De SR wordt erkend.

Als u bovenstaande stappen wilt controleren, moet u **uitgebreide SMPP-sporen inschakelen** om handmatig te controleren of alle stappen correct zijn uitgevoerd. Dit is altijd verplicht wanneer Adobe Campaign wordt verbonden met een nieuwe SMPP-provider.

## Voordat u live gaat {#checklist}

Deze checklist bevat een lijst met dingen die u moet controleren voordat u live gaat. Een onvolledige opstelling kan tot vele kwesties leiden.

### Controleren op conflicten met externe accounts {#external-account-conflict}

Controleer of je geen oude externe SMS-accounts hebt. Als u de testaccount uitschakelt, loopt u het risico dat deze weer wordt ingeschakeld in het productiesysteem en dat er potentiële conflicten ontstaan.

Controleer of er geen andere instantie verbinding maakt met dit account. Controleer met name of de werkgebiedomgeving geen verbinding maakt met de account. Sommige providers ondersteunen dit, maar hiervoor is een zeer specifieke configuratie nodig, zowel aan Adobe Campaign als op het platform van de provider.

Als u meerdere accounts op dezelfde Adobe Campaign-instantie nodig hebt die verbinding maken met dezelfde provider, neemt u contact op met de provider om ervoor te zorgen dat er een onderscheid wordt gemaakt tussen deze accounts. Voor meerdere accounts met dezelfde aanmelding is een extra configuratie vereist.

### Brede SMPP-sporen tijdens controles inschakelen {#enable-verbose}

U zou uitgebreide sporen SMPP tijdens controles altijd moeten toelaten.
Zelfs als u de logboeken niet zelf kunt controleren, is het gemakkelijker voor Steun om u te helpen.

### Je SMS testen {#test}

* **Verzend SMS met allerlei**
tekens. Als u SMS met niet-GSM- of niet-ASCII-tekens moet verzenden, probeer dan berichten met zoveel mogelijk verschillende tekens te verzenden. Als u een aangepaste tekentoewijzingstabel instelt, moet u minstens één SMS verzenden voor alles wat mogelijk is 
`data_coding` values.

* **Controleer of SR correct wordt**
verwerktHet SMS moet worden gemarkeerd als ontvangen in het leveringslogboek. Het leveringslogboek zou succesvol moeten zijn en als het volgende kijken:

Controleer of u de naam van de leverancier van de levering hebt gewijzigd. Het leveringslogboek mag nooit bevatten    `SR yourProvider stat=DELIVRD err=000|#MESSAGE`
Controleer of u de naam van de leverancier van de levering hebt gewijzigd. Het leveringslogboek mag nooit **SR Generic** op productieomgevingen bevatten.

* **Controleren of MO wordt**
verwerktAls u MO moet verwerken (automatische reacties, MO-opslag in de database, enz.) probeer een aantal tests uit te voeren. Verzend een paar SMS voor alle automatische antwoordsleutelwoorden en controleer als het antwoord snel genoeg, niet meer dan een paar seconden is.
Controleer in het logbestand dat Adobe Campaign met succes heeft beantwoord 
`DELIVER_SM_RESP` (command_status=0).

### PDU&#39;s controleren {#check-pdus}

Zelfs als de berichten succesvol kijken, is het belangrijk om te controleren dat PDUs behoorlijk geformatteerd is.

Deze stap is nodig wanneer u verbinding maakt met een provider die nog niet eerder verbinding had met Adobe Campaign.

#### BIND {#bind}

Controleer of `BIND_* PDUs` correct is verzonden. Het belangrijkste te controleren ding is dat de leverancier altijd succesvol `BIND_*_RESP PDUs` (command_status = 0) terugkeert.

Controleer of er niet te veel `BIND_* PDU`s zijn. Als er te veel zijn, zou het erop kunnen wijzen dat de verbinding instabiel is. Zie [Problemen met instabiele verbindingen](../../administration/using/sms-protocol.md#issues-unstable-connection) voor meer informatie.

#### INQUIRE_LINK {#enquire-link-pdus}

Controleer of `ENQUIRE_LINK PDU`s regelmatig wordt uitgewisseld wanneer de verbinding niet actief is.

#### SUBMIT_SM/DELIVER_SM {#submit-sm-deliver-sm}

Verzend een bericht, dan onderzoek in de logboeken naar zijn overeenkomstige `SUBMIT_SM`, `SUBMIT_SM_RESP`, `DELIVER_SM` en `DELIVER_SM_RESP PDU`s.

Met `SUBMIT_SM PDU`:

* Controleer of `data_coding` correct is, standaard 0.
* Controleer of `short_message` correct is gecodeerd. Decoderen met een hexadecimale converter die meerdere coderingen ondersteunt.

Met `SUBMIT_SM_RESP PDU`:

* Controleer of dit gelukt was, command_status = 0.
* Controleer of de hoofdtekst een correct opgemaakte id bevat, gevolgd door de byte &#39;0&#39;.

Met `DELIVER_SM PDU`:

* Decoderen van het hexadecimale veld `short_message`.
* Controleer met een regex controlehulpmiddel dat regex in `Extraction` regex van identiteitskaart in SR precies één vangstgroep terugkeert en dat het volledige identiteitskaart in het bericht vangt.
* Controleer of de geëxtraheerde id overeenkomt met de id in `SUBMIT_SM_RESP`.
* Controleer of de regex die is gedefinieerd in `Extraction` regex van de status in de SR, de inhoud van het statusveld retourneert.
* Controleer of de regex die is gedefinieerd in `Extraction` regex van de fout in de SR, de inhoud van het foutveld retourneert.

Met `DELIVER_SM_RESP PDU`:

* Controleer of het object snel is verzonden nadat het `DELIVER_SM PDU` is ontvangen, meestal minder dan 1 seconde.
* Controleer of dit gelukt was, command_status = 0.

### Vraag de provider of alles OK is {#provider}

Zelfs als uw SMS succesvol is, contacteer de leverancier om te zien of is alles in orde.

### Brede SMPP-sporen uitschakelen {#disable-verbose}

Zodra alle controles volledig zijn, moet het laatste ding **verbose SMPP sporen** onbruikbaar maken om niet teveel logboeken te produceren. U kunt hen voor het oplossen van problemendoeleinden opnieuw toelaten zelfs op productiesystemen.
