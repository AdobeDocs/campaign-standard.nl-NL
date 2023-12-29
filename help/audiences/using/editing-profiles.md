---
title: Profielen bewerken
description: Leer hoe u bestaande profielen kunt bewerken en toegang kunt krijgen tot contactgegevens, voorkeurskanalen, logbestanden voor bijhouden, abonnementen, enzovoort.
audience: audiences
content-type: reference
topic-tags: managing-profiles
feature: Profiles
role: User
level: Intermediate
exl-id: d0c7dc09-6f2b-4336-b545-7afe3a704164
source-git-commit: 13d419c5fc51845ee14f8a3b288f4c467e0a60d9
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 7%

---

# Profielen bewerken{#editing-profiles}

## Profieleigenschappen openen {#accessing-profile-properties}

Als u een bestaand profiel wilt bewerken en de bijbehorende gegevens wilt raadplegen of wijzigen, gaat u als volgt te werk:

1. Klik op de startpagina van Adobe Campaign op de knop **[!UICONTROL Customer profiles]** of de **[!UICONTROL Profiles]** tab.
1. Selecteer een contactpersoon.
1. Klik op de knop **[!UICONTROL Edit profile properties]** voor toegang tot de gedetailleerde informatie van het profiel.

   ![](assets/profile_creation2.png)

   Het eigenschappenvenster van het profiel bevat verschillende tabbladen die toegang geven tot alle profielgegevens.

   Andere tabbladen kunnen ook worden weergegeven, afhankelijk van de aangepaste bronnen die in Adobe Campaign zijn gemaakt of uitgebreid. Zie voor meer informatie over aangepaste bronnen [Informatie over aangepaste bronnen](../../developing/using/data-model-concepts.md).

   >[!NOTE]
   >
   >U kunt alleen de gegevens in het dialoogvenster **[!UICONTROL General]** tab - behalve de **[!UICONTROL Traceability]** sectie.

Profiles Edition is ook mogelijk met de Adobe Campaign Standard API. Raadpleeg de [desbetreffende documentatie](../../api/using/updating-profiles.md) voor meer informatie.

Verwant onderwerp:

* [Geïntegreerd klantprofiel](../../audiences/using/integrated-customer-profile.md)
* [Verzenden in de tijdzone van de ontvanger](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)

## Algemene profielgegevens {#general-profile-data}

De **[!UICONTROL General]** wordt de volgende informatie over het profiel gegroepeerd:

* Contactgegevens met de voornaam, achternaam, geboortedatum, foto, voorkeurstaal van de ontvanger (voor [meertalige e-mails](../../channels/using/creating-a-multilingual-email.md)), enz.
* Kanalen waarop het profiel kan worden gecontacteerd, dat het e-mailadres van de ontvanger, mobiele telefoonaantal, opt-out informatie bevat.
* Postadres (voor [direct mail](../../channels/using/about-direct-mail.md)) en de tijdzone van de contactpersoon (naar [planningsberichten in zijn tijdzone](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)).
* Toegangsvergunning, die de organisatorische eenheid van de ontvanger (aan [machtigingen beheren](../../administration/using/about-access-management.md)). Zie ook [Partitioneringsprofielen](../../administration/using/organizational-units.md#partitioning-profiles).

![](assets/profile_creation4.png)

## Logbestanden verzenden en bijhouden {#sending-and-tracking-logs}

De **[!UICONTROL Sending logs]** en **[!UICONTROL Tracking logs]** tabs groeperen de lijst met leveringen die naar het profiel zijn verzonden, en alle bijbehorende volggegevens.

Raadpleeg voor meer informatie over het verzenden en bijhouden van logbestanden de [leveringslogs](../../sending/using/monitoring-a-delivery.md#delivery-logs) en de [trackingberichten](../../sending/using/tracking-messages.md) secties.

## Lidmaatschappen {#subscriptions}

De abonnementen van de contactpersoon worden vermeld op het overeenkomstige tabblad. Raadpleeg voor meer informatie over het abonneren op een service [deze sectie](../../audiences/using/about-subscriptions.md).

De **[!UICONTROL Mobile App Subscriptions]** verwijst naar de pushmeldingen. Raadpleeg voor meer informatie de [Pushmelding](../../channels/using/about-push-notifications.md) kanaal.
