---
title: Een mobiele toepassing configureren
description: Ontdek hoe u Adobe Campagne kunt configureren voor het verzenden van pushberichten of In-App-berichten met SDK V4 of Experience Platform SDK.
page-status-flag: never-activated
uuid: 63e1476a-7875-4f48-ba9e-97f1a0007e42
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuring-channels
discoiquuid: 2a14500f-5ede-4131-8b1a-b7fd65b7e3aa
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f4f09556fed8c3cca44a72ac6dfeb280379d58c3
workflow-type: tm+mt
source-wordcount: '1344'
ht-degree: 0%

---


# Een mobiele toepassing configureren{#configuring-a-mobile-application}

## Een mobiele toepassing configureren met SDK&#39;s van het Adobe Experience Platform {#using-adobe-experience-platform-sdk}

>[!IMPORTANT]
>
>Pushmeldingen en implementaties in de app moeten worden uitgevoerd door deskundige gebruikers. Neem contact op met de manager of de Professional-servicepartner van Adobe-accounts als u hulp nodig hebt.

Als u pushmeldingen en In-App-berichten wilt verzenden met Experience Platform SDK-toepassing, moet een mobiele toepassing worden ingesteld in Adobe Experience Platform Experience Platform Experience Platform Launch en geconfigureerd in Adobe Campaign.

Raadpleeg deze [pagina](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4-deprecated.html)voor meer informatie over de vervangen functie Mobile versie 4 SDK&#39;s.

Zodra een mobiele toepassing is ingesteld, kunt u de verzamelde PII-gegevens ophalen om profielen te maken of bij te werken vanuit uw database. Raadpleeg voor meer informatie deze sectie: [Profielgegevens maken en bijwerken op basis van gegevens](../../channels/using/updating-profile-with-mobile-app-data.md)van mobiele toepassingen.

