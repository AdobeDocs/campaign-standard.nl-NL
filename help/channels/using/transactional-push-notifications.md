---
title: Transactionele pushmeldingen
description: Meer informatie over het verzenden van pushberichten voor transacties met Adobe Campaign Standard.
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: Transactional Messaging
role: User
level: Intermediate
exl-id: 61988c1d-d538-47b1-94c1-f3fbdf314b65
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '1451'
ht-degree: 4%

---

# Transactionele pushmeldingen{#transactional-push-notifications}

U kunt Adobe Campaign gebruiken om pushmeldingen over transacties te verzenden op mobiele iOS- en Android-apparaten. Deze berichten worden ontvangen op mobiele toepassingen die u in Adobe Campaign instelt door gebruik te maken van de Experience Cloud Mobile SDK.

>[!NOTE]
>
>Het drukkanaal is optioneel. Controleer hiervoor uw licentieovereenkomst. Voor meer informatie over standaardpushmeldingen raadpleegt u [Pushmeldingen](../../channels/using/about-push-notifications.md).

Als u pushmeldingen over transacties wilt verzenden, moet u Adobe Campaign dienovereenkomstig configureren. Zie [Een mobiele toepassing configureren](../../administration/using/configuring-a-mobile-application.md).

U kunt twee typen pushmeldingen voor transacties verzenden:

