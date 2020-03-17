---
title: Transactionele pushmeldingen
description: Leer hoe u een pushmelding voor transacties maakt en publiceert.
page-status-flag: never-activated
uuid: ef31c1b6-9ef8-42e3-b49d-72f9eac8ea32
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: transactional-messaging
discoiquuid: e645d4b9-001f-47d9-8a0f-b4696c75c5d3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Transactionele pushmeldingen{#transactional-push-notifications}

U kunt Adobe Campaign gebruiken om pushmeldingen over transacties te verzenden op mobiele apparaten met iOS en Android. Deze berichten worden ontvangen op mobiele toepassingen die u instelt in Adobe Campagne door gebruik te maken van de Experience Cloud Mobile SDK.

>[!NOTE]
>
>Het drukkanaal is optioneel. Controleer uw licentieovereenkomst. Zie [Pushmeldingen](../../channels/using/about-push-notifications.md)voor meer informatie over standaardpushmeldingen.

U kunt twee typen pushmeldingen voor transacties verzenden:

* Transactionele pushmeldingen die gericht zijn op een gebeurtenis.
* Transactionele pushmeldingen die gericht zijn op profielen uit de Adobe Campagne-database.

Nadat u een gebeurtenis hebt gemaakt en gepubliceerd (de winkelwagentje wordt in [deze sectie](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle)uitgelegd), wordt het bijbehorende pushbericht voor transacties automatisch gemaakt.

De configuratiestappen worden voorgesteld in het [Vormen van een gebeurtenis om een sectie van het transactionele pushbericht](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) te verzenden.

Als de gebeurtenis het verzenden van een transactiemelding moet activeren, moet u het bericht personaliseren, het vervolgens testen en publiceren.

>[!NOTE]
>
>Om tot transactieberichten toegang te hebben, moet u deel van de **[!UICONTROL Administrators (all units)]** veiligheidsgroep uitmaken.

## Transactionele pushmeldingen voor een gebeurtenis {#transactional-push-notifications-targeting-an-event}

U kunt een anoniem pushbericht over een transactie verzenden naar alle gebruikers die zich hebben aangemeld om berichten van uw mobiele toepassing te ontvangen.

In dit geval worden alleen de gegevens in de gebeurtenis zelf gebruikt om het leveringsdoel te definiëren. Er worden geen gegevens van de geïntegreerde profieldatabase van Adobe Campagne gebruikt.

### Een transactionele pushmelding verzenden voor een gebeurtenis {#sending-a-transactional-push-notification-targeting-an-----------event}

Een luchtvaartmaatschappij wil bijvoorbeeld haar gebruikers van mobiele toepassingen uitnodigen om naar de relevante poort voor instapweigering te gaan.

Het bedrijf verzendt één transactioneel pushbericht per gebruiker (geïdentificeerd met een registratietoken), gebruikend één mobiele toepassing, door één enkel apparaat.

1. Ga het transactiemelding dat werd gecreeerd om het uit te geven. Zie Transactieberichten voor [gebeurtenissen](../../channels/using/event-transactional-messages.md).

   ![](assets/message-center_push_message.png)

1. Klik op het **[!UICONTROL Content]** blok om de titel en de tekst van uw bericht te wijzigen.

   U kunt verpersoonlijkingsgebieden opnemen om elementen toe te voegen die u bepaalde toen u uw gebeurtenis creeerde.

   ![](assets/message-center_push_content.png)

   Als u deze velden wilt zoeken, klikt u op het potlood naast een item, klikt u **[!UICONTROL Insert personalization field]** en selecteert u **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**.

   ![](assets/message-center_push_personalization.png)

   Zie Een pushmelding [maken](../../channels/using/preparing-and-sending-a-push-notification.md)voor meer informatie over het bewerken van inhoud van een pushmelding.

1. Sla uw wijzigingen op en publiceer het bericht. Zie [Transactiebericht](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message)publiceren.
1. Stuur met de Adobe Campagne Standard REST API een gebeurtenis naar een registratietoken (ABCDEF123456789) met één mobiele toepassing (WeFlight) op Android (gcm), die de instapgegevens bevat.

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

   Zie [Site-integratie](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)voor meer informatie over het integreren van de activering van een gebeurtenis in een extern systeem.

Als het registratietoken bestaat, ontvangt de overeenkomstige gebruiker een transactioneel pushbericht met de volgende inhoud:

&quot;Hallo Jane Green, het instappen is net begonnen! Ga verder met Gate B18.&quot;

## Transactionele pushmeldingen die gericht zijn op een profiel {#transactional-push-notifications-targeting-a-profile}

U kunt een pushmelding over een transactie verzenden naar de Adobe Campagne-profielen die zijn geabonneerd op uw mobiele toepassing. Deze levering kan [verpersoonlijkingsgebieden](../../designing/using/personalization.md#inserting-a-personalization-field) , zoals de voornaam van de ontvanger bevatten.

In dit geval moet de gebeurtenis enkele velden bevatten waarmee een bestand kan worden vergeleken met een profiel uit de Adobe Campagne-database.

Bij het opgeven van profielen wordt per mobiele toepassing en per apparaat één transactioneel pushbericht verzonden. Als een Adobe Campagnegebruiker bijvoorbeeld op twee toepassingen heeft geabonneerd, ontvangt deze gebruiker twee meldingen. Als een gebruiker zich op dezelfde toepassing heeft geabonneerd met twee verschillende apparaten, ontvangt deze gebruiker een melding op elk apparaat.

De mobiele toepassingen waarop een profiel is geabonneerd, worden weergegeven op het **[!UICONTROL Mobile App Subscriptions]** tabblad van dit profiel. U opent dit tabblad door een profiel te selecteren en op de **[!UICONTROL Edit profile properties]** knop aan de rechterkant te klikken.

![](assets/push_notif_subscriptions.png)

Zie [Profielen](../../audiences/using/creating-profiles.md)voor meer informatie over het openen en bewerken van profielen.

### Transactie-pushmeldingen verzenden voor een profiel {#sending-a-transactional-push-notification-targeting-a-----------profile}

Een luchtvaartmaatschappij wil bijvoorbeeld een laatste instapoproep verzenden naar alle gebruikers van Adobe Campagne die zich hebben geabonneerd op de mobiele toepassing van Adobe.

1. Ga het transactiemelding dat werd gecreeerd om het uit te geven. Zie Transactieberichten voor [gebeurtenissen](../../channels/using/event-transactional-messages.md).

   <!--![](assets/message-center_push_message_profile.png)-->

1. Klik op het **[!UICONTROL Content]** blok om de titel en de tekst van uw bericht te wijzigen.

   In tegenstelling tot configuraties die op gebeurtenissen in real time worden gebaseerd, hebt u directe toegang tot alle profielinformatie om uw bericht te personaliseren. Zie Een verpersoonlijkingsveld [invoegen](../../designing/using/personalization.md#inserting-a-personalization-field).

   <!--![](assets/message-center_push_content_profile.png)-->

   Voor meer informatie over het bewerken van inhoud van een pushmelding. Zie [Een pushmelding](../../channels/using/preparing-and-sending-a-push-notification.md)maken.

1. Sla uw wijzigingen op en publiceer het bericht. Zie [Transactiebericht](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message)publiceren.
1. Verzend een gebeurtenis naar een profiel met de Adobe Campagne Standard REST API.

   ```
   {
     "ctx":
     {
       "email":"janegreen@email.com",
       "gateNumber":"D16",
     }
   }
   ```

   Zie [Site-integratie](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)voor meer informatie over het integreren van de activering van een gebeurtenis in een extern systeem.

   >[!NOTE]
   >
   >Er zijn geen registratietoken, toepassings- en pushplatformvelden. In dit voorbeeld wordt de afstemming uitgevoerd met het e-mailveld.

