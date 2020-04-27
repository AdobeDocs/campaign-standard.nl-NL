---
title: Informatie over transactieberichten
description: Ontdek de verschillende typen transactieberichten die u kunt verzenden en hoe deze in Adobe Campagne worden gebruikt.
page-status-flag: never-activated
uuid: 8470e9e2-ee17-456f-9e4c-460e69c78a2c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: transactional-messaging
discoiquuid: 71a4d5d5-fe2a-4ce5-b22b-a4736f7add83
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f0f7441f06b51f9bd2d5a1b3c26f031d4eb1e4c1

---


# Informatie over transactieberichten{#about-transactional-messaging}

U kunt persoonlijke transactieberichten maken en beheren in Adobe Campagne.

Een transactiebericht is een individuele en unieke communicatie die door een provider, zoals een website, naar een gebruiker wordt verzonden.

* Dit type van bericht wordt met name verwacht, aangezien het informatie bevat die de ontvanger wil controleren of bevestigen. Het kan een welkomstbericht zijn nadat u bijvoorbeeld een account hebt gemaakt, of een bevestiging dat een bestelling is verzonden, een factuur of een bericht waarin een wachtwoordwijziging wordt bevestigd.
* Het is een belangrijk bericht dat de relatie met de client definieert: de gebruiker verwacht dat het in real time wordt verzonden. De vertraging tussen de gebeurtenis die wordt geïnitieerd en het bericht dat aankomt, moet daarom zeer kort zijn.
* Transactieberichten hebben over het algemeen hoge open snelheden.

Met Adobe Campaign kunt u deze functionaliteit integreren met een informatiesysteem dat er gebeurtenissen naar verzendt die moeten worden omgezet in aangepaste transactieberichten.

>[!NOTE]
>
>Transactieberichten kunnen worden verzonden via e-mail, SMS of pushmelding, afhankelijk van uw opties. Controleer uw licentieovereenkomst.

Er zijn twee typen transactieberichten beschikbaar in Adobe Campagne:

* [Transactieberichten](../../channels/using/event-transactional-messages.md) voor gebeurtenissen die zich richten op een gebeurtenis. De gegevens in de gebeurtenis zelf worden gebruikt om het leveringsdoel te bepalen.
* [Transactieberichten](../../channels/using/profile-transactional-messages.md) voor profielen in de marketingdatabase van Adobe Campagne profileren. U kunt gegevens uit de Adobe Campagne-database gebruiken om een transactiemelding te verzenden op basis van marketingprofielen van klanten.

Het berichttype wordt bepaald wanneer het vormen van de gebeurtenis die in een transactioneel bericht zal worden omgezet. Zie [Transactionele overseinenconfiguratie](../../administration/using/configuring-transactional-messaging.md).

>[!NOTE]
>
>Adobe Campaign geeft prioriteit aan het verwerken van de transactiemeldingen boven andere leveringen.

Transactieberichten zijn ook beschikbaar via de Adobe Campagne Standard API. Raadpleeg de [desbetreffende documentatie](../../api/using/managing-transactional-messages.md)voor meer informatie hierover.

>[!NOTE]
>
>Alle transactieberichten worden nu verzonden met de verbeterde MTA van de Campagne van Adobe voor betere leverability, productie, en stuiterende behandeling. Alle effecten zijn hetzelfde als bij standaardmarketingberichten. Zie deze [sectie](../../administration/using/configuring-email-channel.md)voor meer informatie.

## Operationeel beginsel van het transactieverkeer {#transactional-messaging-operating-principle}

Laten we het voorbeeld nemen van een bedrijf dat een website heeft en op deze website kunnen gebruikers producten kopen.

Met Adobe Campaign kunt u een e-mailbericht verzenden naar sitegebruikers die producten aan hun winkelwagentje hebben toegevoegd: wanneer een van hen de site verlaat zonder dat hij of zij met zijn of haar aankopen heeft gedaan , wordt er automatisch een e-mail over het verlaten van het winkelwagentje naar hen gestuurd .