* [Transactionele pushmeldingen voor een gebeurtenis](#transactional-push-notifications-targeting-an-event)
* [Transactionele pushmeldingen voor profielen](#transactional-push-notifications-targeting-a-profile) uit de Adobe Campaign-database

## Transactionele pushmeldingen voor een gebeurtenis {#transactional-push-notifications-targeting-an-event}

Je kunt Adobe Campaign gebruiken om te verzenden **anonieme pushberichten voor transacties aan alle gebruikers** die ervoor hebben gekozen om meldingen van uw mobiele toepassing te ontvangen.

Alleen in dit geval **de gegevens in de gebeurtenis zelf worden gebruikt om het leveringsdoel te bepalen**. Er worden geen gegevens van de Adobe Campaign Integrated Profile Database gebruikt.

### Een op een gebeurtenis gebaseerde pushmelding voor transacties configureren {#configuring-event-based-transactional-push-notification}

Als u een pushmelding over een transactie wilt verzenden aan alle gebruikers die zich hebben aangemeld voor het ontvangen van meldingen van uw mobiele toepassing, moet u eerst een gebeurtenis maken en configureren die gericht is op de gegevens in de gebeurtenis zelf.

>[!NOTE]
>
>U kunt de inhoud van een op een gebeurtenis gebaseerd transactioneel pushbericht nog steeds aanpassen met [gebeurteniskenmerken](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes) (gegevens van de gebeurtenis) en [gebeurtenisverrijking](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content) (gegevens uit de Campagne-database). Zie [het onderstaande voorbeeld](#sending-event-based-transactional-push-notification).

De gebeurtenis moet de volgende drie elementen bevatten:

* A **registratietoken**, de gebruikersnaam voor één mobiele toepassing en één apparaat. Deze komt mogelijk niet overeen met enig profiel uit de Adobe Campaign-database.
* A **naam mobiele toepassing** (één voor alle apparaten - Android en iOS). Dit is de id van de mobiele toepassing die in Adobe Campaign is geconfigureerd en die wordt gebruikt voor het ontvangen van pushberichten op de apparaten van de gebruiker. Raadpleeg voor meer informatie hierover [Een mobiele toepassing configureren](../../administration/using/configuring-a-mobile-application.md).
* A **push-platform** (&quot;gcm&quot; voor Android of &quot;apns&quot; voor iOS).

Volg onderstaande stappen om de gebeurtenis te configureren:

1. Selecteer bij het maken van de gebeurtenisconfiguratie de optie **[!UICONTROL Push notification]** en de **[!UICONTROL Real-time event]** doelgerichtheid (zie [Een gebeurtenis maken](../../channels/using/configuring-transactional-event.md#creating-an-event)).
1. Voeg velden toe aan de gebeurtenis. Hierdoor kunt u het transactiemelding aanpassen (zie [Gebeurteniskenmerken definiëren](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes)). In dit voorbeeld definieert u de velden &#39;gateNumber&#39;, &#39;lastname&#39; en &#39;firstname&#39;.
1. U kunt de inhoud van uw bericht ook verrijken. Hiervoor voegt u velden toe uit de tabel die u aan uw gebeurtenisconfiguratie hebt gekoppeld (zie [De gebeurtenis verrijken](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content)).

   <!--Event-based transactional messaging is supposed to use only the data that are in the sent event to define the recipient and the message content personalization. However, you can enrich the content of your transactional message using information from the Adobe Campaign database.-->

1. [De gebeurtenis voorvertonen en publiceren](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event).

   Wanneer u een voorvertoning van de gebeurtenis weergeeft, bevat de REST-API de kenmerken &quot;registrationToken&quot;, &quot;application&quot; en &quot;pushPlatform&quot; die worden gebruikt voor de levering.

   ![](assets/message-center_push_api.png)

   Nadat de gebeurtenis is gepubliceerd, wordt automatisch een transactioneel pushbericht gemaakt dat aan de nieuwe gebeurtenis is gekoppeld. U kunt het zojuist gemaakte bericht nu wijzigen en publiceren (zie [deze sectie](#sending-event-based-transactional-push-notification)).

1. De gebeurtenis in uw website integreren (zie [De gebeurtenis die leidt tot integratie](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger)).

### Een op een gebeurtenis gebaseerde pushmelding voor transacties verzenden {#sending-event-based-transactional-push-notification}

Een luchtvaartmaatschappij wil bijvoorbeeld haar gebruikers van mobiele toepassingen uitnodigen om naar de relevante poort voor instapweigering te gaan.

Het bedrijf verzendt één transactioneel pushbericht per gebruiker (geïdentificeerd met een registratietoken), gebruikend één mobiele toepassing, door één enkel apparaat.

1. Ga naar het transactionele bericht dat is gemaakt om het te bewerken. Zie [Toegang tot transactieberichten](../../channels/using/editing-transactional-message.md#accessing-transactional-messages).

   ![](assets/message-center_push_message.png)

1. Klik op de knop **[!UICONTROL Content]** blokkeren om de titel en de tekst van uw bericht te wijzigen.

1. U kunt verpersoonlijkingsgebieden opnemen om elementen toe te voegen die u bepaalde toen u uw gebeurtenis creeerde (zie [Gebeurteniskenmerken definiëren](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes)).

   ![](assets/message-center_push_content.png)

   Als u deze velden wilt zoeken, klikt u op het potlood naast een item en klikt u op **[!UICONTROL Insert personalization field]** en selecteert u **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**.

   ![](assets/message-center_push_personalization.png)

   Ga voor meer informatie over het bewerken van inhoud van pushberichten naar [Een pushmelding voorbereiden en verzenden](../../channels/using/preparing-and-sending-a-push-notification.md).

1. U kunt de inhoud van het transactiemeldingsbericht ook verrijken als u aanvullende informatie uit de Adobe Campaign-database wilt gebruiken (zie [De gebeurtenis verrijken](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content)).

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

   Voor meer informatie over het integreren van het activeren van een gebeurtenis in een extern systeem raadpleegt u [De gebeurtenis die leidt tot integratie](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger).

Als het registratietoken bestaat, ontvangt de overeenkomstige gebruiker een transactioneel pushbericht met de volgende inhoud:

*&quot;Hallo Jane Green, het instappen is net begonnen! Ga verder met Gate B18.&quot;*

## Transactionele pushmeldingen die gericht zijn op een profiel {#transactional-push-notifications-targeting-a-profile}

U kunt een pushmelding voor een transactie verzenden **op de Adobe Campaign-profielen die zijn geabonneerd op uw mobiele toepassing**. Deze levering kan [personalisatievelden](../../designing/using/personalization.md#inserting-a-personalization-field), zoals de voornaam van de ontvanger, rechtstreeks opgehaald uit de Adobe Campaign-database.

In dit geval moet de gebeurtenis enkele velden bevatten **die afstemming met een profiel uit de Adobe Campaign-database mogelijk maakt**.

Bij het opgeven van profielen wordt per mobiele toepassing en per apparaat één transactioneel pushbericht verzonden. Als een Adobe Campaign-gebruiker bijvoorbeeld op twee toepassingen heeft geabonneerd, ontvangt deze gebruiker twee meldingen. Als een gebruiker zich op dezelfde toepassing heeft geabonneerd met twee verschillende apparaten, ontvangt deze gebruiker een melding op elk apparaat.

De mobiele toepassingen waarop een profiel is geabonneerd, worden weergegeven in het dialoogvenster **[!UICONTROL Mobile App Subscriptions]** tabblad van dit profiel. Als u dit tabblad wilt openen, selecteert u een profiel en klikt u op de knop **[!UICONTROL Edit profile properties]** rechts.

![](assets/push_notif_subscriptions.png)

Ga voor meer informatie over het openen en bewerken van profielen naar [Profielen](../../audiences/using/about-profiles.md).

### Een op een profiel gebaseerde pushmelding voor transacties configureren {#configuring-profile-based-transactional-push-notification}

Als u een pushmelding over een transactie wilt verzenden naar de Adobe Campaign-profielen die zijn geabonneerd op uw mobiele toepassing, moet u eerst een gebeurtenis maken en configureren die gericht is op de Adobe Campaign-database.

1. Selecteer bij het maken van de gebeurtenisconfiguratie de optie **[!UICONTROL Push notification]** en de **[!UICONTROL Profile]** doelgerichtheid (zie [Een gebeurtenis maken](../../channels/using/configuring-transactional-event.md#creating-an-event)).

   Standaard wordt de transactionele pushmelding verzonden naar alle mobiele toepassingen waarop de ontvangers zich hebben geabonneerd. Als u de pushmelding naar een specifieke mobiele toepassing wilt verzenden, selecteert u deze in de lijst. De andere mobiele toepassingen zullen door het bericht worden gericht maar van het verzenden worden uitgesloten.

   ![](assets/message-center_push_appfilter.png)

1. Voeg velden toe aan de gebeurtenis als u het transactiemelding wilt aanpassen (zie [Gebeurteniskenmerken definiëren](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes)).

   >[!NOTE]
   >
   >U moet ten minste één veld toevoegen om een verrijking te maken. U hoeft geen andere velden te maken, zoals **Voornaam** en **Achternaam** aangezien u verpersoonlijkingsgebieden van het gegevensbestand van Adobe Campaign zult kunnen gebruiken.

1. Een verrijking maken om de gebeurtenis te koppelen aan de **[!UICONTROL Profile]** resource (zie [De gebeurtenis verrijken](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content)) en selecteer deze verrijking als de **[!UICONTROL Targeting enrichment]**.

   >[!IMPORTANT]
   >
   >Deze stap is verplicht voor op profielen gebaseerde gebeurtenissen.

1. [De gebeurtenis voorvertonen en publiceren](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event).

   Wanneer u een voorvertoning van de gebeurtenis weergeeft, bevat de REST API geen kenmerk dat het registratietoken, de toepassingsnaam en het pushplatform opgeeft zoals deze worden opgehaald van het dialoogvenster **[!UICONTROL Profile]** resource.

   Nadat de gebeurtenis is gepubliceerd, wordt automatisch een transactioneel pushbericht gemaakt dat aan de nieuwe gebeurtenis is gekoppeld. U kunt het zojuist gemaakte bericht nu wijzigen en publiceren (zie [deze sectie](#sending-profile-based-transactional-push-notification)).

1. De gebeurtenis in uw website integreren (zie [De gebeurtenis die leidt tot integratie](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger)).

### Een op een profiel gebaseerde pushmelding voor transacties verzenden {#sending-profile-based-transactional-push-notification}

Een luchtvaartmaatschappij wil bijvoorbeeld een laatste instapoproep sturen naar alle Adobe Campaign-gebruikers die zich op de mobiele toepassing hebben geabonneerd.

1. Ga naar het transactionele bericht dat is gemaakt om het te bewerken. Zie [Toegang tot transactieberichten](../../channels/using/editing-transactional-message.md#accessing-transactional-messages).

1. Klik op de knop **[!UICONTROL Content]** blokkeren om de titel en de tekst van uw bericht te wijzigen.

   In tegenstelling tot configuraties die op gebeurtenissen in real time worden gebaseerd, hebt u directe toegang tot alle profielinformatie om uw bericht te personaliseren. Zie [Een personalisatieveld invoegen](../../designing/using/personalization.md#inserting-a-personalization-field).

   Ga voor meer informatie over het bewerken van inhoud van pushberichten naar [Een pushmelding voorbereiden en verzenden](../../channels/using/preparing-and-sending-a-push-notification.md).

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

Voor meer informatie over het integreren van het activeren van een gebeurtenis in een extern systeem raadpleegt u [De gebeurtenis die leidt tot integratie](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger).

De overeenkomstige gebruiker ontvangt een transactioneel pushbericht met daarin alle personalisatie-elementen die uit de Adobe Campaign-database zijn opgehaald.

>[!NOTE]
>
>Er zijn geen registratietoken, toepassings- en pushplatformvelden. In dit voorbeeld wordt de afstemming uitgevoerd met het e-mailveld.

## De doeltoewijzing wijzigen in een transactioneel pushbericht {#change-target-mapping}

Transactiepushberichten gebruiken een specifieke [doeltoewijzing](../../administration/using/target-mappings-in-campaign.md) die de technische instellingen bevat die vereist zijn om dit type leveringen te verzenden.

Volg onderstaande stappen om deze doeltoewijzing te wijzigen:

1. Selecteer een pushmelding in de lijst Transactiebericht.

1. Klik in het berichtdashboard op de knop **[!UICONTROL Edit properties]** knop.

   ![](assets/message-center_push_edit.png)

1. Vouw de sectie **[!UICONTROL Advanced parameters]** uit.

1. Klik op **[!UICONTROL Select a 'Target mapping' element]**.

   ![](assets/message-center_push_target-mapping.png)

1. Selecteer een doelafbeelding in de lijst.

   >[!NOTE]
   >
   >Voor optimale voorbereidingstijd en prestaties bij verzending **op basis van profiel** Transactie-pushberichten gebruiken **[!UICONTROL Profile - Real-time event for Push (mapRtEventAppSubRcp)]** doeltoewijzing.

   ![](assets/message-center_push_target-mapping_change.png)

1. Bevestig uw wijziging en publiceer het bericht. Zie [Een transactioneel bericht publiceren](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message).

   >[!IMPORTANT]
   >
   >U moet het bericht opnieuw publiceren om de verandering effectief te zijn, anders zal de vorige doelafbeelding nog worden gebruikt.


