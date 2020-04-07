---
title: E-mailkanaal configureren in Adobe Campagne Standard
description: Leer hoe u het e-mailkanaal configureert in Adobe Campaign Standard.
page-status-flag: never-activated
uuid: 9fddb655-b445-41f3-9b02-5d356fc88aa1
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuring-channels
discoiquuid: 3752d41f-8c59-4fad-b30f-e98e09cd74a8
context-tags: extAccountEmail,overview;emailConfig,main;ruleSet,overview;delivery,properties,open
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6c7dc7927a7652efab20d976a8c5d0db8a33a66f

---


# E-mailkanaal configureren{#configuring-email-channel}

## Parameters e-mailkanaal {#email-channel-parameters}

In het configuratiescherm voor e-mail kunt u de parameters voor het e-mailkanaal definiëren. Beheerders hebben toegang tot deze configuraties via het menu **[!UICONTROL Administration]>[!UICONTROL Channels]>[!UICONTROL Email]>[!UICONTROL Configuration]**.

![](assets/channels_1.png)

* **Koptekstparameters van verzonden e-mails**

   In deze sectie kunt u opgeven **[!UICONTROL masks]** welke gegevens zijn geautoriseerd voor het verzendadres en het foutadres. Indien nodig, kunnen deze maskers met komma&#39;s worden gescheiden. Deze configuratie is optioneel. Wanneer deze velden worden ingevoerd, controleert Adobe Campagne tijdens het voorbereiden van berichten of de ingevoerde adressen geldig zijn. Deze werkende wijze zorgt ervoor dat geen adressen worden gebruikt die leveringskwesties konden teweegbrengen. De adressen van de levering moeten op de leveringsserver worden gevormd.

* **Leverbaarheid**

   Deze id wordt geleverd door ondersteuning. Leverbaarheidsrapporten moeten correct werken.

