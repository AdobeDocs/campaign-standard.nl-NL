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
source-git-commit: 8111dfd2fd3cf254f73d0b01917d606b0a70aa84

---


# Pushmeldingen{#about-push-notifications}

>[!CAUTION]
>
>De implementatie van pushberichten moet worden uitgevoerd door deskundige gebruikers. Neem contact op met de manager of de Professional-servicepartner van Adobe-accounts als u hulp nodig hebt. Een pushmelding is een optionele functie. Controleer uw licentieovereenkomst en neem contact op met uw accountmanager om deze te activeren.

Met Adobe Campaign kunt u persoonlijke en gesegmenteerde pushmeldingen verzenden naar mobiele apparaten met iOS en Android.

Deze berichten worden ontvangen op mobiele toepassingen die u instelt in Adobe Campagne door gebruik te maken van de Experience Platform SDK. Zie Een mobiele toepassing [configureren met SDK&#39;s van het Adobe Experience Platform voor meer informatie hierover](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html).

In Adobe Campaign worden data van mobiele profielkenmerken die vanaf een mobiel apparaat worden verzonden, opgeslagen in de resource **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** waardoor u de data die u van de abonnees van uw applicaties wilt verzamelen, kunt definiëren.

Deze bron moet worden uitgebreid om gegevens te verzamelen die u van het mobiele apparaat naar de Adobe-campagne wilt verzenden. Raadpleeg hiervoor deze [pagina](../../developing/using/extending-the-subscriptions-to-an-application-resource.md) voor de gedetailleerde stappen.

Er zijn twee typen pushmeldingen beschikbaar in Adobe Campagne:

* **[!UICONTROL Alert/Message/Badge]** Met typedeclaraties kunt u standaardtekstberichten verzenden met extra inhoud (geluid, badge, deplink, enz.) die u in de **[!UICONTROL Advanced options]** sectie kunt definiëren.

   Met deze berichttypen kunt u een titel en een bericht toevoegen waarin u verpersoonlijkingsvelden kunt gebruiken. Als u uw bericht wilt aanpassen, selecteert u de **[!UICONTROL Send push on profiles]** sjabloon.

* **[!UICONTROL Silent push]** typedeclaraties worden gebruikt om de toepassing zonder bericht of inhoud op de hoogte te brengen voor de eindgebruiker. Een typisch geval van gebruik voor dit type van bericht zou zijn om de toepassing zich ervan bewust te maken dat er inhoud op de server beschikbaar is om te downloaden.

Sommige specifieke configuraties kunnen worden ingesteld om het gedrag van meldingen te definiëren. For more on this, refer to [this section](../../channels/using/customizing-a-push-notification.md).

Als deskundige gebruiker, om deze specifieke configuraties te bepalen, verwijs naar de mobiele [toepassingstechnologieën](https://helpx.adobe.com/campaign/kb/acs-article-list.html).

>[!NOTE]
>
>De wetgeving inzake privacy verschilt per land. Sommige landen schrijven voor dat u gebruikers informeert over de typen gegevens die door mobiele toepassingen worden verzameld. Controleer de wetten met betrekking tot mobiele toepassingen in uw land. Zorg ervoor dat pushberichten die naar mobiele toepassingen worden verzonden, voldoen aan de voorwaarden en vereisten die door Apple (Apple Push Notification Service) en Google (Google Cloud Messaging of Firebase Cloud Messaging) zijn opgegeven.

**Gerelateerde inhoud:**

* [Een pushmelding voorbereiden en verzenden](../../channels/using/preparing-and-sending-a-push-notification.md)
* [Meertalige pushmeldingen maken](../../channels/using/creating-a-multilingual-push-notification.md)
* [Pushmeldingsrapport](../../reporting/using/push-notification-report.md)
* [Gids Standaard voor mobiele campagne](https://helpx.adobe.com/campaign/kb/acs-mobile.html)

## Vereisten {#prerequisites}

>[!NOTE]
>Als u de functie voor pushmeldingen van Campagne wilt gebruiken, moet u een geldig pushcertificaat in .pem-indeling opgeven zonder wachtwoorden.
Als u een geldig p12-certificaat hebt, kunt u het gemakkelijk converteren naar een .pem-bestand met onlinebronnen.

Voordat u pushmeldingen verzendt, moet u:

1. Zorg ervoor dat u in Adobe Campaign toegang hebt tot het **[!UICONTROL Push notification]** kanaal. Neem contact op met uw accountteam als u deze kanalen niet kunt openen.

1. Controleer of uw gebruiker beschikt over de vereiste machtigingen in Adobe Campagne Standard en Experience Platform Launch.

1. Maak een mobiele eigenschap in Experience Platform Launch. Zie Een mobiele eigenschap [](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property)instellen voor meer informatie.

1. Installeer de **[!UICONTROL Adobe Campaign Standard]** extensie in Experience Platform Launch.

1. In de Standaard van de Campagne van Adobe, vorm het mobiele bezit dat u in de Lancering van het Platform van de Ervaring creeerde. Zie Uw toepassing voor het starten van het Experience Platform [instellen in Adobe Campaign](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#SettingupyourAdobeExperiencePlatformLaunchapplicationinAdobeCampaign)voor meer informatie.

1. Voeg de kanaalspecifieke configuratie toe aan uw mobiele toepassingsopstelling. Zie [Kanaalspecifieke toepassingsconfiguratie in Adobe Campagne](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#ChannelspecificapplicationconfigurationinAdobeCampaign)voor meer informatie.

1. Voor ondersteuning van implementaties van gevallen voor mobiel gebruik raadpleegt u de gedetailleerde instructies over extensies, Experience Platform Launch-regels en de SDK-implementatie in gevallen van [mobiel gebruik die worden ondersteund in Adobe Campaign Standard met behulp van de SDK&#39;s](https://helpx.adobe.com/campaign/kb/configure-launch-rules-acs-use-cases.html)van het Adobe Experience Platform.