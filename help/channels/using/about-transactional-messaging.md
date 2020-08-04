---
title: Informatie over transactieberichten
description: Ontdek de verschillende typen transactieberichten die u kunt verzenden en hoe deze in Adobe Campaign worden gebruikt.
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
translation-type: ht
source-git-commit: 68e825bc3b6b7f94f61875e7da2bc8f63f06d9cb
workflow-type: ht
source-wordcount: '1147'
ht-degree: 100%

---


# Informatie over transactieberichten{#about-transactional-messaging}

In Adobe Campaign kunt u persoonlijke transactieberichten maken en beheren.

Een transactiebericht is een persoonlijke en unieke communicatie die door een provider, zoals een website, naar een gebruiker wordt verzonden.

* Dit is een type bericht dat door de gebruiker wordt verwacht, aangezien het informatie bevat die de ontvanger wil controleren of bevestigen. Hierbij gaat het bijvoorbeeld om een welkomstbericht nadat een account is aangemaakt, een bevestiging dat een bestelling is verzonden, of om een factuur of een bericht waarin een wachtwoordwijziging wordt bevestigd.
* Dit zijn belangrijke berichten die de relatie met de klant definiëren: de gebruiker verwacht dat het in real time wordt verzonden. De tijd tussen de gebeurtenis die wordt geïnitieerd en het bericht dat aankomt, moet daarom zeer kort zijn.
* Transactieberichten worden bijna altijd geopend.

Met Adobe Campaign kunt u deze functionaliteit integreren met een informatiesysteem. Dit informatiesysteem stuurt gebeurtenissen naar Adobe Campaign die moeten worden omgezet naar aangepaste transactieberichten.

>[!NOTE]
>
>Transactieberichten kunnen worden verzonden via e-mail, sms of pushmeldingen, afhankelijk van uw opties. Controleer hiervoor uw licentieovereenkomst.

Er zijn twee typen transactieberichten beschikbaar in Adobe Campaign:

* [Gebeurtenistransactieberichten](../../channels/using/event-transactional-messages.md) die zijn gericht op een gebeurtenis. De data in de gebeurtenis zelf worden gebruikt om het leveringsdoel te bepalen.
* [Profieltransactieberichten](../../channels/using/profile-transactional-messages.md) die zijn gericht op profielen in de marketingdatabase van Adobe Campaign. Met de data uit de Adobe Campaign-database kunt u een transactiebericht verzenden op basis van het marketingprofiel van klanten.

Het berichttype wordt bepaald tijdens de configuratie van de gebeurtenis die in een transactiebericht wordt omgezet. Zie [Transactieberichten configureren](../../administration/using/configuring-transactional-messaging.md).

>[!NOTE]
>
>Adobe Campaign geeft prioriteit aan het verwerken van de transactieberichten boven andere leveringen.

Transactieberichten zijn ook beschikbaar via de Adobe Campaign Standard-API. Raadpleeg de [desbetreffende documentatie](../../api/using/managing-transactional-messages.md)voor meer informatie hierover.

>[!NOTE]
>
>Alle transactieberichten worden nu verzonden met de verbeterde MTA van Adobe Campaign voor een betere levering en doorvoer, en voor de verwerking van berichten die niet bezorgbaar zijn. Alle effecten zijn hetzelfde als bij standaardmarketingberichten. Zie [deze sectie](../../administration/using/configuring-email-channel.md) voor meer informatie.

## Werkingsprincipe voor transactieberichten {#transactional-messaging-operating-principle}

Laten we als voorbeeld een bedrijf nemen dat een website heeft waarop gebruikers producten kunnen kopen.

Met Adobe Campaign kunt u een e-mailbericht naar sitegebruikers sturen die producten in hun winkelwagen hebben geplaatst: wanneer ze de site verlaten zonder een aankoop te doen, wordt er automatisch een e-mail naar ze gestuurd met de melding dat ze een winkelwagen met artikelen hebben achtergelaten.

Voer daartoe de volgende stappen uit:

1. Configureer een gebeurtenis met de naam &quot;Winkelwagen achtergelaten&quot; en publiceer deze gebeurtenisconfiguratie. Hierdoor wordt automatisch een transactiebericht gemaakt. Het maken en publiceren van een gebeurtenis wordt beschreven in de sectie [Een gebeurtenis configureren voor het sturen van een gebeurtenistransactiebericht](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message).
1. Het transactiebericht moet worden gepersonaliseerd, getest en vervolgens gepubliceerd. Zie [Transactieberichten voor gebeurtenissen](../../channels/using/event-transactional-messages.md).
1. Om de gebeurtenis te activeren wanneer een klant zijn winkelwagen laat staan, moet deze gebeurtenis worden verzonden vanaf de website van het bedrijf met behulp van de Adobe Campaign Standard REST-API. Zie [Site-integratie](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website).

Wanneer al deze stappen zijn uitgevoerd, zal de gebruiker automatisch een e-mailbericht ontvangen zodra hij of zij een volle winkelwagen achterlaat en de site verlaat.

## Publicatieproces voor transactieberichten {#transactional-messaging-pub-process}

De grafiek hieronder illustreert het publicatieproces voor transactieberichten.

![](assets/message-center_pub-process.png)

Voor meer informatie over de stappen in het configuratieproces voor gebeurtenissen gaat u naar [Transactieberichten configureren](../../administration/using/configuring-transactional-messaging.md).

## Beperkingen voor transactieberichten {#transactional-messaging-limitations}

>[!NOTE]
>
>Voor toegang tot de transactieberichten moet u beheerrechten hebben.

### Ontwerp en publicatie {#design-and-publication}

Tijdens het ontwerpen en publiceren van transactieberichten kunnen sommige stappen die u moet uitvoeren, niet worden teruggedraaid. U dient op de hoogte te zijn van de volgende beperkingen:

* Voor elke gebeurtenisconfiguratie kan slechts één kanaal worden gebruikt. Zie [Een gebeurtenis maken](../../administration/using/configuring-transactional-messaging.md#creating-an-event).
* Nadat de gebeurtenis is gemaakt, kunt u het kanaal niet meer wijzigen. Als een bericht niet succesvol wordt verzonden, moet u een mechanisme ontwerpen waardoor het bericht door middel van een workflow via een ander kanaal wordt verzonden. Zie [Workflowdata en processen](../../automating/using/get-started-workflows.md).
* U kunt de doeldimensie (**[!UICONTROL Real-time event]** of **[!UICONTROL Profile]**) niet wijzigen nadat de gebeurtenis is gemaakt. Zie [Een gebeurtenis maken](../../administration/using/configuring-transactional-messaging.md#creating-an-event).
* U kunt een publicatie niet terugdraaien, maar u kunt de publicatie van een gebeurtenis wel ongedaan maken, zodat de gebeurtenis en het bijbehorende transactiebericht ontoegankelijk worden. Zie [Publicatie van een gebeurtenis ongedaan maken](../../administration/using/configuring-transactional-messaging.md#unpublishing-an-event).
* Het enige transactiebericht dat met een gebeurtenis kan worden geassocieerd, is het bericht dat automatisch wordt gemaakt tijdens het publiceren van die gebeurtenis. Zie [Een voorvertoning weergeven en de gebeurtenis publiceren](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event).

### Personalisatie {#personalization}

De manier waarop u berichtcontent kunt personaliseren hangt af van het type transactiebericht. Specifieke informatie staat hieronder:

**Transactieberichten op basis van gebeurtenissen**:

* De persoonlijke informatie komt uit data van de gebeurtenis zelf. Zie [Transactieberichten voor gebeurtenissen](../../channels/using/event-transactional-messages.md).
* U kunt geen contentblok voor **de koppeling Uitschrijven** gebruiken in een transactiebericht voor een gebeurtenis.
* Het gebeurtenistransactiebericht wordt verondersteld om alleen de data in de verzendgebeurtenis zelf te gebruiken bij het bepalen van de ontvanger en de personalisatie van de berichtcontent. U kunt de content van het transactiebericht echter wel verrijken met data uit de Adobe Campaign-database. Zie [De content van het transactiebericht verrijken](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content).
* Aangezien de transactieberichten voor gebeurtenissen geen profielinformatie bevatten, zijn ze niet compatibel met &#39;moeheidsregels&#39;, zelfs in het geval van een verrijking met profielen. Zie [Moeheidsregels](../../sending/using/fatigue-rules.md).

**Transactieberichten op basis van profiel**:

* De personalisatiegegevens kunnen afkomstig zijn van de data in de gebeurtenis of van de afgestemde profielrecord. Zie [Profieltransactieberichten](../../channels/using/profile-transactional-messages.md).
* U kunt het contentblok voor **de koppeling Uitschrijven** gebruiken in een profieltransactiebericht. Zie [Een contentblok](../../designing/using/personalization.md#adding-a-content-block) toevoegen.
* De moeheidsregels zijn compatibel met transactieberichten voor profielen. Zie [Moeheidsregels](../../sending/using/fatigue-rules.md).

Productaanbiedingen zijn alleen beschikbaar in transactionele e-mailberichten. Zie [Productaanbiedingen gebruiken in een transactiebericht](../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message).

### Toestemmingen en branding{#permissions-and-branding}

Wanneer het om het beheer van [branding](../../administration/using/branding.md) gaat, biedt transactionele messaging minder flexibiliteit dan standaard messaging. Adobe raadt u aan alle merken die in transactieberichten worden gebruikt, te koppelen aan de **[!UICONTROL All]** organisatorische eenheid[](../../administration/using/organizational-units.md). Lees de gedetailleerde uitleg hieronder voor meer informatie.

Wanneer u een transactiebericht bewerkt, kunt u het aan een merk koppelen en automatisch bepaalde parameters toepassen, zoals de merknaam of het logo. De optie **[!UICONTROL Default brand]** is standaard geselecteerd in de eigenschappen van het transactiebericht.

![](assets/message-center_branding.png)

Alle objecten (inclusief branding) die in een transactiebericht worden gebruikt, moeten zichtbaar zijn vanuit de **[!UICONTROL Message Center]**-organisatie-eenheid, wat betekent dat deze objecten zich in de organisatie-eenheden **[!UICONTROL Message Center]** of **[!UICONTROL All]** moeten bevinden.

Als het geselecteerde merk in de berichteigenschappen wordt gekoppeld aan een organisatie-eenheid die anders is dan **[!UICONTROL Message Center]** of **[!UICONTROL All]**, wordt een fout veroorzaakt en kunt u het transactiebericht niet verzenden.

Als u multi-branding daarom binnen de context van transactieberichten wilt gebruiken, moet u alle merken ofwel koppelen aan de organisatie-eenheid **[!UICONTROL Message Center]** of aan **[!UICONTROL All]**.

### Transactieberichten exporteren en importeren {#exporting-and-importing-transactional-messages}

* Als u een transactiebericht wilt exporteren, moet u de bijbehorende gebeurtenisconfiguratie opnemen wanneer u [het pakket voor exporteren maakt](../../automating/using/managing-packages.md#creating-a-package).
* Als het transactiebericht eenmaal via een pakket [is geïmporteerd](../../automating/using/managing-packages.md#importing-a-package), wordt het niet weergegeven in de lijst met transactieberichten. U moet de gebeurtenisconfiguratie [publiceren](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event) om het bijbehorende transactiebericht beschikbaar te maken.

