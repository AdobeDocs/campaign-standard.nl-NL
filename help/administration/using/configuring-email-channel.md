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
source-git-commit: 9163a375a4d2345e94a62e38475cb90bd203ce48

---


# E-mailkanaal configureren{#configuring-email-channel}

## Parameters e-mailkanaal {#email-channel-parameters}

In het configuratiescherm voor e-mail kunt u de parameters voor het e-mailkanaal definiëren.

![](assets/channels_1.png)

* **Koptekstparameters van verzonden e-mails**

   In deze sectie kunt u opgeven **[!UICONTROL masks]** welke gegevens zijn geautoriseerd voor het verzendadres en het foutadres. Indien nodig, kunnen deze maskers met komma&#39;s worden gescheiden. Deze configuratie is optioneel. Wanneer deze velden worden ingevoerd, controleert Adobe Campagne tijdens het voorbereiden van berichten of de ingevoerde adressen geldig zijn. Deze werkende wijze zorgt ervoor dat geen adressen worden gebruikt die leveringskwesties konden teweegbrengen. De adressen van de levering moeten op de leveringsserver worden gevormd.

* **Leverbaarheid**

   Deze id wordt geleverd door ondersteuning. Leverbaarheidsrapporten moeten correct werken.

* **Leveringsparameters**

   Adobe Campaign verzendt de berichten die op de begindatum beginnen. In het **[!UICONTROL Message delivery duration]** veld kunt u opgeven gedurende welke periode de berichten kunnen worden verzonden.

   Het **[!UICONTROL Online resources validity duration]** veld wordt gebruikt voor geüploade bronnen, voornamelijk voor de spiegelpagina en afbeeldingen. De bronnen op deze pagina zijn gedurende een beperkte tijd geldig (om schijfruimte te besparen).

* **Opnieuw**

   Voor tijdelijk onafgeleverde berichten moet u het opnieuw proberen. Deze sectie geeft aan hoeveel pogingen moeten worden uitgevoerd op de dag nadat het verzenden is gestart (**Aantal pogingen**) en de minimale vertraging tussen pogingen (periode **** Opnieuw proberen).

   Door gebrek, zijn vijf herpogingen gepland voor de eerste dag met een minimuminterval van één uur, uitgespreid zich over de 24 uren van de dag. Na die datum en tot de uiterste datum van levering, die in de **[!UICONTROL Delivery parameters]** sectie is gedefinieerd, wordt elke dag opnieuw proberen geprogrammeerd.

* **E-mailquarantaineparameters**

   Voer in het **[!UICONTROL Time between two significant errors]** veld een waarde in om de tijd te definiëren die de toepassing wacht voordat de foutenteller bij een fout wordt verhoogd. Standaardwaarde: **&quot;1d&quot;**, gedurende 1 dag.

   Wanneer de **[!UICONTROL Maximum number of errors before quarantine]** waarde is bereikt, wordt het e-mailadres in quarantaine geplaatst. Standaardwaarde: **&quot;5&quot;**: het adres zal op de zesde fout worden quarantined. Dit betekent dat het contact automatisch van volgende leveringen wordt uitgesloten.

**Verwant onderwerp**:

[Werken met quarantainebeheer](../../sending/using/understanding-quarantine-management.md)

## E-mailrouteringsaccounts {#email-routing-accounts}

De **[!UICONTROL Integrated email routing]** externe rekening wordt standaard verschaft. Het bevat de technische parameters waarmee de toepassing e-mailberichten kan verzenden.

![](assets/channels_2.png)

Het accounttype moet altijd worden ingesteld op **[!UICONTROL Routing]**, het kanaal op **[!UICONTROL Email]** en de leveringsmodus op **[!UICONTROL Bulk delivery]**.

**Verwant onderwerp**:

[Externe rekeningen](../../administration/using/external-accounts.md)

## E-mailverwerkingsregels {#email-processing-rules}

Beheerders **[!UICONTROL Email processing rules]** hebben toegang tot dit bestand via het **[!UICONTROL Administration > Channels > Email]** menu.

Deze regels bevatten de lijst met tekenreeksen die door externe servers kunnen worden geretourneerd en waarmee u de fout (**Hard**, **Zacht** of **Genegeerd**) kunt kwalificeren.

