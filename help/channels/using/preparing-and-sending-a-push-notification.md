---
title: Een pushmelding maken en verzenden
description: Voer de volgende stappen uit om een pushmelding voor één verzending te maken in Adobe Campaign.
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: delivery,mobileAppContent,back
feature: Push
role: User
level: Intermediate
exl-id: 41b83014-aea9-4ec2-b20e-c0a05bcad503
source-git-commit: affd4f9716235a283df20de5539e43c4832762f7
workflow-type: tm+mt
source-wordcount: '841'
ht-degree: 7%

---

# Een pushmelding voorbereiden en verzenden{#preparing-and-sending-a-push-notification}

## De melding voorbereiden {#preparing-the-notification}

De stappen voor het maken van een pushmelding met Adobe Campaign zijn:

1. Van de **[!UICONTROL Marketing activities]** venster, [een nieuwe marketingactiviteit maken](../../start/using/marketing-activities.md#creating-a-marketing-activity).

   Merk op dat één enkel duw bericht ook van kan tot stand brengen [campagne](../../start/using/marketing-activities.md#creating-a-marketing-activity) of van de Adobe Campaign [homepage](../../start/using/interface-description.md#home-page).

   U kunt ook een leveringsactiviteit voor pushberichten gebruiken in een workflow. Deze activiteit wordt weergegeven in de [Levering pushmelding](../../automating/using/push-notification-delivery.md) sectie.

1. Selecteer **[!UICONTROL Push notification]**.
1. Selecteer een sjabloon.

   ![](assets/push_notif_type.png)

   Standaard kunt u een van de volgende twee sjablonen selecteren:

   * **[!UICONTROL Send push to Campaign profiles]**: gebruik deze sjabloon als doel voor de Adobe Campaign CRM-profielen die zijn geabonneerd op uw mobiele toepassing en die zich hebben aangemeld voor het ontvangen van pushberichten. U kunt [personalisatie](../../designing/using/personalization.md#inserting-a-personalization-field) in uw pushmelding, zoals de voornaam van de ontvanger.
   * **[!UICONTROL Send push to app subscribers]**: gebruik deze sjabloon om een pushmelding te verzenden naar alle bekende en anonieme gebruikers van mobiele toepassingen die zich hebben aangemeld om meldingen van uw toepassing te ontvangen. U kunt deze berichten personaliseren met gegevens die uit uw mobiele toepassing worden verzameld.

   U kunt ook meertalige sjablonen selecteren. Raadpleeg voor meer informatie [Meertalige pushmeldingen maken](../../channels/using/creating-a-multilingual-push-notification.md).

   Raadpleeg voor meer informatie over sjablonen de [Sjablonen beheren](../../start/using/marketing-activity-templates.md) sectie.

1. Voer de eigenschappen van uw pushmelding in en selecteer uw mobiele app in het dialoogvenster **[!UICONTROL Associate a Mobile App to a delivery]** veld.

   Houd er rekening mee dat in het keuzemenu zowel SDK V4- als SDK-toepassingen voor Experience Platforms worden weergegeven.

   ![](assets/push_notif_properties.png)

   U kunt de pushmelding koppelen aan een campagne. U doet dit door het te selecteren uit de campagnes die al zijn gemaakt.

1. In het volgende scherm kunt u een publiek opgeven, bijvoorbeeld alle VIP klanten die zich hebben geabonneerd op een specifieke mobiele toepassing. Zie voor meer informatie [Soorten publiek maken](../../audiences/using/creating-audiences.md).

   Uw publiek wordt automatisch gefilterd op basis van de mobiele toepassing die u in de vorige stap hebt geselecteerd.

   ![](assets/push_notif_audience.png)

1. U kunt uw pushmelding nu aanpassen. Kies eerst de berichtstijl: **[!UICONTROL Alert/Message/Badge]** of **[!UICONTROL Silent push]**. De typen pushmeldingen worden beschreven in het dialoogvenster [Pushmeldingen](../../channels/using/about-push-notifications.md) sectie.

   Bewerk de inhoud van uw pushmelding en definieer de geavanceerde opties. Zie [Een pushmelding aanpassen](../../channels/using/customizing-a-push-notification.md).

   ![](assets/push_notif_content.png)

   De inhoud en opties van de pushmelding die hier zijn geconfigureerd, worden doorgegeven aan uw mobiele app in de vorm van een payload. De gedetailleerde structuur van de lading wordt beschreven in [Werken met de payloadstructuur van pushberichten voor Campaigns Standard](../../administration/using/push-payload.md) technote.

1. Klik op **[!UICONTROL Create]**.

   ![](assets/push_notif_content_2.png)

1. Voordat u het bericht verzendt, kunt u het testen met testprofielen en vervolgens precies zien wat de ontvangers zullen zien voordat de levering wordt verzonden. Selecteren **[!UICONTROL Audiences]** in uw leveringsoverzicht en klik op **[!UICONTROL Test profiles]** tab.

   Voor meer bij het verzenden van tests, verwijs naar [Testprofielen](../../sending/using/sending-proofs.md).

1. Selecteer de testprofielen en klik op **[!UICONTROL Preview]** om het bericht weer te geven: de inhoud wordt gepersonaliseerd met de gegevens van het testprofiel.
1. Controleer de lay-out van de pushmelding op verschillende apparaten: selecteer iPhone, Android-telefoon, iPad of Android om een voorvertoning van de rendering weer te geven.

   ![](assets/push_notif_preview.png)

1. De **[!UICONTROL Estimated Payload Size]** is een schatting op basis van gegevens van het testprofiel. De werkelijke ladingsgrootte kan variëren. De limiet van het bericht is 4 kB.

   >[!CAUTION]
   >
   >Als de ladingsgrootte 4KB grens overschrijdt, zal het bericht niet worden geleverd.

Merk op dat de verpersoonlijkingsgegevens de grootte van bericht beïnvloeden.

## De melding verzenden {#sending-the-notification}

U kunt pushmeldingen naar een geselecteerd publiek in Adobe Campaign verzenden door de criteria voor het publiek te definiëren. In het onderstaande voorbeeld bestaat ons geselecteerde publiek uit vier beoogde abonnees van mobiele apps.

1. Klikken **[!UICONTROL Prepare]** om het doel te berekenen en de meldingen te genereren.

   ![](assets/push_send_1.png)

1. Zodra de voorbereiding is beëindigd, geeft het venster **[!UICONTROL Deployment]** de volgende KPI&#39;s weer: **[!UICONTROL Target]** en **[!UICONTROL To deliver]**. Houd er rekening mee dat het aantal voor **[!UICONTROL To deliver]** lager is dan het aantal voor **[!UICONTROL Targeted]** vanwege uitsluitingen die kunnen worden weergegeven door op de knop ![](assets/lp_link_properties.png) onder aan het venster **[!UICONTROL Deployment]** te klikken.

   ![](assets/push_send_2.png)

1. In de **[!UICONTROL Exclusion logs]** kunt u de lijst met alle berichten vinden die zijn uitgesloten van het verzonden doel en de reden voor deze uitsluiting.

   Hier kunnen we zien dat een van onze abonnees van mobiele apps is uitgesloten, omdat het adres zich op de lijst van gewezen personen bevond en de andere abonnees omdat het profiel een duplicaat was.

   ![](assets/push_send_5.png)

1. Klik op de knop **[!UICONTROL Exclusion causes]** om het volume van uitgesloten berichten weer te geven.

   ![](assets/push_send_7.png)

1. U kunt nu op **[!UICONTROL Confirm]** om pushmeldingen te verzenden.
1. Controleer de status van uw levering via het berichtdashboard en de logboeken. Zie voor meer informatie [Berichten verzenden](../../sending/using/confirming-the-send.md) en [Leveringslogboeken](../../sending/using/monitoring-a-delivery.md#delivery-logs).

   In dit voorbeeld wordt op het berichtdashboard weergegeven dat Adobe Campaign heeft geprobeerd twee pushmeldingen te verzenden: een bericht is afgeleverd op het apparaat en een ander bericht is mislukt. Om te weten waarom de levering fouten heeft, klik ![](assets/lp_link_properties.png) onder aan het dialoogvenster **[!UICONTROL Deployment]** venster.

   ![](assets/push_send_4.png)

1. Van de **[!UICONTROL Deployment]** venster, klikt u op **[!UICONTROL Sending logs]** voor toegang tot de lijst met verzonden pushberichten en hun status. Voor deze levering is een pushmelding verzonden, terwijl het andere is mislukt door een ongeldige apparaattoken. Deze abonnee zal dan aan de lijst van gewezen personen van verdere leveringen worden toegevoegd.

   >[!NOTE]
   >
   >Redenen kunnen elke mislukking van Adobe Campaign zijn. In het geval van mislukkingen van aanbieders zoals apns en fcm, zal de reden dat ook weerspiegelen. Voor meer informatie over leveranciersmislukkingen, kunt u naar verwijzen [Apple](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CommunicatingwithAPNs.html) en [Android](https://firebase.google.com/docs/cloud-messaging/http-server-ref) documentatie.

   ![](assets/push_send_6.png)

U kunt nu de impact van uw pushmelding meten met dynamische rapporten.

**Verwante onderwerpen:**

* [Pushmeldingenrapport](../../reporting/using/push-notification-report.md)
* [Een pushmelding verzenden binnen een workflow](../../automating/using/push-notification-delivery.md)
