---
title: E-mailkanaal configureren in Adobe Campaign Standard
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
source-git-commit: 1efcd646f4af86175b3b09b53185c792cb4cf7dd
workflow-type: tm+mt
source-wordcount: '2331'
ht-degree: 100%

---


# E-mailkanaal configureren{#configuring-email-channel}

Als [Campaign-beheerder](../../administration/using/users-management.md#functional-administrators) kunt u e-mailkanaalinstellingen configureren. Deze geavanceerde instellingen omvatten de algemene parameters voor e-mailkanalen, accounts voor het routeren van e-mail, verwerkingsregels voor e-mail en e-maileigenschappen. Op deze pagina leert u hoe u de standaardwaarden voor de algemene e-mail- en verzendparameters kunt bewerken.

Sommige e-mailinstellingen worden nu beheerd door de Adobe Campaign Enhanced MTA. Daarom geldt het volgende:
* Sommige configuraties in de gebruikersinterface van de Campaign worden niet meer toegepast:
   * De **[!UICONTROL Retries]**-instellingen in het menu [Configuration](#email-channel-parameters) en in de [Sending parameters](#retries-parameters) van de e-maileigenschappen.
   * De regels voor **[!UICONTROL MX management]** en **[!UICONTROL Domain management]** in het menu [Email processing rules](#email-processing-rules).

* Andere parameters worden nu gedeeltelijk beheerd door de Enhanced MTA, maar bepaalde configuratie kan nog binnen Campaign worden uitgevoerd. Het gaat om de volgende instellingen:
   * De parameter **[!UICONTROL Message delivery duration]** in het menu **[!UICONTROL Configuration]**. Zie [deze sectie](#email-channel-parameters)voor meer informatie.
   * De parameter **[!UICONTROL Delivery duration]** of **[!UICONTROL Validity limit for sending messages]** in de sectie **[!UICONTROL Validity period]**. Zie [deze sectie](#validity-period-parameters)voor meer informatie.
   * De regels **[!UICONTROL Bounce mails]** in de **[!UICONTROL Email processing rules]**. Zie [deze sectie](#email-processing-rules)voor meer informatie.

## Parameters voor e-mailkanaal {#email-channel-parameters}

In het configuratiescherm voor e-mail kunt u de parameters voor het e-mailkanaal definiëren. Beheerders hebben toegang tot deze configuratie-instellingen via het menu **[!UICONTROL Administration]>[!UICONTROL Channels]>[!UICONTROL Email]>[!UICONTROL Configuration]**.

![](assets/channels_1.png)

* **Geautoriseerde maskervelden**

   In de sectie **[!UICONTROL Header parameters of sent emails]** worden de geautoriseerde e-mailadressen vermeld die u kunt gebruiken om e-mails naar uw ontvangers te verzenden (het adres van de afzender) en om hen in staat te stellen geautomatiseerde antwoorden zoals asynchrone onbezorgbare mails, out-of-office antwoorden, enz. terug te sturen. (foutadres).  Adobe Campaign controleert tijdens de voorbereiding van berichten of de ingevoerde adressen geldig zijn. Deze werkwijze zorgt ervoor dat geen adressen worden gebruikt die problemen kunnen veroorzaken.
   * Zowel het adres van de afzender als het foutadres worden door Adobe ingesteld. Deze velden mogen niet leeg zijn.
   * U kunt deze velden niet bewerken. Als u een adres wilt bijwerken, neemt u contact op met de Klantenservice van Adobe.
   * Als u nog een adres wilt toevoegen, gebruikt u het [Configuratiescherm](https://docs.adobe.com/content/help/nl/control-panel/using/subdomains-and-certificates/setting-up-new-subdomain.html) om een nieuw subdomein in te stellen of neemt u contact op met de Klantenservice van Adobe. Als u meerdere maskers gebruikt, worden deze door komma&#39;s van elkaar gescheiden.
   * Het is aan te raden adressen in te stellen met een ster zoals *@yourdomain.com: dan kunt u elk adres gebruiken dat eindigt met uw subdomeinnaam.

* **Bezorging**

   De **[!UICONTROL Delivery reports ID]** wordt geleverd door de Klantenservice van Adobe. Deze identificeert elke instantie aan de hand van een bezorgings-id die in de technische bezorgingsrapporten wordt gebruikt.
   <!--The Technical Deliverability report is not accessible through the UI in ACS. It will be replaced with 250ok in the future (project starting).-->

* **Bezorgingsparameters**

   Adobe Campaign begint met het verzenden van de berichten op de startdatum. In het veld **[!UICONTROL Message delivery duration]** kunt u het tijdkader voor hernieuwde pogingen opgeven voor berichten in de bezorging die op een tijdelijke fout stuiten of tijdelijk niet bezorgd kunnen worden.

   >[!IMPORTANT]
   >
   >**Deze parameter in Campaign wordt nu alleen gebruikt bij een instelling van 3,5 dagen of minder.** Als u een waarde definieert die hoger is dan 3,5 dagen, wordt er geen rekening mee gehouden omdat deze waarde nu wordt beheerd door de Adobe Campaign Enhanced MTA.

   Het veld **[!UICONTROL Online resources validity duration]** wordt gebruikt voor geüploade bronnen, voornamelijk voor de spiegelpagina en -afbeeldingen. De bronnen op deze pagina zijn gedurende een beperkte tijd geldig (om schijfruimte te besparen).

* **Hernieuwde pogingen**

   Voor tijdelijk niet bezorgde berichten wordt automatisch een nieuwe poging uitgevoerd. Zie [Hernieuwde pogingen na een tijdelijke leveringsfout](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure)voor meer informatie.

   >[!NOTE]
   >
   >Het maximumaantal hernieuwde pogingen en de minimale vertraging tussen pogingen worden nu beheerd door de Adobe Campaign Enhanced MTA, op basis van hoe goed een IP presteert op een bepaald domein, zowel in het verleden als nu. De instellingen voor **Retries** in Campaign worden genegeerd.

   <!--This section indicates how many retries should be performed the day after the send is started (**Number of retries**) and the minimum delay between retries (**Retry period**). By default, five retries are scheduled for the first day with a minimum interval of one hour, spread out over the 24 hours of the day. One retry per day is programmed after that and until the delivery deadline, which is defined in the **[!UICONTROL Delivery parameters]** section.-->

* **Parameters voor e-mailquarantaine**

   Voer in het veld **[!UICONTROL Time between two significant errors]** een waarde in om te definiëren hoe lang de toepassing wacht voordat de foutteller wordt verhoogd in het geval van een mail die tijdelijk niet kan worden bezorgd. De standaardwaarde is **1d**, voor 1 dag.

   Wanneer de waarde bij **[!UICONTROL Maximum number of errors before quarantine]** is bereikt, wordt het e-mailadres in quarantaine geplaatst. De standaardwaarde is **5**: het adres wordt na de vijfde fout in quarantaine geplaatst. Dit betekent dat het contact automatisch van volgende bezorgingen wordt uitgesloten.
   <!--Actually the way ACS works is that the address is already on the quarantine list on the first bounce, but with a different status meaning that the error count has started.-->

   Zie [Werken met quarantainebeheer](../../sending/using/understanding-quarantine-management.md) voor meer informatie over quarantaines.

## E-mailrouteringsaccounts {#email-routing-accounts}

Het externe account **[!UICONTROL Integrated email routing]** wordt standaard verschaft. Het bevat de technische parameters waarmee de applicatie e-mailberichten kan verzenden.

![](assets/channels_2.png)

Het accounttype moet altijd worden ingesteld op **[!UICONTROL Routing]**, het kanaal op **[!UICONTROL Email]** en de leveringsmodus op **[!UICONTROL Bulk delivery]**.

**Verwant onderwerp**:

[Externe accounts](../../administration/using/external-accounts.md)

## Regels voor e-mailverwerking {#email-processing-rules}

Beheerders hebben toegang tot de **[!UICONTROL Email processing rules]** via het menu **[!UICONTROL Administration > Channels > Email]**.

De e-maildomeinen en de MX-regels worden nu door de Adobe Campaign Enhanced MTA beheerd:
* **DKIM (DomainKeys Identified Mail)**-e-mailverificatie wordt ondertekend door de Enhanced MTA voor alle berichten met alle domeinen. Deze ondertekent niet met **Afzender-id**, **DomainKeys** of **S/MIME**, tenzij anderszins opgegeven op Enhanced MTA-niveau.
* De Enhanced MTA gebruikt eigen MX-regels zodat deze agent uw doorvoer per domein kan aanpassen op basis van uw eigen historische e-mailreputatie en op basis van realtime-feedback van de domeinen waar u e-mails naartoe stuurt.

### Niet bezorgde mails {#bounce-mails}

De asynchrone, niet bezorgde mails worden nog steeds gekwalificeerd door het Campaign inMail-proces aan de hand van de **[!UICONTROL Bounce mails]**-regels.

Deze regels bevatten de lijst met tekenreeksen die door externe servers kunnen worden geretourneerd en waarmee u de fout (**Hard**, **Soft** of **Ignored**) kunt kwalificeren.

>[!NOTE]
>
>Voor synchrone foutberichten betreffende mislukte bezorging, bepaalt de Adobe Campaign Enhanced MTA het type bezorgingsfout en de kwalificatie en stuurt deze informatie terug naar Campaign.

Zie deze [sectie](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification)voor meer informatie over de kwalificatie voor niet bezorgde mails.

<!--Because they are now managed by the Enhanced MTA, the bounce qualifications in the Campaign **[!UICONTROL Message qualification]** table are no longer used. For more on bounce mail qualification, see this [section](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification).

### Management of email domains {#managing-email-domains}

The email domains are now managed by the Adobe Campaign Enhanced MTA. The Adobe Campaign **[!UICONTROL Domain management]** rules are no longer used.

**DKIM (DomainKeys Identified Mail)** email authentication signing is done by the Enhanced MTA for all messages with all domains. It does not sign with **Sender ID**, **DomainKeys**, or **S/MIME** unless otherwise specified at the Enhanced MTA level.

### MX management {#mx-management}

The MX rules are now managed by the Adobe Campaign Enhanced MTA. The Adobe Campaign **[!UICONTROL MX management]** delivery throughput rules are no longer used.

The Enhanced MTA uses its own MX rules that allow it to customize your throughput by domain based on your own historical email reputation, and on the real-time feedback coming from the domains where you are sending emails.-->

## Lijst met e-maileigenschappen {#list-of-email-properties}

In deze sectie wordt de lijst met parameters besproken die beschikbaar is in het eigenschappenscherm van een e-mail of e-mailsjabloon.

>[!NOTE]
>
>Sommige parameters zijn alleen beschikbaar in sjablonen. [Uw toestemmingen bepalen](../../administration/using/users-management.md) tot welke parameters u toegang hebt.

Met de knop **[!UICONTROL Edit properties]** kunt u de eigenschappen van een e-mail of een e-mailsjabloon bewerken.

![](assets/delivery_options_1.png)

### Algemene parameters {#general-parameters}

Identificeer de e-mail met behulp van de velden **[!UICONTROL Label]** en **[!UICONTROL ID]** boven aan het scherm met e-mailparameters. Deze informatie verschijnt in de interface, maar de ontvangers kunnen deze niet zien.

![](assets/delivery_options_2.png)

>[!IMPORTANT]
>
>De id moet uniek zijn.

In het veld **[!UICONTROL Brand]** kunt u het merk selecteren dat aan de bezorging is gekoppeld. Raadpleeg de sectie [Branding](../../administration/using/branding.md) voor meer informatie over het gebruik en de configuratie van merken.

In het veld **[!UICONTROL Campaign]** kunt u de campagne invoeren die aan de e-mail is gekoppeld.

U kunt ook een **[!UICONTROL Description]** toevoegen in het desbetreffende veld en de afbeelding bewerken die wordt weergegeven in de e-mailminiatuur in de lijsten.

### Parameters voor verzending {#sending-parameters}

De sectie **[!UICONTROL Send]** is alleen beschikbaar voor e-mailsjablonen. Deze bevat de volgende parameters:

#### Parameters voor hernieuwde pogingen{#retries-parameters}

Voor tijdelijk niet bezorgde berichten wordt automatisch een nieuwe poging uitgevoerd. Zie [Hernieuwde pogingen na een tijdelijke leveringsfout](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure)voor meer informatie.

>[!NOTE]
>
>De minimale vertraging tussen hernieuwde pogingen en het maximumaantal hernieuwde pogingen worden nu beheerd door Adobe Campaign Enhanced MTA, op basis van hoe goed een IP presteert op een bepaald domein, zowel in het verleden als nu. De Campaign-instellingen voor **Hernieuwde pogingen** worden genegeerd.

<!--This section indicates how many retries should be performed the day after the send is started ( **[!UICONTROL Max. number of retries]** ) and the minimum delay between retries ( **[!UICONTROL Retry period]** ).

By default, five retries are scheduled for the first day with a minimum interval of one hour, spread out over the 24 hours of the day. One retry per day is programmed after that and until the delivery deadline, which is defined in the [Validity period parameters](#validity-period-parameters) section.

The number of retries can be changed globally (contact your Adobe technical administrator) or for each delivery or delivery template.-->

De **instelling voor de bezorgingsduur** (gedefinieerd in de sectie [Validity period parameters](#validity-period-parameters)) **die in Campaign is ingesteld, wordt gerespecteerd, maar slechts tot maximaal 3,5 dagen**. Op dat punt wordt elk bericht in de wachtrij Hernieuwde pogingen verwijderd uit deze wachtrij en teruggestuurd als onbezorgbaar. Raadpleeg deze [sectie](../../sending/using/understanding-delivery-failures.md#about-delivery-failures) voor meer informatie over bezorgingsfouten.

#### Parameters voor e-mailindeling {#email-format-parameters}

U kunt de indeling van de te verzenden e-mails configureren. Er zijn drie opties beschikbaar:

* **Use recipient preferences** (standaardmodus): de berichtindeling wordt gedefinieerd op basis van de data die zijn opgeslagen in het profiel van de ontvanger en worden standaard opgeslagen in het veld **Email format** (@emailFormat). Als een ontvanger berichten in een bepaalde indeling wenst te ontvangen, wordt deze indeling gebruikt. Als het veld niet is ingevuld, wordt een multipart-alternative bericht verzonden (zie hieronder).
* **Let recipient mail client choose the most appropriate format (multipart-alternative)**: het bericht bevat beide indelingen: tekst en HTML. De indeling die bij ontvangst wordt weergegeven, is afhankelijk van de configuratie van de e-mailsoftware van de ontvanger (multipart-alternative).

   >[!IMPORTANT]
   >
   >Deze optie bevat beide versies van het bericht. Het beïnvloedt daarom de bezorgingsdoorvoer, omdat de berichtgrootte groter is.

* **Send all messages in text format**: het bericht wordt verzonden in de tekstindeling. De HTML-indeling wordt niet verzonden, maar wordt alleen voor de spiegelpagina gebruikt wanneer de ontvanger op de koppeling in het bericht klikt.

#### SMTP-testmodus {#smtp-test-mode}

Met de optie **[!UICONTROL Enable SMTP test mode]** kunt u het verzenden van e-mails via een SMTP-verbinding testen zonder dat u daadwerkelijk berichten verzendt.
De berichten worden verwerkt tot de verbinding met de SMTP-server tot stand is gebracht, maar ze worden niet verzonden.

![](assets/smtp-test-mode.png)

Deze optie is beschikbaar voor e-mails en e-mailsjablonen.

Als u de optie voor de SMTP testmodus voor een e-mailsjabloon inschakelt, is deze optie ingeschakeld voor alle e-mailberichten die op basis van deze sjabloon worden gemaakt.

>[!IMPORTANT]
>
>Als deze optie is ingeschakeld voor een e-mailbericht, worden er geen berichten verzonden totdat deze is uitgeschakeld.
>Er wordt een waarschuwing weergegeven in het dashboard voor e-mails of e-mailsjablonen.

Raadpleeg de sectie [Lijst met SMTP-parameters voor e-mails](#list-of-email-smtp-parameters) voor meer informatie over het configureren van SMTP.

### Parameters voor geldigheidsperiode {#validity-period-parameters}

De sectie **[!UICONTROL Validity period]** bevat de volgende parameters:

![](assets/delivery-validity-period.png)

* **[!UICONTROL Explicitly set validity dates]**: als dit vakje niet is ingeschakeld, moet u een tijdsduur invoeren in de velden **[!UICONTROL Delivery duration]** en **[!UICONTROL Resource validity limit]**.

   Schakel dit selectievakje in als u specifieke tijden en datums wilt definiëren.

   ![](assets/delivery-set-explicit-dates.png)

* **[!UICONTROL Delivery duration]** / **[!UICONTROL Validity limit for sending messages]**: Adobe Campaign begint met het verzenden van berichten op de startdatum. In dit veld kunt u opgeven gedurende welke tijdsduur de berichten kunnen worden verzonden.

   >[!IMPORTANT]
   >
   >Deze parameter wordt nu beheerd door de Adobe Campaign Enhanced MTA. **U kunt een waarde van maximaal 3,5 dagen definiëren.** Als u een waarde definieert die hoger is dan 3,5 dagen, wordt hiermee geen rekening gehouden.

* **[!UICONTROL Resource validity duration]** / **[!UICONTROL Validity limit date for resources]**: dit veld wordt gebruikt voor geüploade bronnen, voornamelijk voor de spiegelpagina en -afbeeldingen. De bronnen op deze pagina zijn gedurende een beperkte tijd geldig (om schijfruimte te besparen).
* **[!UICONTROL Mirror page management]**: de spiegelpagina is een HTML-pagina die online via een webbrowser toegankelijk is. De content komt overeen met de content van de e-mail. Standaard wordt de spiegelpagina gegenereerd als de koppeling wordt ingevoegd in de e-mailcontent. In dit veld kunt u de manier wijzigen waarop deze pagina wordt gegenereerd:

   >[!IMPORTANT]
   >
   >Er moet HTML-content zijn gedefinieerd voordat de spiegelpagina kan worden gemaakt.

   * **[!UICONTROL Generate the mirror page if a mirror link appears in the email content]** (standaardmodus): De spiegelpagina wordt geproduceerd als de koppeling in de e-mailcontent wordt geplaatst.
   * **Force the generation of the mirror page**: zelfs als geen koppeling naar de spiegelpagina in de berichten wordt opgenomen, wordt de spiegelpagina gemaakt.
   * **Do not generate the mirror page**: er wordt geen spiegelpagina gegenereerd, zelfs niet als de koppeling zich in de berichten bevindt.
   * **Generate a mirror page accessible using only the message ID**: met deze optie hebt u toegang tot de content van de spiegelpagina, met personalisatiegegevens, in het venster met het verzendingslog.

>[!NOTE]
>
>De parameter **[!UICONTROL Delivery duration]** is niet van toepassing op transactieberichten. Zie [deze sectie](../../channels/using/getting-started-with-transactional-msg.md)voor meer informatie over transactieberichten.

### Parameters voor tracking {#tracking-parameters}

De sectie **[!UICONTROL Tracking]** bevat de volgende parameters:

* **[!UICONTROL Activate tracking]**: hiermee kunt u de tracking van bericht-URL&#39;s in- of uitschakelen. Als u de URL van elk bericht wilt traceren, gebruikt u het pictogram **[!UICONTROL Links]** in de actiebalk Email Designer. Zie [Informatie over getraceerde URL&#39;s](../../designing/using/links.md#about-tracked-urls).
* **[!UICONTROL Tracking validity limit]**: hiermee kunt u definiëren hoe lang tracking geactiveerd blijft voor de URL&#39;s.
* **[!UICONTROL Substitution URL for expired URLs]**: u kunt een URL invoeren naar een webpagina die wordt weergegeven wanneer tracking is verlopen.

### Geavanceerde parameters {#advanced-parameters}

De sectie **[!UICONTROL Advanced parameters]** bevat meerdere parameters.

In de eerste velden kunt u de informatie invoeren die nodig is om e-mailkopteksten uit te werken. U kunt hier het antwoordadres en de antwoordtekst beheren, evenals het adres van de afzender (in het veld Van). Deze informatie kan worden aangepast.

Klik op de knop rechts van het veld dat wordt gewijzigd en voeg vervolgens het personalisatieveld, het contentblok of de dynamische tekst toe.

![](assets/advancedparameters.png)

Het invoegen en gebruiken van de personalisatiecontent wordt gedetailleerd beschreven in de documentatie over het [aanpassen van e-mailcontent](../../designing/using/personalization.md).

#### Targetcontext {#target-context}

De targetingcontext maakt het mogelijk om een reeks tabellen in te stellen die wordt gebruikt voor e-mailtargeting (in het scherm voor doelgroepdefinitie) en -personalisatie (definiëren van personalisatievelden in de HTML-contenteditor).

#### Routering {#routing}

Dit veld verwijst naar de gebruikte routeringsmodus. Het verwijst naar een extern account. Dit kan bijvoorbeeld worden gebruikt als u een extern account wilt gebruiken dat specifieke brandingconfiguraties bevat.

>[!NOTE]
>
>Externe accounts zijn toegankelijk via het menu **Administration** > **Application settings** > **External accounts**.

#### Voorbereiding {#preparation}

Het voorbereiden van berichten wordt uitgelegd in de sectie [Berichten goedkeuren](../../sending/using/preparing-the-send.md).

* **[!UICONTROL Typology]**: voordat berichten worden verzonden, moeten deze worden voorbereid om de content en configuratie te valideren. De verificatieregels die tijdens de voorbereidingsfase worden toegepast, worden in een **typologie** gedefinieerd. Voor e-mails betekent voorbereiding bijvoorbeeld dat het onderwerp, de URL&#39;s en afbeeldingen gecontroleerd worden. Selecteer in dit veld de typologie die u wilt toepassen.

   >[!NOTE]
   >
   >Typologieën zijn toegankelijk via het menu **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Typologies]** en worden in [deze sectie](../../sending/using/about-typology-rules.md) beschreven.

* **[!UICONTROL Compute the label during delivery preparation]**: hiermee kunt u de labelwaarde van de e-mail berekenen tijdens de voorbereidingsfase met gebruik van personalisatievelden, contentblokken en dynamische tekst.

   Het is ook mogelijk om het bezorgingslabel te personaliseren met gebeurtenisvariabelen die in de externe-signalenactiviteit van de workflow zijn gedeclareerd. Raadpleeg [deze sectie](../../automating/using/calling-a-workflow-with-external-parameters.md) voor meer informatie.

* **[!UICONTROL Save SQL queries in the log]**: met deze optie kunt u tijdens de voorbereidingsfase SQL-querylogs toevoegen aan het rapport.

#### Proefinstellingen {#proof-settings}

In deze sectie kunt u het standaardvoorvoegsel configureren voor gebruik in de onderwerpregel van de proef. Raadpleeg [deze sectie](../../sending/using/sending-proofs.md) voor meer informatie.

### Lijst met SMTP-parameters voor e-mails {#list-of-email-smtp-parameters}

De sectie **[!UICONTROL SMTP]** bevat de volgende parameters:

* **[!UICONTROL Character encoding]**: schakel het selectievakje **[!UICONTROL Force encoding]** in als u berichtcodering wilt afdwingen en selecteer vervolgens de gewenste codering.
* **[!UICONTROL Bounce mails]**: standaard worden de teruggestuurde berichten ontvangen in de fouteninbox van het platform (gedefinieerd in het scherm **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Email]** > **[!UICONTROL Configuration]**). Als u een specifiek foutadres voor een e-mailbericht wilt definiëren, typt u dit adres in het veld **[!UICONTROL Error address]**.
* **[!UICONTROL Additional SMTP headers]**: met deze optie kunt u extra SMTP-kopteksten toevoegen aan uw berichten. Het script dat in het veld **[!UICONTROL Headers]** wordt ingevoerd, moet verwijzen naar één koptekst per regel, en wel in de notatie **name:value**. Waarden worden indien nodig automatisch gecodeerd.

   >[!IMPORTANT]
   >
   >Het toevoegen van een script voor het opnemen van extra SMTP-kopteksten is gereserveerd voor gevorderde gebruikers. De syntaxis van dit script moet voldoen aan de vereisten van dit type content: geen ongebruikte ruimte, geen lege regel, enz.

### Lijst van parameters voor toegang{#list-of-access-authorization-parameters}

De sectie **[!UICONTROL Access authorization]** bevat de volgende parameters:

* In het veld **[!UICONTROL Organizational unit]** kunt u de toegang tot deze e-mail beperken tot bepaalde gebruikers. De gebruikers die zijn gekoppeld aan de opgegeven eenheid of bovenliggende eenheden hebben lees- en schrijftoegang tot deze e-mail. Gebruikers die zijn gekoppeld aan onderliggende eenheden hebben alleen leestoegang tot deze e-mail.

   >[!NOTE]
   >
   >U kunt organisatorische eenheden configureren via het menu **Administration** > **Users &amp; Security**.

* De velden **[!UICONTROL Created by]**, **[!UICONTROL Created]****[!UICONTROL Modified by]** en **[!UICONTROL Last modified]** worden automatisch ingevuld.
