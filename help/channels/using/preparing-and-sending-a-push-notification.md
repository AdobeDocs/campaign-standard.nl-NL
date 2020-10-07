---
title: Een pushmelding maken en verzenden
description: Voer de volgende stappen uit om een pushmelding voor één verzending te maken in Adobe Campaign.
page-status-flag: never-activated
uuid: 01997725-ca0a-420c-9e81-5ea801652f87
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: push-notifications
discoiquuid: ec930cd4-6365-4e54-babe-9dc2eed041fc
context-tags: delivery,mobileAppContent,back
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '856'
ht-degree: 8%

---


# Een pushmelding voorbereiden en verzenden{#preparing-and-sending-a-push-notification}

## De melding voorbereiden {#preparing-the-notification}

De stappen voor het maken van een pushmelding met Adobe Campaign zijn:

1. Maak vanuit het **[!UICONTROL Marketing activities]** venster een nieuwe marketingactiviteit [](../../start/using/marketing-activities.md#creating-a-marketing-activity).

   Merk op dat één enkel dupbericht ook van een [campagne](../../start/using/marketing-activities.md#creating-a-marketing-activity) of van de [homepage](../../start/using/interface-description.md#home-page)van Adobe Campaign kan worden gecreeerd.

   U kunt ook een leveringsactiviteit voor pushberichten gebruiken in een workflow. Deze activiteit wordt voorgesteld in de [sectie van de het berichtlevering](../../automating/using/push-notification-delivery.md) van de duw.

1. Selecteer **[!UICONTROL Push notification]**.
1. Selecteer een sjabloon.

   ![](assets/push_notif_type.png)

   Standaard kunt u een van de volgende twee sjablonen selecteren:

   * **[!UICONTROL Send push to Campaign profiles]**: Gebruik deze sjabloon als doel voor de Adobe Campaign CRM-profielen die zijn geabonneerd op uw mobiele toepassing en zich hebben aangemeld voor het ontvangen van pushberichten. U kunt [verpersoonlijkingsgebieden](../../designing/using/personalization.md#inserting-a-personalization-field) in uw dupmelding, zoals de voornaam van de ontvanger opnemen.
   * **[!UICONTROL Send push to app subscribers]**: gebruik deze sjabloon om een pushmelding te verzenden naar alle bekende en anonieme gebruikers van mobiele toepassingen die zich hebben aangemeld om meldingen van uw toepassing te ontvangen. U kunt deze berichten personaliseren met gegevens die uit uw mobiele toepassing worden verzameld.

   U kunt ook meertalige sjablonen selecteren. Raadpleeg [Een meertalige pushmelding](../../channels/using/creating-a-multilingual-push-notification.md)maken voor meer informatie.

   For more on templates, refer to the [Managing templates](../../start/using/marketing-activity-templates.md) section.

1. Enter your push notification properties and select your mobile app in the **[!UICONTROL Associate a Mobile App to a delivery]** field.

   Houd er rekening mee dat in het keuzemenu zowel SDK V4- als SDK-toepassingen voor Experience Platforms worden weergegeven.

   ![](assets/push_notif_properties.png)

   U kunt de pushmelding koppelen aan een campagne. U doet dit door het te selecteren uit de campagnes die al zijn gemaakt.

1. In het volgende scherm kunt u een publiek opgeven, bijvoorbeeld alle VIP klanten die zich hebben geabonneerd op een specifieke mobiele toepassing. Zie [Soorten publiek](../../audiences/using/creating-audiences.md)maken voor meer informatie hierover.

   Uw publiek wordt automatisch gefilterd op basis van de mobiele toepassing die u in de vorige stap hebt geselecteerd.

   ![](assets/push_notif_audience.png)

1. U kunt uw pushmelding nu aanpassen. Kies eerst de berichtstijl: **[!UICONTROL Alert/Message/Badge]** of **[!UICONTROL Silent push]**. De typen pushmeldingen worden beschreven in de sectie [Over pushmeldingen](../../channels/using/about-push-notifications.md) .

   Bewerk de inhoud van uw pushmelding en definieer de geavanceerde opties. See [Customizing a push notification](../../channels/using/customizing-a-push-notification.md).

   ![](assets/push_notif_content.png)

   De inhoud en opties van de pushmelding die hier zijn geconfigureerd, worden doorgegeven aan uw mobiele app in de vorm van een payload. De gedetailleerde structuur van de lading wordt beschreven in het [Begrip van ACS-push berichten loonlaststructuur](https://docs.adobe.com/content/help/nl-NL/campaign-standard/using/communication-channels/push-notifications/push-payload.html) .

1. Klik op **[!UICONTROL Create]**.

   ![](assets/push_notif_content_2.png)

1. Voordat u het bericht verzendt, kunt u het testen met testprofielen en vervolgens precies zien wat de ontvangers zullen zien voordat de levering wordt verzonden. Selecteer **[!UICONTROL Audiences]** in uw leveringsoverzicht en klik op het **[!UICONTROL Test profiles]** tabblad.

   Raadpleeg de [testprofielen](../../sending/using/sending-proofs.md)voor meer informatie over het verzenden van tests.

1. Selecteer de testprofielen en klik **[!UICONTROL Preview]** om de melding weer te geven: inhoud wordt gepersonaliseerd met de gegevens van het testprofiel.
1. Controleer de lay-out van de pushmelding op verschillende apparaten: Selecteer een iPhone-, Android-telefoon-, iPad- of Android-tablet voor een voorvertoning van de rendering.

   ![](assets/push_notif_preview.png)

1. Dit **[!UICONTROL Estimated Payload Size]** is een schatting op basis van gegevens van het testprofiel. De werkelijke ladingsgrootte kan variëren. De limiet van het bericht is 4 kB.

   >[!CAUTION]
   >
   >Als de ladingsgrootte 4KB grens overschrijdt, zal het bericht niet worden geleverd.

Merk op dat de verpersoonlijkingsgegevens de grootte van bericht beïnvloeden.

## De melding verzenden {#sending-the-notification}

U kunt pushmeldingen naar een geselecteerd publiek in Adobe Campaign verzenden door de criteria voor het publiek te definiëren. In het onderstaande voorbeeld bestaat ons geselecteerde publiek uit vier beoogde abonnees van mobiele apps.

1. Click **[!UICONTROL Prepare]** to compute the target and generate the notifications.

   ![](assets/push_send_1.png)

1. Zodra de voorbereiding is beëindigd, geeft het venster **[!UICONTROL Deployment]** de volgende KPI&#39;s weer: **[!UICONTROL Target]** en **[!UICONTROL To deliver]**. Houd er rekening mee dat het aantal voor **[!UICONTROL To deliver]** lager is dan het aantal voor **[!UICONTROL Targeted]** vanwege uitsluitingen die kunnen worden weergegeven door op de knop ![](assets/lp_link_properties.png) onder aan het venster **[!UICONTROL Deployment]** te klikken.

   ![](assets/push_send_2.png)

1. Op het **[!UICONTROL Exclusion logs]** tabblad vindt u de lijst met alle berichten die zijn uitgesloten van het verzonden doel en de reden voor deze uitsluiting.

   Hier kunnen we zien dat een van onze abonnees van mobiele apps is uitgesloten, omdat het adres zich op de lijst van afgewezen personen bevond en de andere abonnees omdat het profiel een duplicaat was.

   ![](assets/push_send_5.png)

1. Klik op het **[!UICONTROL Exclusion causes]** tabblad om het volume van uitgesloten berichten weer te geven.

   ![](assets/push_send_7.png)

1. U kunt nu klikken **[!UICONTROL Confirm]** om pushmeldingen te verzenden.
1. Controleer de status van uw levering via het berichtdashboard en de logboeken. Voor meer op dit, zie het [Verzenden van berichten](../../sending/using/confirming-the-send.md) en de Logboeken [van de](../../sending/using/monitoring-a-delivery.md#delivery-logs)Levering.

   In dit voorbeeld wordt op het berichtdashboard weergegeven dat Adobe Campaign heeft geprobeerd twee pushmeldingen te verzenden: een werd met succes geleverd aan het apparaat en een andere ontbrak. Als u wilt weten waarom de levering fouten bevat, klikt u op de ![](assets/lp_link_properties.png) knop onder aan het **[!UICONTROL Deployment]** venster.

   ![](assets/push_send_4.png)

1. Klik in het **[!UICONTROL Deployment]** venster op het **[!UICONTROL Sending logs]** tabblad voor toegang tot de lijst met verzonden pushberichten en hun status. Voor deze levering is een pushmelding verzonden, terwijl het andere is mislukt als gevolg van een ongeldige apparaattoken. Deze abonnee zal dan aan de lijst van afgewezen personen van verdere leveringen worden toegevoegd.

   >[!NOTE]
   >
   >Redenen kunnen elke mislukking van Adobe Campaign zijn. In het geval van mislukkingen van aanbieders zoals apns en fcm, zal de reden dat ook weerspiegelen. Raadpleeg de documentatie van [Apple](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CommunicatingwithAPNs.html) en [Android](https://firebase.google.com/docs/cloud-messaging/http-server-ref) voor meer informatie over problemen met leveranciers.

   ![](assets/push_send_6.png)

U kunt nu de impact van uw pushmelding meten met dynamische rapporten.

**Verwante onderwerpen:**

* [Pushmeldingenrapport](../../reporting/using/push-notification-report.md)
* [Een pushmelding verzenden binnen een workflow](../../automating/using/push-notification-delivery.md)
