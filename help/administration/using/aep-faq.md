---
title: Veelgestelde vragen over Adobe Experience Platform SDK en Adobe Campaign-integratie
description: Veelgestelde vragen over Adobe Experience Platform SDK en Adobe Campaign-integratie
page-status-flag: never-activated
uuid: 867b1c4b-4c79-4c52-9d0a-ef71993e50a2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuring-channels
discoiquuid: 406c955a-b2d2-4099-9918-95f5fa966067
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6c5cf90211451587537b9a6121430fc4f352384c
workflow-type: tm+mt
source-wordcount: '818'
ht-degree: 0%

---


# Aan de slag met Adobe Experience Platform SDK en Campaign Standard {#aep-faq}

Als u pushmeldingen en In-App-berichten wilt verzenden met de SDK-toepassing van het Experience Platform, moet een mobiele toepassing worden ingesteld in de SDK van het Adobe Experience Platform en worden geconfigureerd in Adobe Campaign.

In de onderstaande sectie worden veelgestelde vragen over deze synchronisatie weergegeven.

Raadpleeg de volgende veelgestelde vragen voor meer informatie over Push of In-app:

* [Veelgestelde vragen over pushmeldingen](../../channels/using/about-push-notifications.md#push-faq)
* [Veelgestelde vragen in de app](../../channels/using/about-push-notifications.md#in-app-faq)
* [Synchroniseren met veelgestelde vragen over technische workflow starten](../../administration/using/syncwithlaunch-faq.md)

## Nuttige bronnen voordat u begint {#resource-mobile-property}

Raadpleeg de onderstaande bronnen voor meer informatie over de integratie van Adobe Experience Platform SDK en Campaign Standard:

* Video [over het starten/mobiel overzicht](https://www.adobe.com/experience-platform/launch.html#acpl-mobile-video)
* Handleiding voor [tips en trucs voor starten/mobiel](https://www.adobe.com/content/dam/www/us/en/experience-platform/launch-tag-manager/pdfs/adobe-cloud-platform-launch-tips-and-tricks-sheet.pdf)

## Is de integratie van Adobe Experience Platform SDK beschikbaar voor zowel Adobe Campaign Standard als Adobe Campaign Classic? {#aep-validity}

Ja, [!DNL Adobe Experience Platform SDK] integratie is beschikbaar voor zowel Adobe Campaign Standard als Adobe Campaign Classic. U moet de corresponderende software installeren **[!UICONTROL Extension]** via [!DNL Adobe Launch] om de integratie in te schakelen.

Raadpleeg voor meer informatie deze [pagina](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaignclassic) voor Campaign Classic en deze [pagina](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard) voor Campaign Standard.

## Welke mogelijkheden biedt Adobe Experience Platform SDK-integratie in Adobe Campaign? {#aep-capabilities}

Raadpleeg de onderstaande tabel voor meer informatie over deze mogelijkheden.

![](assets/faq.png)

>[!Nofferte]
>
>[!DNL Places] integratie omvat plaatsgebeurtenissen als trekkers voor In-App berichten (n.v.t. Pushberichten), het verrijken van profielen met [!DNL Places] gegevens en lokale berichtsteun. Raadpleeg deze [pagina](../../channels/using/preparing-and-sending-an-in-app-message.md) voor meer informatie. <br>[!DNL Places] beperkte integratie omvat het verrijken van profielen met [!DNL Places] gegevens.

## Wat handig is de integratie van Adobe Experience Platform SDK in Adobe Campaign Standard? {#aep-use-cases}

De volgende gebruiksgevallen worden ondersteund:

* Een bestand ophalen **[!UICONTROL Mobile Profile]** in campagne (aangeduid met ECID in **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]** > **[!UICONTROL Mobile Application subscribers]** tabblad)
* Verrijken een **[!UICONTROL Mobile Profile]** bestand in Adobe Campaign (vereist **[!UICONTROL Custom resource Extension]** de tabel appSubscriberRcp)
* Een pushtoken ophalen voor het verzenden van pushberichten (vereist dat de gebruiker zich aanmeldt om pushberichten te ontvangen)
* Push- en In-App-berichten verzenden
* Houd de interactie van de gebruiker met de Berichten van de Duw en van de In-App en verstrek rapporten over dat

## Wat moet ik doen om een mobiel profiel in Campagne te verwerven? {#mobile-profile-campaign}

Hiervoor voert u de volgende stappen uit:

1. Configureer een **[!UICONTROL Mobile property]** binnen [!DNL Launch].
1. Installeer Adobe Campaign Standard-extensie. Voor Adobe Campaign Standard-extensies zijn ook extensies vereist **[!UICONTROL Mobile Core]****[!UICONTROL Profile]** en **[!UICONTROL Lifecycle]** extensies die standaard zijn geïnstalleerd in [!DNL Launch].
   * Gebruikers dienen een sessietime-out in **[!UICONTROL Mobile Core]** extensie te configureren die invloed heeft op de frequentie van levenscyclusgebeurtenissen.
   * Nadat de extensie is geconfigureerd, moeten gebruikers de juiste afhankelijkheden toevoegen in de mobiele app met Cocoapods voor iOS en Gradle for Android. Volg de aanwijzingen [hier](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard).
   * Neem altijd de nieuwste versies van de bibliotheken.
   * Registreer **[!UICONTROL Campaign]**, registreer **[!UICONTROL UserProfile]**, **[!UICONTROL Identity]**, **[!UICONTROL Lifecycle]** en **[!UICONTROL Signal]** extensies in de mobiele toepassing. Volg de aanwijzingen [hier](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard#register-the-campaign-standard-extension-with-mobile-core).
   * Start ACPCore wanneer extensies zijn geregistreerd. Voor Android moet u setApplication onCreate() gebruiken. Volg de exacte instructies in de instructies bij Mobiele installatie voor uw mobiele eigenschap in Launch.
   * De volgende SDK API&#39;s zijn ook vereist. Implementeer de API&#39;s voor het starten en pauzeren van de levenscyclus zoals [hier](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/lifecycle/lifecycle-extension-in-android) voor Android en hier voor iOS wordt beschreven.
1. Configureer een **[!UICONTROL Mobile Property]** bestand in Adobe Campaign Standard. Volg de procedure [hier](../../administration/using/configuring-a-mobile-application.md#channel-specific-config).

## Wat moet ik doen om een mobiel profiel in Campagne te verrijken? {#enrich-mobile-profile}

U moet een CollectPII postback (verwijs naar deze [pagina](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#PIIpostback)) vormen en CollectPII API van SDK uitvoeren (verwijs naar deze [pagina](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#collect-pii)).

## Hoe vaak zou een vraag moeten worden in brand gestoken CollectPII? {#collect-pii}

Het doel van de vraag CollectPII is het Mobiele Profiel in Campagne te verrijken. Het zou moeten in brand worden gestoken wanneer er nieuwe betekenisvolle informatie is die de klanten aan het profiel afhankelijk van hun gebruiksgevallen en bedrijfsbehoeften willen toevoegen.

## Kan vraag CollectPII in antwoord op veelvoudige triggergebeurtenissen worden in brand gestoken? {#collect-pii-calls}

Ja. Afhankelijk van uw bedrijfsbehoefte, kunt u vraag van CollectPII in werking stellen in antwoord op het programma openen van de gebruiker app, of het kopen van iets of levenscyclusgebeurtenis of gebruiker die een geofence etc. ingaat. Samenvattend, een interactie van gebruiker met app die informatie produceert u voor de verrijking van het Profiel zou willen gebruiken.

## Kan ik de vraag van CollectPII in antwoord op alle Mobiele gebeurtenissen enkel in brand steken? {#collect-pii-events}

De frequentie en het ontwerp van vraag CollectPII zouden door bedrijfsbehoeften moeten worden gedicteerd en zouden niet blindelings moeten worden in brand gestoken aangezien het extra lading op OB creeert.

### Wanneer ik Adobe Experience Platform probeert tot Apps in Campaign of Lancering toegang te hebben, krijg ik soms een bezit niet beschikbare fout. {#aep-error}

Dit is een bekend probleem dat optreedt als een token vervalt. Meld u af en weer aan.

## Wat zouden sommige nuttige middelaanbevelingen zijn om meer over Adobe Experience Platform SDK (vroeger genoemd geworden SDK V5) te leren?{#resource-aep}

Ontdek de onderstaande bronnen:

* Experience Platform SDK- [documentatie](https://aep-sdks.gitbook.io/docs/)
* Aan de slag met de [documentatie van de SDK van Starten en Experience Platforms](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property)
* Bijwerken naar SDK- [documentatie voor Experience Platform](https://aep-sdks.gitbook.io/docs/resources/upgrading-to-aep)
* Github Experience Platform SDK- [documentatie](https://github.com/Adobe-Marketing-Cloud/acp-sdks/)
