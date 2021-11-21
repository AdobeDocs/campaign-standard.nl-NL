---
title: Informatie over pushmeldingen
description: Ontdek de belangrijkste specifieke kenmerken van het pushmeldingskanaal in Adobe Campaign.
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
feature: Push
role: User
level: Intermediate
exl-id: e61daed6-a0ec-49d8-b1ad-77590fafb496
source-git-commit: b5e98c07ee55cab0b6a628a97162ccd64711501a
workflow-type: tm+mt
source-wordcount: '1237'
ht-degree: 49%

---

# Informatie over pushmeldingen{#about-push-notifications}

>[!CAUTION]
>
>De implementatie van pushmeldingen moet worden uitgevoerd door deskundige gebruikers. Neem voor hulp contact op met uw Adobe-accountmanager of uw partner op het gebied van professionele services. Pushmelding is een optionele functie. Controleer uw licentieovereenkomst en neem contact op met uw accountmanager om deze te activeren.

Met Adobe Campaign kunt u persoonlijke en gesegmenteerde pushmeldingen verzenden naar mobiele apparaten met iOS en Android.

Deze berichten worden ontvangen in mobiele applicaties die u instelt in Adobe Campaign door gebruik te maken van de Experience Platform-SDK. Zie [Een mobiele applicatie configureren met Adobe Experience Platform-SDK’s](../../administration/using/configuring-a-mobile-application.md) voor meer informatie.

In Adobe Campaign worden data van mobiele profielkenmerken die vanaf een mobiel apparaat worden verzonden, opgeslagen in de resource **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** waardoor u de data die u van de abonnees van uw applicaties wilt verzamelen, kunt definiëren.

Deze resource moet worden uitgebreid om data te verzamelen die u van het mobiele apparaat naar Adobe Campaign wilt verzenden. Raadpleeg deze [pagina](../../developing/using/extending-the-subscriptions-to-an-application-resource.md) voor de gedetailleerde stappen als u dit wilt doen.

Er zijn twee typen pushmeldingen beschikbaar in Adobe Campaign:

* Met meldingen van het type **[!UICONTROL Alert/Message/Badge]** kunt u standaardtekstberichten verzenden met extra content (geluid, badge, deeplink, enz.), die u in de sectie **[!UICONTROL Advanced options]** kunt definiëren.

   Met deze meldingstypen kunt u een titel en een bericht toevoegen waarin u personalisatievelden kunt gebruiken. Als u uw bericht wilt aanpassen, selecteert u de sjabloon **[!UICONTROL Send push on profiles]**.

* Meldingen van het type **[!UICONTROL Silent push]** worden gebruikt om de applicatie op de hoogte te brengen zonder bericht of content voor de eindgebruiker. Dit type bericht kan bijvoorbeeld worden gebruikt om de applicatie te informeren dat er content op de server beschikbaar is om te downloaden.

Er kunnen specifieke configuraties worden ingesteld om het gedrag van meldingen te definiëren. Raadpleeg [deze sectie](../../channels/using/customizing-a-push-notification.md) voor meer informatie hierover.

>[!NOTE]
>
>De wetgeving inzake privacy verschilt per land. Sommige landen schrijven voor dat u gebruikers informeert over de typen data die door mobiele applicaties worden verzameld. Controleer de wetten met betrekking tot mobiele applicaties in uw land. Zorg ervoor dat pushmeldingen die naar mobiele applicaties worden verzonden, voldoen aan de voorwaarden en vereisten die door Apple (Apple Push Notification Service) en Google (Google Cloud Messaging of Firebase Cloud Messaging) zijn opgegeven.

**Gerelateerde content:**

* [Een pushmelding voorbereiden en verzenden](../../channels/using/preparing-and-sending-a-push-notification.md)
* [Een meertalige pushmelding maken](../../channels/using/creating-a-multilingual-push-notification.md)
* [Pushmeldingenrapport](../../reporting/using/push-notification-report.md)
* [Campaign Standard - gids voor mobiel gebruik](../../channels/using/get-started-communication-channels.md)

