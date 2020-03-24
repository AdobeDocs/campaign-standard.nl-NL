---
title: Transactieberichten configureren
description: Leer hoe te om transactioneel overseinen te vormen.
page-status-flag: never-activated
uuid: 4caeadbe-f4a7-43ce-986d-e99fa9ca0d0d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuring-channels
discoiquuid: 3f968556-e774-43dc-a0b8-7188d7665fbc
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e62fdfba531bcfe18c147e7035c79e1ac6bca979

---


# Transactieberichten configureren{#configuring-transactional-messaging}

Als u een transactiebericht wilt verzenden met Adobe Campaign, moet u eerst de structuur van de gebeurtenisgegevens beschrijven.

De configuratie van de gebeurtenis moet door een **beheerder** door de hieronder stappen worden uitgevoerd:

De configuratie kan afhankelijk van het type van transactiebericht variëren u wilt verzenden. Raadpleeg voor meer informatie de specifieke configuraties van [Transactiegebeurtenissen](#transactional-event-specific-configurations)

Zodra de gebeurtenis wordt gepubliceerd, wordt het overeenkomstige transactiemelding automatisch gecreeerd. Raadpleeg [deze pagina](../../channels/using/about-transactional-messaging.md)voor meer informatie over transacties.

## Een gebeurtenis maken {#creating-an-event}

Begin door de gebeurtenis te creëren die aan uw behoeften beantwoordt.

1. Klik in de linkerbovenhoek op het **[!UICONTROL Adobe Campaign]** logo en selecteer **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]**.
1. Klik op de **[!UICONTROL Create]** knop.
1. Geef een **[!UICONTROL Label]** en een **[!UICONTROL ID]** waarde op voor de gebeurtenis. Het **[!UICONTROL ID]** veld is verplicht en moet beginnen met het voorvoegsel &quot;EVT&quot;. Als u dit voorvoegsel niet gebruikt, wordt het automatisch toegevoegd wanneer u klikt **[!UICONTROL Create]**.

   ![](assets/message-center_1.png)

   >[!IMPORTANT]
   >
   >De id mag niet langer zijn dan 64 tekens, inclusief het voorvoegsel EVT.

1. Selecteer het kanaal dat wordt gebruikt om uw transactiemeldingen te verzenden **[!UICONTROL Email]**, **[!UICONTROL Mobile (SMS)]** of **[!UICONTROL Mobile application]** (pushmelding).

   >[!NOTE]
   >
   >Voor elke gebeurtenisconfiguratie kan slechts één kanaal worden gebruikt. Nadat de gebeurtenis is gemaakt, kunt u het kanaal niet meer wijzigen.

