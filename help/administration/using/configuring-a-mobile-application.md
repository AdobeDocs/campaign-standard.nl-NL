---
title: Een mobiele applicatie configureren
description: Leer hoe u Adobe Campaign configureert voor het verzenden van pushberichten of In-App-berichten met behulp van Experience Platform SDK
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 5f9a8e84-a362-42b6-8bd2-e5d56214c1db
source-git-commit: bfba6b156d020e8d2656239e713d2d24625bda54
workflow-type: tm+mt
source-wordcount: '1245'
ht-degree: 5%

---

# Een mobiele applicatie configureren{#configuring-a-mobile-application}

## Een mobiele toepassing configureren met Adobe Experience Platform SDK&#39;s {#using-adobe-experience-platform-sdk}

>[!IMPORTANT]
>
>Pushmeldingen en implementaties in de app moeten worden uitgevoerd door deskundige gebruikers. Neem voor hulp contact op met uw Adobe-accountmanager of Professional-servicepartner.

Als u pushberichten en In-App-berichten wilt verzenden met de SDK-toepassing van het Experience Platform, moet een mobiele toepassing worden ingesteld in het Adobe Experience Platform Experience Platform-Experience Platform Launch en worden geconfigureerd in Adobe Campaign.

Zodra een mobiele toepassing is ingesteld, kunt u de verzamelde PII-gegevens ophalen om profielen te maken of bij te werken vanuit uw database. Raadpleeg voor meer informatie deze sectie: [Profielgegevens maken en bijwerken op basis van gegevens van mobiele toepassingen](../../channels/using/updating-profile-with-mobile-app-data.md).

Als u meer wilt weten over de verschillende gevallen van mobiel gebruik die in Adobe Campaign Standard worden ondersteund met de SDK&#39;s van Adobe Experience Platform, raadpleegt u deze [page](../../administration/using/supported-mobile-use-cases.md).

Voer de volgende stappen uit om de configuratie te voltooien:

1. Ga in Adobe Campaign naar het volgende:
   * **[!UICONTROL Push notification]**
   * **[!UICONTROL In-App message]**
   * **[!UICONTROL Adobe Places]**

   Als dat niet het geval is, neemt u contact op met uw accountteam.

1. Controleer of de gebruiker over de benodigde rechten beschikt in Adobe Campaign Standard en Experience Platform Launch.
   * In Adobe Campaign Standard moet u ervoor zorgen dat de IMS-gebruiker deel uitmaakt van de standaardprofielen voor gebruikers- en beheerproducten. Met deze stap kan de gebruiker zich aanmelden bij Adobe Campaign Standard, naar de pagina voor de mobiele app van de SDK van het Experience Platform navigeren en de eigenschappen van de mobiele app bekijken die u in het Experience Platform Launch hebt gemaakt.

   * Zorg er in Experience Platform Launch voor dat uw IMS-gebruiker deel uitmaakt van een productprofiel voor Experience Platforms Launch.
Met deze stap kan de gebruiker zich aanmelden bij het Experience Platform Launch om de eigenschappen te maken en weer te geven. Zie Uw productprofiel maken voor meer informatie over productprofielen in Experience Platform Launch. In het productprofiel, zou er geen toestemmingen moeten zijn die op het bedrijf of de eigenschappen worden geplaatst, maar de gebruiker zou nog login moeten kunnen.

   Als u aanvullende taken wilt uitvoeren, zoals het installeren van een extensie, het publiceren van een app, het configureren van omgevingen, enzovoort, moet u machtigingen instellen in het productprofiel.

1. Maak in Experience Platform Launch een **[!UICONTROL Mobile property]**. Zie [Een mobiele eigenschap instellen](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property) voor meer informatie.

1. Klik in het Experience Platform Launch op de knop **[!UICONTROL Extensions]** tab, ga naar **[!UICONTROL Catalog]** en zoek naar **[!UICONTROL Adobe Campaign Standard]** extensie. Zie voor meer informatie [Adobe Campaign Standard](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard).