## Vereisten {#prerequisites}

>[!NOTE]
>Als u de functie voor pushmeldingen van Campaign wilt gebruiken, moet u een geldig pushcertificaat in pem-indeling opgeven zonder wachtwoorden.
>
>Als u een geldig p12-certificaat hebt, kunt u het gemakkelijk converteren naar een pem-bestand met online resources.

Voordat u pushmeldingen verzendt, moet u het volgende doen:

1. Zorg ervoor dat u in Adobe Campaign toegang hebt tot het kanaal **[!UICONTROL Push notification]**. Neem contact op met uw accountteam als u geen toegang hebt tot deze kanalen.

1. Controleer of uw gebruiker beschikt over de vereiste machtigingen in Adobe Campaign Standard en Experience Platform Launch.

1. Maak een mobiele eigenschap in Experience Platform Launch. Zie [Een mobiele eigenschap instellen](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property) voor meer informatie.

1. Installeer de extensie **[!UICONTROL Adobe Campaign Standard]** in Experience Platform Launch.

1. Configureer in Adobe Campaign Standaard de mobiele eigenschap die u in Experience Platform Launch hebt gemaakt. Zie [Uw Experience Platform Launch-applicatie instellen in Adobe Campaign](../../administration/using/configuring-a-mobile-application.md#set-up-campaign) voor meer informatie.

1. Voeg de kanaalspecifieke configuratie toe aan de configuratie van de mobiele applicatie. Zie [Kanaalspecifieke applicatieconfiguratie in Adobe Campaign](../../administration/using/configuring-a-mobile-application.md#channel-specific-config) voor meer informatie.

1. Raadpleeg de gedetailleerde instructies voor extensies, Experience Platform Launch-regels en de SDK-implementatie in [Mobiele gebruikssituaties die in Adobe Campaign Standard worden ondersteund door middel van de Adobe Experience Platform-SDK’s](../../administration/using/configuring-rules-launch.md) voor informatie over de ondersteuning van mobiele gebruikssituaties.

## Veelgestelde vragen over pushmeldingen {#push-faq}

### Wat zouden sommige nuttige middelaanbevelingen zijn om meer over het kanaal van de Duw te leren? {#resource-push}

Ontdek de onderstaande bronnen:

* [Videotutorials](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/communication-channels/mobile/push/creating-a-push-notification.html)
* [Productdocumentatie](../../channels/using/about-push-notifications.md)
* Configureren met AEP SDK [documentatie](../../administration/using/configuring-a-mobile-application.md)
* [Community-pagina](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-standard/ct-p/adobe-campaign-standard-community)

### Wat moet ik doen om een pushtoken te verkrijgen in Campaign? {#push-token-acquisition}

Controleer of het inrichtingsteam de levering van het Push-kanaal in Adobe Campaign Standard heeft voltooid. SetPushIdentifier-API van SDK implementeren. Raadpleeg [deze pagina](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard#set-up-push-messaging) voor meer informatie.

### Als ik Push token en ECID in Campaign heb, wat moet ik dan nog een pushmelding verzenden? {#sending-push}

Klanten moeten een geldig pushcertificaat in .pem-indeling opgeven om een pushmelding te verzenden. U hebt geen wachtwoord nodig voor dit certificaat.

### Wat gebeurt er als ik een .p12-certificaat heb in plaats van een .pem-certificaat? {#certificates}

U kunt een .p12 certificaat in een .pem certificaat omzetten door het hieronder bevel in terminal in werking te stellen. Er zijn verschillende online bronnen beschikbaar voor conversie-instructies.

```
openssl pkcs12 -in pushcert.p12 -out pushcert.pem -nodes -clcerts
```

### Hoe weet ik of het uploaden van het certificaat is gelukt? {#certificate-upload}

Het volgende bericht wordt weergegeven.

![](assets/faq_2.png)

### Kan ik tegelijkertijd productie- en sandboxcertificaten uploaden voor iOS App (N.v.t. Android)? {#prod-sandbox-certificate}

Nee, toepassingen werken in de sandbox- of productiemodus en kunnen niet worden gewijzigd in een andere sandbox (d.w.z. in de productie-app) nadat deze is ingesteld. We raden u aan uw toepassing eerst in de sandboxmodus te testen en vervolgens over te schakelen naar de productiemodus.

Als u wilt overschakelen naar de productiemodus, moet u een andere app maken. Controleer ook niet het selectievakje van de sandbox en upload een productiecertificaat.

### Kan ik zowel iOS- als Android-gebruikersgegevens tegelijk uploaden? {#ios-android-credentials}

Ja, de Campagne steunt beide platforms tezelfdertijd en staat u toe om geloofsbrieven voor beide platforms te uploaden.

### Ik heb pushcertificaten geüpload, maar er worden geen pushberichten verzonden. {#push-certificates-upload}

Controleer of uw pushcertificaten geldig zijn door ze te testen [hier](https://pushtry.com/).

### Ik kan pushmeldingen verzenden vanaf push.com, maar niet via Campagne. {#push-not-sending}

Zorg ervoor dat u de instructies voor pushlading volgt [hier](../../administration/using/push-payload.md).

Merk op dat voor Android de campagne alleen ondersteuning biedt voor gegevenslading en geen berichtlading.

### Ik heb een app geconfigureerd in de sectie Beheer van Adobe Campaign Standard, maar de Mobile App is niet beschikbaar in de leveringseigenschappen. {#mobile-app-unavailable}

Een app moet ook een geldig pushcertificaat hebben geüpload voordat het beschikbaar kan worden gesteld in de leveringseigenschappen.

### Ik heb alle instructies op deze pagina geprobeerd, maar ik kan Push niet vanuit Campaign verzenden. {#push-troubleshoot}

Open een ticket voor de klantenservice.

### Pushmeldingen worden geleverd via Campagne, maar het mediabestand wordt niet weergegeven.{#media-file-unavailable}

Mobiele App-ontwikkelaars moeten de ondersteuning voor mediabestanden in de app afhandelen. Soms voorkomt netwerkbandbreedte ook dat een mediabestand wordt gerenderd. Zie dit [page](../../administration/using/image-push-notification.md) voor extra aanwijzers.

### Wat moet ik doen om pushmeldingen in Campagne mogelijk te maken? {#push-reporting-enable}

Volg de onderstaande stappen:

* Configureer een postback voor het bijhouden van de push. Instructies zijn te vinden [hier](../../administration/using/configuring-a-mobile-application.md).
* TrackAction-API implementeren vanuit Mobile Core. Zie dit [page](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference) voor meer informatie .

Meer gedetailleerde instructies vindt u in deze [page](../../administration/using/push-tracking.md).

### Welke rapporten zijn beschikbaar voor het Push kanaal? {#push-report-available}

Er is een out-of-the-box-rapport beschikbaar in Adobe Campaign for Push channel. Zie dit [documentatie](../../reporting/using/push-notification-report.md).

Zie dit [page](../../reporting/using/indicator-calculation.md#push-notification-delivery) om te begrijpen hoe elke push-metriek wordt berekend.

### Worden verdiepingen ondersteund in pushberichten en in-app-berichten? {#deeplink-push}

Ja, deplinks worden ondersteund in pushberichten. Deeplinks moeten omvatten:

* Taal die verklaart dat levering het volgen moet worden onbruikbaar gemaakt om de diepte te werken.
* Appsflyer met Tak als partners die het zuiveren volgen kunnen doen. Voor meer informatie over de integratie van Branch en Adobe Campaign Standard raadpleegt u deze [page](https://help.branch.io/using-branch/docs/adobe-campaign-standard-1).
