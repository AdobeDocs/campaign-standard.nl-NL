---
title: Migratie van mobiele SDK v4 naar Adobe Experience Platform SDK
description: Leer hoe u uw mobiele toepassing van SDK v4 naar Adobe Experience Platform SDK kunt migreren
audience: channels
feature: Instance Settings
role: Admin
level: Experienced
exl-id: eb7a209e-069e-4068-966d-05344bd838c7
source-git-commit: 3b2f8d9b2b7a4ec9532917af3a0880400d98e636
workflow-type: tm+mt
source-wordcount: '1216'
ht-degree: 1%

---

# Uw mobiele applicatie migreren van SDK v4 naar Adobe Experience Platform SDK {#sdkv4-migration}


De ondersteuning voor de Adobe Experience Platform Mobile-versie 4 SDK&#39;s loopt af op **31 augustus 2021**. In dit artikel leert u hoe u naar Adobe Experience Plaform SDK kunt migreren.

>[!IMPORTANT]
>
> Het migratieproces is onomkeerbaar.
>
> Lees het document zorgvuldig door voordat u de migratie van uw SDK V4 mobiele toepassing naar de Adobe Experience Platform SDK start.

## De SDK V4-migratie

Adobe Campaign Standard verwerkt mobiele toepassingen die SDK V4 gebruiken als aparte toepassingen dan toepassingen die Adobe Experience Platform SDK gebruiken.
Nadat u de SDK-versie van de Adobe van v4 naar Adobe Experience Platform hebt bijgewerkt, moeten mobiele toepassingen de bestaande abonnementsgegevens en -campagnes van de toepassing blijven gebruiken. Daarom is een migratie nodig.

>[!NOTE]
>
> Op deze pagina wordt de migratie van een mobiele SDK v4-toepassing naar een nieuwe Adobe Experience Platform SDK-toepassing gedocumenteerd. Uw SDK v4 mobiele toepassingen worden niet samengevoegd met een mobiele Adobe Experience Platform SDK-toepassing met een **[!UICONTROL Configured]** **[!UICONTROL Property status]**.

| Wat verandert er na de migratie niet |
|:-:|
| Er is geen effect op bestaande leveringen en campagnes met de gemigreerde SDK V4-toepassing. |
| De naam van de mobiele toepassing blijft ongewijzigd. |
| De platformreferenties voor iOS en Android blijven behouden. |
| Alle abonnees van de toepassing en hun gegevens zullen worden bewaard. |
| De bestaande mobiele SDK v4-toepassing zal gegevens (PII-gegevens, Abonnees en token-gegevens) naar Adobe Campaign Standard blijven verzenden. |
| De **[!UICONTROL Organizational unit]** van de mobiele toepassing blijft ongewijzigd. |

| Wat verandert er na de migratie |
|:-:|
| De mobiele toepassing is beschikbaar in **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (Adobe Experience Platform SDK)]**. Voor de migratie was deze beschikbaar in **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (SDK V4)]**. |
| De **[!UICONTROL Collect PII Endpoint]** van de toepassing wordt gewijzigd. De map **[!UICONTROL Collect PII Endpoint]** blijven werken. De verzonden gegevens gaan niet verloren. |
| De toepassing wordt gekoppeld aan een tag **[!UICONTROL Mobile Property]**. Het wordt verwerkt als een nieuwe mobiele toepassing. |
| De oorspronkelijke Adobe Experience Platform SDK-toepassing die in de migratie wordt gebruikt, bestaat niet als een aparte toepassing. Alleen de v4-toepassing voor gemigreerde SDK is beschikbaar. |

## Uw mobiele toepassing migreren van SDK v4 naar Adobe Experience Platform SDK {#how-to-migrate}

Voordat u gaat migreren, moet u rekening houden met de volgende aanbevelingen:

