---
title: Pushmeldingen
description: Ontdek de belangrijkste specifieke kenmerken van het pushmeldkanaal in Adobe Campaign.
page-status-flag: never-activated
uuid: 961aaeb5-6948-4fd2-b8d7-de4510c10566
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: push-notifications
discoiquuid: 23b4212e-e878-4922-be20-50fb7fa88ae8
context-tags: mobileApp,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f9632e88b49c2280c76e709376cfb7a7a27abc1f
workflow-type: tm+mt
source-wordcount: '1280'
ht-degree: 3%

---


# Pushmeldingen{#about-push-notifications}

>[!CAUTION]
>
>De implementatie van pushberichten moet worden uitgevoerd door deskundige gebruikers. Neem contact op met de manager of de Professional-servicepartner van Adobe-accounts als u hulp nodig hebt. Een pushmelding is een optionele functie. Controleer uw licentieovereenkomst en neem contact op met uw accountmanager om deze te activeren.

Met Adobe Campaign kunt u persoonlijke en gesegmenteerde pushmeldingen verzenden naar mobiele apparaten met iOS en Android.

Deze berichten worden ontvangen op mobiele toepassingen die u in Adobe Campaign instelt door de SDK van het Experience Platform te gebruiken. Zie Een mobiele toepassing [configureren met SDK&#39;s van Adobe Experience Platforms voor meer informatie hierover](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html).

In Adobe Campaign worden data van mobiele profielkenmerken die vanaf een mobiel apparaat worden verzonden, opgeslagen in de resource **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** waardoor u de data die u van de abonnees van uw applicaties wilt verzamelen, kunt definiëren.

Deze bron moet worden uitgebreid om gegevens te verzamelen die u van het mobiele apparaat naar Adobe Campaign wilt verzenden. Raadpleeg hiervoor deze [pagina](../../developing/using/extending-the-subscriptions-to-an-application-resource.md) voor de gedetailleerde stappen.

Er zijn twee typen pushberichten beschikbaar in Adobe Campaign:

* **[!UICONTROL Alert/Message/Badge]** Met typedeclaraties kunt u standaardtekstberichten verzenden met extra inhoud (geluid, badge, deplink, enz.) die u in de **[!UICONTROL Advanced options]** sectie kunt definiëren.

   Met deze berichttypen kunt u een titel en een bericht toevoegen waarin u verpersoonlijkingsvelden kunt gebruiken. Als u uw bericht wilt aanpassen, selecteert u de **[!UICONTROL Send push on profiles]** sjabloon.

* **[!UICONTROL Silent push]** typedeclaraties worden gebruikt om de toepassing zonder bericht of inhoud op de hoogte te brengen voor de eindgebruiker. Een typisch geval van gebruik voor dit type van bericht zou zijn om de toepassing zich ervan bewust te maken dat er inhoud op de server beschikbaar is om te downloaden.

Sommige specifieke configuraties kunnen worden ingesteld om het gedrag van meldingen te definiëren. Raadpleeg [deze sectie](../../channels/using/customizing-a-push-notification.md) voor meer informatie.

Als deskundige gebruiker, om deze specifieke configuraties te bepalen, verwijs naar de mobiele [toepassingstechnologieën](https://helpx.adobe.com/campaign/kb/acs-article-list.html).

>[!NOTE]
>
>De wetgeving inzake privacy verschilt per land. Sommige landen schrijven voor dat u gebruikers informeert over de typen gegevens die door mobiele toepassingen worden verzameld. Controleer de wetten met betrekking tot mobiele toepassingen in uw land. Zorg ervoor dat pushberichten die naar mobiele toepassingen worden verzonden, voldoen aan de voorwaarden en vereisten die door Apple (Apple Push Notification Service) en Google (Google Cloud Messaging of Firebase Cloud Messaging) zijn opgegeven.

**Gerelateerde inhoud:**

* [Een pushmelding voorbereiden en verzenden](../../channels/using/preparing-and-sending-a-push-notification.md)
* [Meertalige pushmeldingen maken](../../channels/using/creating-a-multilingual-push-notification.md)
* [Pushmeldingsrapport](../../reporting/using/push-notification-report.md)
* [Campaign Standard Mobile-gids](https://helpx.adobe.com/campaign/kb/acs-mobile.html)

## Vereisten {#prerequisites}

>[!NOTE]
>Als u de functie voor pushmeldingen van Campagne wilt gebruiken, moet u een geldig pushcertificaat in .pem-indeling opgeven zonder wachtwoorden.
Als u een geldig p12-certificaat hebt, kunt u het gemakkelijk converteren naar een .pem-bestand met onlinebronnen.

Voordat u pushmeldingen verzendt, moet u:

1. Zorg ervoor dat u in Adobe Campaign toegang hebt tot het **[!UICONTROL Push notification]** kanaal. Neem contact op met uw accountteam als u deze kanalen niet kunt openen.

1. Controleer of de gebruiker beschikt over de benodigde rechten in Adobe Campaign Standard en Experience Platform Launch.

1. Maak in Experience Platform Launch een eigenschap mobile. Zie Een mobiele eigenschap [](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property)instellen voor meer informatie.

1. Installeer de **[!UICONTROL Adobe Campaign Standard]** extensie in Experience Platform Launch.

1. Configureer in Adobe Campaign Standard de eigenschap mobile die u in Experience Platform Launch hebt gemaakt. Zie Uw Experience Platform Launch-toepassing [instellen in Adobe Campaign](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#SettingupyourAdobeExperiencePlatformLaunchapplicationinAdobeCampaign)voor meer informatie.

1. Voeg de kanaalspecifieke configuratie toe aan uw mobiele toepassingsopstelling. Zie [Kanaalspecifieke toepassingsconfiguratie in Adobe Campaign](../../administration/using/configuring-a-mobile-application.md#channel-specific-config)voor meer informatie.

1. Raadpleeg de gedetailleerde instructies over extensies, Experience Platform Launch-regels en de SDK-implementatie in gevallen van [mobiel gebruik die in Adobe Campaign Standard worden ondersteund met behulp van de SDK&#39;s van het Adobe Experience Platform voor ondersteuning van implementaties van case-uitvoeringen voor mobiele apparaten](https://helpx.adobe.com/campaign/kb/configure-launch-rules-acs-use-cases.html).

## Veelgestelde vragen over pushmeldingen {#push-faq}

### Wat zouden sommige nuttige middelaanbevelingen zijn om meer over het kanaal van de Duw te leren? {#resource-push}

Ontdek de onderstaande bronnen:

* [Videozelfstudies](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/communication-channels/mobile/push/creating-a-push-notification.html)
* [Productdocumentatie](../../channels/using/about-push-notifications.md)
* Configureren met AEP SDK- [documentatie](../../administration/using/configuring-a-mobile-application.md)
* [Community-pagina](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-standard/ct-p/adobe-campaign-standard-community)

### Wat moet ik doen om een pushtoken te verkrijgen in Campaign? {#push-token-acquisition}

Controleer of het inrichtingsteam de levering van het Push-kanaal in Adobe Campaign Standard heeft voltooid. SetPushIdentifier-API van SDK implementeren. For more on this, refer to this [page](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard#set-up-push-messaging).

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

### Kan ik tegelijkertijd zowel iOS- als Android-referenties uploaden? {#ios-android-credentials}

Ja, de Campagne steunt beide platforms tezelfdertijd en staat u toe om geloofsbrieven voor beide platforms te uploaden.

### Ik heb pushcertificaten geüpload, maar er worden geen pushberichten verzonden. {#push-certificates-upload}

Controleer of uw pushcertificaten geldig zijn door ze [hier](https://pushtry.com/)te testen.

### Ik kan pushmeldingen verzenden vanaf push.com, maar niet via Campagne. {#push-not-sending}

Zorg ervoor dat u de instructies voor pushlading volgt die [hier](../../administration/using/push-payload.md)worden gegeven.

Merk op dat voor Android de campagne alleen ondersteuning biedt voor gegevenslading en geen berichtlading.

### Ik heb een app geconfigureerd in de sectie Beheer van Adobe Campaign Standard, maar de Mobile App is niet beschikbaar in de leveringseigenschappen. {#mobile-app-unavailable}

Een app moet ook een geldig pushcertificaat hebben geüpload voordat het beschikbaar kan worden gesteld in de leveringseigenschappen.

### Ik heb alle instructies op deze pagina geprobeerd, maar ik kan Push niet vanuit Campaign verzenden. {#push-troubleshoot}

Open een ticket voor de klantenservice.

### Pushmeldingen worden geleverd via Campagne, maar het mediabestand wordt niet weergegeven.{#media-file-unavailable}

Mobiele App-ontwikkelaars moeten de ondersteuning voor mediabestanden in de app afhandelen. Soms voorkomt netwerkbandbreedte ook dat een mediabestand wordt gerenderd. Zie deze [pagina](../../administration/using/image-push-notification.md) voor extra aanwijzers.

### Wat moet ik doen om pushmeldingen in Campagne mogelijk te maken? {#push-reporting-enable}

Voer de onderstaande stappen uit:

* Configureer een postback voor het bijhouden van de push. Instructies vindt u [hier](../../administration/using/configuring-a-mobile-application.md).
* TrackAction-API implementeren vanuit Mobile Core. Raadpleeg deze [pagina](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference) voor meer informatie.

Meer gedetailleerde instructies vindt u op deze [pagina](../../administration/using/push-tracking.md).

### Welke rapporten zijn beschikbaar voor het Push kanaal? {#push-report-available}

Er is een out-of-the-box-rapport beschikbaar in Adobe Campaign for Push channel. Raadpleeg deze [documentatie](../../reporting/using/push-notification-report.md).

Zie deze [pagina](../../reporting/using/indicator-calculation.md#push-notification-delivery) voor informatie over de berekening van de maateenheden voor pushmeldingen.

### Worden verdiepingen ondersteund in pushberichten en in-app-berichten? {#deeplink-push}

Ja, deplinks worden ondersteund in pushberichten. Deeplinks moeten omvatten:

* de taal die verklaart dat levering het volgen moet worden onbruikbaar gemaakt om de diepte te werken.
* Appsflyer met Tak als partners die het zuiveren volgen kunnen doen. Raadpleeg deze [pagina](https://help.branch.io/using-branch/docs/adobe-campaign-standard-1)voor meer informatie over de integratie met Branch en Adobe Campaign Standard.