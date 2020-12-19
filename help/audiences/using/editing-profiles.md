---
solution: Campaign Standard
product: campaign
title: Profielen bewerken
description: Leer hoe u bestaande profielen kunt bewerken en toegang kunt krijgen tot contactgegevens, voorkeurskanalen, logbestanden bijhouden, abonnementen, enzovoort.
audience: audiences
content-type: reference
topic-tags: managing-profiles
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 11%

---


# Profielen bewerken{#editing-profiles}

## Profieleigenschappen openen {#accessing-profile-properties}

Als u een bestaand profiel wilt bewerken en de bijbehorende gegevens wilt raadplegen of wijzigen, gaat u als volgt te werk:

1. Klik op de Adobe Campaign-startpagina op de kaart **[!UICONTROL Customer profiles]** of het tabblad **[!UICONTROL Profiles]**.
1. Selecteer een contactpersoon.
1. Klik op het pictogram **[!UICONTROL Edit profile properties]** om toegang te krijgen tot de gedetailleerde informatie van het profiel.

   ![](assets/profile_creation2.png)

   Het eigenschappenvenster van het profiel bevat verschillende tabbladen die toegang geven tot alle profielgegevens.

   Andere tabbladen kunnen ook worden weergegeven, afhankelijk van de aangepaste bronnen die in Adobe Campaign zijn gemaakt of uitgebreid. Zie [Informatie over aangepaste bronnen](../../developing/using/data-model-concepts.md) voor meer informatie over aangepaste bronnen.

   >[!NOTE]
   >
   >U kunt de informatie alleen wijzigen op het tabblad **[!UICONTROL General]**, behalve voor de sectie **[!UICONTROL Traceability]**.

Profiles Edition is ook mogelijk met de Adobe Campaign Standard API. Raadpleeg de [desbetreffende documentatie](../../api/using/updating-profiles.md) voor meer informatie.

Verwant onderwerp:

* [Geïntegreerd klantprofiel](../../audiences/using/integrated-customer-profile.md)
* [Verzenden in de tijdzone van de ontvanger](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)

## Algemene profielgegevens {#general-profile-data}

Op het tabblad **[!UICONTROL General]** wordt de volgende informatie over het profiel gegroepeerd:

* Contactgegevens, die de voornaam, achternaam, geboortedatum, foto, voorkeurstaal van de ontvanger bevatten (voor [meertalige e-mails](../../channels/using/creating-a-multilingual-email.md)), enz.
* Kanalen waarop het profiel kan worden gecontacteerd, dat het e-mailadres van de ontvanger, mobiele telefoonaantal, opt-out informatie bevat.
* Postadres (voor [direct mail](../../channels/using/about-direct-mail.md)), en de tijdzone van het contact (aan [planningsberichten in zijn tijdzone](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)).
* De vergunning van de toegang, die op de organisatorische eenheid van de ontvanger (aan [beheer toestemmingen](../../administration/using/about-access-management.md)) wijst. Zie ook [Partitioneringsprofielen](../../administration/using/organizational-units.md#partitioning-profiles).

![](assets/profile_creation4.png)

## Logbestanden verzenden en bijhouden {#sending-and-tracking-logs}

Met de tabbladen **[!UICONTROL Sending logs]** en **[!UICONTROL Tracking logs]** wordt de lijst met leveringen gegroepeerd die naar het profiel zijn verzonden, en alle bijbehorende volggegevens.

Voor meer bij het verzenden van en het volgen van logboeken, verwijs naar [leveringslogboeken](../../sending/using/monitoring-a-delivery.md#delivery-logs) en [volgende berichten](../../sending/using/tracking-messages.md) secties.

## Abonnementen {#subscriptions}

De abonnementen van de contactpersoon worden vermeld op het overeenkomstige tabblad. Raadpleeg [deze sectie](../../audiences/using/about-subscriptions.md) voor meer informatie over het abonneren op een service.

Het tabblad **[!UICONTROL Mobile App Subscriptions]** verwijst naar de pushberichten. Raadpleeg het kanaal [Push notification](../../channels/using/about-push-notifications.md) voor meer informatie.