* Het migratieproces is onomkeerbaar.
* U moet migratie van meerdere toepassingen niet tegelijkertijd uitvoeren. Zorg er ook voor dat de migratie van een zelfde toepassing niet tezelfdertijd door meerdere vensters wordt geactiveerd.
* Controleer vóór de migratie of u de opdracht **[!UICONTROL Organizational unit]** van de mobiele toepassing die u wilt migreren en van de Adobe Experience Platform-toepassing die u gebruikt voor migratie.
* Na de migratie wordt de toepassing een Adobe Experience Platform SDK-toepassing. De wijzigingen worden gekoppeld aan de bijbehorende tag **[!UICONTROL Mobile Property]**.

1. Een nieuwe **[!UICONTROL Mobile property]** in de UI voor gegevensverzameling. Raadpleeg voor meer informatie hierover de [documentatie](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/).

1. Selecteer in Adobe Campaign Standard in het menu Geavanceerd de optie **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]** en opent u de **[!UICONTROL syncWithLaunch]** workflow. Controleer of de workflow zonder fout is beëindigd.

1. Na voltooiing van de workflow, vanuit de **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (Adobe Experience Platform SDK)]** -menu, controleer of de mobiele toepassing beschikbaar is in Adobe Campaign Standard en in **[!UICONTROL Ready to Configure]** status.

   ![](assets/aep_v4_2.png)

1. In **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (SDK V4)]** Selecteer de SDK V4-toepassing die u wilt migreren.

1. Selecteer het tabblad **[!UICONTROL Mobile application migration to AEP SDK]**. 

   ![](assets/aep_v4_3.png)

1. Van de **[!UICONTROL Select AEP SDK mobile application to merge current application with]** selecteert u de mobiele toepassing van Adobe Experience Platform SDK die u eerder hebt gemaakt.

1. Klik op **[!UICONTROL Migrate]**.

   ![](assets/aep_v4_4.png)

1. Van de **[!UICONTROL Migration application]** venster, klikt u op **[!UICONTROL Ok]**.

   ![](assets/aep_v4_5.png)

1. Het venster met voltooide bewerkingen wordt weergegeven. Klik op **[!UICONTROL Go to Adobe Experience Platform SDK Channel list]**.

1. Controleer op de pagina met kanaallijsten van de Adobe Experience Platform SDK of uw vorige mobiele V4-toepassing is ingesteld op **[!UICONTROL Ready To Configure]**.

1. Selecteer uw mobiele toepassing en klik op **[!UICONTROL Save]** de migratie voltooien.

Na deze migratie zijn abonnees die zijn verzameld door de V4-versie van de mobiele toepassing en nieuwe abonnees die zijn verzameld door de AEP-versie van de mobiele toepassing, beschikbaar in de gemigreerde toepassing.

Als u de twee verschillende typen abonnees wilt onderscheiden, kunt u een nieuw aangepast veld toevoegen met **[!UICONTROL Text]** type wanneer het uitbreiden van het douanemiddel **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** als `sdkversion` of `appVersion` bijvoorbeeld. Voor meer informatie over hoe te om een douanemiddel uit te breiden, verwijs naar dit [page](../../developing/using/creating-or-extending-the-resource.md).
U zult dan de bijbehorende markering moeten vormen **[!UICONTROL Mobile property]** om deze aangepaste veldwaarde te verzenden in de oproep PII verzamelen en de configuratie van uw mobiele toepassing dienovereenkomstig te wijzigen.

## Veelgestelde vragen {#faq}

### Q: In de mobiele SDK v4-toepassing is het tabblad Migratie van mobiele toepassingen naar de Adobe Experience Platform SDK niet zichtbaar. {#tab-not-visible}

A: Van het geavanceerde menu **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Options]** controleert u de waarde van de **[!UICONTROL Enable migration of mobile app from SDK v4 to Adobe Experience Platform SDK option]** -optie. Deze moet op 1 worden ingesteld en standaard worden ingeschakeld. Beheerders hebben de toepassing mogelijk handmatig uitgeschakeld.

![](assets/aep_v4_1.png)

### Q: Van het mobiele lusje van de toepassingsmigratie aan SDK van Adobe Experience Platform, verschijnt het bericht Geen gegevens. {#no-data}

