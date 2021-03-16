---
solution: Campaign Standard
product: campaign
title: Belangrijkste stappen voor verzending van een bericht
description: Voer de volgende stappen uit om berichten te maken en te verzenden met Adobe Campaign.
audience: channels
content-type: reference
topic-tags: about-communication-channels
feature: Overzicht
role: Zakelijke praktiserer
level: Begin
translation-type: tm+mt
source-git-commit: a7a1aa2841410674597264927325c073fef4ce26
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 12%

---


# Belangrijkste stappen voor verzending van een bericht{#key-steps-to-send-a-message}

In deze sectie leert u hoe u persoonlijke berichten kunt maken en verzenden naar een doelgroep met Adobe Campaign Standard.

De specifieke informatie over om elk communicatie kanaal tot stand te brengen en te vormen is beschikbaar in deze secties:

* [Een e-mail maken](../../channels/using/creating-an-email.md)
* [SMS maken](../../channels/using/creating-an-sms-message.md)
* [Een direct-maillevering maken](../../channels/using/creating-the-direct-mail.md)
* [Een pushmelding](../../channels/using/preparing-and-sending-a-push-notification.md) maken.
* [Een in-app-bericht voorbereiden en verzenden](../../channels/using/preparing-and-sending-an-in-app-message.md)

Raadpleeg de sectie [Best practices voor levering](../../sending/using/delivery-best-practices.md) voor meer informatie over de best practices voor levering.

## Uw bericht maken

Gebruik Campaign Standard [marketingactiviteiten](../../start/using/marketing-activities.md) om een e-mail-, SMS-, direct-mail-, pushmelding- of In-App-bericht te maken.

![](assets/marketing-activities.png)

Berichten kunnen worden gemaakt op basis van de lijst met marketingactiviteiten of op basis van een workflow met [speciale activiteiten](../../automating/using/about-channel-activities.md).

![](assets/steps-channel.png)

## Het publiek definiëren

Bepaal de ontvangers van uw bericht. Om dit te doen, gebruik [vraagredacteur](../../automating/using/editing-queries.md) van de linkerruit aan filtergegevens in uw gegevensbestand en bouwt regels om uw publiek te richten.

Er zijn verschillende soorten publiek beschikbaar:

* **[!UICONTROL Target]** is het belangrijkste doel van uw e-mail,
* **[!UICONTROL Test profiles]** Hier ziet u de profielen die worden gebruikt voor het testen en valideren van uw e-mail (zie  [Testprofielen](../../audiences/using/managing-test-profiles.md) beheren).

![](assets/steps-audience.png)

## Inhoud ontwerpen en aanpassen

In het **[!UICONTROL Content]** blok, ontwerp en verpersonaliseer de inhoud van uw bericht gebruikend gebieden van uw gegevensbestand. Raadpleeg de secties boven aan deze pagina voor meer informatie over het ontwerpen van inhoud voor een specifiek kanaal.

![](assets/steps-content.png)

## Voorbereiden en testen

[Bereid ](../../sending/using/preparing-the-send.md) het bericht voor. Dit proces berekent de doelpopulatie en bereidt het gepersonaliseerde bericht voor.

![](assets/steps-prepare.png)

**Controleer en test uw** bericht voordat u het verzendt met behulp van Campaign Standard-mogelijkheden: voorvertoning, e-mailweergave, proefdrukken, enz. Raadpleeg [deze sectie](../../sending/using/previewing-messages.md) voor meer informatie.

Gebruik het **[!UICONTROL Schedule]** blok om te bepalen wanneer uw berichten zullen worden verzonden (zie [Plannend berichten](../../sending/using/about-scheduling-messages.md)).

![](assets/steps-schedule.png)

## Verzenden en volgen

Zodra uw bericht klaar is, kunt u het verzenden bevestigen. Het **[!UICONTROL Deployment]** blok toont de verzendvooruitgang en het resultaat.

![](assets/steps-send.png)

Verschillende logboeken zijn beschikbaar om u te helpen de levering van uw berichten controleren (zie [het controleren van een levering](../../sending/using/monitoring-a-delivery.md)). U kunt ook de ontvangers van de levering volgen dankzij het gedrag [traceren functionaliteit](../../sending/using/tracking-messages.md).

![](../../sending/using/assets/tracking_logs.png)

Meet de doeltreffendheid van uw berichten en de evolutie van uw verzendt en campagnes door diverse indicatoren en grafieken (zie [Toegang tot rapporten](../../reporting/using/about-dynamic-reports.md)).

![](assets/steps-reports.png)
