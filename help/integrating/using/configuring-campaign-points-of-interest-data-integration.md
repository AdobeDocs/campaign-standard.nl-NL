---
title: De integratie van data van Campaign-Points of Interest configureren
description: Leer hoe u de functie Punten met interessegegevens in Adobe Campaign configureert om persoonlijke berichten te verzenden op basis van de locatie van uw abonnees.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics-for-mobile
feature: Audiences
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: b097b3fa-f949-446e-ad44-cc6ca025ee55
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '1252'
ht-degree: 1%

---

# De integratie van data van Campaign-Points of Interest configureren{#configuring-campaign-points-of-interest-data-integration}

## Integratie van Campagne-Punten van de Gegevens van de Interesse met Adobe Experience Platform SDKs vormen {#configuring-campaign-poi-aep-sdk}

>[!NOTE]
>
>Uw mobiele toepassing moet al in Adobe Campaign Standard zijn geconfigureerd met Adobe Experience Platform SDK. Voor de gedetailleerde stappen, verwijs naar deze [ pagina ](https://helpx.adobe.com/nl/campaign/kb/configuring-app-sdk.html).

De mobiele toepassingen die worden gebruikt om plaatsgegevens te verzamelen moeten door een **beheerder** in de interface van Adobe Campaign worden gevormd.

Om Adobe Experience Platform Location Services met mobiele toepassingen te kunnen gebruiken die met Adobe Experience Platform SDK worden gevormd, moet u:

1. Voeg de extensie **[!UICONTROL Places]** toe aan uw mobiele toepassingsconfiguratie in de gebruikersinterface voor gegevensverzameling. Stel uw mobiele toepassing in Adobe Campaign in. Zie [ installeren de uitbreiding van Plaatsen ](https://developer.adobe.com/client-sdks/solution/places).

1. Als uw extensies zijn ingesteld, maakt u gegevenselementen in de gebruikersinterface voor gegevensverzameling om gegevens van deze extensies op te halen. Verwijs naar deze [ pagina ](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Step1Createdataelements) om uw gegevenselementen tot stand te brengen.

1. Dan, in de Inzameling van Gegevens UI, moet u regels tot stand brengen om mobiele gebruiksgevallen tussen Punt van Belangen en Adobe Campaign te steunen.\
   Deze regel wordt geactiveerd wanneer een gebruiker een afgezonderde **[!UICONTROL Point of Interest]** invoert. Verwijs naar deze [ pagina ](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Locationpostback) om uw regel tot stand te brengen.

1. Definieer de **[!UICONTROL Points of Interest]** op plaatsen. Zie [ een Punt van Interesse ](https://experienceleague.adobe.com/docs/places/using/poi-mgmt-ui/create-a-poi-ui.html) creëren.

1. Zorg ervoor dat u de mobiele toepassing en de verzamelde locatiegegevens in Adobe Campaign opent. Zie [ Toegang hebbend tot mobiele apps die worden gebruikt om plaatsgegevens ](#accessing-mobile-apps-used-to-collect-location-data) te verzamelen en [ toegang hebbend tot verzamelde plaatsgegevens ](#accessing-collected-location-data).

## Integratie van Campagne-Punten van de Gegevens van het Vormen gebruikend SDK V4 {#configuring-campaign-poi-sdkv4}

De mobiele toepassingen die worden gebruikt om plaatsgegevens te verzamelen moeten door een **beheerder** in de interface van Adobe Campaign worden gevormd.

Als u de Point of Interest-gegevensfunctie wilt gebruiken voor mobiele toepassingen die zijn geconfigureerd met SDK V4, moet u:

1. Toegang tot Adobe Analytics for Mobile. Controleer uw licentieovereenkomst of neem contact op met de manager van uw Adobe-account voor meer informatie.
1. Stel uw mobiele toepassing in Adobe Campaign in. Zie [ Vestiging een mobiele app in Campagne ](#setting-up-a-mobile-app-in-campaign).
1. Stel uw mobiele toepassing in de Adobe Mobile Services-interface in. Op deze manier kunt u ervoor zorgen dat gegevens die door Adobe Mobile Services zijn verzameld, naar Adobe Campaign worden verzonden. Zie [ Vormend een mobiele app in de Mobiele Diensten van Adobe ](#configuring-a-mobile-app-in-adobe-mobile-services).
1. Voer de specifieke installatie van de mobiele toepassing uit:

   * Verpak het configuratiebestand dat is gedownload van de Adobe Mobile Services-interface met de mobiele toepassing.
   * Integreer de Experience Cloud Mobile SDK in uw mobiele toepassing. Zie [ Integrerend SDK in een mobiele toepassing ](#integrating-the-sdk-into-a-mobile-application).

1. Definieer de interessepunten in de Adobe Mobile Services-interface. Zie [ het bepalen van Punten van Interesse in de Mobiele Diensten van Adobe ](#defining-points-of-interest-in-adobe-mobile-services).
1. Definieer de gegevens die u wilt verzamelen van de abonnees van uw mobiele toepassing. Zie [ het Verzamelen van abonnees&#39; Punten van interessegegevens ](#collecting-subscribers--points-of-interest-data).
1. Zorg ervoor dat u de mobiele toepassing en de verzamelde locatiegegevens in Adobe Campaign opent. Zie [ Toegang hebbend tot mobiele apps die worden gebruikt om plaatsgegevens ](#accessing-mobile-apps-used-to-collect-location-data) te verzamelen en [ toegang hebbend tot verzamelde plaatsgegevens ](#accessing-collected-location-data).

### Een mobiele app instellen in Adobe Campaign met SDK V4 {#setting-up-a-mobile-app-in-campaign}

Als u gegevens van punten van belang met Adobe Campaign wilt kunnen verzamelen, moet u de mobiele toepassing configureren waarvan Adobe Campaign gegevens ontvangt.

1. Klik het **Adobe** embleem, in de top-linkerhoek, dan uitgezocht **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app]**.
1. Klik op **[!UICONTROL Create]** om een toepassing in te stellen.
1. Typ een naam in het veld **[!UICONTROL Application name]** en klik op **[!UICONTROL Create]** .

   Vul de sectie **[!UICONTROL Device-specific settings]** niet in. Dit geldt alleen voor het configureren van toepassingen die pushmeldingen ontvangen.

In de sectie **[!UICONTROL Mobile application properties]** worden twee URL&#39;s weergegeven: **[!UICONTROL Collect PII endpoint]** en **[!UICONTROL Location Services endpoint]** . Deze worden gebruikt in de Adobe Mobile Services-interface. Zie [ Vormend een mobiele app in de Mobiele Diensten van Adobe ](#configuring-a-mobile-app-in-adobe-mobile-services).

* De URL van **[!UICONTROL Collect PII endpoint]** wordt gebruikt om de Experience Cloud-id&#39;s en registratietokens van de gebruikers te verzamelen van de mobiele toepassing wanneer deze wordt gestart. Wanneer een gebruiker zich bij de toepassing aanmeldt met referenties, zoals e-mail, voornaam, achternaam, enz., worden deze gegevens ook verzameld en gebruikt om de registratietoken van de gebruiker in overeenstemming te brengen met een Adobe Campaign-profiel.
* De URL van **[!UICONTROL Location Services endpoint]** wordt gebruikt om locatiegegevens te verzamelen, zoals de breedte, lengte en straal van een gebruiker van een Punt van Interesse.

U kunt deze waarden in de Mobiele Diensten van Adobe nu gebruiken om de configuratie te beëindigen, zoals die in [ wordt verklaard die een mobiele app in de Mobiele sectie van de Diensten van Adobe Mobiele ](#configuring-a-mobile-app-in-adobe-mobile-services) vormt.

![](assets/poi_mobile_app_properties.png)

### Een v4 mobiele app configureren in Adobe Mobile Services {#configuring-a-mobile-app-in-adobe-mobile-services}

Als u de gegevens die door Adobe Mobile Services zijn verzameld naar Adobe Campaign wilt verzenden, moet u postbacks configureren in de interface voor mobiele services.

U zult specifieke informatie nodig hebben die u in de mobiele toepassingsparameters kunt vinden in Adobe Campaign (zie [ Vestiging een mobiele app in Campagne ](#setting-up-a-mobile-app-in-campaign)):

* **[!UICONTROL IMS Organization ID]**
* **[!UICONTROL Collect PII Endpoint]**
* **[!UICONTROL Location Services endpoint]**

U moet toegang hebben tot Adobe Analytics om de volgende configuratie te kunnen uitvoeren. Neem contact op met de Adobe Campaign-beheerder als u geen Adobe Analytics-gebruiker bent.

1. Logboek in [ mobilemarketing.adobe.com ](https://mobilemarketing.adobe.com/).
1. Maak de toepassing of selecteer een bestaande toepassing.
1. Ga naar de pagina **[!UICONTROL Manage App Settings]** .
1. In de **sectie van de Dienst van identiteitskaart van de Bezoeker**, laat de controle **** toe en selecteert uw organisatie van de drop-down lijst. Klik **sparen**.

   >[!CAUTION]
   >
   >Deze organisatie moet dezelfde zijn als de organisatie die u gebruikt op het Adobe Campaign-exemplaar.

1. Klik op **[!UICONTROL Manage Postbacks]**.
1. Maak een postback.

   * Selecteer **[!UICONTROL PII]** als de **[!UICONTROL Postback Type]** .
   * Kopieer in het veld **[!UICONTROL URL]** de **[!UICONTROL Collect PII Endpoint]** URL van de mobiele toepassing die u in de Adobe Campaign-interface hebt geconfigureerd, voorafgegaan door de servernaam. Zie [ Vestiging een mobiele app in Campagne ](#setting-up-a-mobile-app-in-campaign).
   * Vul het veld **[!UICONTROL Post Body]** als volgt in:

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

   * Plaats **Type van Inhoud** als **[!UICONTROL application/json]**.
   * In **welke Codes van Gegevens teweegbrengen Postback?** selecteert u een willekeurige gebeurtenis, meestal **[!UICONTROL Launched]** en **[!UICONTROL exists]** .
   * Klik op **[!UICONTROL Save & Activate]**.

1. Maak een tweede postback.

   * Selecteer **[!UICONTROL Postback]** als de **[!UICONTROL Postback Type]** .
   * Kopieer in het veld **[!UICONTROL URL]** de **[!UICONTROL Location Services Endpoint]** URL van de mobiele toepassing die u in de Adobe Campaign-interface hebt geconfigureerd, voorafgegaan door de servernaam. Zie [ Vestiging een mobiele app in Campagne ](#setting-up-a-mobile-app-in-campaign).
   * Vul het veld **[!UICONTROL Post Body]** als volgt in:

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

   * Plaats **Type van Inhoud** als **[!UICONTROL application/json]**.
   * In **welke Codes van Gegevens teweegbrengen Postback?** selecteert u **[!UICONTROL campaign.test]** en **[!UICONTROL exists]** .
   * Klik op **[!UICONTROL Save & Activate]**.

>[!NOTE]
>
>Voor gedetailleerde informatie bij het vormen van postbacks, verwijs naar de [ documentatie van de Diensten van Adobe Mobile ](https://experienceleague.adobe.com/docs/mobile-services/using/manage-app-settings-ug/configuring-app/signals.html).

### De SDK integreren in een mobiele toepassing {#integrating-the-sdk-into-a-mobile-application}

De softwareontwikkelingskit (SDK) van de Mobile Core-service maakt de integratie van een mobiele toepassing in Adobe Campaign mogelijk.

Deze stap wordt beschreven in deze [ pagina ](https://helpx.adobe.com/nl/campaign/kb/configuring-app-sdkv4.html).

### Belangenpunten in Adobe Mobile Services definiëren {#defining-points-of-interest-in-adobe-mobile-services}

U definieert de interessepunten die worden gebruikt om locatiegegevens te verzamelen:

1. Ga naar de Adobe Mobile Services interface.
1. Voeg uw toepassing toe.

   Voor meer informatie bij het beheren van toepassingen in de Mobiele Diensten, verwijs naar de [ documentatie van de Diensten van Adobe Mobiele ](https://experienceleague.adobe.com/docs/mobile-services/using/manage-apps-ug/t-new-app.html).

1. Definieer de interessepunten.

   Voor meer informatie bij het beheren van Punten van Interesse, verwijs naar de [ documentatie van de Mobiele Diensten van Adobe ](https://experienceleague.adobe.com/docs/mobile-services/using/location-ug/t-manage-points.html).

### Gegevens over belangenpunten van abonnees verzamelen {#collecting-subscribers--points-of-interest-data}

Een specifieke douanemiddel laat u toe om de gegevens te bepalen die u van de abonnees van uw toepassingen wilt verzamelen.

Deze stap wordt beschreven in [ Vormend een mobiele toepassing gebruikend SDK V4 ](https://helpx.adobe.com/nl/campaign/kb/configuring-app-sdkv4.html) pagina.

## Toegang verkrijgen tot mobiele apps die worden gebruikt om locatiegegevens te verzamelen {#accessing-mobile-apps-used-to-collect-location-data}

Om tot de met succes gecreeerde toepassingen in Adobe Campaign toegang te hebben:

1. Klik het **Adobe** embleem, in de top-left hoek.
1. Selecteer **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (SDK v4)]** of **[!UICONTROL Mobile app (AEP SDK)]** , afhankelijk van de SDK.
1. Selecteer een mobiele toepassing in de lijst om de eigenschappen ervan weer te geven.

   ![](assets/poi_mobile_app_subscribers.png)

Een lijst met de abonnees van de toepassing wordt ook weergegeven op het tabblad **[!UICONTROL Mobile application subscribers]** . De abonnees zijn alle gebruikers die de toepassing op hun mobiele apparaat hebben geïnstalleerd. De Adobe Campaign-databaseprofielen worden aangeduid met een registratietoken.

## Toegang verkrijgen tot verzamelde locatiegegevens {#accessing-collected-location-data}

Zodra de setup is voltooid, worden de verzamelde gegevens over de punten van interesse weergegeven op het tabblad **[!UICONTROL Places]** van elk profiel. U kunt als volgt de lijst openen:

1. Selecteer een profiel.
1. Klik op de knop **[!UICONTROL Edit profile properties]** aan de rechterkant.
1. Selecteer het tabblad **[!UICONTROL Places]**. 

   ![](assets/poi_profile_places.png)

De verzamelde gegevens van Punten van Interesse voor het huidige profiel zijn vermeld. Locatiegegevens worden zes maanden lang opgeslagen in de Adobe Campaign-database.

Voor meer informatie bij de toegang tot van en het uitgeven van profielen, zie [ Profielen ](../../audiences/using/about-profiles.md).
