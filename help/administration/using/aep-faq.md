---
title: Veelgestelde vragen over Adobe Experience Platform SDK en Adobe Campaign-integratie
description: Veelgestelde vragen over Adobe Experience Platform SDK en Adobe Campaign-integratie
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 6b3c189d-8ddd-4dc0-8831-65ae62e04c70
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '914'
ht-degree: 4%

---

# Veelgestelde vragen over de integratie van Experience Platform SDK {#aep-faq}

Als u pushmeldingen en In-App-berichten wilt verzenden met de SDK-toepassing van het Experience Platform, moet een mobiele toepassing worden ingesteld in de SDK van Adobe Experience Platform en worden geconfigureerd in Adobe Campaign.

In de onderstaande sectie worden veelgestelde vragen over deze synchronisatie weergegeven.

Raadpleeg de volgende veelgestelde vragen voor meer informatie over Push of In-App:

* [Veelgestelde vragen over pushmeldingen](../../channels/using/about-push-notifications.md#push-faq)
* [Veelgestelde vragen In-App](../../channels/using/in-app-faq.md)
* [Synchroniseren met veelgestelde vragen over technische workflow starten](../../administration/using/syncwithlaunch-faq.md)

## Nuttige bronnen voordat u begint {#resource-mobile-property}

Raadpleeg de onderstaande bronnen voor meer informatie over de Adobe Experience Platform SDK en de integratie van Campaign Standard:

* Starten/Mobiel [Overzicht Video](https://www.adobe.com/experience-platform/launch.html#acpl-mobile-video)
* Starten/Mobiele [Handleiding voor tips en trucs](https://www.adobe.com/content/dam/www/us/en/experience-platform/launch-tag-manager/pdfs/adobe-cloud-platform-launch-tips-and-tricks-sheet.pdf)

## Is de integratie van Adobe Experience Platform SDK beschikbaar voor zowel Adobe Campaign Standard als Adobe Campaign Classic? {#aep-validity}

Ja, integratie [!DNL Adobe Experience Platform SDK] is beschikbaar voor zowel Adobe Campaign Standard als Adobe Campaign Classic. U moet de corresponderende **[!UICONTROL Extension]** via [!DNL Adobe Launch] installeren om de integratie in te schakelen.

Raadpleeg [deze pagina](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard) voor meer informatie.

## Welke mogelijkheden biedt Adobe Experience Platform SDK-integratie in Adobe Campaign? {#aep-capabilities}

Raadpleeg de onderstaande tabel voor meer informatie over deze mogelijkheden.

![](assets/faq.png)

>[!NOTE]
>
>[!DNL Places] integratie omvat plaatsgebeurtenissen als trekkers voor In-App berichten (n.v.t. Pushberichten), het verrijken van profielen met  [!DNL Places] gegevens en lokale berichtsteun. Raadpleeg deze [pagina](../../channels/using/preparing-and-sending-an-in-app-message.md) voor meer informatie. <br>[!DNL Places] beperkte integratie omvat het verrijken van profielen met  [!DNL Places] gegevens.

## Wat is het nut van de integratie van Adobe Experience Platform SDK in Adobe Campaign Standard? {#aep-use-cases}

De volgende gebruiksgevallen worden ondersteund:

* Een **[!UICONTROL Mobile Profile]** ophalen in campagne (aangeduid met ECID in **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]** > **[!UICONTROL Mobile Application subscribers]** tab)
* Verrijk een **[!UICONTROL Mobile Profile]** in Adobe Campaign (vereist **[!UICONTROL Custom resource Extension]** van appSubscriberRcp-tabel)
* Een pushtoken ophalen voor het verzenden van pushberichten (vereist dat de gebruiker zich aanmeldt om pushberichten te ontvangen)
* Push- en In-App-berichten verzenden
* Houd de interactie van de gebruiker met de Berichten van de Duw en van de In-App en verstrek rapporten over dat

## Wat moet ik doen om een mobiel profiel in Campagne te verwerven? {#mobile-profile-campaign}

Hiervoor voert u de volgende stappen uit:

1. Configureer een **[!UICONTROL Mobile property]** in [!DNL Launch].
1. Installeer Adobe Campaign Standard-extensie. Voor Adobe Campaign Standard-extensies **[!UICONTROL Mobile Core]**, **[!UICONTROL Profile]** en **[!UICONTROL Lifecycle]** zijn ook extensies nodig die standaard worden geïnstalleerd in [!DNL Launch].
   * Gebruikers dienen een sessietime-out in de extensie **[!UICONTROL Mobile Core]** te configureren die invloed heeft op de frequentie van levenscyclusgebeurtenissen.
   * Nadat de extensie is geconfigureerd, moeten gebruikers de juiste afhankelijkheden toevoegen in de mobiele app met Cocoapods voor iOS en Gradle for Android. Volg de aanwijzingen [hier](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard).
   * Neem altijd de nieuwste versies van de bibliotheken.
   * Registreer **[!UICONTROL Campaign]**, **[!UICONTROL UserProfile]**, **[!UICONTROL Identity]**, **[!UICONTROL Lifecycle]** en **[!UICONTROL Signal]** extensies. Volg de aanwijzingen [hier](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard#register-the-campaign-standard-extension-with-mobile-core).
   * Start ACPCore wanneer extensies zijn geregistreerd. Voor Android moet u setApplication onCreate() gebruiken. Volg de exacte instructies in de instructies bij Mobiele installatie voor uw mobiele eigenschap in Launch.
   * De volgende SDK API&#39;s zijn ook vereist. Implementeer de begin- en pauze-API&#39;s van de levenscyclus zoals beschreven [hier](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/lifecycle/lifecycle-extension-in-android) voor Android en hier voor iOS.
1. Configureer een **[!UICONTROL Mobile Property]** in Adobe Campaign Standard. Volg de procedure [hier](../../administration/using/configuring-a-mobile-application.md#channel-specific-config).

## Wat moet ik doen om een mobiel profiel in Campagne te verrijken? {#enrich-mobile-profile}

U moet een CollectPII postback (verwijs naar deze [pagina](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#PIIpostback)) vormen en CollectPII API van SDK uitvoeren (verwijs naar deze [pagina](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#collect-pii)).

## Hoe vaak zou een vraag moeten worden in brand gestoken CollectPII? {#collect-pii}

Het doel van de vraag CollectPII is het Mobiele Profiel in Campagne te verrijken. Het zou moeten in brand worden gestoken wanneer er nieuwe betekenisvolle informatie is die de klanten aan het profiel afhankelijk van hun gebruiksgevallen en bedrijfsbehoeften willen toevoegen.

## Kan vraag CollectPII in antwoord op veelvoudige triggergebeurtenissen worden in brand gestoken? {#collect-pii-calls}

Ja. Afhankelijk van uw bedrijfsbehoefte, kunt u vraag van CollectPII in werking stellen in antwoord op het programma openen van de gebruiker app, of het kopen van iets of levenscyclusgebeurtenis of gebruiker die een geofence etc. ingaat. Samenvattend, een interactie van gebruiker met app die informatie produceert u voor de verrijking van het Profiel zou willen gebruiken.

## Kan ik de vraag van CollectPII in antwoord op alle Mobiele gebeurtenissen enkel in brand steken? {#collect-pii-events}

De frequentie en het ontwerp van vraag CollectPII zouden door bedrijfsbehoeften moeten worden gedicteerd en zouden niet blindelings moeten worden in brand gestoken aangezien het extra lading op OB creeert.

### Wanneer ik toegang probeer te krijgen tot Adobe Experience Platform Apps in Campaign of Launch, krijg ik soms een eigenschap die niet beschikbaar is. {#aep-error}

Dit is een bekend probleem en gebeurt als het token vervalt. Meld u af en weer aan.

## Wat zouden enkele nuttige middelaanbevelingen zijn om meer over Adobe Experience Platform SDK (vroeger genoemd geworden SDK V5) te leren?{#resource-aep}

Ontdek de onderstaande bronnen:

* Experience Platform SDK [documentatie](https://aep-sdks.gitbook.io/docs/)
* Aan de slag met Starten en Experience Platform SDK [documentatie](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property)
* Bijwerken naar SDK van Experience Platform [documentatie](https://aep-sdks.gitbook.io/docs/resources/upgrading-to-aep)
* Github Experience Platform SDK [documentatie](https://github.com/Adobe-Marketing-Cloud/acp-sdks/)

## Ik krijg fout &quot;u hebt geen schrijftoegang bij levering&quot;terwijl het creëren van een levering van het dupbericht. {#write-access-error}

Controleer het volgende:

* De mobiele app moet worden toegewezen aan de organisatie-eenheid van de gebruiker die push-items moet maken en verzenden. De gebruiker van een onderliggende organisatie kan geen push-levering maken met een app die is toegewezen aan de bovenliggende organisatie-eenheid.

* De campagne of het programma waarin de levering van de duw wordt gecreeerd zouden aan de organisatorische eenheid van de gebruiker moeten worden in kaart gebracht die tot dupleveringen moet leiden en verzenden. Gebruiker van de onderliggende organisatie kan geen pushlevering maken in een campagne of programma dat is toegewezen aan de bovenliggende organisatie-eenheid.