* **Leveringsparameters**

   Adobe Campaign verzendt de berichten die op de begindatum beginnen. In het **[!UICONTROL Message delivery duration]** veld kunt u opgeven gedurende welke periode de berichten kunnen worden verzonden.

   >[!IMPORTANT]
   >
   >Zodra de upgrade naar de [Adobe Campagne Enhanced MTA](https://helpx.adobe.com/campaign/kb/campaign-enhanced-mta.html)is uitgevoerd, wordt de **[!UICONTROL Message delivery duration]** parameter in uw campagneleveringen alleen gebruikt als deze op 3,5 dagen of minder is ingesteld. Als u een waarde definieert die hoger is dan 3,5 dagen, wordt hiermee geen rekening gehouden.

   Het **[!UICONTROL Online resources validity duration]** veld wordt gebruikt voor geüploade bronnen, voornamelijk voor de spiegelpagina en afbeeldingen. De bronnen op deze pagina zijn gedurende een beperkte tijd geldig (om schijfruimte te besparen).

* **Opnieuw**

   Voor tijdelijk onafgeleverde berichten moet u het opnieuw proberen. Zie [Opnieuw proberen na een tijdelijke leveringsfout](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure)voor meer informatie.

   >[!IMPORTANT]
   >
   >Nadat de upgrade naar de [Adobe Campagne Enhanced MTA](https://helpx.adobe.com/campaign/kb/campaign-enhanced-mta.html)is uitgevoerd, worden de instellingen voor **Opnieuw proberen** in Campagne genegeerd. De **[!UICONTROL Number of retries]** (hoeveel pogingen zouden moeten worden uitgevoerd de dag nadat verzenden is begonnen) en de **[!UICONTROL Retry period]** (minimumvertraging tussen pogingen) worden beheerd door Verbeterde MTA, op basis van hoe goed IP zowel historisch als momenteel bij een bepaald domein presteert.

   <!--This section indicates how many retries should be performed the day after the send is started (**Number of retries**) and the minimum delay between retries (**Retry period**). By default, five retries are scheduled for the first day with a minimum interval of one hour, spread out over the 24 hours of the day. One retry per day is programmed after that and until the delivery deadline, which is defined in the **[!UICONTROL Delivery parameters]** section.-->

* **E-mailquarantaineparameters**

   Voer in het **[!UICONTROL Time between two significant errors]** veld een waarde in om de tijd te definiëren die de toepassing wacht voordat de foutenteller bij een fout wordt verhoogd. De standaardwaarde is **&quot;1d&quot;**, voor 1 dag.

   Wanneer de **[!UICONTROL Maximum number of errors before quarantine]** waarde is bereikt, wordt het e-mailadres in quarantaine geplaatst. De standaardwaarde is **&quot;5&quot;**: het adres zal op de vijfde fout in quarantined zijn. Dit betekent dat het contact automatisch van volgende leveringen wordt uitgesloten.

   Voor meer op quarantines, zie het [Begrip van quarantainebeheer](../../sending/using/understanding-quarantine-management.md).

## E-mailrouteringsaccounts {#email-routing-accounts}

De **[!UICONTROL Integrated email routing]** externe rekening wordt standaard verschaft. Het bevat de technische parameters waarmee de toepassing e-mailberichten kan verzenden.

![](assets/channels_2.png)

Het accounttype moet altijd worden ingesteld op **[!UICONTROL Routing]**, het kanaal op **[!UICONTROL Email]** en de leveringsmodus op **[!UICONTROL Bulk delivery]**.

**Verwant onderwerp**:

[Externe rekeningen](../../administration/using/external-accounts.md)

## E-mailverwerkingsregels {#email-processing-rules}

Beheerders **[!UICONTROL Email processing rules]** hebben toegang tot dit bestand via het **[!UICONTROL Administration > Channels > Email]** menu.

Deze regels bevatten de lijst met tekenreeksen die door externe servers kunnen worden geretourneerd en waarmee u de fout (**Hard**, **Zacht** of **Genegeerd**) kunt kwalificeren.

De standaardregels zijn als volgt.

### Stuitberichten {#bounce-mails}

Voor de synchrone foutenmeldingen van de leveringsmislukking, bepaalt Verbeterde MTA het stuittype en de kwalificatie, en stuurt die informatie terug naar Campagne. Raadpleeg dit [document](https://helpx.adobe.com/campaign/kb/campaign-enhanced-mta.html)voor meer informatie over de verbeterde MTA voor Adobe-campagne.

De asynchrone stuitingen worden nog gekwalificeerd door het proces van de Campagne inMail door de **[!UICONTROL Bounce mails]** regel.

>[!IMPORTANT]
>
>Zodra bijgewerkt naar de verbeterde MTA, worden de stuiterende kwalificaties in de **[!UICONTROL Message qualification]** lijst van de Campagne niet meer gebruikt. Zie deze [sectie](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification)voor meer informatie over stuiterende mailkwalificatie.

<!--The user can create his own rules.

>[!IMPORTANT]
>
>When importing a package and when updating data via the **Update for deliverability** workflow, the user-created rules are overwritten.-->

### Beheer van e-maildomeinen {#managing-email-domains}

<!--The Adobe Campaign messaging server applies rules specific to the domains, and then the rules for the general case represented by an asterisk in the list of rules.

The **SMTP parameters** act as filters applied for a blocking rule.

* You can choose whether or not to activate certain identification standards and encryption keys to check the domain name, such as **Sender ID**, **DomainKeys**, **DKIM**, and **S/MIME**.
* **SMTP relay**: lets you configure the IP address and the port of a relay server for a particular domain.-->

>[!IMPORTANT]
>
>Zodra de upgrade naar de verbeterde MTA is uitgevoerd, worden de **[!UICONTROL Domain management]** regels voor Adobe-campagne niet meer gebruikt.

**DKIM (DomainKeys Identified Mail)** e-mailverificatie wordt ondertekend door de Enhanced MTA voor alle berichten met alle domeinen. Het ondertekent niet met identiteitskaart **van de** Afzender, **DomainKeys**, of **S/MIME** tenzij anders gespecificeerd op het Verbeterde niveau MTA.

Raadpleeg dit [document](https://helpx.adobe.com/campaign/kb/campaign-enhanced-mta.html)voor meer informatie over de verbeterde MTA voor Adobe-campagne.

### MX-beheer {#mx-management}

<!--The MX management rules are used to regulate the flow of outgoing emails for a specific domain. They sample the bounce messages and block sending where appropriate.

The Adobe Campaign messaging server applies rules specific to the domains, and then the rules for the general case represented by an asterisk in the list of rules.

To configure MX management rules, simply set a threshold and select certain SMTP parameters. A **threshold** is a limit calculated as an error percentage beyond which all messages towards a specific domain are blocked.-->

>[!IMPORTANT]
>
>Nadat de upgrade naar de verbeterde MTA is uitgevoerd, worden de regels voor de **[!UICONTROL MX management]** leveringstijd van Adobe Campagne niet meer gebruikt.

Verbeterde MTA gebruikt zijn eigen MX regels die het toestaan om uw productie door domein aan te passen die op uw eigen historische e-mailreputatie wordt gebaseerd, en op real time terugkoppelen die uit de domeinen komt waar u e-mails verzendt.

Raadpleeg dit [document](https://helpx.adobe.com/campaign/kb/campaign-enhanced-mta.html)voor meer informatie over de verbeterde MTA voor Adobe-campagne.

<!--Each rule defines an address mask for the MX. Any MX whose name matches this mask is therefore eligible. The mask can contain "&#42;" and "?" generic characters.

For example, the following addresses:

* a.mx.yahoo.com 
* b.mx.yahoo.com 
* c.mx.yahoo.com

are compatible with the following masks:

* &#42;.yahoo.com
* ?.mx.yahoo.com

These rules are applied in sequence: the first rule whose MX mask is compatible with the targeted MX is applied.

The following parameters are available for each rule:

* **[!UICONTROL Range of IDs]**: this option lets you indicate the ranges of identifiers (publicId) for which the rule applies. You can specify:

    * A number: the rule will only apply to this publicId.
    * A range of numbers (number1-number2): the rule will apply to all publicIds between these two numbers.

  If the field is empty, the rule applies to all IDs.

* **[!UICONTROL Shared]**: this option indicates that the highest number of messages per hour and of connections applies to all MXs linked to this rule. 
* **[!UICONTROL Maximum number of connections]**: maximum number of simultaneous connections to an MX from a given address. 
* **Maximum number of messages**: maximum number of messages that can be sent by one connection. After this amount, the connection is closed and a new one is reopened. 
* **[!UICONTROL Messages per hour]**: maximum number of messages that can be sent in one hour for an MX via a given address.

>[!IMPORTANT]
>
>* The delivery server (MTA) must be restarted if the parameters have been changed. 
>* The modification or creation of management rules is for expert users only. -->

## Lijst met e-maileigenschappen {#list-of-email-properties}

In deze sectie wordt de lijst met parameters weergegeven die beschikbaar is in het eigenschappenscherm van een e-mail- of e-mailsjabloon.

>[!NOTE]
>
>Sommige parameters zijn alleen beschikbaar in sjablonen. De parameters u tot toegang hebt [hangen van uw toestemmingen](../../administration/using/users-management.md)af.

Met de **[!UICONTROL Edit properties]** knop kunt u de eigenschappen van een e-mailsjabloon of een e-mailsjabloon bewerken.

![](assets/delivery_options_1.png)

### Algemene parameters {#general-parameters}

Identificeer boven aan het parameterscherm E-mail de e-mail met behulp van de **[!UICONTROL Label]** en de **[!UICONTROL ID]** velden. Deze informatie verschijnt in de interface maar is niet zichtbaar aan de berichtontvangers.

![](assets/delivery_options_2.png)

>[!IMPORTANT]
>
>De id moet uniek zijn.

In het **[!UICONTROL Brand]** veld kunt u het merk selecteren dat aan de levering is gekoppeld. Raadpleeg de sectie [Branding](../../administration/using/branding.md) voor meer informatie over het gebruik en de configuratie van merken.

In het **[!UICONTROL Campaign]** veld kunt u de campagne invoeren die aan de e-mail is gekoppeld.

U kunt ook een afbeelding toevoegen **[!UICONTROL Description]** in het desbetreffende veld en de afbeelding bewerken die wordt weergegeven in de miniatuur van de e-mail in de lijsten.

### Parameters verzenden {#sending-parameters}

De **[!UICONTROL Send]** sectie is alleen beschikbaar voor e-mailsjablonen. Het bevat de volgende parameters:

#### Parameters opnieuw {#retries-parameters}

Voor tijdelijk onafgeleverde berichten moet u het opnieuw proberen. Zie [Opnieuw proberen na een tijdelijke leveringsfout](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure)voor meer informatie.

>[!IMPORTANT]
>
>Nadat de upgrade naar de [Adobe Campagne Enhanced MTA](https://helpx.adobe.com/campaign/kb/campaign-enhanced-mta.html)is uitgevoerd, worden de instellingen voor **Opnieuw proberen** in Campagne genegeerd. De **[!UICONTROL Retry period]** (minimumvertraging tussen pogingen) en **[!UICONTROL Max. number of retries]** (hoeveel herpogingen zouden moeten worden uitgevoerd de dag nadat verzenden is begonnen) worden geleid door Verbeterde MTA, gebaseerd op hoe goed IP zowel historisch als momenteel bij een bepaald domein uitvoert.

<!--This section indicates how many retries should be performed the day after the send is started ( **[!UICONTROL Max. number of retries]** ) and the minimum delay between retries ( **[!UICONTROL Retry period]** ).

By default, five retries are scheduled for the first day with a minimum interval of one hour, spread out over the 24 hours of the day. One retry per day is programmed after that and until the delivery deadline, which is defined in the [Validity period parameters](#validity-period-parameters) section.

The number of retries can be changed globally (contact your Adobe technical administrator) or for each delivery or delivery template.-->

Momentum houdt zich aan de instelling voor de leveringsduur (die wordt gedefinieerd in de sectie Parameters [voor](#validity-period-parameters) geldigheidsperiode) in de campagne, maar slechts tot 3,5 dagen. Op dat punt, zal om het even welk bericht in de herprobeer rij worden verwijderd uit de rij en terug als stuiteren. Zie deze [sectie](../../sending/using/understanding-delivery-failures.md#about-delivery-failures)voor meer informatie over leveringsfouten.

#### Parameters voor e-mailindeling {#email-format-parameters}

U kunt de indeling van de te verzenden e-mails configureren. Er zijn drie opties beschikbaar:

* **Voorkeuren** voor ontvangers gebruiken (standaardmodus): De berichtindeling wordt gedefinieerd op basis van de gegevens die zijn opgeslagen in het ontvangende profiel en wordt standaard opgeslagen in het veld **E-mailindeling** (@emailFormat). Als een ontvanger berichten in een bepaald formaat wenst te ontvangen, is dit het verzonden formaat. Als het veld niet is ingevuld, wordt een meerdelig alternatief bericht verzonden (zie hieronder).
* **Laat de ontvanger e-mailcliënt het meest aangewezen formaat (multipart-alternatief)** kiezen: het bericht bevat beide indelingen : tekst en HTML. De indeling die bij ontvangst wordt weergegeven, is afhankelijk van de configuratie van de e-mailsoftware van de ontvanger (meerdelig-alternatief).

   >[!IMPORTANT]
   >
   >Deze optie omvat beide versies van het bericht. Het beïnvloedt daarom de leveringsproductie, omdat de berichtgrootte groter is.

* **Verzend alle berichten in tekstformaat**: het bericht wordt verzonden in tekstformaat. De HTML-indeling wordt niet verzonden, maar wordt alleen voor de spiegelpagina gebruikt wanneer de ontvanger op de koppeling in het bericht klikt.

#### SMTP-testmodus {#smtp-test-mode}

Met de **[!UICONTROL Enable SMTP test mode]** optie kunt u het verzenden van e-mails via een SMTP-verbinding testen zonder dat u daadwerkelijk berichten verzendt.
De berichten worden verwerkt tot de verbinding met de server SMTP wordt bereikt, maar zij worden niet verzonden.

![](assets/smtp-test-mode.png)

Deze optie is beschikbaar voor e-mails en e-mailsjablonen.

Als u de optie van de SMTP testwijze voor een e-mailmalplaatje toelaat, zullen alle e-mailberichten die van dit malplaatje worden gecreeerd deze optie toegelaten hebben.

>[!IMPORTANT]
>
>Als deze optie is ingeschakeld voor een e-mailbericht, worden er geen berichten verzonden totdat deze zijn uitgeschakeld.
>Er wordt een waarschuwing weergegeven in het dashboard voor de sjabloon E-mail of E-mail.

Voor meer informatie bij het vormen van SMTP, verwijs naar de [Lijst van e-mailSMTP parametersectie](#list-of-email-smtp-parameters) .

### Geldigheidsperiode {#validity-period-parameters}

De **[!UICONTROL Validity period]** sectie bevat de volgende parameters:

![](assets/delivery-validity-period.png)

* **[!UICONTROL Explicitly set validity dates]**: Als dit vakje niet is ingeschakeld, moet u een duur invoeren in de velden **[!UICONTROL Delivery duration]** en in de **[!UICONTROL Resource validity limit]** velden.

   Schakel dit selectievakje in als u specifieke tijden en datums wilt definiëren.

   ![](assets/delivery-set-explicit-dates.png)

* **[!UICONTROL Delivery duration]** / **[!UICONTROL Validity limit for sending messages]**: Adobe Campaign verzendt de berichten die op de begindatum beginnen. In dit veld kunt u opgeven gedurende welke periode de berichten kunnen worden verzonden.

   >[!IMPORTANT]
   >
   >Zodra de upgrade naar de [Adobe Campagne Enhanced MTA](https://helpx.adobe.com/campaign/kb/campaign-enhanced-mta.html)is uitgevoerd, wordt de **[!UICONTROL Delivery duration]** parameter in uw campagneleveringen alleen gebruikt als deze op 3,5 dagen of minder is ingesteld. Als u een waarde definieert die hoger is dan 3,5 dagen, wordt hiermee geen rekening gehouden.

* **[!UICONTROL Resource validity duration]** / **[!UICONTROL Validity limit date for resources]**: dit veld wordt gebruikt voor geüploade bronnen , voornamelijk voor de spiegelpagina en afbeeldingen . De bronnen op deze pagina zijn gedurende een beperkte tijd geldig (om schijfruimte te besparen).
* **[!UICONTROL Mirror page management]**: De spiegelpagina is een HTML-pagina die online via een webbrowser toegankelijk is. De inhoud is identiek aan de e-mailinhoud. Standaard wordt de spiegelpagina gegenereerd als de koppeling wordt ingevoegd in de e-mailinhoud. In dit veld kunt u de manier wijzigen waarop deze pagina wordt gegenereerd:

   >[!IMPORTANT]
   >
   >Er moet HTML-inhoud zijn gedefinieerd voordat de e-mailpagina kan worden gemaakt.

   * **[!UICONTROL Generate the mirror page if a mirror link appears in the email content]** (standaardmodus): De spiegelpagina wordt geproduceerd als de verbinding in de postinhoud wordt opgenomen.
   * **Het genereren van de spiegelpagina** forceren: zelfs als geen verbinding aan de spiegelpagina in de berichten wordt opgenomen, zal de spiegelpagina worden gecreeerd.
   * **Genereer de spiegelpagina** niet: er wordt geen spiegelpagina gegenereerd, zelfs niet als de koppeling zich in de berichten bevindt.
   * **Genereer een spiegelpagina die alleen toegankelijk is met de bericht-id**: deze optie laat u tot de inhoud van de spiegelpagina, met verpersoonlijkingsinformatie, in het venster van het leveringslogboek toegang hebben.

>[!NOTE]
>
>De **[!UICONTROL Delivery duration]** parameter is niet van toepassing op transactieberichten. Zie [deze sectie](../../channels/using/about-transactional-messaging.md)voor meer informatie over transacties.

### Parameters bijhouden {#tracking-parameters}

De **[!UICONTROL Tracking]** sectie bevat de volgende parameters:

* **[!UICONTROL Activate tracking]**: Hiermee kunt u het bijhouden van berichten in- of uitschakelen. Als u de URL van elk bericht wilt bijhouden, gebruikt u het **[!UICONTROL Links]** pictogram in de actiebalk E-mailontwerp. Zie [Informatie over bijgehouden URL&#39;s](../../designing/using/links.md#about-tracked-urls).
* **[!UICONTROL Tracking validity limit]**: Hiermee kunt u de duur definiëren waarvoor de tracering wordt geactiveerd op de URL&#39;s.
* **[!UICONTROL Substitution URL for expired URLs]**: u kunt een URL invoeren naar een webpagina die wordt weergegeven wanneer de tekstspatiëring is verlopen.

### Geavanceerde parameters {#advanced-parameters}

De **[!UICONTROL Advanced parameters]** sectie bevat meerdere parameters.

In de eerste velden kunt u informatie invoeren die nodig is om e-mailkopteksten uit te werken. U kunt hier het antwoordadres en de tekst evenals het afzenderadres beheren (dat het gebied &quot;van:&quot;vult). Deze informatie kan worden gepersonaliseerd.

Klik op de knop rechts van het veld dat wordt gewijzigd en voeg vervolgens het verpersoonlijkingsveld, het inhoudsblok of dynamische tekst toe.

![](assets/advancedparameters.png)

Het invoegen en gebruiken van de verpersoonlijkingsinhoud wordt gedetailleerd beschreven in de documentatie voor [het aanpassen van e-mailinhoud](../../designing/using/personalization.md) .

#### Doelcontext {#target-context}

De het richten context staat u toe om een reeks lijsten te bepalen die voor e-mail het richten (in het scherm van de publieksdefinitie) en verpersoonlijking zullen worden gebruikt (bepalend verpersoonlijkingsgebieden in de HTML inhoudsredacteur).

#### Routering {#routing}

Dit gebied wijst op de verpletterende gebruikte wijze. Het verwijst naar een externe rekening. Dit kan bijvoorbeeld worden gebruikt als u een externe account wilt gebruiken die specifieke brandingconfiguraties bevat.

>[!NOTE]
>
>Externe accounts zijn toegankelijk via het menu **Beheer** > **Toepassingsinstellingen** > **Externe accounts** .

#### Voorbereiding {#preparation}

Het voorbereiden van berichten wordt gedetailleerd in de [Goedkeuring berichten](../../sending/using/preparing-the-send.md) sectie.

* **[!UICONTROL Typology]**: voordat berichten worden verzonden, moeten berichten worden voorbereid om de inhoud en configuratie te valideren. De verificatieregels die tijdens de voorbereidingsfase worden toegepast, worden in een **typologie** gedefinieerd. Voor e-mails betekent voorbereiding bijvoorbeeld dat het onderwerp, de URL&#39;s en afbeeldingen worden gecontroleerd. Selecteer de typologie die u wilt toepassen in dit veld.

   >[!NOTE]
   >
   >Typologieën, die toegankelijk zijn via het menu **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Typologies]** , worden weergegeven in de sectie [Typologieën](../../sending/using/about-typology-rules.md) .

* **[!UICONTROL Compute the label during delivery preparation]**: Hiermee kunt u de labelwaarde van de e-mail tijdens de voorbereidingsfase berekenen met gebruik van verpersoonlijkingsvelden, inhoudsblokken en dynamische tekst.

   Het is ook mogelijk om het leveringsetiket met gebeurtenisvariabelen te personaliseren die in de externe signaalactiviteit van het werkschema zijn verklaard. For more on this, refer to [this section](../../automating/using/calling-a-workflow-with-external-parameters.md).

* **[!UICONTROL Save SQL queries in the log]**: met deze optie kunt u SQL-querylogs toevoegen in het journaal tijdens de voorbereidingsfase.

#### Proefinstellingen {#proof-settings}

In deze sectie kunt u het standaardvoorvoegsel configureren voor gebruik in de onderwerpregel van de proefdruk. For more in this, refer to [this section](../../sending/using/sending-proofs.md).

### Lijst met SMTP-parameters voor e-mail {#list-of-email-smtp-parameters}

De **[!UICONTROL SMTP]** sectie bevat de volgende parameters:

* **[!UICONTROL Character encoding]**: Schakel het **[!UICONTROL Force encoding]** selectievakje in als u berichtcodering wilt forceren en selecteer vervolgens de gewenste codering.
* **[!UICONTROL Bounce mails]**: Standaard worden de stuiterende berichten ontvangen in de fout inbox van het platform (die in **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Email]** > **[!UICONTROL Configuration]** scherm wordt bepaald). Als u een specifiek foutadres voor een e-mailbericht wilt definiëren, voert u het adres in het **[!UICONTROL Error address]** veld in.
* **[!UICONTROL Additional SMTP headers]**: deze optie staat voor extra kopballen SMTP toe om aan uw berichten worden toegevoegd. Het script dat in het **[!UICONTROL Headers]** veld wordt ingevoerd, moet verwijzen naar één header per regel, in de vorm van **name:value**. Waarden worden indien nodig automatisch gecodeerd.

   >[!IMPORTANT]
   >
   >Het toevoegen van een manuscript voor het opnemen van extra kopballen SMTP is gereserveerd voor gevorderde gebruikers. De syntaxis van dit script moet voldoen aan de vereisten van dit inhoudstype: geen ongebruikte ruimte, geen lege regel, enz.

### Lijst van parameters voor toegangsvergunningen {#list-of-access-authorization-parameters}

De **[!UICONTROL Access authorization]** sectie bevat de volgende parameters:

* In het **[!UICONTROL Organizational unit]** veld kunt u de toegang tot deze e-mail beperken tot bepaalde gebruikers. De gebruikers die zijn gekoppeld aan de opgegeven eenheid of bovenliggende eenheden hebben lees- en schrijftoegang tot deze e-mail. Gebruikers die zijn gekoppeld aan onderliggende eenheden hebben alleen leestoegang tot deze e-mail.

   >[!NOTE]
   >
   >U kunt organisatorische eenheden configureren via het menu **Beheer** > **Gebruikers en beveiliging** .

* De velden **[!UICONTROL Created by]**, **[!UICONTROL Created]****[!UICONTROL Modified by]** en **[!UICONTROL Last modified]** velden worden automatisch ingevuld.
