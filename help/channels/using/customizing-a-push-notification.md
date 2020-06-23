---
title: Een pushmelding aanpassen
description: Leer hoe u uw pushmeldingen kunt aanpassen met verschillende geavanceerde opties.
page-status-flag: never-activated
uuid: 8cf74cad-b1ba-4aad-83bd-7289cb22d5f4
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: push-notifications
discoiquuid: dc944c85-2059-46df-b396-676fe3617dd1
context-tags: delivery,mobileAppContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d4ac80810a77c0a6b512b3ed4c925fa0fb8a219c
workflow-type: tm+mt
source-wordcount: '1494'
ht-degree: 0%

---


# Een pushmelding aanpassen{#customizing-a-push-notification}

Als u uw pushmelding wilt verfijnen, kunt u in Adobe Campaign toegang krijgen tot een set geavanceerde opties terwijl u een pushmelding ontwerpt.

Als deskundige gebruiker, om mobiele toepassingen in Adobe Campaign te vormen, verwijs naar het volgende technische [Begrip van de Structuur](https://helpx.adobe.com/campaign/kb/understanding-campaign-standard-push-notifications-payload-struc.html)van de Payload van de Berichten van Campaign Standard.

![](assets/push_notif_advanced.png)

**Gerelateerde inhoud:**

* [Pushmeldingsrapport](../../reporting/using/push-notification-report.md)
* [Een pushmelding verzenden binnen een workflow](../../automating/using/push-notification-delivery.md)

## Geluid afspelen {#play-a-sound}

De functie **[!UICONTROL Play a sound]** biedt de toepassing de mogelijkheid om geluiden af te spelen op uw apparaat met de levering van een pushmelding wanneer de app niet wordt uitgevoerd.

Met een geluid worden gebruikers gewaarschuwd voor een pushmelding, waardoor deze meer zichtbaar wordt. Een geluid opnemen in uw mobiele app:

1. Open de pushmelding en open de **[!UICONTROL Advanced options]** sectie.
1. Voer in het **[!UICONTROL Play a sound]** veld de bestandsnaam in van het geluidsbestand, zonder de extensie, dat door het mobiele apparaat moet worden afgespeeld wanneer het bericht wordt ontvangen.

   Raadpleeg de documentatie van [Apple](https://support.apple.com/kb/PH16864?locale=en_US) en [Android](https://developer.android.com/guide/topics/media/media-formats) voor meer informatie over ondersteunde media-indelingen.

   ![](assets/push_notif_advanced_7.png)

1. Het geluidsbestand wordt afgespeeld bij het verzenden van de melding als het bestand is gedefinieerd in het pakket van de mobiele toepassing. Anders wordt het standaardgeluid van het apparaat afgespeeld.

De gebruiker zal dan het dupbericht en het geluid ontvangen slechts als zijn telefoon niet gedempt is.

## De badwaarde vernieuwen {#refresh-the-badge-value}

Een badge wordt gebruikt om het aantal nieuwe ongelezen informatie direct op het toepassingspictogram te tonen. De merkwaarde verdwijnt zodra de gebruiker de nieuwe inhoud in de toepassing opent of leest.

Wanneer een melding op een apparaat wordt ontvangen, kan het een merkwaarde voor de verwante app vernieuwen of toevoegen. Een merkwaarde verzenden vanaf de serverzijde:

1. Open de pushmelding en open de **[!UICONTROL Advanced options]** sectie.
1. De badge-waarde moet een geheel getal zijn en kan op verschillende manieren worden bijgewerkt:

   * Voer in het **[!UICONTROL Value of the badge]** veld 0 in om de badge te vernieuwen. Hierdoor wordt de badge uit het toepassingspictogram verwijderd.
   * Voer een willekeurig nummer in het **[!UICONTROL Value of the badge]** veld in om een badgewaarde toe te voegen. Dit nummer wordt automatisch op de badge weergegeven zodra de gebruiker het pushbericht heeft ontvangen.
   * Als het veld leeg is of geen geheel getal bevat, verandert de merkwaarde niet.
   Hier, gingen wij 1 op het **[!UICONTROL Value of the badge]** gebied in om de gebruikers te laten weten dat zij een nieuwe informatie in hun toepassing hebben.

   ![](assets/push_notif_advanced_8.png)

1. Na het verzenden van uw bericht ontvangen gebruikers het pushbericht en geeft hun toepassing automatisch de nieuwe merkwaarde weer.

   ![](assets/push_notif_advanced_1.png)

## Een diepkoppeling toevoegen {#add-a-deeplink}

Met een deplink kunt u de gebruikers rechtstreeks naar inhoud in de toepassing brengen (in plaats van een webbrowserpagina te openen).

Een deplink kan aanpassingsgegevens bevatten voor een aangepaste ervaring in de app. Voornamen van ontvangers worden bijvoorbeeld automatisch ingevuld op de pagina waarnaar de toepassing verwijst.

Een koppeling toevoegen in een pushmelding:

1. Open de pushmelding en open de **[!UICONTROL Advanced options]** sectie.
1. Voer de koppeling in het **[!UICONTROL Add a deeplink]** veld in.

   ![](assets/push_notif_advanced_3.png)

1. Na het verzenden van uw bericht ontvangen de gebruikers het pushbericht en krijgen ze toegang tot de specifieke pagina in de app door te communiceren met het bericht, bijvoorbeeld door te tikken op de knop voor het oproepen van actie of door te klikken.

   ![](assets/push_notif_advanced_4.png)

## Een handeling definiëren {#define-an-action}

U kunt een categorie-id toevoegen als deze beschikbaar is in de mobiele toepassing en vervolgens de knoppen voor handelingen weergeven. Met deze meldingen kan de gebruiker sneller verschillende taken uitvoeren als reactie op een melding zonder de toepassing te openen of erin te navigeren.

De dialoog die op de telefoon van de gebruiker verschijnt vereist een besluit te werk te gaan. Wanneer de gebruiker een van de handelingen selecteert, brengt het systeem de toepassing op de hoogte, zodat deze alle bijbehorende taken kan uitvoeren.

Een categorie toevoegen aan een pushmelding:

1. Open de pushmelding en open de **[!UICONTROL Advanced options]** sectie.
1. Voer in het **[!UICONTROL Category]** veld een vooraf gedefinieerde categorienaam in om knoppen voor handelingen weer te geven wanneer het pushbericht wordt ontvangen.

   De ontwikkelaar van de mobiele toepassing moet de categorie-id en het verwachte gedrag van de knoppen in de toepassing definiëren. Raadpleeg voor meer informatie de documentatie [van](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/SupportingNotificationsinYourApp.html) Apple Developer (**sectie Categorieën en actiefmeldingen** configureren) of de documentatie [van](https://developer.android.com/guide/topics/ui/notifiers/notifications.html)Android Developer.

   ![](assets/push_notif_advanced_9.png)

1. Na het verzenden van uw pushmelding ontvangen gebruikers het bericht en moeten ze actie ondernemen met de eerder geconfigureerde actieknoppen.

   ![](assets/push_notif_actionable_buttons.png)

Afhankelijk van de actie van de gebruiker, zal de toepassing worden op de hoogte gebracht zodat het om het even welke bijbehorende taken kan uitvoeren.

## Een vervaldatum toevoegen {#add-expiration-date}

Als u een vervaldatum instelt op uw pushmelding, kunt u een specifieke vervaldatum instellen waarop het bericht niet langer wordt verzonden door Apple ([APNS](https://developer.apple.com/documentation/usernotifications/setting_up_a_remote_notification_server/sending_notification_requests_to_apns)) of Android ([FCM](https://firebase.google.com/docs/cloud-messaging/concept-options)).

Een vervaldatum toevoegen aan uw pushmelding:

1. Schakel de **[!UICONTROL Expire message]** optie in.

   >[!NOTE]
   >
   >Als u de **[!UICONTROL Expire message]** optie selecteert, wordt de duur automatisch ingesteld op 0. Als u de waarde niet wijzigt, proberen zowel APNS als FCM het bericht onmiddellijk te verzenden. Als het ontbreekt, zal het bericht niet opnieuw worden verzonden.

1. Selecteer in het **[!UICONTROL Duration]** veld de geldigheid van uw pushmelding.

   ![](assets/push_expiration.png)

1. Na het verzenden van uw dupmelding, als de gebruiker het niet onmiddellijk wegens de telefoon die of geen signaal ontvangen heeft, zal de duw nog binnen de groef van de vervaldatumtijd worden verzonden.

Als de pushmelding niet is verzonden vóór de vervaldatum, wordt deze genegeerd.

## Aangepaste velden toevoegen {#add-custom-fields}

Met aangepaste velden kunt u aangepaste gegevens in de lading doorgeven in de vorm van een sleutelwaardepaar. Deze optie kan worden gebruikt om extra gegevens aan de toepassing voorbij de vooraf bepaalde sleutels over te gaan.

Daartoe:

1. Open de pushmelding en open de **[!UICONTROL Advanced options]** sectie.
1. Klik in de **[!UICONTROL Custom fields]** categorie op de **[!UICONTROL Add an element]** knop.
1. Voer **[!UICONTROL Keys]** vervolgens de **[!UICONTROL Values]** bijbehorende sleutel in.

   ![](assets/push_notif_advanced_10.png)

1. De verwerking en het doel van aangepaste velden zijn volledig afhankelijk van de mobiele app. In de onderstaande pushmelding heeft de app aangepaste velden gebruikt om knoplabels voor de pushmelding weer te geven.

   ![](assets/push_notif_actionable_buttons.png)

## Rich media-inhoud toevoegen {#add-rich-media-content}

Dankzij rijke media-inhoud kunt u een betere betrokkenheid van de gebruiker krijgen. Dit houdt in dat uw gebruiker meer geneigd zal zijn om uw pushmelding te openen.

U kunt een afbeeldings-, gif-, audio- of videobestand opnemen dat wordt afgespeeld of weergegeven in het bericht zelf. Gebruikers van uw app hoeven de toepassing niet te openen om deze te kunnen zien.

Rijke media opnemen in de pushmelding:

1. Open de pushmelding en open de **[!UICONTROL Advanced options]** sectie.
1. Voer in het **[!UICONTROL Rich media content URL]** veld de URL van het bestand in voor elke indeling: iOS en Android.

   Voor iOS 10 of hoger kunt u afbeeldings-, gif-, audio- en videobestanden invoegen. Voor eerdere iOS-versies wordt de pushmelding weergegeven zonder rijke inhoud. Raadpleeg deze [pagina](https://helpx.adobe.com/campaign/kb/display-image-push.html)voor gedetailleerde stappen over het weergeven van een afbeelding vanuit een Adobe Campaign-pushmelding op een iOS-apparaat.

   Voor Android kunt u alleen afbeeldingen opnemen.

   ![](assets/push_notif_advanced_6.png)

1. Na het verzenden van uw bericht ontvangt de gebruiker uw pushmelding en kan hij de rich media-inhoud weergeven.

   ![](assets/push_notif_advanced_2.png)

## Het meldingsgedrag voor iOS wijzigen {#change-the-notification-behavior-for-ios}

![](assets/push_notif_advanced_5.png)

Voor iOS 10 of hoger zijn twee extra opties beschikbaar in het **[!UICONTROL Advanced options]** gedeelte met pushmeldingen: **[!UICONTROL Mutable content]** en **[!UICONTROL Content available]**.

Wanneer de **[!UICONTROL Mutable content]** optie is ingeschakeld en/of een URL voor veelzijdige media-inhoud wordt toegevoegd, wordt de markering voor meerbare inhoud verzonden in de pushlading en kan de inhoud van het pushbericht worden gewijzigd door een uitbreiding van de berichtservice die is opgegeven in iOS SDK. Raadpleeg de documentatie bij [ontwikkelaars van](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/ModifyingNotifications.html)Apple voor meer informatie hierover.

Vervolgens kunt u uw mobiele app-extensies gebruiken om de inhoud of presentatie van aankomende pushberichten die vanuit Adobe Campaign zijn verzonden, verder te wijzigen. Gebruikers kunnen deze optie bijvoorbeeld gebruiken om:

* Gegevens decoderen die in een gecodeerde indeling zijn geleverd
* Afbeeldingen of andere mediabestanden downloaden en toevoegen als bijlagen aan een melding
* De tekst van de hoofdtekst of titel van een melding wijzigen
* Een thread-id toevoegen aan een bericht

Wanneer **[!UICONTROL Content available]** deze optie is ingeschakeld, wordt de markering voor de beschikbare inhoud verzonden in de pushlading om ervoor te zorgen dat de app wordt geactiveerd zodra deze de pushmelding ontvangt. Dit betekent dat de app toegang kan krijgen tot de payload-gegevens. Dit werkt zelfs als de app op de achtergrond wordt uitgevoerd en zonder tussenkomst van de gebruiker (bijvoorbeeld tikken op pushmeldingen), maar dit geldt niet als de app niet wordt uitgevoerd. Raadpleeg de documentatie bij [ontwikkelaars van](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CreatingtheNotificationPayload.html)Apple voor meer informatie hierover.

## Het meldingsgedrag voor Android wijzigen {#change-the-notification-behavior-for-android}

Voor Android kunt u de URL van het bestand invoeren in het veld URL **van** rich media-inhoud. Terwijl u met de iOS-versie voor Android alleen afbeeldingen en geen gif-, audio- of videobestanden kunt opnemen.

Met het **[!UICONTROL High priority]** selectievakje kunt u een hoge of normale prioriteit instellen voor uw pushberichten. Raadpleeg de documentatie [van](https://firebase.google.com/docs/cloud-messaging/concept-options#setting-the-priority-of-a-message)Google Developer voor meer informatie over berichtprioriteit.

![](assets/push_notif_advanced_11.png)