1. Selecteer de doeldimensie die overeenkomt met de gewenste gebeurtenisconfiguratie en klik op **[!UICONTROL Create]**.

   Transactieberichten die zijn gebaseerd op gebeurtenissen, zijn gericht op gegevens die zich in de gebeurtenis zelf bevinden, terwijl op profielen gebaseerde transactieberichten gegevens bevatten die zich in de Adobe Campagne-database bevinden. Raadpleeg voor meer informatie de specifieke configuraties [van](#transactional-event-specific-configurations)Transactionele gebeurtenissen.

## Gebeurteniskenmerken definiëren {#defining-the-event-attributes}

In de **[!UICONTROL Fields]** sectie, bepaal de attributen die in de gebeurtenisinhoud zullen worden geïntegreerd en dan zullen kunnen worden gebruikt om het transactionele bericht te personaliseren.

De stappen voor het toevoegen en wijzigen van velden zijn gelijk aan die voor [aangepaste bronnen](../../developing/using/configuring-the-resource-s-data-structure.md#adding-fields-to-a-resource).

![](assets/message-center_2.png)

>[!NOTE]
>
>Als u een meertalig transactiebericht wilt maken, definieert u een extra gebeurteniskenmerk met de **[!UICONTROL AC_language]** id. Dit is alleen van toepassing op transactieberichten voor gebeurtenissen. Nadat de gebeurtenis is gepubliceerd, zijn de stappen voor het bewerken van de inhoud van een meertalig transactiebericht gelijk aan die voor een meertalig standaard-e-mailbericht. Zie [Een meertalige e-mail](../../channels/using/creating-a-multilingual-email.md)maken.

## Gegevensverzamelingen definiëren {#defining-data-collections}

U kunt aan de inhoud van de gebeurtenis een inzameling van elementen toevoegen, elk element zelf met verscheidene attributen.

Deze verzameling kan worden gebruikt in een transactie-e-mail om productaanbiedingen aan de inhoud van het bericht toe te voegen, bijvoorbeeld een lijst met producten - met de prijs, het referentienummer, het aantal, enz. voor elk product in de lijst.

1. Klik in de **[!UICONTROL Collections]** sectie op de **[!UICONTROL Create element]** knop.

   ![](assets/message-center_collection_create.png)

1. Voeg een label en een id voor uw verzameling toe.
1. Voeg alle velden toe die u in het transactiebericht voor elk product in de lijst wilt weergeven.

   In dit voorbeeld hebben we de volgende velden toegevoegd:

   ![](assets/message-center_collection_fields.png)

Zodra de gebeurtenis en het bericht worden gepubliceerd, zult u deze inzameling in uw transactiebericht kunnen gebruiken.

Hier volgt de API-voorvertoning voor dit voorbeeld:

![](assets/message-center_collection_api-preview.png)

**Verwante onderwerpen:**

* [De gebeurtenis voorvertonen en publiceren](#previewing-and-publishing-the-event)
* [Productaanbiedingen in een transactiebericht gebruiken](../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message)

## De inhoud van transactiemeldingen verrijken {#enriching-the-transactional-message-content}

Door de inhoud van transactiemeldingen te verrijken met informatie uit de Adobe Campagne-database, kunt u uw berichten personaliseren. Van achternaam of identiteitskaart van CRM van elk van uw ontvangers, bijvoorbeeld, kunt u gegevens zoals hun adres of geboortedatum of een ander douanegebied terugkrijgen dat in de lijst van het Profiel wordt toegevoegd, om de informatie te personaliseren die naar hen wordt verzonden.

Het is mogelijk om de inhoud van het transactiebericht met informatie van uitgebreide **[!UICONTROL Profile]** of **[!UICONTROL Service]** middelen te verrijken.

Deze informatie kan ook in nieuwe middelen worden opgeslagen. In dat geval moet de bron rechtstreeks of via een andere tabel worden gekoppeld aan de **[!UICONTROL Profile]** of de **[!UICONTROL Service]** bronnen. Bijvoorbeeld, in de configuratie hieronder, is het mogelijk om de transactionele berichtinhoud met informatie van het **[!UICONTROL Product]** middel zoals de productcategorie of identiteitskaart te verrijken, als het middel met het **[!UICONTROL Product]** **[!UICONTROL Profile]** middel verbonden is.

![](assets/message-center_usecaseschema.png)

Raadpleeg [deze pagina](../../developing/using/key-steps-to-add-a-resource.md)voor meer informatie over het maken en publiceren van bronnen.

1. Klik in de **[!UICONTROL Enrichment]** sectie op de **[!UICONTROL Create element]** knop.

   ![](assets/message-center_addenrichment.png)

1. Selecteer de bron waarmee u uw bericht wilt koppelen. Kies in dit geval de **[!UICONTROL Profile]** bron.

   ![](assets/message-center_new-enrichment.png)

1. Gebruik de **[!UICONTROL Create element]** knop om een veld van de geselecteerde bron te koppelen aan een van de velden die u eerder aan de gebeurtenis hebt toegevoegd (zie [De gebeurteniskenmerken](#defining-the-event-attributes)definiëren).

   ![](assets/message-center_enrichment-join.png)

1. In dit voorbeeld combineren we de velden **[!UICONTROL Last name]** en de **[!UICONTROL First name]** velden met de corresponderende velden in de **[!UICONTROL Profile]** bron.

   ![](assets/message-center_enrichment-join-fields.png)

   U kunt de transactionele berichtinhoud ook verrijken gebruikend het **[!UICONTROL Service]** middel. Zie deze [sectie](../../audiences/using/creating-a-service.md)voor meer informatie over services.

1. Als u een op een profiel gebaseerde gebeurtenis maakt of bewerkt, selecteert u in de **[!UICONTROL Targeting enrichment]** sectie de verrijking die tijdens de uitvoering van de levering als berichtdoel wordt gebruikt.

   ![](assets/message-center_marketing_targeting_enrichment.png)

   >[!NOTE]
   >
   >Het selecteren van een het richten verrijking die op de **[!UICONTROL Profile]** middel wordt gebaseerd is verplicht voor op profiel-gebaseerde gebeurtenissen.

Zodra de gebeurtenis en het bericht worden gepubliceerd, zal deze verbinding u toestaan om de inhoud van het transactiebericht te verrijken.

**Verwante onderwerpen:**

* [Een voorvertoning weergeven en de gebeurtenis](#previewing-and-publishing-the-event)publiceren.
* [Een transactiebericht](../../channels/using/event-transactional-messages.md#personalizing-a-transactional-message)aanpassen.

## De gebeurtenis voorvertonen en publiceren {#previewing-and-publishing-the-event}

Voordat u de gebeurtenis kunt gebruiken, moet u deze voorvertonen en publiceren.

1. Klik op de **[!UICONTROL API preview]** knop voor een simulatie van de REST API die door de ontwikkelaar van uw website wordt gebruikt voordat deze wordt gepubliceerd. Nadat de gebeurtenis is gepubliceerd, kunt u met deze knop ook een voorvertoning van de API in productie zien. Zie Het activeren van de gebeurtenis [integreren in een website](#integrating-the-triggering-of-the-event-in-a-website).

   ![](assets/message-center_api_preview.png)

   >[!NOTE]
   >
   >De REST API varieert afhankelijk van het geselecteerde kanaal en de geselecteerde doeldimensie. Voor meer details over de diverse configuraties, verwijs naar [Transactiegebeurtenis specifieke configuraties](#transactional-event-specific-configurations).

1. Klik **[!UICONTROL Publish]** om de publicatie te starten.

   ![](assets/message-center_pub.png)

1. U kunt de publicatielogboeken weergeven op het bijbehorende tabblad.

   ![](assets/message-center_logs.png)


>[!NOTE]
>
>Telkens wanneer u de gebeurtenis wijzigt, moet u **[!UICONTROL Publish]** opnieuw klikken om de bijgewerkte REST API te genereren die door uw websiteontwikkelaar wordt gebruikt.

Nadat de gebeurtenis is gepubliceerd, wordt automatisch een transactiebericht gemaakt dat aan de nieuwe gebeurtenis is gekoppeld. Als u wilt dat deze gebeurtenis het verzenden van een transactiebericht activeert, moet u het bericht wijzigen en publiceren dat zojuist is gemaakt. Zie Transactieberichten voor [gebeurtenissen](../../channels/using/event-transactional-messages.md).

U kunt tot het transactiebericht toegang hebben dat direct van de verbinding in het linkerzijgebied werd gecreeerd.

![](assets/message-center_messagegeneration.png)

U moet deze triggergebeurtenis ook integreren in uw website. Zie Het activeren van de gebeurtenis [integreren in een website](#integrating-the-triggering-of-the-event-in-a-website).

<!-->>[!NOTE]
>Als u de vorige publicaties wilt raadplegen, klikt u op de **[!UICONTROL Latest transactional events]** koppeling onder de **[!UICONTROL History]** sectie in het linkergedeelte.-->

### Publicatie van een gebeurtenis ongedaan maken {#unpublishing-an-event}

Met de **[!UICONTROL Unpublish]** knop kunt u de publicatie van de gebeurtenis annuleren. Hierdoor wordt de bron die overeenkomt met de gebeurtenis die u eerder hebt gemaakt, van de REST-API verwijderd. Zelfs als de gebeurtenis via uw website wordt geactiveerd, worden de bijbehorende berichten niet meer verzonden en niet opgeslagen in de database.

![](assets/message-center_unpublish.png)

>[!NOTE]
Als u het overeenkomstige transactiemelding reeds hebt gepubliceerd, wordt de transactieberichtpublicatie ook geannuleerd. Zie [Publicatie van een transactiebericht](../../channels/using/event-transactional-messages.md#unpublishing-a-transactional-message)ongedaan maken.

Klik op de **[!UICONTROL Publish]** knop om een nieuwe REST API te genereren.

### Een gebeurtenis verwijderen {#deleting-an-event}

Nadat een gebeurtenis niet gepubliceerd is of nog niet gepubliceerd is, kunt u deze verwijderen uit de lijst met gebeurtenisconfiguraties. Dit doet u als volgt:

1. Klik in de linkerbovenhoek op het **[!UICONTROL Adobe Campaign]** logo en selecteer **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]**.
1. Houd de muis boven de gewenste gebeurtenisconfiguratie en selecteer de **[!UICONTROL Delete element]** knop.

   ![](assets/message-center_delete-button.png)

   >[!NOTE]
   Zorg ervoor dat de gebeurtenisconfiguratie de **[!UICONTROL Draft]** status heeft, anders kunt u deze niet verwijderen. De **[!UICONTROL Draft]** status is van toepassing op een gebeurtenis die nog niet is gepubliceerd of die [niet is gepubliceerd](#unpublishing-an-event).

1. Klik op de **[!UICONTROL Confirm]** knop.

   ![](assets/message-center_delete-confirm.png)

>[!IMPORTANT]
Als u een gebeurtenisconfiguratie verwijdert die is gepubliceerd en al wordt gebruikt, worden ook de bijbehorende transactiemeldingen en de bijbehorende verzendings- en trackinglogboeken verwijderd.

## De activering van de gebeurtenis in een website integreren {#integrating-the-triggering-of-the-event-in-a-website}

Nadat u een gebeurtenis hebt gemaakt, moet u de activering van deze gebeurtenis integreren in uw website.

In het voorbeeld dat wordt beschreven in de sectie [Transaction messaging Operating Principle](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle) , wilt u dat een gebeurtenis &quot;Cart-stopzetting&quot; wordt geactiveerd wanneer een van uw klanten uw website verlaat voordat ze de producten in hun winkelwagentje kopen. Hiervoor moet de webontwikkelaar van uw website de Adobe Campagne Standard REST API gebruiken.

Zie de documentatie van de [REST API](../../api/using/managing-transactional-messages.md) .

## Specifieke configuraties voor gebeurtenissen {#transactional-event-specific-configurations}

Transactionele gebeurtenisconfiguratie kan afhankelijk van het type van transactiebericht variëren u (gebeurtenis of profiel) wilt verzenden, en het kanaal dat zal worden gebruikt.

In de volgende secties wordt gedetailleerd welke specifieke configuratie moet worden ingesteld op basis van het gewenste transactiebericht. Zie Een gebeurtenis [maken voor meer informatie over de algemene stappen voor het configureren van een gebeurtenis](#creating-an-event).

### Transactieberichten die zijn gebaseerd op gebeurtenissen {#event-based-transactional-messages}

Als u een op een gebeurtenis gebaseerd transactiebericht wilt verzenden, moet u eerst een gebeurtenis maken en configureren die zich richt op de gegevens in de gebeurtenis zelf.
Voor meer informatie, zie het [Inschakelen met transactioneel overseinen](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Managedatatofuelengagingexperiences).

1. Selecteer bij het maken van de gebeurtenisconfiguratie de **[!UICONTROL Real-time event]** doeldimensie (zie [Een gebeurtenis](#creating-an-event)maken).
1. Voeg velden toe aan de gebeurtenis om het transactiemelding aan te passen (zie Gebeurteniskenmerken [](#defining-the-event-attributes)definiëren).
1. Verrijk de inhoud van het transactiemeldingsbericht als u aanvullende informatie uit de Adobe Campagne-database wilt gebruiken (zie [Verrijken van de inhoud](#enriching-the-transactional-message-content)van het transactiebericht).

   >[!NOTE]
   Het op gebeurtenis-gebaseerde transactieoverseinen wordt verondersteld om slechts de gegevens te gebruiken die in de verzonden gebeurtenis zijn om de ontvanger en de verpersoonlijking van de berichtinhoud te bepalen. U kunt de inhoud van uw transactiemelding echter verrijken met gegevens uit de Adobe Campagne-database.

1. Een voorvertoning van de gebeurtenis weergeven en deze publiceren (zie [De gebeurtenis](#previewing-and-publishing-the-event)voorvertonen en publiceren).

   Wanneer u een voorvertoning van de gebeurtenis weergeeft, bevat de REST API een kenmerk dat het e-mailadres of de mobiele telefoon opgeeft volgens het geselecteerde kanaal.

   Nadat de gebeurtenis is gepubliceerd, wordt automatisch een transactiebericht gemaakt dat aan de nieuwe gebeurtenis is gekoppeld. Als de gebeurtenis het verzenden van een transactiemelding moet activeren, moet u het bericht wijzigen en publiceren dat net werd gecreeerd, zie de transactieberichten [van de](../../channels/using/event-transactional-messages.md)Gebeurtenis.

1. Integreer de gebeurtenis in uw website (zie het activeren van de gebeurtenis in een website [](#integrating-the-triggering-of-the-event-in-a-website)integreren).

### Transactieberichten op basis van profielen {#profile-based-transactional-messages}

Als u een op een profiel gebaseerd transactiebericht wilt verzenden, moet u eerst een gebeurtenis maken en configureren die gegevens als doel heeft die zich in de Adobe Campagne-database bevinden.

1. Selecteer bij het maken van de gebeurtenisconfiguratie de **[!UICONTROL Profile event]** doeldimensie (zie [Een gebeurtenis](#creating-an-event)maken).
1. Voeg velden toe aan de gebeurtenis om het transactiemelding aan te passen (zie Gebeurteniskenmerken [](#defining-the-event-attributes)definiëren). U moet ten minste één veld toevoegen om een verrijking te maken. U hoeft geen andere velden te maken, zoals de **voornaam** en de **achternaam** , omdat u verpersoonlijkingsvelden uit de Adobe Campagne-database kunt gebruiken.
1. Maak een verrijking om de gebeurtenis aan de **[!UICONTROL Profile]** bron te koppelen (zie De inhoud [van het transactiebericht](#enriching-the-transactional-message-content)verrijken). Het is verplicht een verrijking te maken wanneer u een **[!UICONTROL Profile]** doeldimensie gebruikt.
1. Een voorvertoning van de gebeurtenis weergeven en deze publiceren (zie [De gebeurtenis](#previewing-and-publishing-the-event)voorvertonen en publiceren).

   Als u een voorvertoning van de gebeurtenis weergeeft, bevat de REST API geen kenmerk dat het e-mailadres of de mobiele telefoon opgeeft zoals deze uit de **[!UICONTROL Profile]** bron wordt opgehaald.

   Nadat de gebeurtenis is gepubliceerd, wordt automatisch een transactiebericht gemaakt dat aan de nieuwe gebeurtenis is gekoppeld. Als de gebeurtenis het verzenden van een transactiemelding moet activeren, moet u het bericht wijzigen en publiceren dat net werd gecreeerd, zie het [Verzenden van een bericht](../../channels/using/profile-transactional-messages.md#sending-a-profile-transactional-message)van de profieltransactie.

1. Integreer de gebeurtenis in uw website (zie het activeren van de gebeurtenis in een website [](#integrating-the-triggering-of-the-event-in-a-website)integreren).

### Op gebeurtenissen gebaseerde pushmeldingen voor transacties {#event-based-transactional-push-notifications}

Als u pushmeldingen over transacties wilt verzenden, moet u Adobe Campaign op basis daarvan configureren. Zie [Push-configuratie](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html).

Als u een anonieme pushmelding over een transactie wilt verzenden naar alle gebruikers die zich hebben aangemeld voor het ontvangen van berichten van uw mobiele toepassing, moet u eerst een gebeurtenis maken en configureren die gericht is op de gegevens in de gebeurtenis zelf. De bijbehorende stappen worden hieronder weergegeven.

De gebeurtenis moet de volgende drie elementen bevatten:

* Een **registratietoken**, de gebruikers-id voor één mobiele toepassing en één apparaat. Het komt mogelijk niet overeen met een profiel uit de Adobe Campagne-database.
* Een **mobiele toepassingsnaam** (één voor alle apparaten - Android en iOS). Dit is de id van de mobiele toepassing die in Adobe Campagne is geconfigureerd en die wordt gebruikt voor het ontvangen van pushberichten op de apparaten van de gebruikers. Raadpleeg deze [pagina voor meer informatie](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html)
* Een **pushplatform** (&quot;gcm&quot; voor Android of &quot;apns&quot; voor iOS).

1. Wanneer u de gebeurtenisconfiguratie maakt, selecteert u het **[!UICONTROL Mobile application]** kanaal en de **[!UICONTROL Real-time event]** doeldimensie (zie [Een gebeurtenis](#creating-an-event)maken).
1. Voeg velden toe aan de gebeurtenis om het transactiemelding aan te passen (zie Gebeurteniskenmerken [](#defining-the-event-attributes)definiëren).
1. Verrijk de inhoud van het transactiemeldingsbericht als u aanvullende informatie uit de Adobe Campagne-database wilt gebruiken (zie [Verrijken van de inhoud](#enriching-the-transactional-message-content)van het transactiemelding).

   >[!NOTE]
   Het op gebeurtenis-gebaseerde transactieoverseinen wordt verondersteld om slechts de gegevens te gebruiken die in de verzonden gebeurtenis zijn om de ontvanger en de verpersoonlijking van de berichtinhoud te bepalen. U kunt de inhoud van uw transactiemelding echter verrijken met gegevens uit de Adobe Campagne-database.

1. Een voorvertoning van de gebeurtenis weergeven en deze publiceren (zie [De gebeurtenis](#previewing-and-publishing-the-event)voorvertonen en publiceren).

   Wanneer u een voorvertoning van de gebeurtenis weergeeft, bevat de REST-API de kenmerken &quot;registrationToken&quot;, &quot;application&quot; en &quot;pushPlatform&quot; die worden gebruikt voor de levering.

   ![](assets/message-center_push_api.png)

   Nadat de gebeurtenis is gepubliceerd, wordt automatisch een transactioneel pushbericht gemaakt dat aan de nieuwe gebeurtenis is gekoppeld. Als u het bericht wilt wijzigen en publiceren dat zojuist is gemaakt, raadpleegt u [Transactie push-berichten voor een gebeurtenis](../../channels/using/transactional-push-notifications.md#transactional-push-notifications-targeting-an-event)verzenden.

1. Integreer de gebeurtenis in uw website (zie het activeren van de gebeurtenis in een website [](#integrating-the-triggering-of-the-event-in-a-website)integreren).

### Op profielen gebaseerde pushmeldingen voor transacties {#profile-based-transactional-push-notifications}

Als u een pushmelding over transacties wilt verzenden naar de Adobe Campagne-profielen die zijn geabonneerd op uw mobiele toepassing, moet u eerst een gebeurtenis maken en configureren die gericht is op de Adobe Campagne-database.

1. Wanneer u de gebeurtenisconfiguratie maakt, selecteert u het **[!UICONTROL Mobile application]** kanaal en de **[!UICONTROL Profile]** doeldimensie (zie [Een gebeurtenis](#creating-an-event)maken).

   Standaard wordt de transactionele pushmelding verzonden naar alle mobiele toepassingen waarop de ontvangers zich hebben geabonneerd. Als u de pushmelding naar een specifieke mobiele toepassing wilt verzenden, selecteert u deze in de lijst. De andere mobiele toepassingen zullen door het bericht worden gericht maar van het verzenden worden uitgesloten.

   ![](assets/message-center_push_appfilter.png)

1. Voeg velden toe aan de gebeurtenis als u het transactiemelding wilt aanpassen (zie Gebeurteniskenmerken [](#defining-the-event-attributes)definiëren).

   >[!NOTE]
   U moet ten minste één veld toevoegen om een verrijking te maken. U hoeft geen andere velden te maken, zoals de **voornaam** en de **achternaam** , omdat u verpersoonlijkingsvelden uit de Adobe Campagne-database kunt gebruiken.

1. Maak een verrijking om de gebeurtenis aan de **[!UICONTROL Profile]** bron te koppelen (zie De inhoud [van het transactiebericht](#enriching-the-transactional-message-content)verrijken). Het is verplicht een verrijking te maken wanneer u een **[!UICONTROL Profile]** doeldimensie gebruikt.
1. Een voorvertoning van de gebeurtenis weergeven en deze publiceren (zie [De gebeurtenis](#previewing-and-publishing-the-event)voorvertonen en publiceren).

   Wanneer de voorvertoning van de gebeurtenis wordt weergegeven, bevat de REST API geen kenmerk dat het registratietoken, de toepassingsnaam en het pushplatform opgeeft zoals deze uit de **[!UICONTROL Profile]** bron worden opgehaald.

   Nadat de gebeurtenis is gepubliceerd, wordt automatisch een transactioneel pushbericht gemaakt dat aan de nieuwe gebeurtenis is gekoppeld. Als u het bericht wilt wijzigen dat zojuist is gemaakt, raadpleegt u [Transactie push-berichten voor een profiel](../../channels/using/transactional-push-notifications.md#transactional-push-notifications-targeting-a-profile)verzenden.

1. Integreer de gebeurtenis in uw website (zie het activeren van de gebeurtenis in een website [](#integrating-the-triggering-of-the-event-in-a-website)integreren).

### Een gebeurtenis configureren om een vervolgbericht te verzenden {#configuring-an-event-to-send-a-follow-up-message}

Een follow-upbericht is een vooraf bepaalde marketing leveringsmalplaatje dat in een werkschema kan worden gebruikt om berichten naar de ontvangers van een specifiek transactiebericht te verzenden. Zie [Vervolgberichten](../../channels/using/follow-up-messages.md)voor meer informatie hierover.

1. Gebruik dezelfde gebeurtenisconfiguratie die u hebt gemaakt om een transactiebericht voor een gebeurtenis te verzenden. Zie Transactieberichten [op basis van](#event-based-transactional-messages)gebeurtenissen.
1. Schakel het **[!UICONTROL Create follow-up delivery template for this event]** vakje in wanneer u de gebeurtenis configureert voordat u de gebeurtenis publiceert.

   ![](assets/message-center_follow-up-checkbox.png)

1. Een voorvertoning van de gebeurtenis weergeven en deze publiceren (zie [De gebeurtenis](#previewing-and-publishing-the-event)voorvertonen en publiceren).

   Nadat de gebeurtenis is gepubliceerd, worden automatisch een transactiemelding en een leveringssjabloon voor de follow-up gemaakt die aan de nieuwe gebeurtenis zijn gekoppeld. Zie Een vervolgbericht [verzenden voor meer informatie over het gebruik van vervolgberichten](../../channels/using/follow-up-messages.md#sending-a-follow-up-message).

## Hoofdlettergebruik: een gebeurtenis configureren om een transactiemelding te verzenden {#use-case--configuring-an-event-to-send-a-transactional-message}

In dit voorbeeld willen we een gebeurtenis configureren om na elke aankoop op onze website bevestigingsberichten te verzenden met de volgende voorwaarden:

Aangezien wij onze cliënt via zijn identiteitskaart van CRM willen identificeren, zorg eerst ervoor dat het **[!UICONTROL Profile]** middel met dit nieuwe gebied is uitgebreid.

Op dezelfde manier, moet een douanemiddel die met aankopen beantwoordt zijn gecreeerd en gepubliceerd, en moet met het **[!UICONTROL Profile]** middel verbonden zijn. Op deze manier kunt u informatie ophalen uit deze bron om de inhoud van het bericht te verrijken.

Raadpleeg [deze pagina](../../developing/using/key-steps-to-add-a-resource.md)voor meer informatie over het maken en publiceren van bronnen.

1. Maak een nieuwe gebeurtenis met gebruik van het **[!UICONTROL Email]** kanaal en de **[!UICONTROL Profile]** doeldimensie (zie [Een gebeurtenis](#creating-an-event)maken).
1. Definieer de kenmerken die beschikbaar zijn om het transactiebericht aan te passen. Voeg in ons geval de velden &quot;CRM-id&quot; en &quot;Product-id&quot; toe (zie [Gebeurteniskenmerken](#defining-the-event-attributes)definiëren).

   ![](assets/message-center_usecase1.png)

1. Om de berichtinhoud met informatie betreffende de vorige aankopen van de cliënt te verrijken, creeer een verrijking gericht op het **[!UICONTROL Purchase]** middel (zie het [Verrijken van de transactionele berichtinhoud](#enriching-the-transactional-message-content)).

   ![](assets/message-center_usecase2.png)

1. Maak een verbindingsvoorwaarde tussen het veld &quot;Product-id&quot; dat eerder aan het bericht is toegevoegd en het bijbehorende veld van de **[!UICONTROL Purchase]** bron

   ![](assets/message-center_usecase3.png)

1. Een voorvertoning van de gebeurtenis weergeven en deze publiceren (zie [De gebeurtenis](#previewing-and-publishing-the-event)voorvertonen en publiceren).
1. Integreer de gebeurtenis in uw website (zie [Het activeren van de gebeurtenis in een website](#integrating-the-triggering-of-the-event-in-a-website)integreren).