De stappen om dit in werking te stellen zijn:

1. Configureer een gebeurtenis met de naam &quot;Afstand starten&quot; en publiceer deze gebeurtenisconfiguratie, die automatisch een transactiebericht maakt. Het creëren van en het publiceren van een gebeurtenis worden voorgesteld in het [Vormen van een gebeurtenis om een het berichtsectie van de gebeurtenistransactie](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) te verzenden.
1. Het transactiebericht moet worden gepersonaliseerd, worden getest, dan worden gepubliceerd. Zie Transactieberichten voor [gebeurtenissen](../../channels/using/event-transactional-messages.md).
1. Bovendien moet deze gebeurtenis, voordat de gebeurtenis wordt geactiveerd wanneer een klant zijn winkelwagen verlaat, vanaf de website van het bedrijf worden verzonden met de Adobe Campagne Standard REST API. Zie [Site-integratie](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website).

Zodra al deze stappen zijn uitgevoerd, zodra een gebruiker de site verlaat zonder de producten in zijn winkelwagentje te bestellen, ontvangen zij automatisch een e-mail met meldingen.

## Transactieproces voor de publicatie van berichten {#transactional-messaging-pub-process}

De grafiek hieronder illustreert het transactieoverseinenpublicatieproces.

![](assets/message-center_pub-process.png)

Voor meer op de stappen van de gebeurtenisconfiguratie, zie [Transactionele overseinenconfiguratie](../../administration/using/configuring-transactional-messaging.md).

## Transactionele berichtenbeperkingen {#transactional-messaging-limitations}

>[!NOTE]
>
>Om tot transactieberichten toegang te hebben, moet u beleidsrechten hebben.

### Ontwerp en publicatie {#design-and-publication}

Tijdens het ontwerpen en publiceren van transactieberichten kunnen sommige stappen die u moet uitvoeren, niet worden teruggezet. U dient op de hoogte te zijn van de volgende beperkingen:

* Voor elke gebeurtenisconfiguratie kan slechts één kanaal worden gebruikt. Zie [Een gebeurtenis](../../administration/using/configuring-transactional-messaging.md#creating-an-event)maken.
* Nadat de gebeurtenis is gemaakt, kunt u het kanaal niet meer wijzigen. Daarom als een bericht niet met succes wordt verzonden, moet u het mechanisme ontwerpen dat het toestaat om het van een ander kanaal te verzenden gebruikend een werkschema. Zie [Werkstroomgegevens en processen](../../automating/using/workflow-data-and-processes.md).
* U kunt de doeldimensie ( **[!UICONTROL Real-time event]** of **[!UICONTROL Profile]** ) niet wijzigen nadat de gebeurtenis is gemaakt. Zie [Een gebeurtenis](../../administration/using/configuring-transactional-messaging.md#creating-an-event)maken.
* U kunt een publicatie niet terugdraaien, maar u kunt de publicatie van een gebeurtenis wel ongedaan maken: deze bewerking maakt de gebeurtenis en het bijbehorende transactiemelding ontoegankelijk. Zie Publicatie van een gebeurtenis [](../../administration/using/configuring-transactional-messaging.md#unpublishing-an-event)ongedaan maken.
* Het enige transactiebericht dat aan een gebeurtenis kan worden geassocieerd is het bericht dat automatisch wordt gecreeerd bij het publiceren van die gebeurtenis. Zie [Een voorvertoning weergeven en de gebeurtenis](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)publiceren.

### Personalisatie {#personalization}

De manier u een berichtinhoud kunt personaliseren hangt van het type van transactioneel bericht af. De specifieke kenmerken worden hieronder vermeld:

**Transactieberichten** op basis van gebeurtenissen:

* De verpersoonlijkingsinformatie komt uit de gegevens in de gebeurtenis zelf. Zie Transactieberichten voor [gebeurtenissen](../../channels/using/event-transactional-messages.md).
* U kunt inhoudsblokken voor **Unsubscription-koppelingen** niet gebruiken in een transactiebericht voor een gebeurtenis.
* Het op gebeurtenis-gebaseerde transactieoverseinen wordt verondersteld om slechts de gegevens te gebruiken die in de verzonden gebeurtenis zijn om de ontvanger en de verpersoonlijking van de berichtinhoud te bepalen. U kunt de inhoud van uw transactiemelding echter verrijken met gegevens uit de Adobe Campagne-database. Zie [De inhoud](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content)van het transactiebericht verrijken.
* Aangezien de berichten van de gebeurtenistransactie geen profielinformatie bevatten, zijn zij niet compatibel met vermoeidheidsregels, zelfs in het geval van een verrijking met profielen. Zie [Vermoeidheidsregels](../../sending/using/fatigue-rules.md).

**Transactieberichten** op basis van profiel:

* De personalisatiegegevens kunnen afkomstig zijn van de gegevens in de gebeurtenis of uit de profielrecord die met elkaar in overeenstemming is. Zie Transactieberichten [voor profielen](../../channels/using/profile-transactional-messages.md).
* U kunt de blokken van de de verbindingsinhoud van de Verbinding **van de** Unsubscription in een bericht van de profieltransactie gebruiken. Zie [Een inhoudsblok](../../designing/using/personalization.md#adding-a-content-block)toevoegen.
* De regels van de moeheid zijn compatibel met de berichten van de profieltransactie. Zie [Vermoeidheidsregels](../../sending/using/fatigue-rules.md).

Productaanbiedingen zijn alleen beschikbaar in transactie-e-mailberichten. Zie [Productaanbiedingen gebruiken in een transactiebericht](../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message).

### Machtigingen en branding {#permissions-and-branding}

Wanneer het over [branding](../../administration/using/branding.md) beheer komt, laat het transactionele overseinen minder flexibiliteit dan standaardoverseinen toe. Adobe raadt u aan alle merken die in transactieberichten worden gebruikt, te koppelen aan de **[!UICONTROL All]** organisatorische eenheid [](../../administration/using/organizational-units.md). Lees de gedetailleerde uitleg hieronder voor meer informatie.

Wanneer u een transactiemelding bewerkt, kunt u deze koppelen aan een merk om automatisch bepaalde parameters toe te passen, zoals de merknaam of het merklogo. De optie **[!UICONTROL Default brand]** is standaard geselecteerd in de eigenschappen van het transactiebericht.

![](assets/message-center_branding.png)

Alle objecten (inclusief branding) die in een transactiebericht worden gebruikt, moeten zichtbaar zijn vanuit de **[!UICONTROL Message Center]** organisatie-eenheid, wat betekent dat deze objecten zich in de **[!UICONTROL Message Center]** of **[!UICONTROL All]** organisatie-eenheden moeten bevinden.

Nochtans, als het merk in de berichteigenschappen wordt geselecteerd met een organisatorische eenheid wordt verbonden die van **[!UICONTROL Message Center]** of **[!UICONTROL All]** verschillend is, zal dit een fout veroorzaken en u zult niet het transactiebericht kunnen verzenden.

Daarom als u multi-branding in de context van transactioneel overseinen wilt gebruiken, zou u alle merken of aan de **[!UICONTROL Message Center]** organisatorische eenheid of aan de **[!UICONTROL All]** organisatorische eenheid moeten verbinden.

### Transactieberichten exporteren en importeren {#exporting-and-importing-transactional-messages}

* Als u een transactiebericht wilt exporteren, moet u de bijbehorende gebeurtenisconfiguratie opnemen wanneer u het pakket exporteert [](../../automating/using/managing-packages.md#creating-a-package)maakt.
* Zodra het transactiebericht door een pakket [wordt](../../automating/using/managing-packages.md#importing-a-package)ingevoerd, wordt het niet getoond in de transactiemeldlijst. U moet de gebeurtenisconfiguratie [publiceren](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event) om het bijbehorende transactiebericht beschikbaar te maken.

