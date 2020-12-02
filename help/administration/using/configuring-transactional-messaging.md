---
solution: Campaign Standard
product: campaign
title: Transactionele berichten configureren
description: Leer hoe te om transactioneel overseinen te vormen.
audience: administration
content-type: reference
topic-tags: configuring-channels
translation-type: tm+mt
source-git-commit: a0ad969c86a5047f3f967a21fdc2d6040d7d939f
workflow-type: tm+mt
source-wordcount: '3169'
ht-degree: 7%

---


# Transactionele berichten configureren{#configuring-transactional-messaging}

Als u een transactiebericht met Adobe Campaign wilt verzenden, moet u eerst de structuur van de gebeurtenisgegevens beschrijven.

De configuratie van de gebeurtenis moet door een [beheerder](../../administration/using/users-management.md#functional-administrators) volgend de hieronder stappen worden uitgevoerd.

>[!NOTE]
>
>De configuratie kan afhankelijk van het type van transactiebericht variëren u wilt verzenden. Raadpleeg [Transactionele specifieke configuraties voor gebeurtenissen](#transactional-event-specific-configurations) voor meer informatie.

Nadat de gebeurtenis is gepubliceerd:

* De API die door uw websiteontwikkelaar wordt gebruikt, wordt opgesteld en de transactionele gebeurtenissen kunnen nu worden verzonden. Zie [Het activeren van de gebeurtenis in een website integreren](#integrating-the-triggering-of-the-event-in-a-website).

* Het overeenkomstige transactiemelding wordt automatisch gecreeerd. Zie [Aan de slag met transactioneel overseinen](../../channels/using/getting-started-with-transactional-msg.md).

## Een gebeurtenis {#creating-an-event} maken

Maak de gebeurtenis die aan uw behoeften voldoet om aan de slag te gaan.

>[!IMPORTANT]
>
>Alleen gebruikers met de rol **[!UICONTROL Administration]** en die deel uitmaken van de **[!UICONTROL All]** [organisatie-eenheid](../../administration/using/organizational-units.md) hebben de juiste rechten om een gebeurtenisconfiguratie te maken.

1. Klik in de linkerbovenhoek op het logo **[!UICONTROL Adobe Campaign]** en selecteer **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]**.
1. Klik op de knop **[!UICONTROL Create]**.
1. Geef een **[!UICONTROL Label]** en een **[!UICONTROL ID]** aan de gebeurtenis. Het veld **[!UICONTROL ID]** is verplicht en moet beginnen met het voorvoegsel &quot;EVT&quot;. Als u dit voorvoegsel niet gebruikt, wordt het automatisch toegevoegd zodra u **[!UICONTROL Create]** klikt.

   ![](assets/message-center_1.png)

   >[!IMPORTANT]
   >
   >De id mag niet langer zijn dan 64 tekens, inclusief het voorvoegsel EVT.

1. Selecteer het kanaal dat wordt gebruikt om uw transactiemeldingen **[!UICONTROL Email]**, **[!UICONTROL Mobile (SMS)]** of **[!UICONTROL Mobile application]** (pushmelding) te verzenden.

   >[!NOTE]
   >
   >Voor elke gebeurtenisconfiguratie kan slechts één kanaal worden gebruikt. Nadat de gebeurtenis is gemaakt, kunt u het kanaal niet meer wijzigen.

1. Selecteer de doeldimensie die overeenkomt met de gewenste gebeurtenisconfiguratie en klik op **[!UICONTROL Create]**.

   Transactieberichten die zijn gebaseerd op gebeurtenissen, zijn gericht op gegevens die zich in de gebeurtenis zelf bevinden, terwijl op een profiel gebaseerde transactieberichten bedoeld zijn voor gegevens die zich in de Adobe Campaign-database bevinden. Raadpleeg [Transactionele specifieke configuraties voor gebeurtenissen](#transactional-event-specific-configurations) voor meer informatie.

>[!NOTE]
>
>Het aantal gemaakte realtime-gebeurtenissen kan van invloed zijn op uw platform. Voor optimale prestaties moet u realtime gebeurtenissen verwijderen die u niet meer nodig hebt. Zie [Een gebeurtenis verwijderen](#deleting-an-event).

## Gebeurteniskenmerken definiëren {#defining-the-event-attributes}

In **[!UICONTROL Fields]** sectie, bepaal de attributen die in de gebeurtenisinhoud zullen worden geïntegreerd en dan kunnen worden gebruikt om het transactionele bericht te personaliseren.

De stappen voor het toevoegen en wijzigen van gebieden zijn het zelfde als voor [douanemiddelen](../../developing/using/configuring-the-resource-s-data-structure.md#adding-fields-to-a-resource).

![](assets/message-center_2.png)

>[!NOTE]
>
>Als u een meertalig transactiebericht wilt creëren, bepaal een extra gebeurtenisattribuut met **[!UICONTROL AC_language]** identiteitskaart Dit is alleen van toepassing op transactieberichten voor gebeurtenissen. Nadat de gebeurtenis is gepubliceerd, zijn de stappen voor het bewerken van de inhoud van een meertalig transactiebericht gelijk aan die voor een meertalig standaard-e-mailbericht. Zie [Een meertalige e-mail maken](../../channels/using/creating-a-multilingual-email.md).

## Gegevensverzamelingen {#defining-data-collections} definiëren

U kunt aan de inhoud van de gebeurtenis een inzameling van elementen toevoegen, elk element zelf met verscheidene attributen.

Deze verzameling kan worden gebruikt in een transactie-e-mail om [productaanbiedingen](../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message) aan de inhoud van het bericht toe te voegen, bijvoorbeeld een lijst met producten - met de prijs, het referentienummer, het aantal, enz. voor elk product in de lijst.

1. Klik in de sectie **[!UICONTROL Collections]** op de knop **[!UICONTROL Create element]**.

   ![](assets/message-center_collection_create.png)

1. Voeg een label en een id voor uw verzameling toe.
1. Voeg alle velden toe die u in het transactiebericht voor elk product in de lijst wilt weergeven.

   In dit voorbeeld hebben we de volgende velden toegevoegd:

   ![](assets/message-center_collection_fields.png)

1. Met het tabblad **[!UICONTROL Enrichment]** kunt u elk item van de verzameling verrijken. Op deze manier kunt u de elementen van de overeenkomende productlijst aanpassen met informatie uit de Adobe Campaign-database of uit andere bronnen die u hebt gemaakt.

>[!NOTE]
>
>De stappen voor het verrijken van de elementen van een inzameling zijn het zelfde als beschreven in [het Verrijken van de gebeurtenis](#enriching-the-transactional-message-content) sectie. Door de gebeurtenis te verrijken, kunt u een verzameling niet verrijken: u moet een verrijking aan de inzameling zelf in **[!UICONTROL Collections]** sectie toevoegen.

Zodra de gebeurtenis en het bericht worden gepubliceerd, zult u deze inzameling in uw transactiebericht kunnen gebruiken.

Hier volgt de API-voorvertoning voor dit voorbeeld:

![](assets/message-center_collection_api-preview.png)

**Verwante onderwerpen:**

* [De gebeurtenis voorvertonen en publiceren](#previewing-and-publishing-the-event)
* [Productvermeldingen gebruiken in een transactiebericht](../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message)

## De gebeurtenis {#enriching-the-transactional-message-content} verrijken

U kunt de inhoud van het transactiebericht verrijken met informatie uit de Adobe Campaign-database om uw berichten aan te passen. Van achternaam of identiteitskaart van CRM van elk van uw ontvangers, bijvoorbeeld, kunt u gegevens zoals hun adres of geboortedatum of een ander douanegebied terugkrijgen dat in de lijst van het Profiel wordt toegevoegd, om de informatie te personaliseren die naar hen wordt verzonden.

Het is mogelijk om de inhoud van het transactiebericht met informatie van uitgebreide **[!UICONTROL Profile and services Ext API]** te verrijken. Raadpleeg [API uitbreiden voor meer informatie: De extensie publiceren](../../developing/using/step-2--publish-the-extension.md)

Deze informatie kan ook in nieuwe middelen worden opgeslagen. In dat geval moet de bron direct of via een andere tabel worden gekoppeld aan de **[!UICONTROL Profile]**- of **[!UICONTROL Service]**-bronnen. Bijvoorbeeld, in de configuratie hieronder, is het mogelijk om de inhoud van het transactionele bericht met informatie van de **[!UICONTROL Product]** middel zoals de productcategorie of identiteitskaart te verrijken, als **[!UICONTROL Product]** middel met **[!UICONTROL Profile]** middel wordt verbonden.

![](assets/message-center_usecaseschema.png)

Raadpleeg [deze pagina](../../developing/using/key-steps-to-add-a-resource.md) voor meer informatie over het maken en publiceren van bronnen.

1. Klik in de sectie **[!UICONTROL Enrichment]** op de knop **[!UICONTROL Create element]**.

   ![](assets/message-center_addenrichment.png)

1. Selecteer de bron waarmee u uw bericht wilt koppelen. Kies in dit geval de **[!UICONTROL Profile]**-bron.

   ![](assets/message-center_new-enrichment.png)

1. Met de knop **[!UICONTROL Create element]** kunt u een veld van de geselecteerde bron koppelen aan een van de velden die u eerder aan de gebeurtenis hebt toegevoegd (zie [De gebeurteniskenmerken definiëren](#defining-the-event-attributes)).

   ![](assets/message-center_enrichment-join.png)

1. In dit voorbeeld combineren we de **[!UICONTROL Last name]**- en **[!UICONTROL First name]**-velden met de corresponderende velden in de **[!UICONTROL Profile]**-bron.

   ![](assets/message-center_enrichment-join-fields.png)

   U kunt de transactionele berichtinhoud ook verrijken gebruikend **[!UICONTROL Service]** middel. Zie deze [sectie](../../audiences/using/creating-a-service.md) voor meer informatie over services.

1. Als u of een op profiel-gebaseerde gebeurtenis creeert uitgeeft, in **[!UICONTROL Targeting enrichment]** sectie, selecteer de verrijking die als berichtdoel tijdens de leveringsuitvoering zal worden gebruikt.

   ![](assets/message-center_marketing_targeting_enrichment.png)

   >[!NOTE]
   >
   >Het selecteren van een het richten verrijking die op **[!UICONTROL Profile]** middel wordt gebaseerd is verplicht voor op profiel-gebaseerde gebeurtenissen.

Zodra de gebeurtenis en het bericht worden gepubliceerd, zal deze verbinding u toestaan om de inhoud van het transactiebericht te verrijken.

**Verwante onderwerpen:**

* [Een voorvertoning weergeven en de gebeurtenis](#previewing-and-publishing-the-event) publiceren.
* [Een transactiebericht aanpassen](../../channels/using/event-transactional-messages.md#personalizing-a-transactional-message).

## De gebeurtenis voorvertonen en publiceren {#previewing-and-publishing-the-event}

Voordat u de gebeurtenis kunt gebruiken, moet u deze voorvertonen en publiceren.

1. Klik op de knop **[!UICONTROL API preview]** om een simulatie van de REST API weer te geven die door uw websiteontwikkelaar wordt gebruikt voordat deze wordt gepubliceerd. Nadat de gebeurtenis is gepubliceerd, kunt u met deze knop ook een voorvertoning van de API in productie zien. Zie [Het activeren van de gebeurtenis in een website integreren](#integrating-the-triggering-of-the-event-in-a-website).

   ![](assets/message-center_api_preview.png)

   >[!NOTE]
   >
   >De REST API varieert afhankelijk van het geselecteerde kanaal en de geselecteerde doeldimensie. Raadpleeg [Transactionele specifieke configuraties van gebeurtenissen](#transactional-event-specific-configurations) voor meer informatie over de verschillende configuraties.

1. Klik op **[!UICONTROL Publish]** om de publicatie te starten.

   ![](assets/message-center_pub.png)

   De API die door uw websiteontwikkelaar wordt gebruikt, wordt opgesteld en de transactionele gebeurtenissen kunnen nu worden verzonden.

1. U kunt de publicatielogboeken weergeven op het bijbehorende tabblad.

   ![](assets/message-center_logs.png)

   >[!IMPORTANT]
   >
   >Telkens wanneer u de gebeurtenis wijzigt, moet u **[!UICONTROL Publish]** opnieuw klikken om de bijgewerkte REST API te genereren die door uw websiteontwikkelaar zal worden gebruikt.

   Nadat de gebeurtenis is gepubliceerd, wordt automatisch een transactiebericht gemaakt dat aan de nieuwe gebeurtenis is gekoppeld.

1. U kunt tot dit transactiebericht direct toegang hebben door de verbinding die in het linkerzijgebied wordt gevestigd.

   ![](assets/message-center_messagegeneration.png)

Als de gebeurtenis het verzenden van een transactiemelding moet activeren, moet u het bericht wijzigen en publiceren dat net is gemaakt. Zie [Transactieberichten voor gebeurtenissen](../../channels/using/event-transactional-messages.md).

U moet deze triggergebeurtenis ook integreren in uw website. Zie [Het activeren van de gebeurtenis in een website integreren](#integrating-the-triggering-of-the-event-in-a-website).

Zodra Adobe Campaign gebeurtenissen ontvangt die betrekking hebben op deze gebeurtenisconfiguratie, kunt u via de koppeling **[!UICONTROL Latest transactional events]** onder de sectie **[!UICONTROL History]** toegang krijgen tot de meest recente gebeurtenissen die door uw externe service worden verzonden en door Adobe Campaign worden verwerkt.

![](assets/message-center_latest-events.png)

De gebeurtenissen (in JSON-indeling) worden weergegeven van de meest recente tot de oudste. Met deze lijst kunt u gegevens zoals de inhoud of de status van een gebeurtenis controleren voor controle en foutopsporing.

### Publiceren van een gebeurtenis {#unpublishing-an-event} ongedaan maken

Met de knop **[!UICONTROL Unpublish]** kunt u de publicatie van de gebeurtenis annuleren. Hierdoor wordt de bron die overeenkomt met de gebeurtenis die u eerder hebt gemaakt, verwijderd uit de REST API. Zelfs als de gebeurtenis via uw website wordt geactiveerd, worden de bijbehorende berichten niet meer verzonden en niet opgeslagen in de database.

![](assets/message-center_unpublish.png)

>[!NOTE]
>
>Als u het overeenkomstige transactiemelding reeds hebt gepubliceerd, wordt de transactieberichtpublicatie ook geannuleerd. Zie [Publicatie van een transactiebericht opheffen](../../channels/using/event-transactional-messages.md#unpublishing-a-transactional-message).

Klik op de knop **[!UICONTROL Publish]** om een nieuwe REST API te genereren.

### Publicatieproces voor transactieberichten {#transactional-messaging-pub-process}

De grafiek hieronder illustreert het publicatieproces voor transactieberichten.

![](assets/message-center_pub-process.png)

Zie [deze sectie](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message) voor meer informatie over het publiceren, pauzeren en publiceren van een transactiebericht.

### Een gebeurtenis {#deleting-an-event} verwijderen

Nadat een gebeurtenis niet gepubliceerd is of nog niet gepubliceerd is, kunt u deze verwijderen uit de lijst met gebeurtenisconfiguraties. Dit doet u als volgt:

1. Klik in de linkerbovenhoek op het logo **[!UICONTROL Adobe Campaign]** en selecteer **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]**.
1. Houd de muis boven de gebeurtenisconfiguratie van uw keuze en selecteer de knop **[!UICONTROL Delete element]**.

   ![](assets/message-center_delete-button.png)

   >[!NOTE]
   >
   >Zorg ervoor de gebeurtenisconfiguratie de **[!UICONTROL Draft]** status heeft, anders zult u niet het kunnen schrappen. De status **[!UICONTROL Draft]** is van toepassing op een gebeurtenis die nog niet is gepubliceerd of die [niet is gepubliceerd](#unpublishing-an-event).

1. Klik op de knop **[!UICONTROL Confirm]**.

   ![](assets/message-center_delete-confirm.png)

>[!IMPORTANT]
>
>Als u een gebeurtenisconfiguratie verwijdert die is gepubliceerd en al wordt gebruikt, worden ook de bijbehorende transactiemeldingen en de bijbehorende verzendings- en trackinglogboeken verwijderd.

## Transactiegebeurtenissen zoeken {#searching-transactional-events}

Voer de onderstaande stappen uit om de reeds gemaakte transactiegebeurtenissen te openen en te doorzoeken.

1. Klik in de linkerbovenhoek op het logo **[!UICONTROL Adobe Campaign]** en selecteer **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]**.
1. Klik op de knop **[!UICONTROL Show search]**.

   ![](assets/message-center_search-events.png)

1. U kunt filteren op **[!UICONTROL Publication status]**. Zo kunt u bijvoorbeeld alleen de gepubliceerde gebeurtenissen weergeven.
1. U kunt de gebeurtenissen ook filteren met de **[!UICONTROL Last event received]**. Als u bijvoorbeeld 10 invoert, worden alleen de gebeurtenisconfiguraties met de laatste gebeurtenis die tien dagen geleden of later is ontvangen, weergegeven. Hierdoor kunt u weergeven welke gebeurtenissen gedurende een bepaalde periode inactief zijn geweest.

   ![](assets/message-center_last-event-received.png)

   >[!NOTE]
   >
   >De standaardwaarde is 0. Alle gebeurtenissen worden dan weergegeven.

## De activering van de gebeurtenis integreren in een website {#integrating-the-triggering-of-the-event-in-a-website}

Nadat u een gebeurtenis hebt gemaakt, moet u de activering van deze gebeurtenis integreren in uw website.

In het voorbeeld dat wordt beschreven in de sectie [Transactioneel messaging-besturingssysteem](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle), wilt u dat een gebeurtenis &quot;Afkapping van winkelwagentje&quot; wordt geactiveerd wanneer een van uw klanten uw website verlaat voordat ze de producten in hun winkelwagentje kopen. Hiervoor moet de webontwikkelaar van uw website de Adobe Campaign Standard REST API gebruiken.

Zie de [REST API-documentatie](../../api/using/managing-transactional-messages.md).

## Specifieke configuraties voor transactiegebeurtenissen {#transactional-event-specific-configurations}

Transactionele gebeurtenisconfiguratie kan afhankelijk van het type van transactiebericht variëren u (gebeurtenis of profiel) wilt verzenden, en het kanaal dat zal worden gebruikt.

In de volgende secties wordt gedetailleerd welke specifieke configuratie moet worden ingesteld op basis van het gewenste transactiebericht. Raadpleeg [Een gebeurtenis maken](#creating-an-event) voor meer informatie over de algemene stappen voor het configureren van een gebeurtenis.

### Transactieberichten op basis van gebeurtenissen {#event-based-transactional-messages}

Als u een op een gebeurtenis gebaseerd transactiebericht wilt verzenden, moet u eerst een gebeurtenis maken en configureren die zich richt op de gegevens in de gebeurtenis zelf.
Voor meer informatie, zie [Het aangaan met transactioneel overseinen](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Managedatatofuelengagingexperiences).

1. Wanneer u de gebeurtenisconfiguratie maakt, selecteert u de **[!UICONTROL Real-time event]**-doeldimensie (zie [Een gebeurtenis maken](#creating-an-event)).
1. Voeg velden aan de gebeurtenis toe om het transactiebericht aan te passen (zie [Gebeurteniskenmerken definiëren](#defining-the-event-attributes)).
1. Verrijk de inhoud van het transactiebericht als u extra informatie van het gegevensbestand van Adobe Campaign wilt gebruiken (zie [Verrijkend de inhoud van het transactionele bericht](#enriching-the-transactional-message-content)).

   >[!NOTE]
   >
   >Het gebeurtenistransactiebericht wordt verondersteld om alleen de data in de verzendgebeurtenis zelf te gebruiken bij het bepalen van de ontvanger en de personalisatie van de berichtcontent. U kunt de content van het transactiebericht echter wel verrijken met data uit de Adobe Campaign-database.

1. Geef een voorvertoning weer van de gebeurtenis en publiceer de gebeurtenis (zie [De gebeurtenis voorvertonen en publiceren](#previewing-and-publishing-the-event)).

   Wanneer u een voorvertoning van de gebeurtenis weergeeft, bevat de REST API een kenmerk dat het e-mailadres of de mobiele telefoon opgeeft volgens het geselecteerde kanaal.

   Nadat de gebeurtenis is gepubliceerd, wordt automatisch een transactiebericht gemaakt dat aan de nieuwe gebeurtenis is gekoppeld. Opdat de gebeurtenis het verzenden van een transactiebericht teweegbrengt, moet u het bericht wijzigen en publiceren dat enkel werd gecreeerd, zie [Transactieberichten van de Gebeurtenis](../../channels/using/event-transactional-messages.md).

1. Integreer de gebeurtenis in uw website (zie [Het activeren van de gebeurtenis in een website integreren](#integrating-the-triggering-of-the-event-in-a-website)).

### Transactieberichten op basis van profiel {#profile-based-transactional-messages}

Als u een op een profiel gebaseerd transactiebericht wilt verzenden, moet u eerst een gebeurtenis maken en configureren die gegevens als doel heeft die zich in de Adobe Campaign-database bevinden.

1. Wanneer u de gebeurtenisconfiguratie maakt, selecteert u de **[!UICONTROL Profile event]**-doeldimensie (zie [Een gebeurtenis maken](#creating-an-event)).
1. Voeg velden aan de gebeurtenis toe om het transactiebericht aan te passen (zie [Gebeurteniskenmerken definiëren](#defining-the-event-attributes)). U moet ten minste één veld toevoegen om een verrijking te maken. U hoeft geen andere velden te maken, zoals **Voornaam** en **Achternaam**, omdat u verpersoonlijkingsvelden uit de Adobe Campaign-database kunt gebruiken.
1. Maak een verrijking om de gebeurtenis te koppelen aan de **[!UICONTROL Profile]**-bron (zie [De inhoud van het transactiebericht verrijken](#enriching-the-transactional-message-content)). Het maken van een verrijking is verplicht wanneer u een **[!UICONTROL Profile]**-doeldimensie gebruikt.
1. Geef een voorvertoning weer van de gebeurtenis en publiceer de gebeurtenis (zie [De gebeurtenis voorvertonen en publiceren](#previewing-and-publishing-the-event)).

   Als u een voorvertoning van de gebeurtenis weergeeft, bevat de REST API geen kenmerk dat het e-mailadres of de mobiele telefoon opgeeft zoals deze wordt opgehaald uit de **[!UICONTROL Profile]**-bron.

   Nadat de gebeurtenis is gepubliceerd, wordt automatisch een transactiebericht gemaakt dat aan de nieuwe gebeurtenis is gekoppeld. Opdat de gebeurtenis het verzenden van een transactiebericht teweegbrengt, moet u het bericht wijzigen en publiceren dat enkel werd gecreeerd, zie [Verzendend een bericht van de profieltransactie](../../channels/using/profile-transactional-messages.md#sending-a-profile-transactional-message).

1. Integreer de gebeurtenis in uw website (zie [Het activeren van de gebeurtenis in een website integreren](#integrating-the-triggering-of-the-event-in-a-website)).

### Op gebeurtenissen gebaseerde pushmeldingen voor transacties {#event-based-transactional-push-notifications}

Als u pushmeldingen over transacties wilt verzenden, moet u Adobe Campaign dienovereenkomstig configureren. Zie [Push configuration](https://docs.adobe.com/content/help/nl-NL/campaign-standard/using/administrating/configuring-channels/configuring-a-mobile-application.htmll).

Als u een anonieme pushmelding over een transactie wilt verzenden naar alle gebruikers die zich hebben aangemeld voor het ontvangen van berichten van uw mobiele toepassing, moet u eerst een gebeurtenis maken en configureren die gericht is op de gegevens in de gebeurtenis zelf. De bijbehorende stappen worden hieronder weergegeven.

De gebeurtenis moet de volgende drie elementen bevatten:

* A **registration token**, de gebruikersnaam voor één mobiele toepassing en één apparaat. Deze komt mogelijk niet overeen met enig profiel uit de Adobe Campaign-database.
* A **naam mobiele toepassing** (één voor alle apparaten - Android en iOS). Dit is de id van de mobiele toepassing die in Adobe Campaign is geconfigureerd en die wordt gebruikt voor het ontvangen van pushberichten op de apparaten van de gebruiker. Raadpleeg [deze pagina](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html) voor meer informatie
* A **push-platform** (&quot;gcm&quot; voor Android of &quot;apns&quot; voor iOS).

1. Wanneer u de gebeurtenisconfiguratie maakt, selecteert u het **[!UICONTROL Mobile application]**-kanaal en de **[!UICONTROL Real-time event]**-doeldimensie (zie [Een gebeurtenis maken](#creating-an-event)).
1. Voeg velden aan de gebeurtenis toe om het transactiebericht aan te passen (zie [Gebeurteniskenmerken definiëren](#defining-the-event-attributes)).
1. Verrijk de inhoud van het transactiebericht als u extra informatie van het gegevensbestand van Adobe Campaign wilt gebruiken (zie [Verrijkend de inhoud van het transactionele bericht](#enriching-the-transactional-message-content)).

   >[!NOTE]
   >
   >Het gebeurtenistransactiebericht wordt verondersteld om alleen de data in de verzendgebeurtenis zelf te gebruiken bij het bepalen van de ontvanger en de personalisatie van de berichtcontent. U kunt de content van het transactiebericht echter wel verrijken met data uit de Adobe Campaign-database.

1. Geef een voorvertoning weer van de gebeurtenis en publiceer de gebeurtenis (zie [De gebeurtenis voorvertonen en publiceren](#previewing-and-publishing-the-event)).

   Wanneer u een voorvertoning van de gebeurtenis weergeeft, bevat de REST-API de kenmerken &quot;registrationToken&quot;, &quot;application&quot; en &quot;pushPlatform&quot; die worden gebruikt voor de levering.

   ![](assets/message-center_push_api.png)

   Nadat de gebeurtenis is gepubliceerd, wordt automatisch een transactioneel pushbericht gemaakt dat aan de nieuwe gebeurtenis is gekoppeld. Om het bericht te wijzigen en te publiceren dat enkel werd gecreeerd, zie [Verzendend een transactie dupmelding richtend een gebeurtenis](../../channels/using/transactional-push-notifications.md#transactional-push-notifications-targeting-an-event).

1. Integreer de gebeurtenis in uw website (zie [Het activeren van de gebeurtenis in een website integreren](#integrating-the-triggering-of-the-event-in-a-website)).

### Op profielen gebaseerde pushmeldingen voor transacties {#profile-based-transactional-push-notifications}

Als u een pushmelding over een transactie wilt verzenden naar de Adobe Campaign-profielen die zijn geabonneerd op uw mobiele toepassing, moet u eerst een gebeurtenis maken en configureren die gericht is op de Adobe Campaign-database.

1. Wanneer u de gebeurtenisconfiguratie maakt, selecteert u het **[!UICONTROL Mobile application]**-kanaal en de **[!UICONTROL Profile]**-doeldimensie (zie [Een gebeurtenis maken](#creating-an-event)).

   Standaard wordt de transactionele pushmelding verzonden naar alle mobiele toepassingen waarop de ontvangers zich hebben geabonneerd. Als u de pushmelding naar een specifieke mobiele toepassing wilt verzenden, selecteert u deze in de lijst. De andere mobiele toepassingen zullen door het bericht worden gericht maar van het verzenden worden uitgesloten.

   ![](assets/message-center_push_appfilter.png)

1. Voeg velden toe aan de gebeurtenis als u het transactiebericht wilt aanpassen (zie [Gebeurteniskenmerken definiëren](#defining-the-event-attributes)).

   >[!NOTE]
   >
   >U moet ten minste één veld toevoegen om een verrijking te maken. U hoeft geen andere velden te maken, zoals **Voornaam** en **Achternaam**, omdat u verpersoonlijkingsvelden uit de Adobe Campaign-database kunt gebruiken.

1. Maak een verrijking om de gebeurtenis te koppelen aan de **[!UICONTROL Profile]**-bron (zie [De inhoud van het transactiebericht verrijken](#enriching-the-transactional-message-content)). Het maken van een verrijking is verplicht wanneer u een **[!UICONTROL Profile]**-doeldimensie gebruikt.
1. Geef een voorvertoning weer van de gebeurtenis en publiceer de gebeurtenis (zie [De gebeurtenis voorvertonen en publiceren](#previewing-and-publishing-the-event)).

   Wanneer de voorvertoning van de gebeurtenis wordt weergegeven, bevat de REST API geen kenmerk dat het registratietoken, de toepassingsnaam en het pushplatform opgeeft zoals deze worden opgehaald uit de **[!UICONTROL Profile]**-bron.

   Nadat de gebeurtenis is gepubliceerd, wordt automatisch een transactioneel pushbericht gemaakt dat aan de nieuwe gebeurtenis is gekoppeld. Om het bericht te wijzigen en te publiceren dat enkel werd gecreeerd, zie [Verzendend een transactie dupmelding richtend een profiel](../../channels/using/transactional-push-notifications.md#transactional-push-notifications-targeting-a-profile).

1. Integreer de gebeurtenis in uw website (zie [Het activeren van de gebeurtenis in een website integreren](#integrating-the-triggering-of-the-event-in-a-website)).

### Een gebeurtenis configureren om een vervolgbericht te verzenden {#configuring-an-event-to-send-a-follow-up-message}

Een follow-upbericht is een vooraf bepaalde marketing leveringsmalplaatje dat in een werkschema kan worden gebruikt om berichten naar de ontvangers van een specifiek transactiebericht te verzenden. Zie [Vervolgberichten](../../channels/using/follow-up-messages.md) voor meer informatie.

1. Gebruik dezelfde gebeurtenisconfiguratie die u hebt gemaakt om een transactiebericht voor een gebeurtenis te verzenden. Zie [Transactieberichten op basis van gebeurtenissen](#event-based-transactional-messages).
1. Wanneer het vormen van uw gebeurtenis, controleer **[!UICONTROL Create follow-up delivery template for this event]** vakje alvorens de gebeurtenis te publiceren.

   ![](assets/message-center_follow-up-checkbox.png)

1. Geef een voorvertoning weer van de gebeurtenis en publiceer de gebeurtenis (zie [De gebeurtenis voorvertonen en publiceren](#previewing-and-publishing-the-event)).

   Nadat de gebeurtenis is gepubliceerd, worden automatisch een transactiemelding en een leveringssjabloon voor de follow-up gemaakt die aan de nieuwe gebeurtenis zijn gekoppeld. Zie [Een vervolgbericht verzenden](../../channels/using/follow-up-messages.md#sending-a-follow-up-message) voor meer informatie over het gebruik van follow-upberichten.

## Hoofdlettergebruik: configureren van een gebeurtenis om een transactiebericht te verzenden {#use-case--configuring-an-event-to-send-a-transactional-message}

In dit voorbeeld willen we een gebeurtenis configureren om na elke aankoop op onze website bevestigingsberichten te verzenden met de volgende voorwaarden:

Aangezien wij onze cliënt via zijn identiteitskaart van CRM willen identificeren, zorg eerst ervoor dat **[!UICONTROL Profile]** middel met dit nieuwe gebied is uitgebreid.

Op dezelfde manier, moet een douanemiddel die aan aankopen beantwoordt zijn gecreeerd en gepubliceerd, en moet met **[!UICONTROL Profile]** middel worden verbonden. Op deze manier kunt u informatie ophalen uit deze bron om de inhoud van het bericht te verrijken.

Raadpleeg [deze pagina](../../developing/using/key-steps-to-add-a-resource.md) voor meer informatie over het maken en publiceren van bronnen.

1. Maak een nieuwe gebeurtenis met het kanaal **[!UICONTROL Email]** en de doeldimensie **[!UICONTROL Profile]** (zie [Een gebeurtenis maken](#creating-an-event)).
1. Definieer de kenmerken die beschikbaar zijn om het transactiebericht aan te passen. Voeg in ons geval de velden &quot;CRM-id&quot; en &quot;Product-id&quot; toe (zie [Gebeurteniskenmerken definiëren](#defining-the-event-attributes)).

   ![](assets/message-center_usecase1.png)

1. Om de berichtinhoud met informatie betreffende de vorige aankopen van de cliënt te verrijken, creeer een verrijking richtend de **[!UICONTROL Purchase]** bron (zie [Verrijkend de inhoud van het transactionele bericht](#enriching-the-transactional-message-content)).

   ![](assets/message-center_usecase2.png)

1. Creeer samen voorwaarde tussen het gebied van het &quot;Herkenningsteken van het Product&quot;dat eerder aan het bericht werd toegevoegd, en het overeenkomstige gebied van **[!UICONTROL Purchase]** middel.

   ![](assets/message-center_usecase3.png)

1. Geef een voorvertoning weer van de gebeurtenis en publiceer de gebeurtenis (zie [De gebeurtenis voorvertonen en publiceren](#previewing-and-publishing-the-event)).
1. Integreer de gebeurtenis in uw website (zie [De gebeurtenis activeren in een website](#integrating-the-triggering-of-the-event-in-a-website)).

