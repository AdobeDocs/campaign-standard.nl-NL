---
title: Belangrijkste stappen voor het instellen van een transactiebericht
description: Ontdek wat transactiemeldingen zijn en leer de belangrijkste stappen om een transactiemelding in Adobe Campaign Standard op te zetten.
page-status-flag: never-activated
uuid: b316bf47-7d98-46fa-ab4f-67ff50de8095
contentOwner: lemaitre
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: landing-pages
discoiquuid: ca8d1698-6e8a-4f5a-b017-74a152e14286
context-tags: landingPage,wizard;landingPage,overview;landingPage,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1b1fb4a0dc0f7881e24e10f8ac171feab2ac8cba
workflow-type: tm+mt
source-wordcount: '814'
ht-degree: 28%

---


# Aan de slag met transactiemeldingen {#getting-started-with-transactional-messaging}

## Overzicht

<table>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_transactional.svg" width="60px"><br><p>Introductie van het concept van <b>transactioneel overseinen</b></p></td>
<td ><br><p>Het transactieoverseinen laat u toe om individuele en unieke berichten <b>naar uw klanten in real time te</b> verzenden.</p></td>
<td>Dit kunnen welkomstberichten, bestellingen voor het verzenden van bestellingen, wachtwoordwijzigingen, enzovoort zijn.</td>
<td>Met Adobe Campaign kunt u deze functionaliteit integreren met een informatiesysteem dat gebeurtenissen verzendt die moeten worden omgezet in aangepaste transactieberichten.</td>
</tr>
</table>

Transactieberichten kunnen worden verzonden via e-mail, sms of pushmeldingen, afhankelijk van uw opties. Controleer hiervoor uw licentieovereenkomst.

Adobe Campaign geeft voorrang aan het verwerken van transactieberichten boven elke andere levering.

Transactieberichten zijn ook beschikbaar via de Adobe Campaign Standard-API. Raadpleeg de [desbetreffende documentatie](../../api/using/managing-transactional-messages.md)voor meer informatie hierover.

>[!NOTE]
>
>Alle transactieberichten worden nu verzonden met de verbeterde MTA van Adobe Campaign voor een betere levering en doorvoer, en voor de verwerking van berichten die niet bezorgbaar zijn. Alle effecten zijn hetzelfde als bij standaardmarketingberichten. Zie [deze sectie](../../administration/using/configuring-email-channel.md) voor meer informatie.

## Transactionele berichtendefinitie {#transactional-messaging-definition}

<table>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_concepts.svg" width="60px"><br><p><b>Wat is een transactioneel bericht?</b></p></td>
<td><p>Het is een individuele en unieke communicatie, die door een leverancier zoals een website wordt verzonden.</p></td>
<td><p>Dit wordt vooral verwacht, omdat het belangrijke informatie bevat die de ontvanger wil controleren of bevestigen.</p></td>
</tr>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_channels.svg" width="60px"><br><p><b>Wanneer komt het?</b></p></td>
<td><p> Omdat dit bericht belangrijke informatie bevat, verwacht de gebruiker dat het in echt - tijd wordt verzonden.</p></td>
<td><p>De vertraging tussen de gebeurtenis die wordt geactiveerd en het bericht dat aankomt, moet daarom zeer kort zijn.</p></td>
</tr>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_important.svg" width="60px"><br><p><b>Waarom is het belangrijk?</b></p></td>
<td><p>Over het algemeen zijn er voor een transactiebericht hoge open tarieven. Het moet daarom zorgvuldig worden ontworpen.</p></td>
<td><p>Het kan namelijk een sterke invloed hebben op het gedrag van de klanten, aangezien het de relatie met de klant definieert.</p></td>
</tr>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_example.svg" width="60px"><br><p><b>Bijvoorbeeld?</b></p></td>
<td><p>Het zou een welkomstbericht kunnen zijn na het maken van een account, een bevestiging dat een bestelling is verzonden, een factuur...</p></td>
<td><p>Het kan ook een bericht zijn dat een wachtwoordwijziging bevestigt, of een bericht nadat een klant door uw website heeft gebladerd...</p></td>
</tr>
</table>

## Transactieberichttypen

Er zijn twee typen transactieberichten beschikbaar in Adobe Campaign:

<table>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_event.svg" width="60px"><br><p><a href="../../channels/using/event-transactional-messages.md">Gebeurtenistransactieberichten</a><br><b> die zijn gericht op een gebeurtenis</b></p></td>
<td><p><ul><li>Transactieberichten van gebeurtenissen bevatten geen profielinformatie.</li><li>Zij zijn niet verenigbaar met <a href="../../sending/using/fatigue-rules.md">vermoeidheidsregels</a> (zelfs in geval van verrijking met profielen).</li><li>Het leveringsdoel wordt bepaald door de gegevens in de gebeurtenis zelf.</li></ul></p></td>
</tr>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_profile.svg" width="60px"><br><p><a href="../../channels/using/profile-transactional-messages.md">Profieltransactieberichten</a><br><b> die zijn gericht op profielen in de marketingdatabase van Adobe Campaign</b></p></td>
<td><p>Transactieberichten van het profiel laten u toe:<ul><li>Apply marketing <a href="../../sending/using/managing-typology-rules.md">typology rules</a> or <a href="../../sending/using/fatigue-rules.md">fatigue rules</a>.</li><li>De koppeling voor het opzeggen van abonnementen in de berichten opnemen.</li><li>De transactionele berichten aan de globale leveringsrapportage toevoegen.</li><li>De transactionele berichten in het klanttraject gebruiken.</li></ul></p></td>
</tr>
</table>

