---
solution: Campaign Standard
product: campaign
title: Transactionele pushmeldingen
description: Meer informatie over het verzenden van pushberichten voor transacties met Adobe Campaign Standard.
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
translation-type: tm+mt
source-git-commit: f19d4b5c1837f3f03789958abb1539d4edea0744
workflow-type: tm+mt
source-wordcount: '1336'
ht-degree: 4%

---


# Transactionele pushmeldingen{#transactional-push-notifications}

Met Adobe Campaign kunt u pushmeldingen over transacties verzenden op mobiele apparaten met iOS en Android. Deze berichten worden ontvangen op mobiele toepassingen die u in Adobe Campaign instelt door gebruik te maken van de Experience Cloud Mobile SDK.

>[!NOTE]
>
>Het drukkanaal is optioneel. Controleer hiervoor uw licentieovereenkomst. Zie [Pushmeldingen](../../channels/using/about-push-notifications.md) voor meer informatie over standaardpushmeldingen.

Als u pushmeldingen over transacties wilt verzenden, moet u Adobe Campaign dienovereenkomstig configureren. Zie [Een mobiele toepassing configureren](../../administration/using/configuring-a-mobile-application.md).

U kunt twee typen pushmeldingen voor transacties verzenden:

* [Transactionele pushmeldingen voor een gebeurtenis](#transactional-push-notifications-targeting-an-event)
* [Transactionele pushmeldingen die gericht zijn op ](#transactional-push-notifications-targeting-a-profile) profielen uit de Adobe Campaign-database

## Transactiepushmeldingen voor een gebeurtenis {#transactional-push-notifications-targeting-an-event}

Met Adobe Campaign kunt u **anonieme pushberichten over transacties verzenden naar alle gebruikers** die zich hebben aangemeld om berichten van uw mobiele toepassing te ontvangen.

In dit geval worden alleen **de gegevens in de gebeurtenis zelf gebruikt om het leveringsdoel te definiëren**. Er worden geen gegevens van de Adobe Campaign Integrated Profile Database gebruikt.

### Een op een gebeurtenis gebaseerde pushmelding voor transacties configureren {#configuring-event-based-transactional-push-notification}

Als u een pushmelding over een transactie wilt verzenden aan alle gebruikers die zich hebben aangemeld voor het ontvangen van meldingen van uw mobiele toepassing, moet u eerst een gebeurtenis maken en configureren die gericht is op de gegevens in de gebeurtenis zelf.

>[!NOTE]
>
>U kunt de inhoud van een op een gebeurtenis gebaseerd transactioneel pushbericht nog aanpassen met de gebeurteniskenmerken [a1/> (gegevens van de gebeurtenis) en [event enrichment](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content) (gegevens van de Campagne-database). ](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes) Zie [het onderstaande voorbeeld](#sending-event-based-transactional-push-notification).

De gebeurtenis moet de volgende drie elementen bevatten:

* A **registration token**, de gebruikersnaam voor één mobiele toepassing en één apparaat. Deze komt mogelijk niet overeen met enig profiel uit de Adobe Campaign-database.
* A **naam mobiele toepassing** (één voor alle apparaten - Android en iOS). Dit is de id van de mobiele toepassing die in Adobe Campaign is geconfigureerd en die wordt gebruikt voor het ontvangen van pushberichten op de apparaten van de gebruiker. Raadpleeg [Een mobiele toepassing configureren](../../administration/using/configuring-a-mobile-application.md) voor meer informatie.
* A **push-platform** (&quot;gcm&quot; voor Android of &quot;apns&quot; voor iOS).

Volg onderstaande stappen om de gebeurtenis te configureren:

1. Wanneer u de gebeurtenisconfiguratie maakt, selecteert u het **[!UICONTROL Push notification]**-kanaal en de **[!UICONTROL Real-time event]**-doeldimensie (zie [Een gebeurtenis maken](../../channels/using/configuring-transactional-event.md#creating-an-event)).
1. Voeg velden toe aan de gebeurtenis. Dit zal u toestaan om het transactionele bericht aan te passen (zie [Bepalend de gebeurtenisattributen](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes)). In dit voorbeeld definieert u de velden &#39;gateNumber&#39;, &#39;lastname&#39; en &#39;firstname&#39;.
1. U kunt de inhoud van uw bericht ook verrijken. Hiervoor voegt u velden uit de tabel toe die u aan uw gebeurtenisconfiguratie hebt gekoppeld (zie [De gebeurtenis verrijken](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content)).

   <!--Event-based transactional messaging is supposed to use only the data that are in the sent event to define the recipient and the message content personalization. However, you can enrich the content of your transactional message using information from the Adobe Campaign database.-->

1. [Bekijk een voorvertoning van de gebeurtenis](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event) en publiceer deze.

   Wanneer u een voorvertoning van de gebeurtenis weergeeft, bevat de REST-API de kenmerken &quot;registrationToken&quot;, &quot;application&quot; en &quot;pushPlatform&quot; die worden gebruikt voor de levering.

   ![](assets/message-center_push_api.png)

   Nadat de gebeurtenis is gepubliceerd, wordt automatisch een transactioneel pushbericht gemaakt dat aan de nieuwe gebeurtenis is gekoppeld. U kunt nu het bericht wijzigen en publiceren dat net werd gecreeerd (zie [deze sectie](#sending-event-based-transactional-push-notification)).

1. Integreer de gebeurtenis in uw website (zie [De gebeurtenis activeren](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger)).

### Een op een gebeurtenis gebaseerde pushmelding voor transacties verzenden {#sending-event-based-transactional-push-notification}

Een luchtvaartmaatschappij wil bijvoorbeeld haar gebruikers van mobiele toepassingen uitnodigen om naar de relevante poort voor instapweigering te gaan.

Het bedrijf verzendt één transactioneel pushbericht per gebruiker (geïdentificeerd met een registratietoken), gebruikend één mobiele toepassing, door één enkel apparaat.

1. Ga naar het transactionele bericht dat is gemaakt om het te bewerken. Zie [Transactieberichten benaderen](../../channels/using/editing-transactional-message.md#accessing-transactional-messages).

   ![](assets/message-center_push_message.png)

1. Klik op het blok **[!UICONTROL Content]** om de titel en de tekst van uw bericht te wijzigen.

1. U kunt verpersoonlijkingsgebieden opnemen om elementen toe te voegen die u bepaalde toen u uw gebeurtenis creeerde (zie [Bepalend de gebeurtenisattributen](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes)).

   ![](assets/message-center_push_content.png)

   Als u deze velden wilt zoeken, klikt u op het potlood naast een item, klikt u op **[!UICONTROL Insert personalization field]** en selecteert u **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**.

   ![](assets/message-center_push_personalization.png)

   Zie [Een pushmelding voorbereiden en verzenden](../../channels/using/preparing-and-sending-a-push-notification.md) voor meer informatie over het bewerken van de inhoud van een pushmelding.

1. U kunt ook de inhoud van het transactiemelding verrijken als u extra informatie van het gegevensbestand van Adobe Campaign wilt gebruiken (zie [Verrijkend de gebeurtenis](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content)).

1. Sla uw wijzigingen op en publiceer het bericht. Zie [Een transactioneel bericht publiceren](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message).

1. Verstuur met de Adobe Campaign Standard REST API een gebeurtenis naar een registratietoken (ABCDEF123456789), met één mobiele toepassing (WeFlight), op Android (gcm), die de instapgegevens bevat:

   ```
   {
     "registrationToken":"ABCDEF123456789",
     "application":"WeFlight",
     "pushPlatform":"gcm",
     "ctx":
     {
       "gateNumber":"Gate B18",
       "lastname":"Green",
       "firstname":"Jane"
     }
   }
   ```

   Zie [De gebeurtenis activeren](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger) integreren voor meer informatie over het integreren van de activering van een gebeurtenis in een extern systeem.

Als het registratietoken bestaat, ontvangt de overeenkomstige gebruiker een transactioneel pushbericht met de volgende inhoud:

*&quot;Hallo Jane Green, het instappen is net begonnen! Ga verder met Gate B18.&quot;*

## Transactiepushmeldingen voor een profiel {#transactional-push-notifications-targeting-a-profile}

U kunt een transactioneel pushbericht **verzenden naar de Adobe Campaign-profielen die zijn geabonneerd op uw mobiele toepassing**. Deze levering kan [verpersoonlijkingsgebieden](../../designing/using/personalization.md#inserting-a-personalization-field), zoals de voornaam van de ontvanger, direct bevatten die van het gegevensbestand van Adobe Campaign wordt teruggewonnen.

In dit geval moet de gebeurtenis enkele velden **bevatten waarmee kan worden vergeleken met een profiel uit de Adobe Campaign-database**.

Bij het opgeven van profielen wordt per mobiele toepassing en per apparaat één transactioneel pushbericht verzonden. Als een Adobe Campaign-gebruiker bijvoorbeeld op twee toepassingen heeft geabonneerd, ontvangt deze gebruiker twee meldingen. Als een gebruiker zich op dezelfde toepassing heeft geabonneerd met twee verschillende apparaten, ontvangt deze gebruiker een melding op elk apparaat.

De mobiele toepassingen waarop een profiel is geabonneerd, worden weergegeven op het tabblad **[!UICONTROL Mobile App Subscriptions]** van dit profiel. U opent dit tabblad door een profiel te selecteren en op de knop **[!UICONTROL Edit profile properties]** aan de rechterkant te klikken.

![](assets/push_notif_subscriptions.png)

Zie [Informatie over profielen](../../audiences/using/about-profiles.md) voor meer informatie over het openen en bewerken van profielen.

### Een op een profiel gebaseerde pushmelding voor transacties configureren {#configuring-profile-based-transactional-push-notification}

Als u een pushmelding over een transactie wilt verzenden naar de Adobe Campaign-profielen die zijn geabonneerd op uw mobiele toepassing, moet u eerst een gebeurtenis maken en configureren die gericht is op de Adobe Campaign-database.

1. Wanneer u de gebeurtenisconfiguratie maakt, selecteert u het **[!UICONTROL Push notification]**-kanaal en de **[!UICONTROL Profile]**-doeldimensie (zie [Een gebeurtenis maken](../../channels/using/configuring-transactional-event.md#creating-an-event)).

   Standaard wordt de transactionele pushmelding verzonden naar alle mobiele toepassingen waarop de ontvangers zich hebben geabonneerd. Als u de pushmelding naar een specifieke mobiele toepassing wilt verzenden, selecteert u deze in de lijst. De andere mobiele toepassingen zullen door het bericht worden gericht maar van het verzenden worden uitgesloten.

   ![](assets/message-center_push_appfilter.png)

1. Voeg velden toe aan de gebeurtenis als u het transactiebericht wilt aanpassen (zie [Gebeurteniskenmerken definiëren](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes)).

   >[!NOTE]
   >
   >U moet ten minste één veld toevoegen om een verrijking te maken. U hoeft geen andere velden te maken, zoals **Voornaam** en **Achternaam**, omdat u verpersoonlijkingsvelden uit de Adobe Campaign-database kunt gebruiken.

1. Maak een verrijking om de gebeurtenis te koppelen aan de **[!UICONTROL Profile]**-bron (zie [De gebeurtenis verrijken](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content)) en selecteer deze verrijking als **[!UICONTROL Targeting enrichment]**.

   >[!IMPORTANT]
   >
   >Deze stap is verplicht voor op profielen gebaseerde gebeurtenissen.

1. [Bekijk een voorvertoning van de gebeurtenis](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event) en publiceer deze.

   Wanneer de voorvertoning van de gebeurtenis wordt weergegeven, bevat de REST API geen kenmerk dat het registratietoken, de toepassingsnaam en het pushplatform opgeeft zoals deze worden opgehaald uit de **[!UICONTROL Profile]**-bron.

   Nadat de gebeurtenis is gepubliceerd, wordt automatisch een transactioneel pushbericht gemaakt dat aan de nieuwe gebeurtenis is gekoppeld. U kunt nu het bericht wijzigen en publiceren dat net werd gecreeerd (zie [deze sectie](#sending-profile-based-transactional-push-notification)).

1. Integreer de gebeurtenis in uw website (zie [De gebeurtenis activeren](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger)).

### Een op een profiel gebaseerde pushmelding voor transacties verzenden {#sending-profile-based-transactional-push-notification}

Een luchtvaartmaatschappij wil bijvoorbeeld een laatste instapoproep sturen naar alle Adobe Campaign-gebruikers die zich op de mobiele toepassing hebben geabonneerd.

1. Ga naar het transactionele bericht dat is gemaakt om het te bewerken. Zie [Transactieberichten benaderen](../../channels/using/editing-transactional-message.md#accessing-transactional-messages).

1. Klik op het blok **[!UICONTROL Content]** om de titel en de tekst van uw bericht te wijzigen.

   In tegenstelling tot configuraties die op gebeurtenissen in real time worden gebaseerd, hebt u directe toegang tot alle profielinformatie om uw bericht te personaliseren. Zie [Een personalisatieveld invoegen](../../designing/using/personalization.md#inserting-a-personalization-field).

   Zie [Een pushmelding voorbereiden en verzenden](../../channels/using/preparing-and-sending-a-push-notification.md) voor meer informatie over het bewerken van de inhoud van een pushmelding.

1. Sla uw wijzigingen op en publiceer het bericht. Zie [Een transactioneel bericht publiceren](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message).
1. Stuur een gebeurtenis met de Adobe Campaign Standard REST-API naar een profiel:

   ```
   {
     "ctx":
     {
       "email":"janegreen@email.com",
       "gateNumber":"D16",
     }
   }
   ```

Zie [De gebeurtenis activeren](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger) integreren voor meer informatie over het integreren van de activering van een gebeurtenis in een extern systeem.

De overeenkomstige gebruiker ontvangt een transactioneel pushbericht met daarin alle personalisatie-elementen die uit de Adobe Campaign-database zijn opgehaald.

>[!NOTE]
>
>Er zijn geen registratietoken, toepassings- en pushplatformvelden. In dit voorbeeld wordt de afstemming uitgevoerd met het e-mailveld.
