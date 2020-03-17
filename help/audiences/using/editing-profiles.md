---
title: Profielen bewerken
description: Leer hoe u bestaande profielen kunt bewerken en toegang kunt krijgen tot contactgegevens, voorkeurskanalen, logbestanden bijhouden, abonnementen, enzovoort.
page-status-flag: never-activated
uuid: 6fcdb719-6149-48fc-b400-64c24a51487f
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-profiles
discoiquuid: 8d3ba7bf-90ae-4c6d-aaeb-a48572a69f2f
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: aee0e0437cbfe578cb2f715a2433099c79dd1748

---


# Profielen bewerken{#editing-profiles}

## Profieleigenschappen openen {#accessing-profile-properties}

Als u een bestaand profiel wilt bewerken en de bijbehorende gegevens wilt raadplegen of wijzigen, gaat u als volgt te werk:

1. Klik op de **[!UICONTROL Customer profiles]** kaart of het **[!UICONTROL Profiles]** tabblad op de startpagina van Adobe Campagne.
1. Selecteer een contactpersoon.
1. Klik op het **[!UICONTROL Edit profile properties]** pictogram om de gedetailleerde informatie van het profiel te openen.

   ![](assets/profile_creation2.png)

   Het eigenschappenvenster van het profiel bevat verschillende tabbladen die toegang geven tot alle profielgegevens.

   Andere tabbladen kunnen ook worden weergegeven, afhankelijk van de aangepaste bronnen die zijn gemaakt of uitgebreid in Adobe Campagne. Zie [Informatie over aangepaste bronnen](../../developing/using/data-model-concepts.md)voor meer informatie over aangepaste bronnen.

   >[!NOTE]
   >
   >U kunt alleen de informatie op het **[!UICONTROL General]** tabblad wijzigen - behalve de **[!UICONTROL Traceability]** sectie.

Profiles Edition is ook mogelijk met de Adobe Campagne Standard API. Raadpleeg de [desbetreffende documentatie](../../api/using/updating-profiles.md) voor meer informatie.

Verwant onderwerp:

* [Geïntegreerd klantprofiel](../../audiences/using/integrated-customer-profile.md)
* [Verzenden in de tijdzone van de ontvanger](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)

## Algemene profielgegevens {#general-profile-data}

Op het **[!UICONTROL General]** tabblad wordt de volgende informatie over het profiel gegroepeerd:

* Contactgegevens, die de voornaam, achternaam, geboortedatum, foto, voorkeurstaal (voor [meertalige e-mails](../../channels/using/creating-a-multilingual-email.md)), enz. van de ontvanger bevatten.
* Kanalen waarop het profiel kan worden gecontacteerd, dat het e-mailadres van de ontvanger, mobiele telefoonaantal, opt-out informatie bevat.
* Postadres (voor [direct mail](../../channels/using/about-direct-mail.md)), en de tijdzone van het contact (om berichten in zijn tijdzone [te](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)plannen).
* De vergunning van de toegang, die op de organisatorische eenheid van de ontvanger (om toestemmingen [te](../../administration/using/about-access-management.md)beheren) wijst. Zie ook [Partitioneringsprofielen](../../administration/using/organizational-units.md#partitioning-profiles).

![](assets/profile_creation4.png)

## Logbestanden verzenden en bijhouden {#sending-and-tracking-logs}

Met de tabbladen **[!UICONTROL Sending logs]** **[!UICONTROL Tracking logs]** en de tabbladen wordt de lijst met leveringen gegroepeerd die naar het profiel zijn verzonden, en worden alle bijbehorende volggegevens gegroepeerd.

Raadpleeg de [leveringslogboeken](../../sending/using/monitoring-a-delivery.md#delivery-logs) en de secties over [traceerberichten](../../sending/using/tracking-messages.md) voor meer informatie over het verzenden en bijhouden van logboeken.

## Abonnementen {#subscriptions}

De abonnementen van de contactpersoon worden vermeld op het overeenkomstige tabblad. Raadpleeg [deze sectie](../../audiences/using/about-subscriptions.md)voor meer informatie over het abonneren op een service.

Het tabblad **[!UICONTROL Mobile App Subscriptions]** verwijst naar de pushmeldingen. Raadpleeg het [kanaal voor pushmeldingen](../../channels/using/about-push-notifications.md) voor meer informatie.
