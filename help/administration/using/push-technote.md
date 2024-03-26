---
title: Aanstaande wijzigingen in het kanaal voor pushmeldingen
description: Aanstaande wijzigingen in het kanaal voor pushmeldingen
audience: channels
feature: Push
role: Admin
level: Experienced
exl-id: e273b443-7c43-482b-8f86-60ada4b57cbf
source-git-commit: db035a41515e94836bdfbfc3d620586dc1f5ce31
workflow-type: tm+mt
source-wordcount: '1134'
ht-degree: 1%

---

# Wijzigingen in kanaal voor pushmelding {#push-upgrade}

Met Campagne kunt u pushmeldingen verzenden op Android- en iOS-apparaten. Om dit te doen, baseert de Campagne zich op de specifieke abonnementsdiensten. Enkele belangrijke wijzigingen in de Android Firebase Cloud Messaging (FCM)-service worden in 2024 gepubliceerd en kunnen van invloed zijn op uw Adobe Campaign-implementatie. Mogelijk moet de configuratie van uw abonnementsservices voor Android-pushberichten worden bijgewerkt om deze wijziging te ondersteunen.

Bovendien adviseert de Adobe hoogst om naar de op teken-gebaseerde verbinding aan APNs eerder dan een op certificaat-gebaseerde verbinding te bewegen, die veiliger en scalable is.

Voor een ononderbroken service moet u een upgrade uitvoeren van uw mobiele toepassing die bij Adobe Campaign is geregistreerd, zodat deze de nieuwste verificatiemechanismen voor FCM (Android) en APNs (iOS) bevat.


