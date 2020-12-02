---
solution: Campaign Standard
product: campaign
title: Belangrijkste stappen voor het instellen van een transactiebericht
description: Ontdek wat transactiemeldingen zijn en leer de belangrijkste stappen om een transactiemelding in Adobe Campaign Standard op te zetten.
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
translation-type: tm+mt
source-git-commit: 00032b1a8bfef301d1a87750695ba1670b2eed6c
workflow-type: tm+mt
source-wordcount: '831'
ht-degree: 18%

---


# Aan de slag met transactionele berichten {#getting-started-with-transactional-messaging}

## Overzicht {#overview}

### Wat is een transactioneel bericht?

Het is een individuele en unieke communicatie, die in real time door een leverancier zoals een website wordt verzonden. Dit wordt vooral verwacht, omdat het belangrijke informatie bevat die de ontvanger wil controleren of bevestigen.

* **Wanneer komt het?** Omdat dit bericht belangrijke informatie bevat, verwacht de gebruiker dat het in echt - tijd wordt verzonden. De vertraging tussen de gebeurtenis die wordt geactiveerd en het bericht dat aankomt, moet daarom zeer kort zijn.

* **Waarom is het belangrijk?** Over het algemeen zijn er voor een transactiebericht hoge open tarieven. Het moet daarom zorgvuldig worden ontworpen, omdat het een sterke invloed kan hebben op het gedrag van de klanten, aangezien het de relatie met de klant definieert.

* **Bijvoorbeeld?** Het kan een welkomstbericht zijn nadat u een account hebt gemaakt, een bevestiging dat een bestelling is verzonden, een factuur, een bericht ter bevestiging van een wijziging in het wachtwoord of een bericht nadat een klant door uw website is gebladerd..

### Transactiebericht verzenden

Met Adobe Campaign kunt u deze functionaliteit integreren met een informatiesysteem dat gebeurtenissen verzendt die moeten worden omgezet in aangepaste transactieberichten.

Transactieberichten kunnen worden verzonden via e-mail, sms of pushmeldingen, afhankelijk van uw opties. Controleer hiervoor uw licentieovereenkomst.

>[!NOTE]
>
>Adobe Campaign geeft voorrang aan het verwerken van transactieberichten boven elke andere levering.

Transactieberichten zijn ook beschikbaar via de Adobe Campaign Standard-API. Zie de [speciale documentatie](../../api/using/managing-transactional-messages.md) voor meer informatie.

>[!NOTE]
>
>Alle transactieberichten worden nu verzonden met de verbeterde MTA van Adobe Campaign voor een betere levering en doorvoer, en voor de verwerking van berichten die niet bezorgbaar zijn. Alle effecten zijn hetzelfde als bij standaardmarketingberichten. Zie [deze sectie](../../administration/using/configuring-email-channel.md)voor meer informatie.

### Transactietypen {#transactional-message-types}

Er zijn twee typen transactieberichten beschikbaar in Adobe Campaign:

**Transactieberichten voor gebeurtenissen** zijn gericht op een gebeurtenis:
* Ze bevatten geen profielgegevens.
* Zij zijn niet verenigbaar met vermoeidheidsvoorschriften (zelfs in geval van verrijking met profielen).
* Het leveringsdoel wordt bepaald door de gegevens in de gebeurtenis zelf.

**De transactiemeldingen van het profiel** richten zich op profielen van het marketing gegevensbestand van de Campagne. Met dit type berichten kunt u:
* Pas [marketingtypologische regels](../../sending/using/managing-typology-rules.md) of [vermoeidheidsregels](../../sending/using/fatigue-rules.md) toe.
* De koppeling voor het opzeggen van abonnementen in de berichten opnemen.
* De transactionele berichten aan de globale leveringsrapportage toevoegen.
* De transactionele berichten in het klanttraject gebruiken.