1. Installeer de **[!UICONTROL Places]** en de **[!UICONTROL Places Monitor]** extensie.
   * Installeer de **[!UICONTROL Places]** in Experience Platform Launch. Zie dit [page](https://experienceleague.adobe.com/docs/places/using/places-ext-aep-sdks/places-extension/places-extension.html).
   * Installeer de **[!UICONTROL Places Monitor]** in Experience Platform Launch. Zie dit [page](https://experienceleague.adobe.com/docs/places/using/places-ext-aep-sdks/places-monitor-extension/using-places-monitor-extension.html)

1. Configureer in Adobe Campaign Standaard de mobiele eigenschap die u in Experience Platform Launch hebt gemaakt. Zie [Een Adobe Experience Platform Launch-toepassing instellen in Adobe Campaign](../../administration/using/configuring-a-mobile-application.md#set-up-campaign).

1. Voeg de kanaalspecifieke configuratie toe aan de configuratie van de mobiele applicatie.
Zie [Kanaalspecifieke applicatieconfiguratie in Adobe Campaign](../../administration/using/configuring-a-mobile-application.md#channel-specific-config) voor meer informatie.

1. Indien nodig kunt u de eigenschap Experience Platform Launch verwijderen.
Zie voor meer informatie [De toepassing Experience Platform Launch verwijderen](../../administration/using/configuring-a-mobile-application.md#delete-app).

## Mobiele app synchroniseren met AEPSDK vanuit technische workflow starten {#aepsdk-workflow}

Nadat u uw mobiele eigenschap in het Experience Platform Launch hebt gemaakt en geconfigureerd, kunt u **[!UICONTROL Sync Mobile app AEPSDK from Launch]** In de technische workflow worden nu de Adobe Launch mobile-eigenschappen gesynchroniseerd die in Adobe Campaign Standard zijn geïmporteerd.

Standaard begint de technische werkstroom elke 15 minuten. Indien nodig kan de toepassing handmatig opnieuw worden gestart:

1. Selecteer in Adobe Campaign Standard in het menu Geavanceerd de optie **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**.
1. Open de **[!UICONTROL Sync Mobile app AEPSDK from Launch (syncWithLaunch)]** workflow.

   ![](assets/launch_10.png)

1. Klik op de knop **[!UICONTROL Scheduler]** activiteit.

1. Selecteer **[!UICONTROL Immediate execution]**.

   ![](assets/launch_11.png)

De Adobe Launch mobile-eigenschappen die in Adobe Campaign Standard zijn geïmporteerd, worden nu opnieuw opgestart en gesynchroniseerd.

## Een Adobe Experience Platform Launch-toepassing instellen in Adobe Campaign {#set-up-campaign}

Om een Experience Platform Launch mobiel bezit in Campagne te gebruiken, moet u dit bezit in Adobe Campaign ook vormen. In Adobe Campaign moet u ervoor zorgen dat de IMS-gebruiker deel uitmaakt van de standaardprofielen voor gebruikers- en beheerproducten.

U moet wachten tot de technische workflow wordt uitgevoerd en de eigenschap Mobiele site starten moet worden gesynchroniseerd met Adobe Campaign. U kunt de configuratie vervolgens configureren in Adobe Campaign.

Raadpleeg voor meer informatie over het synchroniseren van mobiele app AEPSDK vanuit de technische workflow van Starten de volgende [sectie](../../administration/using/configuring-a-mobile-application.md#aepsdk-workflow).

>[!NOTE]
>
>Standaard kunnen beheerders met een organisatorische eenheid ingesteld op ALL de mobiele toepassing bewerken.

1. Selecteer in het menu Geavanceerd de optie **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]**.

   ![](assets/launch.png)

1. Selecteer de mobiele toepassing die u in Experience Platform Launch hebt gemaakt.
haar **[!UICONTROL Property Status]** moeten **[!UICONTROL Ready to configure]**.

   >[!NOTE]
   >
   >Standaard gebruikt Campaign Standard om de lijst met mobiele toepassingen op te halen die zijn gemaakt in Adobe Launch de waarde die is gedefinieerd in de optie NmsServer_URL om te zoeken naar overeenkomende eigenschappen.
   >
   >In sommige gevallen, kan het eindpunt van de Campagne voor een mobiele toepassing van die in NmsServer_URL worden bepaald verschillend zijn. Definieer in dat geval het eindpunt in de optie Launch_URL_Campaign. De campagne zal de waarde van deze optie gebruiken om passende eigenschappen in de Lancering van de Adobe te zoeken.

   ![](assets/launch_4.png)

1. U kunt de organisatorische eenheid van uw mobiele toepassing veranderen onder **[!UICONTROL Access Authorization]** om de toegang tot deze mobiele toepassing te beperken tot specifieke organisatie-eenheden. Raadpleeg deze sectie voor meer informatie.

   Hier, kan de beheerder suborganisatorische eenheden toewijzen door hen van drop-down te selecteren.

   ![](assets/launch_12.png)

1. Als u een verbinding wilt maken tussen Campagne en Experience Platform Launch, klikt u op **[!UICONTROL Save]**.

1. Controleer of de status van de mobiele app is gewijzigd van **[!UICONTROL Ready to Configure]** tot **[!UICONTROL Configured]**.

   Wanneer de uitbreiding van de Campagne van het Experience Platform Launch toont dat de sleutel opstelling met succes is geweest, kunt u ook verifiëren dat het bezit met succes opstelling in Campagne is geweest.

   ![](assets/launch_5.png)

1. Deze configuratie wordt pas van kracht als de wijzigingen in Experience Platform Launch worden gepubliceerd.

   Zie voor meer informatie [Configuratie publiceren](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#publish-configuration).

## Kanaalspecifieke toepassingsconfiguratie in Adobe Campaign {#channel-specific-config}

Uw mobiele toepassing kan nu worden gebruikt in Campagne voor pushberichten of in-app-leveringen. U kunt het nu verder configureren als dat nodig is om gebeurtenissen te maken die uw In-App-berichten activeren en/of pushcertificaten uploaden.

1. Selecteer in het menu Geavanceerd de optie **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]**.

1. Selecteer de mobiele toepassing die u in Experience Platform Launch hebt gemaakt en geconfigureerd.

1. Op de **[!UICONTROL Mobile application properties]** kunt u gebeurtenissen toevoegen die beschikbaar zijn in uw mobiele toepassing voor uw In-App-berichten.

1. Om uw gebeurtenissen te vormen, klik **[!UICONTROL Create Element]**.

   ![](assets/launch_6.png)

1. Typ een naam en een beschrijving.

   ![](assets/launch_7.png)

1. Klik op **[!UICONTROL Add]**.

   De gebeurtenis is nu beschikbaar op het tabblad Triggers wanneer u een bericht in de app maakt. Zie voor meer informatie [Een bericht in de app voorbereiden en verzenden](../../channels/using/preparing-and-sending-an-in-app-message.md).

1. In de **[!UICONTROL Device-specific settings]** in een dashboard voor mobiele toepassingen voor elk apparaat de toepassingsgegevens opgeven, inclusief het certificaat voor iOS en de serversleutel voor Android.

   Nadat het certificaat is geüpload, verschijnt er een bericht met de melding dat het uploaden is voltooid en wordt de vervaldatum van het certificaat weergegeven.

   >[!NOTE]
   >
   >Nadat u het certificaat in Adobe Campaign Standard hebt toegevoegd, kunt u de instellingen niet meer wijzigen omdat slechts één APNS-platform (productie of sandbox) aan de MCPNS-app kan worden toegevoegd.

   ![](assets/launch_8.png)

1. Klik op de knop **[!UICONTROL Mobile application subscribers]** om een lijst met abonnees en andere informatie over deze abonnees weer te geven, bijvoorbeeld of ze uw meldingen hebben verlaten.

## Adobe Experience Platform Launch-toepassing verwijderen {#delete-app}

Het verwijderen van uw Experience Platform Launch kan niet ongedaan worden gemaakt.

>[!CAUTION]
>
>Het verwijderen van uw Experience Platform Launch kan niet ongedaan worden gemaakt.

Voer de volgende stappen uit om uw Experience Platform Launch-toepassing te verwijderen: [Mobiele eigenschappen verwijderen](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard#deleting-mobile-properties-in-experience-platform-launch).

Nadat uw toepassing is verwijderd, controleert u in Adobe Campaign of de eigenschappenstatus van uw toepassing correct is bijgewerkt naar Verwijderd in Launch.

Als u op de toepassing in Adobe Campaign klikt, kunt u deze toepassing volledig uit Adobe Campaign verwijderen door op Verwijderen uit campagne te klikken.

![](assets/launch_9.png)
