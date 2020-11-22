---
solution: Campaign Standard
product: campaign
title: Belangrijkste stappen voor het instellen van een transactiebericht
description: Ontdek wat transactiemeldingen zijn en leer de belangrijkste stappen om een transactiemelding in Adobe Campaign Standard op te zetten.
audience: channels
content-type: reference
topic-tags: landing-pages
context-tags: landingPage,wizard;landingPage,overview;landingPage,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '814'
ht-degree: 28%

---


# Aan de slag met transactionele berichten {#getting-started-with-transactional-messaging}

## Overzicht

<img src="assets/do-not-localize/icon_transactional.svg" width="60px">

Introductie van het concept van **transactioneel overseinen**

Het transactieoverseinen laat u toe om individuele en unieke berichten naar uw klanten in real time te verzenden.

Dit kunnen welkomstberichten, bestellingen voor verzendbevestigingen, wachtwoordupdates, enzovoort zijn.
Met Adobe Campaign kunt u deze functionaliteit integreren met een informatiesysteem dat gebeurtenissen verzendt die moeten worden omgezet in aangepaste transactieberichten.

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

<img src="assets/do-not-localize/icon_event.svg" width="60px">

[Gebeurtenistransactieberichten](../../channels/using/event-transactional-messages.md) die zijn gericht op een gebeurtenis.

* Transactieberichten van gebeurtenissen bevatten geen profielinformatie.

* Zij zijn niet verenigbaar met [vermoeidheidsregels](../../sending/using/fatigue-rules.md) (zelfs in geval van verrijking met profielen).

* Het leveringsdoel wordt bepaald door de gegevens in de gebeurtenis zelf.


<img src="assets/do-not-localize/icon_profile.svg" width="60px">

[Profieltransactieberichten](../../channels/using/profile-transactional-messages.md) die zijn gericht op profielen in de marketingdatabase van Campaign.

Met profielen kunt u transactieberichten gebruiken:

* Apply [marketing typology rules](../../sending/using/managing-typology-rules.md) or [fatigue rules](../../sending/using/fatigue-rules.md)

* De koppeling voor het opzeggen van abonnementen in de berichten opnemen.

* De transactionele berichten aan de globale leveringsrapportage toevoegen.

* De transactionele berichten in het klanttraject gebruiken.

Het berichttype wordt bepaald tijdens de configuratie van de gebeurtenis die in een transactiebericht wordt omgezet. Zie [Transactieberichten configureren](../../administration/using/configuring-transactional-messaging.md).

>[!IMPORTANT]
>
>To access all transactional messages, you must be part of the **[!UICONTROL Administrators (all units)]** security group.

## Werkingsprincipe voor transactieberichten {#transactional-messaging-operating-principle}

Laten we het voorbeeld nemen van een bedrijf dat een website heeft en op deze website kunnen klanten producten kopen.

Met Adobe Campaign kunt u een e-mailbericht naar sitegebruikers sturen die producten in hun winkelwagen hebben geplaatst: wanneer ze de site verlaten zonder een aankoop te doen, wordt er automatisch een e-mail naar ze gestuurd met de melding dat ze een winkelwagen met artikelen hebben achtergelaten.

De maatregelen om dit in te voeren zijn als volgt.

### Stap 1 - creeer en publiceer de gebeurtenisconfiguratie {#create-event-configuration}

<img src="assets/do-not-localize/icon_config.svg" width="60px">

**Transactionele gebeurtenisconfiguratie**:

* Configureer een gebeurtenis met de naam &quot;Afstand starten&quot; en publiceer deze gebeurtenisconfiguratie.

* De API die wordt gebruikt door uw websiteontwikkelaar, wordt geïmplementeerd en er wordt automatisch een transactiemelding gemaakt.

* Merk op dat deze stap door een gebruiker met [beleidsrechten](../../administration/using/users-management.md#functional-administrators)moet worden uitgevoerd.

Het maken en publiceren van een gebeurtenis wordt beschreven in de sectie [Een gebeurtenis configureren voor het sturen van een gebeurtenistransactiebericht](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message).

### Stap 2 - geef en publiceer het transactiebericht uit {#create-transactional-message}

<img src="assets/do-not-localize/icon_notification.svg" width="40px">

**Transactievergadering**

* Bewerk het transactiebericht, test het en publiceer het.

* Het transactiebericht is dan klaar om te worden verzonden.

* Deze stap kan worden uitgevoerd door elke marketinggebruiker met [standaardtoegangsrechten](../../administration/using/users-management.md#basic-users)voor gebruikers.

For more on editing and publishing a transactional message, see [Event transactional messages](../../channels/using/event-transactional-messages.md).

### Stap 3 - Integreer de gebeurtenis die teweegbrengt {#integrate-event-trigger}

<img src="assets/do-not-localize/icon_api.svg" width="55px">

**Gebeurtenis die integratie teweegbrengt**

* Gebruik de REST Transaction Messages API om de gebeurtenis in uw website te integreren.&lt;

* De gebeurtenis wordt geactiveerd wanneer een klant zijn winkelwagentje verlaat.

* Deze stap wordt uitgevoerd door de ontwikkelaar van uw website.

Zie [Site-integratie](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)voor meer informatie over het integreren van de gebeurtenis in uw website.

### Stap 4 - Berichtlevering {#message-delivery}

<img src="assets/do-not-localize/icon_channels.svg" width="60px">

**Externe gebeurtenis van uw website**

* Zodra al deze stappen zijn uitgevoerd, kan het bericht worden geleverd.

* Zodra een gebruiker de site verlaat zonder de producten in zijn winkelwagentje te bestellen, wordt de bijbehorende Campagne-gebeurtenis geactiveerd.

* Vervolgens ontvangt de gebruiker automatisch een e-mailbericht.

## Belangrijkste stappen {#key-steps}

De belangrijkste stappen bij het maken en beheren van persoonlijke transactiemeldingen in Adobe Campaign worden hieronder samengevat.

![](assets/message-center-overview.png)

## Verwante onderwerpen

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