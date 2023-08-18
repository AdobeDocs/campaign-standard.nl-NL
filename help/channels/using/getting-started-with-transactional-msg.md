---
title: Aan de slag met transactionele berichten
description: Ontdek wat transactiemeldingen zijn en leer de belangrijkste stappen om een transactiemelding in Adobe Campaign Standard op te zetten.
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: Transactional Messaging
role: User
level: Beginner
exl-id: 49fba1af-3c99-45b7-bcbb-b9b9678eedcd
source-git-commit: 0e486e87c94e273442de23d6eb65c99f065e5a71
workflow-type: tm+mt
source-wordcount: '988'
ht-degree: 9%

---

# Aan de slag met transactionele berichten {#getting-started-with-transactional-messaging}

Een transactiebericht is een individuele en unieke communicatie die in real time door een leverancier zoals een website wordt verzonden. Dit wordt vooral verwacht, omdat het belangrijke informatie bevat die de ontvanger wil controleren of bevestigen.

* **Wanneer is het te verwachten?** Omdat dit bericht belangrijke informatie bevat, verwacht de gebruiker dat het in echt - tijd wordt verzonden. De vertraging tussen de gebeurtenis die wordt geactiveerd en het bericht dat aankomt, moet daarom zeer kort zijn.

* **Waarom is het belangrijk?** Over het algemeen zijn er voor een transactiebericht hoge open tarieven. Het moet daarom zorgvuldig worden ontworpen, omdat het een sterke invloed kan hebben op het gedrag van de klanten, aangezien het de relatie met de klant definieert.

* **Bijvoorbeeld?** Het kan een welkomstbericht zijn na het maken van een account, een bevestiging dat een bestelling is verzonden, een factuur, een bericht waarin een wijziging van het wachtwoord wordt bevestigd, of een melding nadat een klant door uw website heeft gebladerd, enz.

Met Adobe Campaign kunt u deze functionaliteit integreren met een informatiesysteem dat gebeurtenissen verzendt die moeten worden omgezet in aangepaste transactieberichten.

Transactieberichten kunnen via e-mail, SMS of [pushmelding](../../channels/using/transactional-push-notifications.md), afhankelijk van uw opties. Controleer hiervoor uw licentieovereenkomst.

>[!NOTE]
>
>Adobe Campaign geeft voorrang aan het verwerken van transactieberichten boven elke andere levering.

<!--Guidelines to implement transactional messaging capabilities in your website are detailed in [this section](../../api/using/managing-transactional-messages.md).-->

Voordat u begint met een transactiebericht, moet u ervoor zorgen dat u de bijbehorende [beste praktijken en beperkingen](../../channels/using/transactional-messaging-limitations.md).

## Werkingsprincipe voor transactieberichten {#transactional-messaging-operating-principle}

Het algemene proces van het transactieoverseinen kan als volgt worden beschreven:

![](assets/message-center-process.png)

Stel dat u een bedrijf bent met een website waar uw klanten producten kunnen kopen.

Met Adobe Campaign kunt u een meldingsbericht verzenden naar klanten die producten aan hun winkelwagentje hebben toegevoegd. Wanneer een van hen uw website verlaat zonder door te gaan met hun aankopen (externe gebeurtenis die een Campagne-gebeurtenis activeert), wordt er automatisch een e-mailbericht over het verlaten van de winkelwagen naar hen verzonden (levering van transactiemeldingen).