Het berichttype wordt bepaald tijdens de configuratie van de gebeurtenis die in een transactiebericht wordt omgezet. Zie [deze sectie](../../channels/using/configuring-transactional-event.md#transactional-event-specific-configurations).

>[!IMPORTANT]
>
>Om tot alle transactionele berichten toegang te hebben, moet u deel van **[!UICONTROL Administrators (all units)]** veiligheidsgroep uitmaken.

## Werkingsprincipe voor transactieberichten {#transactional-messaging-operating-principle}

Het algemene proces van het transactieoverseinen kan als volgt worden beschreven:

![](assets/message-center-process.png)

Stel dat u een bedrijf bent met een website waarop uw klanten producten kunnen kopen.

Met Adobe Campaign kunt u een meldingsbericht verzenden naar klanten die producten aan hun winkelwagentje hebben toegevoegd: als een van hen uw website verlaat zonder dat er een aankoop plaatsvindt (externe gebeurtenis die een Campagne-gebeurtenis activeert), wordt er automatisch een e-mailbericht over het verlaten van de winkelwagen naar hen verzonden (levering van transactiemeldingen).

<!--The steps for putting this into place are detailed below.-->

### Belangrijke stappen {#key-steps}

De belangrijkste stappen bij het maken en beheren van persoonlijke transactiemeldingen in Adobe Campaign worden in de onderstaande tabel samengevat.

![](assets/message-center-overview.png)

Elk van deze stappen wordt hieronder nader beschreven.

### Stap 1 - creeer en publiceer de gebeurtenisconfiguratie {#create-event-configuration}

<img src="assets/do-not-localize/icon_config.svg" width="60px">

| Gebruiker | Handeling | Resultaat |
|--- |--- |--- |
| Deze stap moet worden uitgevoerd door een gebruiker met [beheerrechten](../../administration/using/users-management.md#functional-administrators). | Configureer een gebeurtenis met de naam &quot;Afstand starten&quot; en publiceer deze gebeurtenisconfiguratie. | De API die wordt gebruikt door uw websiteontwikkelaar, wordt geïmplementeerd en er wordt automatisch een transactiemelding gemaakt. |

Het creëren van en het publiceren van een gebeurtenis worden voorgesteld in [het Vormen van een transactiegebeurtenis](../../channels/using/configuring-transactional-event.md) en [het Publiceren van een transactiegebeurtenis](../../channels/using/publishing-transactional-event.md) secties.

### Stap 2 - geef en publiceer het transactiebericht {#create-transactional-message} uit

<img src="assets/do-not-localize/icon_notification.svg" width="40px">

| Gebruiker | Handeling | Resultaat |
|--- |--- |--- |
| Deze stap kan door om het even welke marketing gebruiker met [standaard gebruikerstoegangsrechten](../../administration/using/users-management.md#basic-users) worden uitgevoerd. | Bewerk het transactiebericht, test het en publiceer het. | Het transactiebericht is dan klaar om te worden verzonden. |

Zie [Transactieberichten bewerken](../../channels/using/editing-transactional-message.md) en [Levenscyclus van transactieberichten](../../channels/using/publishing-transactional-message.md) voor meer informatie over het bewerken en publiceren van een transactiebericht.

### Stap 3 - Integreer de gebeurtenis die {#integrate-event-trigger} teweegbrengt

<img src="assets/do-not-localize/icon_api.svg" width="55px">

<!--**Event triggering integration**-->

| Gebruiker | Handeling | Resultaat |
|--- |--- |--- |
| Deze stap wordt uitgevoerd door de ontwikkelaar van uw website. | Gebruik de REST Transaction Messages API om de gebeurtenis in uw website te integreren. | De gebeurtenis wordt geactiveerd wanneer een klant zijn winkelwagentje verlaat. |

Nadat u een gebeurtenis hebt gemaakt, moet u het activeren van deze gebeurtenis integreren in uw website.<!--In this example, you want a "Cart abandonment" event to be triggered whenever one of your clients leaves your website before purchasing the products in their cart.--> Hiervoor moet de webontwikkelaar van uw website de  **Adobe Campaign Standard REST API** gebruiken.

Zie de [REST API-documentatie](../../api/using/managing-transactional-messages.md) voor meer informatie over het gebruik van de API voor campagne REST voor het beheer van transactieberichten.

### Stap 4 - Berichtlevering {#message-delivery}

<img src="assets/do-not-localize/icon_channels.svg" width="60px">

Zodra al deze stappen zijn uitgevoerd, kan het bericht worden geleverd.

Zodra een gebruiker de site verlaat zonder de producten in zijn winkelwagentje te bestellen, wordt de bijbehorende Campagne-gebeurtenis geactiveerd. De gebruiker ontvangt automatisch een e-mailbericht.

## Verwante onderwerpen

* [Belangrijkste stappen om een bericht te verzenden](../../channels/using/key-steps-to-send-a-message.md)
* [Aan de slag met communicatiekanalen](../../channels/using/get-started-communication-channels.md)
* [Transactionele pushmeldingen](../../channels/using/transactional-push-notifications.md)
* [Vervolgberichten](../../channels/using/follow-up-messages.md)