Raadpleeg deze [pagina](https://helpx.adobe.com/campaign/kb/configure-launch-rules-acs-use-cases.html)voor meer informatie over de verschillende gevallen van mobiel gebruik die worden ondersteund in Adobe Campaign Standard met de SDK&#39;s van het Adobe Experience Platform.

Voer de volgende stappen uit om de configuratie te voltooien:

1. In de Campagne van Adobe, zorg ervoor dat u tot het volgende kunt toegang hebben:
   * **[!UICONTROL Push notification]**
   * **[!UICONTROL In-App message]**
   * **[!UICONTROL Adobe Places]**
   Als dat niet het geval is, neemt u contact op met uw accountteam.

1. Controleer of uw gebruiker over de benodigde machtigingen beschikt in Adobe Campagne Standard en Experience Platform Launch.
   * Controleer in Adobe Campaign Standard of de IMS-gebruiker deel uitmaakt van de standaardprofielen voor gebruikers- en beheerproducten. Met deze stap kan de gebruiker zich aanmelden bij Adobe Campagne Standard, naar de pagina voor mobiele apps voor het Experience Platform SDK navigeren en de eigenschappen van de mobiele app bekijken die u hebt gemaakt in Experience Platform Launch.

   * Zorg er in Experience Platform Launch voor dat uw IMS-gebruiker deel uitmaakt van een Experience Platform Launch-productprofiel.
Met deze stap kan de gebruiker zich aanmelden bij Experience Platform Launch om de eigenschappen te maken en weer te geven. Zie Uw productprofiel maken voor meer informatie over productprofielen in Experience Platform Launch. In het productprofiel, zou er geen toestemmingen moeten zijn die op het bedrijf of de eigenschappen worden geplaatst, maar de gebruiker zou nog login moeten kunnen.
   Als u aanvullende taken wilt uitvoeren, zoals het installeren van een extensie, het publiceren van een app, het configureren van omgevingen, enzovoort, moet u machtigingen instellen in het productprofiel.

1. In de Lancering van het Platform van de Ervaring, creeer een **[!UICONTROL Mobile property]**. Zie Een mobiele eigenschap [](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property)instellen voor meer informatie.

1. Klik in Experience Platform Launch op het **[!UICONTROL Extensions]** tabblad, ga naar **[!UICONTROL Catalog]** en zoek naar de **[!UICONTROL Adobe Campaign Standard]** extensie. Zie [Adobe Campaign Standard](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard)voor meer informatie.

1. Installeer de **[!UICONTROL Places]** **[!UICONTROL Places Monitor]** extensie en de extensie om gevallen van locatiegebruik in Campaign Standard te ondersteunen.
   * Installeer de **[!UICONTROL Places]** extensie in Experience Platform Launch. Zie deze [pagina](https://docs.adobe.com/content/help/en/places/using/places-ext-aep-sdks/places-extension/places-extension.html).
   * Installeer de **[!UICONTROL Places Monitor]** extensie in Experience Platform Launch. Zie deze [pagina](https://docs.adobe.com/content/help/en/places/using/places-ext-aep-sdks/places-monitor-extension/using-places-monitor-extension.html)

1. In de Standaard van de Campagne van Adobe, vorm het mobiele bezit dat u in de Lancering van het Platform van de Ervaring creeerde. Raadpleeg [Setting up your Adobe Experience Platform Launch application in Adobe Campaign](../../administration/using/configuring-a-mobile-application.md#set-up-campaign).

1. Voeg de kanaalspecifieke configuratie toe aan uw mobiele toepassingsopstelling.
Zie [Kanaalspecifieke toepassingsconfiguratie in Adobe Campagne](../../administration/using/configuring-a-mobile-application.md#channel-specific-config)voor meer informatie.

1. Indien nodig, kunt u de opstarteigenschap van het Experience Platform verwijderen.
Zie Uw toepassing [voor het starten van het Experience Platform](../../administration/using/configuring-a-mobile-application.md#delete-app)verwijderen voor meer informatie.

## Mobiele app synchroniseren met AEPSDK vanuit technische workflow starten {#aepsdk-workflow}

>[!IMPORTANT]
>
>Deze functie is een bètafunctie in Adobe Campaign vanaf release 20.3. U moet een ticket naar de klantenservice van Adobe verzenden (rechtstreeks of via uw Adobe-contactpersoon) om de **[!UICONTROL sync Mobile app AEPSDK from Launch]** technische workflow in uw Adobe Campagne-instantie in te schakelen.

Nadat u uw mobiele eigenschap hebt gemaakt en geconfigureerd in Experience Platform Launch, worden in de **[!UICONTROL Sync Mobile app AEPSDK from Launch]** technische workflow nu de mobiele eigenschappen van Adobe Launch gesynchroniseerd die zijn geïmporteerd in Adobe Campagne Standard.

Standaard begint de technische werkstroom elke 15 minuten. Indien nodig kan de toepassing handmatig opnieuw worden gestart:

1. Kies in Adobe Campaign Standard in het menu Geavanceerd **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**.
1. Open de **[!UICONTROL Sync Mobile app AEPSDK from Launch (syncWithLaunch)]** workflow.

   ![](assets/launch_10.png)

1. Klik op de **[!UICONTROL Scheduler]** activiteit.

1. Selecteer **[!UICONTROL Immediate execution]**.

   ![](assets/launch_11.png)

De Adobe Launch mobile-eigenschappen die zijn geïmporteerd in Adobe Campagne Standard, worden nu opnieuw gestart en gesynchroniseerd.

## Een Adobe Experience Platform Starten-toepassing instellen in Adobe Campagne {#set-up-campaign}

Als u een mobiele eigenschap van het Experience Platform Launch in Campaign wilt gebruiken, moet u deze eigenschap ook configureren in Adobe Campaign. In de Campagne van Adobe, zorg ervoor dat de gebruiker IMS deel van de Standaard Profiles van het Product van de Gebruiker en van de Beheerder uitmaakt.

Voor gebruikers die de markering Functie voor technische werkstroom starten hebben ingeschakeld in de app AEPSDK voor mobiele apparaten synchroniseren, moet u wachten tot de technische werkstroom is uitgevoerd en de eigenschap Mobiele site starten hebt gesynchroniseerd met Adobe Campagne. U kunt de toepassing vervolgens configureren in Adobe Campaign.

Raadpleeg deze [sectie](../../administration/using/configuring-a-mobile-application.md#aepsdk-workflow)voor meer informatie over het synchroniseren van de functiemarkering voor mobiele app AEPSDK vanuit de functiemarkering voor technische workflows starten.

>[!NOTE]
>
>Standaard kunnen beheerders met een organisatorische eenheid ingesteld op ALL de mobiele toepassing bewerken.

1. Selecteer in het menu Geavanceerd **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]**.

   ![](assets/launch.png)

1. Selecteer de mobiele toepassing die u hebt gemaakt in Experience Platform Launch.
Het **[!UICONTROL Property Status]** moet zijn **[!UICONTROL Ready to configure]**.

   >[!NOTE]
   >
   >Standaard gebruikt de campagnestandaard voor het ophalen van de lijst met mobiele toepassingen die zijn gemaakt in Adobe Launch de waarde die is gedefinieerd in de optie NmsServer_URL om te zoeken naar overeenkomende eigenschappen.
In sommige gevallen, kan het eindpunt van de Campagne voor een mobiele toepassing van die in NmsServer_URL worden bepaald verschillend zijn. Definieer in dat geval het eindpunt in de optie Launch_URL_Campaign. De campagne gebruikt de waarde van deze optie om te zoeken naar overeenkomende eigenschappen in Adobe Launch.

   ![](assets/launch_4.png)

1. U kunt de organisatorische eenheid van uw mobiele toepassing onder de **[!UICONTROL Access Authorization]** sectie veranderen om toegang tot deze mobiele toepassing tot specifieke organisatorische eenheden te beperken. Raadpleeg deze pagina voor meer informatie.

   Hier, kan de beheerder suborganisatorische eenheden toewijzen door hen van drop-down te selecteren.

   ![](assets/launch_12.png)

1. Als u de verbinding tussen Starten van campagne en ervaringsplatform tot stand wilt brengen, klikt u **[!UICONTROL Save]**.

1. Controleer of de status van de mobiele app is gewijzigd van **[!UICONTROL Ready to Configure]** naar **[!UICONTROL Configured]**.

   Wanneer de uitbreiding van de Campagne van de Lancering van het Platform van de Ervaring toont dat pkey opstelling met succes is geweest, kunt u ook verifiëren dat het bezit met succes in Campagne is geplaatst.

   ![](assets/launch_5.png)

1. Om deze configuratie van kracht te worden, moeten de veranderingen in de Lancering van het Platform van de Ervaring worden gepubliceerd.

   Zie Configuratie [](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#publish-configuration)publiceren voor meer informatie.

## Kanaalspecifieke toepassingsconfiguratie in Adobe-campagne {#channel-specific-config}

Uw mobiele toepassing kan nu worden gebruikt in Campagne voor pushmeldingen of in-app-leveringen. U kunt het nu verder configureren als dat nodig is om gebeurtenissen te maken die uw berichten in de app activeren en/of pushcertificaten uploaden.

1. Selecteer in het menu Geavanceerd **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]**.

1. Selecteer de mobiele toepassing die u hebt gemaakt en geconfigureerd in Launch van Experience Platform.

1. Op het **[!UICONTROL Mobile application properties]** tabblad kunt u beginnen met het toevoegen van gebeurtenissen die beschikbaar zijn in uw mobiele toepassing voor berichten in de app.

1. Klik **[!UICONTROL Create Element]** om uw gebeurtenissen te configureren.

   ![](assets/launch_6.png)

1. Typ een naam en een beschrijving.

   ![](assets/launch_7.png)

1. Klik op **[!UICONTROL Add]**.

   De gebeurtenis is nu beschikbaar op het tabblad Triggers wanneer u een bericht in de app maakt. Zie Een bericht [in de app](../../channels/using/preparing-and-sending-an-in-app-message.md)voorbereiden en verzenden voor meer informatie.

1. Geef in de **[!UICONTROL Device-specific settings]** sectie van een dashboard voor mobiele toepassingen voor elk apparaat de toepassingsgegevens op, inclusief het certificaat voor iOS en de serversleutel voor Android.

   Nadat het certificaat is geüpload, verschijnt er een bericht met de melding dat het uploaden is voltooid en wordt de vervaldatum van het certificaat weergegeven.

   >[!NOTE]
   >
   >Nadat u het certificaat hebt toegevoegd in Adobe Campaign Standard, kunt u de instellingen niet meer wijzigen omdat slechts één APNS-platform (productie of sandbox) aan de MCPNS-app kan worden toegevoegd.

   ![](assets/launch_8.png)

1. Klik op het **[!UICONTROL Mobile application subscribers]** tabblad om een lijst met abonnees en andere informatie over deze abonnees weer te geven, bijvoorbeeld of ze uw meldingen hebben verlaten.

## Uw Adobe Experience Platform Launch-toepassing verwijderen {#delete-app}

Het verwijderen van uw Experience Platform Launch-toepassing kan niet ongedaan worden gemaakt.

>[!CAUTION]
>
>Het verwijderen van uw Experience Platform Launch-toepassing kan niet ongedaan worden gemaakt.

Als u uw Experience Platform Launch-toepassing wilt verwijderen, voert u de stappen in [Mobiele eigenschappen](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard#deleting-mobile-properties-in-experience-platform-launch)verwijderen uit.

Nadat uw toepassing is verwijderd, controleert u in Adobe Campaign of de eigenschappenstatus van uw toepassing correct is bijgewerkt naar Verwijderd in Launch.

Als u in Adobe Campaign op uw toepassing klikt, kunt u deze toepassing volledig uit Adobe Campagne verwijderen door op Verwijderen uit Campagne te klikken.

    ![](assets/launch_9.png)
