---
title: Integratie van Campagne-Punten van interessegegevens configureren
description: Leer hoe u de functie Punten met interessegegevens in Adobe Campaign configureert om persoonlijke berichten te verzenden op basis van de locatie van uw abonnees.
page-status-flag: never-activated
uuid: 0689a06c-cc1a-442f-95b8-a07fcec85d79
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics-for-mobile
discoiquuid: a967c6cc-c53b-41b4-866b-90860d78f463
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: fc9c6371732aa0eba9e675d2709cd62c25b27b96

---


# Integratie van Campagne-Punten van interessegegevens configureren{#configuring-campaign-points-of-interest-data-integration}

## Integratie van interessepunten voor campagnes configureren met SDK&#39;s van het Adobe Experience Platform {#configuring-campaign-poi-aep-sdk}

>[!NOTE]
>
>Uw mobiele toepassing moet al in Adobe Campaign Standard zijn geconfigureerd met de Adobe Experience Platform SDK. Raadpleeg deze [pagina](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html)voor de gedetailleerde stappen.

De mobiele toepassingen die worden gebruikt om locatiegegevens te verzamelen, moeten door een **beheerder** in de interface van de Campagne van Adobe worden gevormd.

Als u Adobe Experience Platform Location Services wilt gebruiken voor mobiele toepassingen die zijn geconfigureerd met Adobe Experience Platform SDK, moet u:

