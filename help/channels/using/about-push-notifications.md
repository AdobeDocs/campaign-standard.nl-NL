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
source-git-commit: 5ed46987a3778dfa100639de8be9b6d5ac5348b4

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

Ten eerste moet u uw mobiele toepassing configureren met behulp van Experience Platform SDK&#39;s om pushmeldingen te kunnen verzenden. Raadpleeg deze [pagina](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html)voor meer informatie.

Voordat u pushmeldingen verzendt, moet u:

1. Zorg ervoor dat u toegang hebt tot het **[!UICONTROL Mobile app]** kanaal in Adobe Campaign.
1. Uw mobiele toepassing configureren in:

   * Adobe-campagne
   * De interface van Adobe Mobile Services

1. Voer de specifieke installatie van de mobiele toepassing uit:

   * Verpak het configuratiebestand dat u hebt gedownload van de Adobe Mobile Services-interface met de mobiele toepassing.
   * Integreer de Experience Cloud Mobile SDK in uw mobiele toepassing.

1. Definieer de gegevens die u van de abonnees van uw toepassing wilt verzamelen. De abonnees van de mobiele toepassing die een profiel in de Adobe Campagne-database hebben, worden op basis van de criteria die u hebt gedefinieerd met elkaar in overeenstemming gebracht.

Nadat u de mobiele toepassing hebt geconfigureerd, kunt u nu uw In-app-berichten voorbereiden en verzenden. Zie Een pushmelding [voorbereiden en verzenden voor meer informatie](../../channels/using/preparing-and-sending-a-push-notification.md).