Het berichttype wordt bepaald tijdens de configuratie van de gebeurtenis die in een transactiebericht wordt omgezet. Zie [Transactieberichten configureren](../../administration/using/configuring-transactional-messaging.md).

>[!IMPORTANT]
>
>To access all transactional messages, you must be part of the **[!UICONTROL Administrators (all units)]** security group.

## Werkingsprincipe voor transactieberichten {#transactional-messaging-operating-principle}

Laten we het voorbeeld nemen van een bedrijf dat een website heeft en op deze website kunnen klanten producten kopen.

Met Adobe Campaign kunt u een e-mailbericht naar sitegebruikers sturen die producten in hun winkelwagen hebben geplaatst: wanneer ze de site verlaten zonder een aankoop te doen, wordt er automatisch een e-mail naar ze gestuurd met de melding dat ze een winkelwagen met artikelen hebben achtergelaten.

De maatregelen om dit in te voeren zijn als volgt.

### Stap 1 - creeer en publiceer de gebeurtenisconfiguratie {#create-event-configuration}

<table>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_config.svg" width="60px"><br><p><b>Transactionele gebeurtenisconfiguratie</b></p></td>
<td><br><p>Configureer een gebeurtenis met de naam "Afstand starten" en publiceer deze gebeurtenisconfiguratie.</p></td>
<td>De API die wordt gebruikt door uw websiteontwikkelaar, wordt geïmplementeerd en er wordt automatisch een transactiemelding gemaakt.</td>
<td>Merk op dat deze stap door een gebruiker met <a href="../../administration/using/users-management.md#functional-administrators">beleidsrechten</a>moet worden uitgevoerd.</td>
</tr>
</table>

Het maken en publiceren van een gebeurtenis wordt beschreven in de sectie [Een gebeurtenis configureren voor het sturen van een gebeurtenistransactiebericht](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message).

### Stap 2 - geef en publiceer het transactiebericht uit {#create-transactional-message}

<table>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_notification.svg" width="40px"><br><p><b>Transactievergadering</b></p></td>
<td><br><p>Bewerk het transactiebericht, test het en publiceer het.</p></td>
<td>Het transactiebericht is dan klaar om te worden verzonden.</td>
<td>Deze stap kan worden uitgevoerd door elke marketinggebruiker met <a href="../../administration/using/users-management.md#basic-users">basistoegangsrechten</a>.
</tr>
</table>

For more on editing and publishing a transactional message, see [Event transactional messages](../../channels/using/event-transactional-messages.md).

### Stap 3 - Integreer de gebeurtenis die teweegbrengt {#integrate-event-trigger}

<table>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_api.svg" width="55px"><br><p><b>Gebeurtenis die integratie teweegbrengt</b></p></td>
<td><br><p>Gebruik de REST Transaction Messages API om de gebeurtenis in uw website te integreren.</p></td>
<td>De gebeurtenis wordt geactiveerd wanneer een klant zijn winkelwagentje verlaat.</td>
<td>Deze stap wordt uitgevoerd door de ontwikkelaar van uw website.
</tr>
</table>

Zie [Site-integratie](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)voor meer informatie over het integreren van de gebeurtenis in uw website.

### Stap 4 - Berichtlevering {#message-delivery}

<table>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_channels.svg" width="60px"><br><p><b>Externe gebeurtenis van uw website</b></p></td>
<td><br><p>Zodra al deze stappen zijn uitgevoerd, kan het bericht worden geleverd.</p></td>
<td>Zodra een gebruiker de site verlaat zonder de producten in zijn winkelwagentje te bestellen, wordt de bijbehorende Campagne-gebeurtenis geactiveerd.</td>
<td>Vervolgens ontvangt de gebruiker automatisch een e-mailbericht.</td>
</tr>
</table>

## Belangrijkste stappen {#key-steps}

De belangrijkste stappen bij het maken en beheren van persoonlijke transactiemeldingen in Adobe Campaign worden in de onderstaande tabel samengevat.

![](assets/message-center-overview.png)

**Verwante onderwerpen:**

* [Belangrijkste stappen om een bericht te verzenden](../../channels/using/key-steps-to-send-a-message.md)
* [Aan de slag met communicatiekanalen](../../channels/using/get-started-communication-channels.md)

<!--## Transactional messaging publication process {#transactional-messaging-pub-process}

The chart below illustrates the whole transactional messaging publication process.

![](assets/message-center_pub-process.png)

For more on the event configuration steps, see [Transactional messaging configuration](../../administration/using/configuring-transactional-messaging.md).

Read more:

* [Event transactional messages](../../channels/using/event-transactional-messages.md)
* [Profile transactional messages](../../channels/using/profile-transactional-messages.md)
* [Transactional push notifications](../../channels/using/transactional-push-notifications.md)
* [Follow-up messages](../../channels/using/follow-up-messages.md)-->