1. Voeg de **[!UICONTROL Places]** extensies en **[!UICONTROL Places Monitor]** extensies toe aan de configuratie van uw mobiele app in Adobe Experience Platform Launch. Stel uw mobiele toepassing in Adobe Campaign in. Zie De extensie Plaatsen [installeren in Adobe Experience Platform Launch](https://docs.adobe.com/content/help/en/places/using/places-ext-aep-sdks/places-extension/places-extension.html#install-the-places-extension-in-adobe-experience-platform-launch) en de extensie Places Monitor [installeren in Experience Platform Launch](https://docs.adobe.com/content/help/en/places/using/places-ext-aep-sdks/places-monitor-extension/using-places-monitor-extension.html#install-the-places-monitor-extension-in-experience-platform-launch).

1. Als uw extensies zijn ingesteld, maakt u gegevenselementen binnen **[!UICONTROL Adobe Experience Platform Launch]** om gegevens van deze extensies op te halen. Raadpleeg deze [pagina](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Step1Createdataelements) om uw gegevenselementen te maken.

1. Vervolgens moet u in **[!UICONTROL Adobe Experience Platform Launch]** de toepassing zelf regels maken voor de ondersteuning van gevallen van mobiel gebruik tussen Point of Interesses en Adobe Campaign.\
   Deze regel wordt geactiveerd wanneer een gebruiker een afgezonderd bestand ingaat **[!UICONTROL Point of Interest]**. Verwijs naar deze [pagina](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Locationpostback) om uw regel tot stand te brengen.

1. Definieer uw **[!UICONTROL Points of Interest]** voorinstellingen. Zie Een [punt van interesse](https://docs.adobe.com/content/help/en/places/using/poi-mgmt-ui/create-a-poi-ui.html)maken.

1. Zorg ervoor dat u toegang hebt tot de mobiele toepassing en de verzamelde locatiegegevens in Adobe Campaign. Zie [Toegang krijgen tot mobiele apps die worden gebruikt om locatiegegevens](#accessing-mobile-apps-used-to-collect-location-data) te verzamelen en [toegang te krijgen tot verzamelde locatiegegevens](#accessing-collected-location-data).

## Campagne-Punten van de gegevensintegratie van de Rente vormen gebruikend SDK V4 {#configuring-campaign-poi-sdkv4}

De mobiele toepassingen die worden gebruikt om locatiegegevens te verzamelen, moeten door een **beheerder** in de interface van de Campagne van Adobe worden gevormd.

Om de de gegevenseigenschap van het Punt van Interesse met mobiele toepassingen te gebruiken die met SDK V4 worden gevormd, moet u:

1. Toegang tot Adobe Analytics voor Mobile. Controleer uw licentieovereenkomst of neem contact op met de manager van uw Adobe-account voor meer informatie.
1. Stel uw mobiele toepassing in Adobe Campaign in. Zie Een mobiele app [instellen in Campagne](#setting-up-a-mobile-app-in-campaign).
1. Stel uw mobiele toepassing in de interface van Adobe Mobile Services in. Op deze manier kunt u ervoor zorgen dat de gegevens die door Adobe Mobile Services zijn verzameld, naar Adobe Campagne worden verzonden. Zie Een mobiele app [configureren in Adobe Mobile Services](#configuring-a-mobile-app-in-adobe-mobile-services).
1. Voer de specifieke installatie van de mobiele toepassing uit:

   * Verpak het configuratiebestand dat u hebt gedownload van de Adobe Mobile Services-interface met de mobiele toepassing.
   * Integreer de Experience Cloud Mobile SDK in uw mobiele toepassing. Zie De SDK [integreren in een mobiele toepassing](#integrating-the-sdk-into-a-mobile-application).

1. Definieer de interessepunten in de interface van Adobe Mobile Services. Zie [Belangenpunten definiëren in Adobe Mobile Services](#defining-points-of-interest-in-adobe-mobile-services).
1. Definieer de gegevens die u wilt verzamelen van de abonnees van uw mobiele toepassing. Zie [Gegevens](#collecting-subscribers--points-of-interest-data)van abonnees verzamelen.
1. Zorg ervoor dat u toegang hebt tot de mobiele toepassing en de verzamelde locatiegegevens in Adobe Campaign. Zie [Toegang krijgen tot mobiele apps die worden gebruikt om locatiegegevens](#accessing-mobile-apps-used-to-collect-location-data) te verzamelen en [toegang te krijgen tot verzamelde locatiegegevens](#accessing-collected-location-data).

### Een mobiele app instellen in Adobe Campagne met SDK V4 {#setting-up-a-mobile-app-in-campaign}

Als u gegevens van aandachtspunten wilt verzamelen met Adobe Campaign, moet u de mobiele toepassing configureren waarvan Adobe Campagne gegevens ontvangt.

1. Klik in de linkerbovenhoek op het **[!UICONTROL Adobe Campaign]** logo en selecteer **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app]**.
1. Klik **[!UICONTROL Create]** om een toepassing in te stellen.
1. Typ een naam in het **[!UICONTROL Application name]** veld en klik op **[!UICONTROL Create]**.

   Vul de **[!UICONTROL Device-specific settings]** sectie niet in. Dit geldt alleen voor het configureren van toepassingen die pushmeldingen ontvangen.

In de **[!UICONTROL Mobile application properties]** sectie worden twee URL&#39;s weergegeven: **[!UICONTROL Collect PII endpoint]** en **[!UICONTROL Location Services endpoint]**. Deze worden gebruikt in de interface van Adobe Mobile Services. Zie Een mobiele app [configureren in Adobe Mobile Services](#configuring-a-mobile-app-in-adobe-mobile-services).

* De **[!UICONTROL Collect PII endpoint]** URL wordt gebruikt om de Experience Cloud-id&#39;s en registratietokens van de mobiele toepassing te verzamelen wanneer deze wordt gestart. Wanneer een gebruiker zich bij de toepassing aanmeldt op basis van referenties, zoals e-mail, voornaam, achternaam, enz., worden deze gegevens ook verzameld en gebruikt om de registratietoken van de gebruiker te combineren met een Adobe Campagne-profiel.
* De **[!UICONTROL Location Services endpoint]** URL wordt gebruikt om locatiegegevens te verzamelen, zoals de breedte, lengte en straal van een gebruiker van een Punt van Interesse.

U kunt deze waarden nu gebruiken in Adobe Mobile Services om de configuratie te voltooien, zoals wordt uitgelegd in de sectie [Een mobiele toepassing configureren in Adobe Mobile Services](#configuring-a-mobile-app-in-adobe-mobile-services) .

![](assets/poi_mobile_app_properties.png)

### Een v4 mobiele app configureren in Adobe Mobile Services {#configuring-a-mobile-app-in-adobe-mobile-services}

Als u de gegevens die door Adobe Mobile Services zijn verzameld naar Adobe Campaign wilt verzenden, moet u postbacks configureren in de interface voor mobiele services.

U hebt specifieke informatie nodig die u kunt vinden in de parameters voor mobiele toepassingen die zijn ingesteld in Adobe Campagne (zie Een mobiele app [instellen in Campagne](#setting-up-a-mobile-app-in-campaign)):

* **[!UICONTROL IMS Organization ID]**
* **[!UICONTROL Collect PII Endpoint]**
* **[!UICONTROL Location Services endpoint]**

U moet toegang hebben tot Adobe Analytics voor de volgende configuratie. Neem contact op met de Adobe Campagnebeheerder als u geen Adobe Analytics-gebruiker bent.

1. Meld u aan bij [mobilemarketing.adobe.com](https://mobilemarketing.adobe.com/).
1. Maak de toepassing of selecteer een bestaande toepassing.
1. Ga naar de **[!UICONTROL Manage App Settings]** pagina.
1. Schakel in de sectie **Bezoekersidentiteitsservice** de optie **Inschakelen** in en selecteer uw organisatie in de vervolgkeuzelijst. Klik op **Opslaan**.

   >[!CAUTION]
   >
   >Deze organisatie moet dezelfde zijn als de organisatie die u gebruikt voor de Adobe Campagne-instantie.

1. Klik op **[!UICONTROL Manage Postbacks]**.
1. Maak een postback.

   * Selecteer **[!UICONTROL PII]** als **[!UICONTROL Postback Type]**.
   * Kopieer in het **[!UICONTROL URL]** veld de **[!UICONTROL Collect PII Endpoint]** URL uit de mobiele toepassing die u in de Adobe Campagne-interface hebt geconfigureerd, voorafgegaan door de servernaam. Zie Een mobiele app [instellen in Campagne](#setting-up-a-mobile-app-in-campaign).
   * Vul het **[!UICONTROL Post Body]** veld als volgt in:

      Voor iOS:

      ```
      {
      "userKey": "{userKey}",
      "pushPlatform":"apns",
      "marketingCloudId":"{%mcid%}",
      "cusEmail":"{email}",
      "cusFirstName":"{firstName}",
      "cusLastName":"{lastName}"
      }
      ```

      Voor Android:

      ```
      {
      "userKey": "{userKey}",
      "pushPlatform":"gcm",
      "marketingCloudId":"{%mcid%}",
      "cusEmail":"{email}",
      "cusFirstName":"{firstName}",
      "cusLastName":"{lastName}"
      }
      ```

   * Stel **Inhoudstype** in op **[!UICONTROL application/json]**.
   * In **Welke Tags van Gegevens teweegbrengen de Postback?** selecteert u een gebeurtenis, meestal **[!UICONTROL Launched]** en **[!UICONTROL exists]**.
   * Klik op **[!UICONTROL Save & Activate]**.

1. Maak een tweede postback.

   * Selecteer **[!UICONTROL Postback]** als **[!UICONTROL Postback Type]**.
   * Kopieer in het **[!UICONTROL URL]** veld de **[!UICONTROL Location Services Endpoint]** URL uit de mobiele toepassing die u in de Adobe Campagne-interface hebt geconfigureerd, voorafgegaan door de servernaam. Zie Een mobiele app [instellen in Campagne](#setting-up-a-mobile-app-in-campaign).
   * Vul het **[!UICONTROL Post Body]** veld als volgt in:

      ```
      {
      "locationData":{
      "distances":"{a.loc.dist}",
      "poiLabel":"{a.loc.poi}",
      "latitude.a":"{a.loc.lat.a}",
      "latitude.b":"{a.loc.lat.b}",
      "latitude.c":"{a.loc.lat.c}",
      "longitude.a":"{a.loc.lon.a}",
      "longitude.b":"{a.loc.lon.b}",
      "longitude.c":"{a.loc.lon.c}",
      "appId":"{a.appid}",
      "marketingCloudId":"{mid}"
      }
      }
      ```

   * Stel **Inhoudstype** in op **[!UICONTROL application/json]**.
   * In **Welke Tags van Gegevens teweegbrengen de Postback?**, selecteert **[!UICONTROL campaign.test]** en **[!UICONTROL exists]**.
   * Klik op **[!UICONTROL Save & Activate]**.

>[!NOTE]
>
>Raadpleeg de documentatie bij [Adobe Mobile Services voor gedetailleerde informatie over het configureren van postbacks](https://marketing.adobe.com/resources/help/en_US/mobile/signals_.html).

### De SDK integreren in een mobiele toepassing {#integrating-the-sdk-into-a-mobile-application}

De SDK (Software Development Kit) van de Mobile Core-service vereenvoudigt de integratie van een mobiele toepassing in Adobe Campaign.

Deze stap wordt beschreven in deze [pagina](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html).

### Belangenpunten definiëren in Adobe Mobile Services {#defining-points-of-interest-in-adobe-mobile-services}

U definieert de interessepunten die worden gebruikt om locatiegegevens te verzamelen:

1. Ga naar de interface van Adobe Mobile Services.
1. Voeg uw toepassing toe.

   Raadpleeg de documentatie bij [Adobe Mobile Services voor meer informatie over het beheer van toepassingen in Mobile Services](https://marketing.adobe.com/resources/help/en_US/mobile/t_new_app.html).

1. Definieer de interessepunten.

   Raadpleeg de documentatie [bij](https://marketing.adobe.com/resources/help/en_US/mobile/t_manage_points.html)Adobe Mobile Services voor meer informatie over het beheren van belangenpunten.

### Gegevens over belangenpunten van abonnees verzamelen {#collecting-subscribers--points-of-interest-data}

Een specifieke douanemiddel laat u toe om de gegevens te bepalen die u van de abonnees van uw toepassingen wilt verzamelen.

Deze stap wordt beschreven in de pagina Een mobiele toepassing [configureren met SDK V4](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html) .


## Toegang verkrijgen tot mobiele apps die worden gebruikt om locatiegegevens te verzamelen {#accessing-mobile-apps-used-to-collect-location-data}

De met succes gemaakte toepassingen openen in Adobe Campaign:

1. Klik in de linkerbovenhoek op het **[!UICONTROL Adobe Campaign]** logo.
1. Selecteer **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (SDK v4)]** of **[!UICONTROL Mobile app (AEP SDK)]** afhankelijk van de SDK.
1. Selecteer een mobiele toepassing in de lijst om de eigenschappen ervan weer te geven.

   ![](assets/poi_mobile_app_subscribers.png)

Op het **[!UICONTROL Mobile application subscribers]** tabblad wordt ook een lijst met de abonnees van de toepassing weergegeven. De abonnees zijn alle gebruikers die de toepassing op hun mobiele apparaat hebben geïnstalleerd. De Adobe Campagne-databaseprofielen worden aangeduid met een registratietoken.

## Toegang tot verzamelde locatiegegevens {#accessing-collected-location-data}

Zodra de opstelling wordt gedaan, worden de verzamelde Punten van Gegevens vermeld van de Interesse op het **[!UICONTROL Places]** lusje van elk profiel. De lijst openen:

1. Selecteer een profiel.
1. Klik op de **[!UICONTROL Edit profile properties]** knop aan de rechterkant.
1. Selecteer het **[!UICONTROL Places]** tabblad.

   ![](assets/poi_profile_places.png)

De verzamelde gegevens van Punten van Interesse voor het huidige profiel zijn vermeld. Locatiegegevens worden zes maanden lang opgeslagen in de Adobe Campagne-database.

Zie [Profielen](../../audiences/using/about-profiles.md)voor meer informatie over het openen en bewerken van profielen.