[Meer informatie over het configureren van certificaten voor mobiele toepassingen in Adobe Campaign Standard](configuring-a-mobile-application.md#channel-specific-config)


## Google Android Firebase Cloud Messaging (FCM)-service {#fcm-push-upgrade}

### Wat is er veranderd? {#fcm-changes}

Als onderdeel van de voortdurende inspanningen van Google om haar diensten te verbeteren, zullen de bestaande FCM API&#39;s worden stopgezet op **20 juni 2024**. Meer informatie over het HTTP-protocol voor Firebase Cloud Messaging vindt u in [Google Firebase-documentatie](https://firebase.google.com/docs/cloud-messaging/http-server-ref){target="_blank"}.

Starten [24.1-release](../../rn/using/release-notes.md), Adobe Campaign Standard ondersteunt de HTTP v1 API&#39;s voor het verzenden van Android Push Notification Berichten.

### Heb je invloed op? {#fcm-impact}

Als u Adobe Campaign Standard al gebruikt om pushmeldingen te verzenden, moet uw implementatie worden bijgewerkt.

De overgang naar de nieuwste API&#39;s is verplicht om elke onderbreking van de service te voorkomen.

<!--To check if you are impacted, you can filter your **Services and Subscriptions** as per the filter below

* If any of your active push notification service uses the **HTTP (legacy)** API, your setup will be directly impacted by this change. You must review your current configurations and move to the newer APIs as described below.

* If your setup exclusively uses the **HTTP v1** API for Android push notifications, then you are already in compliance and no further action will be required on your part.-->

### Hoe kan ik bijwerken? {#fcm-transition-procedure}

#### Vereisten {#fcm-transition-prerequisites}

* De steun van **HTTP v1-API** Deze modus is toegevoegd in versie 24.1. Als uw omgeving op een oudere versie wordt uitgevoerd, is een upgrade van uw omgeving naar de [nieuwste release van Campaign Standard](../../rn/using/release-notes.md).

* Het JSON-bestand van de Android Firebase Admin SDK-service is vereist om de mobiele toepassing naar HTTP v1 te verplaatsen. Leer hoe u dit bestand kunt ophalen in [Google Firebase-documentatie](https://firebase.google.com/docs/admin/setup#initialize-sdk){target="_blank"}.

* Als u deze oudere versie van de SDK nog steeds gebruikt, moet u uw implementatie bijwerken met de Adobe Experience Platform SDK. Meer informatie over het migreren naar Adobe Experience Plaform SDK in [dit artikel](sdkv4-migration.md).

* Zorg ervoor dat u de **Mobiele toepassingsconfiguratie** toestemming in Adobe Experience Platform Data Collection Mobile alvorens de hieronder stappen uit te voeren. [Meer informatie](https://experienceleague.adobe.com/docs/experience-platform/collection/permissions.html?lang=en#adobe-experience-platform-data-collection-permissions){target="_blank"}.


#### Overgangprocedure {#fcm-transition-steps}

Ga als volgt te werk om uw omgeving te verplaatsen naar HTTP v1:

1. Bladeren naar **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]**.

   ![](assets/push_technote_1.png)

1. Selecteer de specifieke mobiele toepassing waarvoor het certificaat moet worden bijgewerkt.

1. Controleer de **[!UICONTROL Update app credentials]** selectievakje.

   ![](assets/push_technote_5.png)

1. Geef de toepassings-id (Android-pakketnaam) van uw Android-project op `build.gradle` bestand. Bijvoorbeeld: `com.android.test.testApp`. Zorg ervoor dat u verschillende id&#39;s gebruikt voor testomgevingen en productieomgevingen.

1. Upload uw JSON-sleutelbestand met uw persoonlijke sleutel voor Android.

   ![](assets/push_technote_3.png)

1. Klik op de knop **Opslaan** knop.

>[!NOTE]
>
>Zodra deze wijzigingen zijn toegepast, gebruiken alle nieuwe pushberichten die aan Android-apparaten worden geleverd de HTTP v1-API. Bestaande push-items worden opnieuw uitgevoerd, in uitvoering en in gebruik, maar gebruiken nog steeds de HTTP (legacy) API.


## Apple iOS Push Notification Service (APNs) {#apns-push-upgrade}

### Wat is er veranderd? {#ios-changes}

Zoals aanbevolen door Apple, moet u uw communicatie met de APNs (Apple Push Notification service) beveiligen door stateless verificatietokens te gebruiken.

Token-gebaseerde authentificatie biedt een stateless manier om met APNs te communiceren. Stateloze communicatie is sneller dan op certificaat-gebaseerde communicatie omdat het geen APNs vereist om het certificaat, of andere informatie, met betrekking tot uw leverancierserver op te zoeken. Er zijn andere voordelen aan het gebruiken van op teken-gebaseerde authentificatie:

* U kunt hetzelfde token gebruiken van meerdere providerservers.

* U kunt één token gebruiken om meldingen te distribueren voor alle apps van uw bedrijf.

Meer informatie over op token gebaseerde verbindingen met APNs vindt u in [Apple Developer-documentatie](https://developer.apple.com/documentation/usernotifications/establishing-a-token-based-connection-to-apns){target="_blank"}.

Adobe Campaign Standard ondersteunt zowel tokenverbindingen als verbindingen op basis van certificaten. Als uw implementatie afhankelijk is van een verbinding op basis van een certificaat, raadt de Adobe u ten zeerste aan om deze bij te werken naar een tokenverbinding.

### Heb je invloed op? {#ios-impact}

Als uw huidige implementatie afhankelijk is van op een certificaat gebaseerde aanvragen om verbinding te maken met APNs, heeft dit gevolgen voor u. De overgang naar een op een token gebaseerde verbinding wordt aanbevolen.

<!--To check if you are impacted, you can filter your **Services and Subscriptions** as per the filter below:

![](assets/filter-services-ios.png)


* If any of your active push notification service uses the **Certificate-based authentication** mode (.p12), your current implementations should be reviewed and moved to a **Token-based authentication** mode (.p8) as described below.

* If your setup exclusively uses the **Token-based authentication** mode for iOS push notifications, then your implementation is already up-to-date and no further action will be required on your part.-->

### Hoe kan ik bijwerken? {#ios-transition-procedure}

#### Vereisten {#ios-transition-prerequisites}

* De steun van **Op token gebaseerde verificatie** modus is toegevoegd in [24.1-release](../../rn/using/release-notes.md). Als uw omgeving op een oudere versie wordt uitgevoerd, is een upgrade van uw omgeving naar de [nieuwste release van Campaign Standard](../../rn/using/release-notes.md).

* U hebt een APNs-verificatietoken voor ondertekening nodig om de tokens te genereren die uw server gebruikt. U kunt deze sleutel aanvragen via uw Apple-ontwikkelaarsaccount, zoals wordt uitgelegd in [Apple Developer-documentatie](https://developer.apple.com/documentation/usernotifications/establishing-a-token-based-connection-to-apns){target="_blank"}.


#### Overgangprocedure {#ios-transition-steps}

Voer de volgende stappen uit om uw mobiele iOS-toepassingen te verplaatsen naar de op token gebaseerde verificatiemodus:

1. Bladeren naar **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]**.

   ![](assets/push_technote_1.png)

1. Selecteer de specifieke mobiele toepassing waarvoor het certificaat moet worden bijgewerkt.

1. Controleer de **[!UICONTROL Update app credentials]** selectievakje.

   ![](assets/push_technote_2.png)

1. Geef de **Toepassings-id** (iOS-bundel-id). U vindt de iOS Bundle ID (App ID) in het primaire doel van uw app in Xcode.

1. Upload uw **iOS p8-certificaatbestand**.

1. De APN-verbindingsinstellingen invullen **[!UICONTROL Key Id]** en **[!UICONTROL iOS Team Id]**.

   ![](assets/push_technote_4.png)

1. Klik op **[!UICONTROL Save]**.

Uw iOS-toepassing wordt nu verplaatst naar de op token gebaseerde verificatiemodus.

## Veelgestelde vragen{#push-upgrade-faq}

+++Kunnen we dezelfde appID behouden in het werkgebied en de prod-instantie?

Voor mobiele iOS-toepassingen kunt u dezelfde app-id gebruiken, de bundel-id van de iOS-app, voor zowel testomgevingen als productieomgevingen. Op Android-systemen moet de toepassings-id echter uniek zijn voor elke omgeving. Daarom wordt aanbevolen &#39;stage&#39; toe te voegen aan de toepassings-id die in de testomgeving is gemaakt

+++


+++Kunnen we alleen de Android-toepassing migreren?

Nee, zowel Android- als iOS-toepassingen moeten worden gemigreerd volgens de bovenstaande stappen.

+++

+++Welk type verificatie moeten we uitvoeren na de migratie?

Onze aanbeveling is om functionele validatie uit te voeren van al uw zaken met betrekking tot het gebruik van pushtechnologie.

+++

+++Wat moet u doen als u de fout &#39;Niet geautoriseerd&#39; verkrijgt terwijl u de mobiele app opslaat?

Dit lijkt een machtigingsprobleem te zijn met betrekking tot de gegevensverzameling van Adobe Experience Platform. U kunt dit oplossen door de machtigingen Mobiele en Mobiele toepassingsconfiguratie toe te voegen in de Adobe Admin Console, zoals beschreven in de sectie Voorwaarden van dit artikel.

+++

+++Zijn wijzigingen vereist in mobiele toepassingscode?

Nee, alleen configuratiewijzigingen zijn vereist in Firebase en de ontwikkelaarsaccount van de app. Wijzigingen in de mobiele app van de klant zijn niet vereist.

+++

+++Moeten we het iOS-certificaat elk jaar bijwerken?

Nee, na deze migratie is het niet nodig om het iOS-certificaat elk jaar bij te werken.

+++

+++Wat gebeurt er als deze migratie niet wordt uitgevoerd?

De Android-pushberichten mislukken na 20 juni 2024, zoals wordt gemeld door Google. [Meer informatie](https://firebase.google.com/docs/cloud-messaging/migrate-v1){target="_blank"}.

+++

+++Kunnen klanten na voltooiing van de FCMv1-migratie terugmigreren naar FCM?

Ja, klanten kunnen tot 20 juni 2024 terugmigreren naar FCM. Na deze datum is de migratieoptie niet meer beschikbaar.

+++

+++Wordt de migratie van de HTTP v1-API ondersteund op de mobiele SDK V4-app?

Nee, klanten moeten hun mobiele app eerst migreren naar de V5 SDK en vervolgens doorgaan met de bovenstaande migratie. Zij moeten dit als prioriteit doen, aangezien hun pushservice vanaf juni 2024 zal mislukken, zoals in de kennisgeving van Google wordt aangegeven.

+++

+++Heeft een wijziging in een instantie van het werkgebied enig effect op het productieexemplaar?

Nee, wijzigingen in de stage mobile-app hebben geen invloed op de productie-instantie.

+++