De standaardregels zijn als volgt:

### Stuitberichten {#bounce-mails}

Wanneer een e-mailbericht mislukt, retourneert de server voor het externe bericht een stuitfoutbericht naar het adres dat is opgegeven in de toepassingsinstellingen.

De Campagne van Adobe vergelijkt de inhoud van elke stuiterende post met de koorden in de lijst van regels, en wijst het dan toe één van de drie foutentypes.

>[!IMPORTANT]
>
>Zodra bijgewerkt naar de verbeterde MTA, worden de stuiterende kwalificaties in de **[!UICONTROL Message qualification]** lijst van de Campagne niet meer gebruikt. Voor de synchrone foutenmeldingen van de leveringsmislukking, bepaalt Verbeterde MTA het stuittype en de kwalificatie, en stuurt die informatie terug naar Campagne. Asynchrone stuitingen worden nog steeds gekwalificeerd door het inMail-proces.
>
>Raadpleeg dit [document](https://helpx.adobe.com/campaign/kb/campaign-enhanced-mta.html)voor meer informatie over de verbeterde MTA voor Adobe-campagne.

De gebruiker kan zijn eigen regels tot stand brengen.

>[!IMPORTANT]
>
>Wanneer u een pakket importeert en gegevens bijwerkt via de workflow **Bijwerken voor** de levering, worden de door de gebruiker gemaakte regels overschreven.

### E-maildomeinen beheren {#managing-email-domains}

De regels van het domeinbeheer worden gebruikt om de stroom van uitgaande e-mails voor een specifiek domein te regelen. Ze nemen een monster van de stuiterende berichten en blokkeren het verzenden, indien van toepassing.

De het overseinenserver van de Campagne van Adobe past regels toe specifiek voor de domeinen, en toen de regels voor het algemene geval dat door een asterisk in de lijst van regels wordt vertegenwoordigd.

>[!IMPORTANT]
>
>Zodra bijgewerkt aan Verbeterde MTA, wordt het ondertekenen van de e-mailauthentificatie DKIM (DomainKeys Identified Mail) gedaan door Verbeterde MTA. DKIM-signing door de native Campagne MTA zal binnen de **[!UICONTROL Domain management]** lijst als deel van de Verbeterde verbetering MTA worden uitgezet.
>
>Raadpleeg dit [document](https://helpx.adobe.com/campaign/kb/campaign-enhanced-mta.html)voor meer informatie over de verbeterde MTA voor Adobe-campagne.

Om domeinbeheerregels te vormen, eenvoudig plaats een drempel en selecteer bepaalde parameters SMTP. Een **drempel** is een grens die als foutenpercentage wordt berekend waarvoorbij alle berichten naar een specifiek domein worden geblokkeerd.

De **parameters** SMTP handelen als filters die voor een blokkerende regel worden toegepast.

* U kunt kiezen al dan niet om bepaalde identificatienormen en encryptiesleutels te activeren om de domeinnaam, zoals identiteitskaart **van de** Afzender, **Domeinsleutels**, **DKIM**, en **S/MIME** te controleren.
* **SMTP-relais**: laat u het IP adres en de haven van een relaisserver voor een bepaald domein vormen.

### MX-beheer {#mx-management}

Elke regel bepaalt een adresmasker voor MX. Elke MX waarvan de naam overeenkomt met dit masker is daarom in aanmerking. Het masker kan &quot;*&quot; en &quot;?&quot; bevatten algemene tekens.

De volgende adressen zijn bijvoorbeeld:

* a.mx.yahoo.com
* b.mx.yahoo.com
* c.mx.yahoo.com

zijn compatibel met de volgende maskers:

* *.yahoo.com
* ?.mx.yahoo.com

Deze regels worden achtereenvolgens toegepast: de eerste regel wordt toegepast waarvan MX-masker compatibel is met de beoogde MX.

>[!IMPORTANT]
>
>Nadat de upgrade naar de verbeterde MTA is uitgevoerd, worden de regels voor de leveringstijd van de Adobe Campagne **** MX niet meer gebruikt. Verbeterde MTA gebruikt zijn eigen MX regels die het toestaan om uw productie door domein aan te passen die op uw eigen historische e-mailreputatie wordt gebaseerd, en op real time terugkoppelen die uit de domeinen komt waar u e-mails verzendt.
>
>Raadpleeg dit [document](https://helpx.adobe.com/campaign/kb/campaign-enhanced-mta.html)voor meer informatie over de verbeterde MTA voor Adobe-campagne.

De volgende parameters zijn beschikbaar voor elke regel:

* **[!UICONTROL Range of IDs]**: Met deze optie kunt u de bereiken van id&#39;s (publicId) aangeven waarop de regel van toepassing is. U kunt het volgende opgeven:

   * Een getal: de regel is alleen van toepassing op deze publicId.
   * Een reeks getallen (getal1-getal2): de regel zal op alle publicIds tussen deze twee aantallen van toepassing zijn.
   Als het veld leeg is, geldt de regel voor alle id&#39;s.

* **[!UICONTROL Shared]**: deze optie wijst erop dat het hoogste aantal berichten per uur en van verbindingen op alle MXs van toepassing is verbonden aan deze regel.
* **[!UICONTROL Maximum number of connections]**: maximumaantal gelijktijdige verbindingen aan MX van een bepaald adres.
* **Maximum aantal berichten**: maximum aantal berichten dat door één verbinding kan worden verzonden. Na dit bedrag, wordt de verbinding gesloten en een nieuwe wordt heropend.
* **[!UICONTROL Messages per hour]**: maximumaantal berichten dat in één uur voor MX via een bepaald adres kan worden verzonden.

>[!IMPORTANT]
>
>* De leveringsserver (MTA) moet opnieuw worden begonnen als de parameters zijn veranderd.
>* De wijziging of invoering van beheerregels is alleen voor professionele gebruikers.
>



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

Voor tijdelijk onafgeleverde berichten moet u het opnieuw proberen. In deze sectie wordt aangegeven hoeveel pogingen moeten worden uitgevoerd op de dag nadat de verzending is gestart ( **[!UICONTROL Max. number of retries]** ) en wordt aangegeven hoeveel tijd er minimaal is verstreken ( **[!UICONTROL Retry period]** ).

Door gebrek, zijn vijf herpogingen gepland voor de eerste dag met een minimuminterval van één uur, uitgespreid zich over de 24 uren van de dag. Elke dag opnieuw proberen wordt geprogrammeerd na dat en tot de leveringsdeadline, die in de sectie van de parameters [van de](#validity-period-parameters) Geldigheidsperiode wordt bepaald.

Het aantal pogingen kan globaal worden gewijzigd (neem contact op met uw technische beheerder van Adobe) of voor elke levering of leveringsmalplaatje

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

* **[!UICONTROL Explicitly set validity dates]**: Als dit vakje niet is ingeschakeld, moet u een duur invoeren in de velden **[!UICONTROL Delivery duration]** en in de **[!UICONTROL Resource validity limit]** velden. Schakel dit selectievakje in als u specifieke tijden en datums wilt definiëren.

   ![](assets/delivery-set-explicit-dates.png)

* **[!UICONTROL Delivery duration]**: Adobe Campaign verzendt de berichten die op de begindatum beginnen. In dit veld kunt u opgeven gedurende welke periode de berichten kunnen worden verzonden.

   >[!IMPORTANT]
   >
   >Zodra bijgewerkt aan Verbeterde MTA, wordt de **[!UICONTROL Delivery duration]** parameter in uw levering van de Campagne gebruikt slechts als reeks aan 3.5 dagen of minder. Als u een waarde definieert die hoger is dan 3,5 dagen, wordt hiermee geen rekening gehouden. Alle gevolgen worden beschreven in het document [Verbeterde MTA](https://helpx.adobe.com/campaign/kb/campaign-enhanced-mta.html) van de Campagne van Adobe.

* **[!UICONTROL Resource validity duration]**: dit veld wordt gebruikt voor geüploade bronnen , voornamelijk voor de spiegelpagina en afbeeldingen . De bronnen op deze pagina zijn gedurende een beperkte tijd geldig (om schijfruimte te besparen).
* **[!UICONTROL Mirror page management]**: De spiegelpagina is een HTML-pagina die online via een webbrowser toegankelijk is. De inhoud is identiek aan de e-mailinhoud. Standaard wordt de spiegelpagina gegenereerd als de koppeling wordt ingevoegd in de e-mailinhoud. In dit veld kunt u de manier wijzigen waarop deze pagina wordt gegenereerd:

   >[!IMPORTANT]
   >
   >Het e-mailbericht kan alleen worden gemaakt als er een HTML-inhoud is gedefinieerd.

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
   >Typologieën, die toegankelijk zijn via het menu **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Typologies]** , worden weergegeven in de sectie [Typologieën](../../administration/using/about-typology-rules.md) .

* **[!UICONTROL Compute the label during delivery preparation]**: Hiermee kunt u de labelwaarde van de e-mail tijdens de voorbereidingsfase berekenen met gebruik van verpersoonlijkingsvelden, inhoudsblokken en dynamische tekst.

   Het is ook mogelijk om het leveringsetiket met gebeurtenisvariabelen te personaliseren die in de externe signaalactiviteit van het werkschema zijn verklaard. For more on this, refer to [this section](../../automating/using/calling-a-workflow-with-external-parameters.md).

* **[!UICONTROL Save SQL queries in the log]**: met deze optie kunt u SQL-querylogs toevoegen in het journaal tijdens de voorbereidingsfase.

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

## E-mails archiveren {#archiving-emails}

U kunt Adobe Campaign zodanig configureren dat een kopie van de e-mails die u van uw platform hebt ontvangen, bewaard blijft.

Adobe Campaign zelf beheert echter geen gearchiveerde bestanden. Het laat u toe om de berichten van uw keus naar een specifiek adres te verzenden, van waar zij kunnen worden verwerkt en worden gearchiveerd gebruikend een extern systeem.

Wanneer geactiveerd in het leveringsmalplaatje, staat deze eigenschap u toe om een nauwkeurige kopie van de overeenkomstige verzonden berichten naar een BCC e-mailadres (onzichtbaar aan de leveringsontvangers) te verzenden dat u moet specificeren.

### Aanbevelingen en beperkingen {#recommendations-and-limitations}

* Deze functie is optioneel. Controleer uw licentieovereenkomst en neem contact op met uw accountmanager om deze te activeren.
* Het BCC-adres van uw keuze moet worden opgegeven aan het Adobe-team dat het voor u zal configureren.
* U kunt slechts één BCC-e-mailadres gebruiken.
* Alleen e-mailberichten die correct zijn verzonden, worden in aanmerking genomen. Bounces niet.
* Om privacyredenen moeten BCC-e-mails worden verwerkt door een archiveringssysteem dat veilig identificeerbare informatie (PII) kan opslaan.
* Bij het maken van een nieuwe leveringssjabloon is de optie BCC via e-mail niet standaard ingeschakeld, zelfs niet als de optie is aangeschaft. U moet het manueel in elke leveringsmalplaatje toelaten waar u het wilt gebruiken.

### E-mailarchivering activeren {#activating-email-archiving}

E-mail BCC wordt geactiveerd in de [e-mailsjabloon](../../start/using/marketing-activity-templates.md)via een speciale optie:

1. Ga naar **Bronnen** > **Sjablonen** > **Leveringssjablonen**.
1. Dupliceer de out-of-box **[!UICONTROL Send via email]** sjabloon.
1. Selecteer de gedupliceerde sjabloon.
1. Klik op de **[!UICONTROL Edit properties]** knop om de eigenschappen van de sjabloon te bewerken.
1. Vouw de sectie **[!UICONTROL Send]** uit.
1. Schakel het **[!UICONTROL Archive emails]** selectievakje in om een kopie van alle verzonden berichten te bewaren voor elke levering die op deze sjabloon is gebaseerd.

   ![](assets/email_archiving.png)

>[!NOTE]
>
>Als de e-mails die naar het BCC-adres worden verzonden worden geopend en doorgeklikt, wordt hiermee rekening gehouden in de analyse **[!UICONTROL Total opens]** en **[!UICONTROL Clicks]** de verzendanalyse, wat tot onjuiste berekeningen kan leiden.