A: Alleen in aanmerking komende toepassing van uw **[!UICONTROL Organizational unit]** wordt weergegeven in de lijst. Zorg ervoor dat u over de juiste Adobe Experience Platform-toepassing voor de migratie beschikt. De **[!UICONTROL Property Status]** van uw Adobe Experience Platform-toepassing moet worden ingesteld op **[!UICONTROL Ready to Configure]**  en de **[!UICONTROL Mobile app migration status]** instellen op **[!UICONTROL Not Migrated]**.

![](assets/aep_v4_6.png)

### Q: Waarom kan de toepassing van SDK van Adobe Experience Platform met de Gevormde Status van het Bezit niet voor migratie worden gebruikt? {#property-status}

A: Tijdens het migratieproces blijven de SDK v4-abonnees en -kenmerken behouden. Deze houdt alleen de taggerelateerde informatie van de Adobe Experience Platform SDK-toepassing bij. Abonnees en andere gegevens uit de Adobe Experience Platform SDK-toepassing gaan verloren. Om gegevensverlies te voorkomen, gebruiken alleen Adobe Experience Platform SDK-toepassingen met de **[!UICONTROL Ready to Configure]** **[!UICONTROL Property Status]** in aanmerking komen voor migratie.

### V: Waar kan ik na de migratie mijn vorige SDK v4 mobiele toepassing vinden? {#v4-app-not-visible}

A: De mobiele toepassing na de migratie wordt weergegeven via het geavanceerde menu **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (Adobe Experience Platform SDK)]**.

### V: Waar kan ik na de migratie mijn nieuwe Adobe Experience Platform SDK-toepassing vinden? {#aep-not-visible}

A: De nieuwe Adobe Experience Platform SDK-toepassing die voor de migratie wordt gebruikt, bestaat niet als een aparte toepassing. Alleen de v4-toepassing voor gemigreerde SDK is beschikbaar.

### Q: Als de SDK v4 mobile application Organizational unit is ingesteld op A (een onderliggend element van de Organizer-eenheid ALL) en de SDK van Adobe Experience Platform op ALL. Hoe kan ik mijn mobiele toepassing migreren? {#v4-org-unit}

A: Administrateurs van de **[!UICONTROL Organizational unit]** Iedereen heeft de rechten om zowel mobiele toepassingen als migratie te beheren.

### Q: Als de SDK v4 mobile application Organizational unit is ingesteld op A en de Adobe Experience Platform SDK-toepassing is ingesteld op B (een verwant van de Organizational Unit A). Hoe kan ik mijn mobiele toepassing migreren? {#aep-org-unit}

A: Adobe Experience Platform SDK-toepassing is het middel van een verwant **[!UICONTROL Organizational unit]**, is de mobiele toepassing niet zichtbaar voor gebruikers van de **[!UICONTROL Organizational unit]** A. De mobiele toepassing is beschikbaar voor de beheerders van de **[!UICONTROL Organizational unit]** ALLES, maar we raden deze beheerders niet aan om de mobiele toepassing te migreren.
In dit geval moet u uw mobiele toepassingen in hetzelfde formaat verplaatsen **[!UICONTROL Organizational unit]** of in een **[!UICONTROL Organizational unit]** met een bovenliggende koppeling.
Voor meer informatie over **[!UICONTROL Organizational unit]**, gelieve deze [sectie](../../administration/using/organizational-units.md).

### Q: Van uw Adobe Experience Platform SDK-pagina voor mobiele apparaten (die is gemigreerd vanuit uw mobiele v4-toepassing), wordt onder de vervolgkeuzelijst voor Push channel-instellingen geen informatie zoals de geüploade datum/naam weergegeven voor de Android-sleutel of het iOS-certificaat {#no-information-v5}

A: Het systeem slaat deze informatie niet op wanneer de mobiele SDK V4-toepassing wordt gemaakt. Wanneer u uw SDK V4 mobiele toepassing naar een mobiele Adobe Experience Platform SDK-toepassing migreert, beschikt uw gemigreerde mobiele toepassing ook niet over dit soort informatie. Zodra een gebruiker een nieuw iOS-certificaat of een Android-sleutel uploadt, worden de verschillende details van de sleutel of het certificaat correct opgeslagen en weergegeven onder de **[!UICONTROL Push channel settings]** vervolgkeuzelijst.