De belangrijkste stappen om dit in te voeren zijn hieronder beschreven [deze sectie](#key-steps).

## Transactieberichttypen {#transactional-message-types}

Er zijn twee typen transactieberichten beschikbaar in Adobe Campaign.

**Transactieberichten voor gebeurtenissen** doelgegevens in de gebeurtenis zelf. Deze berichten:
* Bevat geen profielgegevens en kan daarom geen abonnementkoppelingen bevatten.
* zijn niet verenigbaar met vermoeidheidsvoorschriften (zelfs in geval van verrijking met profielen).
* Hun leveringsdoel laten bepalen door de gegevens in de gebeurtenis zelf.

U kunt een bericht van de gebeurtenistransactie naar een klant sturen die een vergeten wachtwoord moet terugwinnen bijvoorbeeld, of een orde bevestigen. U wilt namelijk niet dat de ontvanger zich afmeldt bij dit type communicatie en deze melding mag niet worden toegevoegd aan de teller van marketingberichten als onderdeel van een moeitelijn.

**Transactieberichten profileren** doelprofielen uit de marketingdatabase voor campagnes. Met dit type berichten kunt u:
* Gebruikmaken van gegevens in de Adobe Campaign-database.
* Pas uw bericht aan met profielgegevens door een [verrijking](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content) naar de gebeurtenisconfiguratie.
* Toepassen [marketingtypologieregels](../../sending/using/managing-typology-rules.md) of [vermoeidheidsregels](../../sending/using/fatigue-rules.md).
* De koppeling voor het opzeggen van abonnementen in de berichten opnemen.
* De transactionele berichten aan de globale leveringsrapportage toevoegen.
* De transactionele berichten in het klanttraject gebruiken.

U kunt dit type berichten bijvoorbeeld gebruiken wanneer u contact opneemt met uw klanten nadat ze hun winkelwagentje op uw website hebben verlaten, om hen aan te moedigen verder te gaan met hun aankoop. Dit doet, kunt u uw bericht gemakkelijker personaliseren met directe toegang tot alle informatie van uw profielgegevensbestand, marketingregels toepassen en dit bericht aan de globale klantenreis en rapportering voor een betere mening over uw klantengedrag omvatten.

Het berichttype wordt bepaald tijdens de configuratie van de gebeurtenis die in een transactiebericht wordt omgezet. Zie de [Transactieberichten die zijn gebaseerd op gebeurtenissen](../../channels/using/configuring-transactional-event.md#event-based-transactional-messages) en [Transactieberichten op basis van profielen](../../channels/using/configuring-transactional-event.md#profile-based-transactional-messages) configuratiesecties.

## Belangrijkste stappen {#key-steps}

De belangrijkste stappen bij het maken en beheren van persoonlijke transactiemeldingen in Adobe Campaign worden in het onderstaande schema samengevat.

![](assets/message-center-overview.png)

Elk van deze stappen wordt hieronder nader beschreven.

>[!IMPORTANT]
>
>Alleen gebruikers met de [Administratie](../../administration/using/users-management.md#functional-administrators) de rol kan transactionele gebeurtenissen vormen en tot transactionele berichten toegang hebben.

### Stap 1 - creeer en publiceer de gebeurtenisconfiguratie {#create-event-configuration}

<!--<img src="assets/do-not-localize/icon_config.svg" width="60px">-->

| Een gebeurtenis maken | Gebruiker | Actie | Resultaat |
| --- |--- |--- |--- |
| <img src="assets/do-not-localize/icon_config.svg" width="60px"> | Deze stap moet worden uitgevoerd door een beheerder die [administratierechten](../../administration/using/users-management.md#functional-administrators). | Configureer een gebeurtenis met de naam &quot;Afstand starten&quot; en publiceer deze gebeurtenisconfiguratie. | De API die wordt gebruikt door uw websiteontwikkelaar, wordt geïmplementeerd en er wordt automatisch een transactiemelding gemaakt. |

Het creëren van en het publiceren van een gebeurtenis worden voorgesteld in [Een transactiegebeurtenis configureren](../../channels/using/configuring-transactional-event.md) en [Transactiegebeurtenissen publiceren](../../channels/using/publishing-transactional-event.md) secties.

### Stap 2 - geef en publiceer het transactiebericht uit {#create-transactional-message}

<!--<img src="assets/do-not-localize/icon_notification.svg" width="40px">-->

| Het bericht bewerken | Gebruiker | Actie | Resultaat |
| --- |--- |--- |--- |
| <img src="assets/do-not-localize/icon_notification.svg" width="40px"> | Deze stap kan worden uitgevoerd door een marketinggebruiker die [administratierechten](../../administration/using/users-management.md#functional-administrators). | Bewerk het transactiebericht, test het en publiceer het. | Het transactiebericht is dan klaar om te worden verzonden. |

Voor meer informatie over het bewerken en publiceren van een transactiemelding raadpleegt u [Transactieberichten bewerken](../../channels/using/editing-transactional-message.md) en [Levenscyclus van transactionele berichten](../../channels/using/publishing-transactional-message.md).

### Stap 3 - Integreer de gebeurtenis die teweegbrengt {#integrate-event-trigger}

<!--<img src="assets/do-not-localize/icon_api.svg" width="55px">-->

Nadat u een gebeurtenis hebt gemaakt, moet u het activeren van deze gebeurtenis integreren in uw website.<!--In this example, you want a "Cart abandonment" event to be triggered whenever one of your clients leaves your website before purchasing the products in their cart.--> Hiervoor moet uw webontwikkelaar van uw website de opdracht **ADOBE CAMPAIGN STANDARD REST API**.

| De trigger implementeren | Gebruiker | Actie | Resultaat |
| --- |--- |--- |--- |
| <img src="assets/do-not-localize/icon_api.svg" width="55px"> | Deze stap wordt uitgevoerd door de ontwikkelaar van uw website. | Gebruik de REST Transaction Messages API om de gebeurtenis in uw website te integreren. | De gebeurtenis wordt geactiveerd wanneer een klant zijn winkelwagen verlaat. |

Zie voor meer informatie over het gebruik van de campagne REST API voor het beheer van transactieberichten de [REST API-documentatie](../../api/using/managing-transactional-messages.md).

### Stap 4 - Berichtlevering {#message-delivery}

<!--<img src="assets/do-not-localize/icon_channels.svg" width="60px">-->

Zodra alle bovenstaande stappen zijn uitgevoerd, kan het bericht worden geleverd.

| Het bericht verzenden | Gebruiker | Actie | Resultaat |
| --- |--- |--- |--- |
| <img src="assets/do-not-localize/icon_channels.svg" width="60px"> | Deze stap wordt uitgevoerd door klanten die uw website bezoeken. | Zodra een gebruiker de site verlaat zonder de producten in zijn winkelwagentje te bestellen, wordt de bijbehorende Campagne-gebeurtenis geactiveerd. | De gebruiker ontvangt automatisch een e-mailbericht. |

## Verwante onderwerpen

* [Belangrijkste stappen voor verzending van een bericht](../../channels/using/key-steps-to-send-a-message.md)
* [Aan de slag met communicatiekanalen](../../channels/using/get-started-communication-channels.md)
* [Transactionele pushmeldingen](../../channels/using/transactional-push-notifications.md)
* [Vervolgberichten](../../channels/using/follow-up-messages.md)
