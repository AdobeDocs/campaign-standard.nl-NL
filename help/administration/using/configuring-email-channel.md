---
title: E-mailkanaal configureren in Adobe Campaign Standard
description: Leer hoe u het e-mailkanaal in Adobe Campaign Standard configureert
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 76d70fd1-dd93-4a6d-b18c-96ebe5a27a7d
source-git-commit: 2e81a05b1b647991250d13d7d37f5da275a8db44
workflow-type: tm+mt
source-wordcount: '2749'
ht-degree: 55%

---

# E-mailkanaal configureren{#configuring-email-channel}

Als [Campaign-beheerder](../../administration/using/users-management.md#functional-administrators) kunt u e-mailkanaalinstellingen configureren. Deze geavanceerde instellingen omvatten de algemene parameters voor e-mailkanalen, accounts voor het routeren van e-mail, verwerkingsregels voor e-mail en e-maileigenschappen. Leer op deze pagina hoe u de standaardwaarden voor de algemene e-mail en het verzenden van parameters kunt bewerken.

## Parameters e-mailkanaal {#email-channel-parameters}

In het configuratiescherm voor e-mail kunt u de parameters voor het e-mailkanaal definiëren. Beheerders hebben toegang tot deze configuratie-instellingen via het menu **[!UICONTROL Administration]> [!UICONTROL Channels] > [!UICONTROL Email] >[!UICONTROL Configuration]**.

![](assets/channels_1.png)

* **Geautoriseerde maskervelden**

  In de sectie **[!UICONTROL Header parameters of sent emails]** worden de geautoriseerde e-mailadressen vermeld die u kunt gebruiken om e-mails naar uw ontvangers te verzenden (het adres van de afzender) en om hen in staat te stellen geautomatiseerde antwoorden zoals asynchrone onbezorgbare mails, out-of-office antwoorden, enz. terug te sturen. (foutadres).

  Adobe Campaign controleert tijdens de voorbereiding van berichten of de ingevoerde adressen geldig zijn. Deze werkwijze zorgt ervoor dat geen adressen worden gebruikt die problemen kunnen veroorzaken.

   * Zowel het adres van de afzender als het foutadres worden door Adobe ingesteld. Deze velden mogen niet leeg zijn.
   * U kunt deze velden niet bewerken. Als u een adres wilt bijwerken, neemt u contact op met de Klantenservice van Adobe.
   * Als u nog een adres wilt toevoegen, kunt u [Campagne](https://experienceleague.adobe.com/docs/control-panel/using/subdomains-and-certificates/setting-up-new-subdomain.html?lang=nl) om een nieuw subdomein in te stellen, of contact op te nemen met het team van de Zorg van de Adobe. Als u meerdere maskers gebruikt, worden deze door komma&#39;s van elkaar gescheiden.
   * Het is een goede praktijk om adressen te plaatsen gebruikend een ster zoals **@yourdomain.com**: hiermee kunt u elk adres gebruiken dat eindigt met uw subdomeinnaam.

* **Bezorging**

  De **[!UICONTROL Delivery reports ID]** wordt geleverd door de Klantenservice van Adobe. Deze identificeert elke instantie aan de hand van een bezorgings-id die in de technische bezorgingsrapporten wordt gebruikt.
  <!--The Technical Deliverability report is not accessible through the UI in ACS. It will be replaced with 250ok in the future (project starting).-->

* **Bezorgingsparameters**

  Adobe Campaign verzendt de berichten die beginnen op de begindatum.

  Wanneer een bericht in een levering wegens een tijdelijke fout of een zachte stuit wordt verworpen, probeert de Campagne opnieuw om dit bericht elke dag te verzenden. Gebruik de **[!UICONTROL Message delivery duration]** kan het veld waarin de tijdlijn wordt opgegeven tijdens nieuwe pogingen worden weergegeven.

  >[!IMPORTANT]
  >
  >**Deze parameter in Campaign wordt nu alleen gebruikt bij een instelling van 3,5 dagen of minder.** Als u een waarde definieert die hoger is dan 3,5 dagen, wordt hiermee geen rekening gehouden.

  Het veld **[!UICONTROL Online resources validity duration]** wordt gebruikt voor geüploade bronnen, voornamelijk voor de spiegelpagina en -afbeeldingen. De bronnen op deze pagina zijn gedurende een beperkte tijd geldig (om schijfruimte te besparen).

* **Hernieuwde pogingen**

  Voor tijdelijk niet bezorgde berichten wordt automatisch een nieuwe poging uitgevoerd. Zie [Hernieuwde pogingen na een tijdelijke leveringsfout](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure)voor meer informatie.

  >[!IMPORTANT]
  >
  >Het maximumaantal uit te voeren pogingen en de minimumvertraging tussen opnieuw proberen zijn nu gebaseerd op hoe goed IP zowel historisch als momenteel bij een bepaald domein uitvoert. De **[!UICONTROL Retry period]** en **[!UICONTROL Number of retries]** instellingen in Campagne worden genegeerd.

  <!--This section indicates how many retries should be performed the day after the send is started (**Number of retries**) and the minimum delay between retries (**Retry period**). By default, five retries are scheduled for the first day with a minimum interval of one hour, spread out over the 24 hours of the day. One retry per day is programmed after that and until the delivery deadline, which is defined in the **[!UICONTROL Delivery parameters]** section.-->

* **Parameters voor e-mailquarantaine**

  Voer in het veld **[!UICONTROL Time between two significant errors]** een waarde in om te definiëren hoe lang de toepassing wacht voordat de foutteller wordt verhoogd in het geval van een mail die tijdelijk niet kan worden bezorgd. De standaardwaarde is **1d**, voor 1 dag.

  Wanneer de waarde bij **[!UICONTROL Maximum number of errors before quarantine]** is bereikt, wordt het e-mailadres in quarantaine geplaatst. De standaardwaarde is **&quot;5&quot;**: het adres wordt in quarantined op de vijfde fout. Dit betekent dat het contact automatisch van volgende bezorgingen wordt uitgesloten.
  <!--Actually the way ACS works is that the address is already on the quarantine list on the first bounce, but with a different status meaning that the error count has started.-->

  Zie [Werken met quarantainebeheer](../../sending/using/understanding-quarantine-management.md) voor meer informatie over quarantaines.

## E-mailrouteringsaccounts {#email-routing-accounts}

Het externe account **[!UICONTROL Integrated email routing]** wordt standaard verschaft. Het bevat de technische parameters waarmee de applicatie e-mailberichten kan verzenden.

![](assets/channels_2.png)

Het accounttype moet altijd worden ingesteld op **[!UICONTROL Routing]**, het kanaal op **[!UICONTROL Email]** en de leveringsmodus op **[!UICONTROL Bulk delivery]**.

**Verwant onderwerp**:

[Externe accounts](../../administration/using/external-accounts.md)

## E-mailverwerkingsregels {#email-processing-rules}

Beheerders hebben toegang tot de **[!UICONTROL Email processing rules]** via het menu **[!UICONTROL Administration > Channels > Email]**.

>[!IMPORTANT]
>
>De e-maildomeinen en de MX-regels worden nu automatisch beheerd<!--by the Adobe Campaign Enhanced MTA (Message Transfer Agent)--> en kan niet worden gewijzigd.

* **DKIM (DomainKeys Identified Mail)** Ondertekening van e-mailverificatie wordt uitgevoerd voor alle berichten met alle domeinen. Het wordt niet ondertekend met **Afzender-id**, **DomainKeys**, of **S/MIME**.
* MX-regels passen uw doorvoer automatisch aan per domein op basis van uw eigen historische e-mailreputatie en de real-time feedback uit de domeinen waar u e-mails verzendt.

<!--Note that the email domains and the MX rules are now managed by the Adobe Campaign Enhanced MTA:
* **DKIM (DomainKeys Identified Mail)** email authentication signing is done by the Enhanced MTA for all messages with all domains. It does not sign with **Sender ID**, **DomainKeys**, or **S/MIME** unless otherwise specified at the Enhanced MTA level.
* The Enhanced MTA uses its own MX rules that allow it to customize your throughput by domain based on your own historical email reputation, and on the real-time feedback coming from the domains where you are sending emails.-->

### Stuitberichten {#bounce-mails}

De asynchrone, niet bezorgde mails worden nog steeds gekwalificeerd door het Campaign inMail-proces aan de hand van de **[!UICONTROL Bounce mails]**-regels.

Deze regels bevatten de lijst met tekenreeksen die door externe servers kunnen worden geretourneerd en waarmee u de fout (**Hard**, **Soft** of **Ignored**) kunt kwalificeren.

>[!IMPORTANT]
>
>De synchrone de foutenmeldingen van de leveringsmislukking worden nu gekwalificeerd door Adobe Campaign Verbeterde MTA, die het stuitertype en de kwalificatie bepaalt, en die informatie terugstuurt naar Campagne.

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

Gebruik de **[!UICONTROL Brand]** het merk te selecteren dat aan de levering is gekoppeld. Raadpleeg de sectie [Branding](../../administration/using/branding.md) voor meer informatie over het gebruik en de configuratie van merken.

In de **[!UICONTROL Campaign]** voert u de campagne in die aan de e-mail is gekoppeld.

U kunt ook een **[!UICONTROL Description]** toevoegen in het desbetreffende veld en de afbeelding bewerken die wordt weergegeven in de e-mailminiatuur in de lijsten.

### Parameters verzenden {#sending-parameters}

De sectie **[!UICONTROL Send]** is alleen beschikbaar voor e-mailsjablonen. Deze bevat de volgende parameters:

#### Parameters opnieuw {#retries-parameters}

Voor tijdelijk niet bezorgde berichten wordt automatisch een nieuwe poging uitgevoerd. Zie [Hernieuwde pogingen na een tijdelijke leveringsfout](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure)voor meer informatie.

>[!IMPORTANT]
>
>De minimale vertraging tussen pogingen en het maximumaantal uit te voeren pogingen zijn nu gebaseerd op hoe goed IP zowel historisch als momenteel bij een bepaald domein uitvoert. De **[!UICONTROL Retry period]** en **[!UICONTROL Max. number of retries]** instellingen in Campagne worden genegeerd.

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

Gebruik de **[!UICONTROL Enable SMTP test mode]** optie om het verzenden van e-mails via een SMTP-verbinding te testen zonder daadwerkelijk berichten te verzenden. De levering wordt verwerkt tot verbinding aan de server SMTP maar niet verzonden: voor elke ontvanger van de levering, verbindt de Campagne met de SMTP leverancierserver, voert SMTP RCPT aan bevel uit, en sluit de verbinding vóór het bevel SMTP DATA.

![](assets/smtp-test-mode.png)

Deze optie is beschikbaar voor e-mails en e-mailsjablonen.

Als u de optie voor de SMTP testmodus voor een e-mailsjabloon inschakelt, is deze optie ingeschakeld voor alle e-mailberichten die op basis van deze sjabloon worden gemaakt.

>[!IMPORTANT]
>
>Als deze optie is ingeschakeld voor een e-mailbericht, worden er geen berichten verzonden totdat deze is uitgeschakeld.
>Er wordt een waarschuwing weergegeven in het dashboard voor e-mails of e-mailsjablonen.

Raadpleeg de sectie [Lijst met SMTP-parameters voor e-mails](#list-of-email-smtp-parameters) voor meer informatie over het configureren van SMTP.

### Geldigheidsperiode {#validity-period-parameters}

De sectie **[!UICONTROL Validity period]** bevat de volgende parameters:

![](assets/delivery-validity-period.png)

* **[!UICONTROL Explicitly set validity dates]**: als dit vakje niet is ingeschakeld, moet u een tijdsduur invoeren in de velden **[!UICONTROL Delivery duration]** en **[!UICONTROL Resource validity limit]**.

  Schakel dit selectievakje in als u specifieke tijden en datums wilt definiëren.

  ![](assets/delivery-set-explicit-dates.png)

* **[!UICONTROL Delivery duration]** / **[!UICONTROL Validity limit for sending messages]**: Adobe Campaign begint met het verzenden van berichten op de startdatum. In dit veld kunt u opgeven gedurende welke periode de berichten kunnen worden verzonden.

  >[!IMPORTANT]
  >
  >**U kunt een waarde van maximaal 3,5 dagen definiëren.** Als u een waarde instelt die hoger is dan 3,5 dagen, wordt hiermee geen rekening gehouden.
  >
  >De parameter **[!UICONTROL Delivery duration]** is niet van toepassing op transactieberichten. Zie [deze sectie](../../channels/using/getting-started-with-transactional-msg.md)voor meer informatie over transactieberichten.

* **[!UICONTROL Resource validity duration]** / **[!UICONTROL Validity limit date for resources]**: dit veld wordt gebruikt voor geüploade bronnen, voornamelijk voor de spiegelpagina en -afbeeldingen. De bronnen op deze pagina zijn gedurende een beperkte tijd geldig (om schijfruimte te besparen).
* **[!UICONTROL Mirror page management]**: de spiegelpagina is een HTML-pagina die online via een webbrowser toegankelijk is. De content komt overeen met de content van de e-mail. Standaard wordt de spiegelpagina gegenereerd als de koppeling wordt ingevoegd in de e-mailcontent. Met dit veld wijzigt u de manier waarop deze pagina wordt gegenereerd:

   * **[!UICONTROL Generate the mirror page if a mirror link appears in the email content]** (standaardmodus): De spiegelpagina wordt geproduceerd als de koppeling in de e-mailcontent wordt geplaatst.
   * **Force the generation of the mirror page**: zelfs als geen koppeling naar de spiegelpagina in de berichten wordt opgenomen, wordt de spiegelpagina gemaakt.
   * **Do not generate the mirror page**: er wordt geen spiegelpagina gegenereerd, zelfs niet als de koppeling zich in de berichten bevindt.
   * **Generate a mirror page accessible using only the message ID**: met deze optie hebt u toegang tot de content van de spiegelpagina, met personalisatiegegevens, in het venster met het verzendingslog.

  >[!IMPORTANT]
  >
  >De spiegelpagina wordt alleen gegenereerd als er voor de e-mail een HTML-inhoud is gedefinieerd.
  >


### Parameters bijhouden {#tracking-parameters}

De sectie **[!UICONTROL Tracking]** bevat de volgende parameters:

* **[!UICONTROL Activate tracking]**: gebruik deze optie om URL-tracking van berichten te activeren/deactiveren. Als u de URL van elk bericht wilt traceren, gebruikt u het pictogram **[!UICONTROL Links]** in de actiebalk Email Designer. Zie [Informatie over getraceerde URL&#39;s](../../designing/using/links.md#about-tracked-urls).
* **[!UICONTROL Tracking validity limit]**: gebruik deze optie om de duur te bepalen waarvoor het volgen op URLs zal worden geactiveerd.
* **[!UICONTROL Substitution URL for expired URLs]**: gebruik deze optie om een URL in te voeren naar een fallback-webpagina: deze wordt weergegeven zodra de tekstspatiëring is verlopen.
* **[!UICONTROL Use tracking pixel at the top of email]**: gebruik deze optie als u de pixel die het beeld bijhoudt, boven in de e-mail wilt plaatsen in plaats van onderaan. Deze pixel bevindt zich standaard onder aan uw e-mailberichten. Als u grote berichten verzendt, kunt u deze pixel boven aan uw e-mails in plaats van onder aan de e-mail verplaatsen om het bijhouden van de gegevens te verbeteren. Anders kan de pixel voor het bijhouden van de berichten door sommige e-mailproviders worden geknipt.

### Geavanceerde parameters {#advanced-parameters}

De sectie **[!UICONTROL Advanced parameters]** bevat meerdere parameters.

In de eerste velden kunt u de informatie invoeren die nodig is om e-mailkopteksten uit te werken. U kunt hier het antwoordadres en de antwoordtekst beheren, evenals het adres van de afzender (in het veld Van). Deze informatie kan worden aangepast.

Klik op de knop rechts van het veld dat wordt gewijzigd en voeg vervolgens het personalisatieveld, het contentblok of de dynamische tekst toe.

![](assets/advancedparameters.png)

Het invoegen en gebruiken van de personalisatiecontent wordt gedetailleerd beschreven in de documentatie over het [aanpassen van e-mailcontent](../../designing/using/personalization.md).

#### Doelcontext {#target-context}

Gebruik de het richten context om een reeks lijsten te bepalen die voor e-mail het richten (in het scherm van de publieksdefinitie) en verpersoonlijking zullen worden gebruikt (bepalend verpersoonlijkingsgebieden in de HTML inhoudsredacteur).

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

* **[!UICONTROL Compute the label during delivery preparation]**: gebruik deze optie om de labelwaarde van de e-mail tijdens de voorbereidingsfase van het bericht te berekenen aan de hand van verpersoonlijkingsvelden, inhoudsblokken en dynamische tekst.

  Het is ook mogelijk om het bezorgingslabel te personaliseren met gebeurtenisvariabelen die in de externe-signalenactiviteit van de workflow zijn gedeclareerd. Raadpleeg [deze sectie](../../automating/using/calling-a-workflow-with-external-parameters.md) voor meer informatie.

* **[!UICONTROL Save SQL queries in the log]**: gebruik deze optie om SQL vraaglogboeken in het dagboek tijdens de voorbereidingsfase toe te voegen.

#### Proefinstellingen {#proof-settings}

In deze sectie kunt u het standaardvoorvoegsel configureren voor gebruik op de onderwerpregel van de proefberichten. Meer informatie over proefdrukken in [deze sectie](../../sending/using/sending-proofs.md).

### Lijst met SMTP-parameters voor e-mail {#list-of-email-smtp-parameters}

De sectie **[!UICONTROL SMTP]** bevat de volgende parameters:

* **[!UICONTROL Character encoding]**: schakel het selectievakje **[!UICONTROL Force encoding]** in als u berichtcodering wilt afdwingen en selecteer vervolgens de gewenste codering.
* **[!UICONTROL Bounce mails]**: standaard worden de teruggestuurde berichten ontvangen in de fouteninbox van het platform (gedefinieerd in het scherm **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Email]** > **[!UICONTROL Configuration]**). Als u een specifiek foutadres voor een e-mailbericht wilt definiëren, typt u dit adres in het veld **[!UICONTROL Error address]**.
* **[!UICONTROL Additional SMTP headers]**: met deze optie kunt u extra SMTP-kopteksten toevoegen aan uw berichten. Het script dat in het veld **[!UICONTROL Headers]** wordt ingevoerd, moet verwijzen naar één koptekst per regel, en wel in de notatie **name:value**. Waarden worden indien nodig automatisch gecodeerd.

  >[!IMPORTANT]
  >
  >Het toevoegen van een script voor het opnemen van extra SMTP-kopteksten is gereserveerd voor gevorderde gebruikers. De syntaxis van dit script moet voldoen aan de vereisten van dit type content: geen ongebruikte ruimte, geen lege regel, enz.

  Vanaf 1 juni 2024 moeten afzenders bij Google en Yahoo! afzenders verplichten te voldoen aan **Een-klik List-Unsubscribe**. De campagne steunt dit vermogen uit-van-de-doos voor leveringsmalplaatjes.

  Toepassen **Een-klik List-Unsubscribe** voor alle e-mailleveringen die geen template zijn, moet u de **[!UICONTROL Copy headers from delivery templates]** technische workflow. [Meer informatie](technical-workflows.md)

  >[!CAUTION]
  >
  >Als u de koptekstwaarde in het dialoogvenster **[!UICONTROL Additional SMTP headers]** van uw e-mailsjablonen kan de compatibiliteit met de **Een-klik List-Unsubscribe** eis van Google en Yahoo!

### Lijst van parameters voor toegangsvergunningen {#list-of-access-authorization-parameters}

De sectie **[!UICONTROL Access authorization]** bevat de volgende parameters:

* De **[!UICONTROL Organizational unit]** wordt gebruikt om toegang tot deze e-mail tot bepaalde gebruikers te beperken. De gebruikers die zijn gekoppeld aan de opgegeven eenheid of bovenliggende eenheden hebben lees- en schrijftoegang tot deze e-mail. Gebruikers die zijn gekoppeld aan onderliggende eenheden hebben alleen leestoegang tot deze e-mail.

  >[!NOTE]
  >
  >U kunt organisatorische eenheden configureren via het menu **Administration** > **Users &amp; Security**.

* De velden **[!UICONTROL Created by]**, **[!UICONTROL Created]****[!UICONTROL Modified by]** en **[!UICONTROL Last modified]** worden automatisch ingevuld.

## Oudere instellingen {#legacy-settings}

Als u **NOT** Als u de meest recente versie van Campagne uitvoert, zijn de hieronder beschreven parameters en UI-secties nog steeds op u van toepassing.

### Opnieuw {#legacy-retries}

De **[!UICONTROL Retries]** in de [Menu Configuratie](#email-channel-parameters) en in de [Parameters verzenden](#retries-parameters) van de e-maileigenschappen geven aan hoeveel pogingen moeten worden uitgevoerd op de dag nadat de verzending is gestart (**[!UICONTROL Number of retries]** / **[!UICONTROL Max. number of retries]**) en de minimale vertraging tussen pogingen (**[!UICONTROL Retry period]**).

Het aantal pogingen kan globaal worden veranderd (contacteer uw Adobe technische beheerder) of voor elke levering of leveringsmalplaatje.

Door gebrek, zijn vijf herpogingen gepland voor de eerste dag met een minimuminterval van één uur, uitgespreid zich over de 24 uren van de dag. Na die datum en tot de uiterste datum van levering, die globaal in het **[!UICONTROL Delivery parameters]** van de **[!UICONTROL Configuration]** of in het menu **[!UICONTROL Validity period]** op het niveau van de levering (zie de [Leveringsduur](#legacy-delivery-duration) hieronder).

### Leveringsduur {#legacy-delivery-duration}

Gebruik de **[!UICONTROL Message delivery duration]** in de [Menu Configuratie](#email-channel-parameters) om het tijdkader te specificeren waarin om het even welk bericht in de levering die een tijdelijke fout of zachte stuit ontmoet opnieuw zal worden geprobeerd.

Gebruik de **[!UICONTROL Delivery duration]** of **[!UICONTROL Validity limit for sending messages]** in de [Geldigheidsperiode](#validity-period-parameters) om de duur aan te geven gedurende welke de berichten kunnen worden verzonden.

### E-mailverwerkingsregels {#legacy-email-processing-rules}

De **[!UICONTROL MX management]**, **[!UICONTROL Bounce mails]** en **[!UICONTROL Domain management]** de regels kunnen door beheerders door **[!UICONTROL Administration > Channels > Email > Email processing rules]** -menu. [Meer informatie](#email-processing-rules)

### Bounce mail-kwalificatie {#legacy-bounce-mail-qualification}

Als u de verschillende grenzen en de bijbehorende fouttypen en redenen wilt weergeven, klikt u op de knop **Adobe** logo, in de linkerbovenhoek, selecteert u **[!UICONTROL Administration > Channels > Quarantines > Message qualification]**.

Stuiterwaarden kunnen de volgende kwalificatiestatus hebben:

* **[!UICONTROL To qualify]**: de stuiterende post moet worden gekwalificeerd. De kwalificatie moet door het leveringsteam worden gedaan om ervoor te zorgen dat de platformleverbaarheid correct functioneert. Zolang het niet wordt gekwalificeerd, wordt de stuiterende post niet gebruikt om de lijst van e-mailverwerkingsregels te verrijken.
* **[!UICONTROL Keep]**: de stuiterende post werd gekwalificeerd en zal door worden gebruikt **Update voor leverbaarheid** te vergelijken met bestaande regels voor e-mailverwerking en de lijst te verrijken.
* **[!UICONTROL Ignore]**: de stuiterende post werd gekwalificeerd maar zal niet door **Update voor leverbaarheid** workflow. Het wordt dus niet naar de clientinstanties verzonden.

>[!NOTE]
>
>In het geval van een stroomonderbreking van ISP, zullen de e-mails die door Campaign worden verzonden verkeerd als stegels worden gemerkt. U moet de stuiterkwalificatie bijwerken om dit te corrigeren. [Meer informatie](../../administration/using/update-bounce-qualification.md).

<!--Bounces are qualified through the **[!UICONTROL Bounce mails]** processing rule. For more on accessing this rule, refer to this [section](#legacy-bounce-mail-qualification).-->

### Rapportage van geleverde indicatoren {#legacy-delivered-status-report}

In de **[!UICONTROL Summary]** de weergave van elk bericht, **[!UICONTROL Delivered]** het percentage stijgt geleidelijk gedurende de gehele geldigheidsperiode van de levering, naarmate de zachte en harde schokken worden gemeld.

Zachte-stuiterende berichten tonen zoals **[!UICONTROL Failed]** op de eerste dag na de levering. Deze berichten worden elke dag opnieuw geprobeerd, tot de geldigheidsperiode van de levering beëindigt.
