---
title: Informatie over Adobe Experience Cloud-triggers
description: Door specifiek gedrag van klanten te volgen met Adobe Analytics, kunt u nu gepersonaliseerde e-mails naar uw klanten in Adobe Campaign verzenden.
page-status-flag: never-activated
uuid: 0aa4bd6e-1bb5-4d0b-913b-eca93f050acd
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
discoiquuid: e526b205-2d01-4a8b-9685-ba1d9a1f459f
context-tags: trigger,overview;trigger,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 100%

---


# Informatie over Adobe Experience Cloud-triggers{#about-adobe-experience-cloud-triggers}

Dankzij de integratie tussen de Experience Cloud Activation-kernservice **[!UICONTROL Triggers]** en Adobe Campaign kunt u persoonlijke e-mails naar uw klanten sturen als reactie op specifiek gedrag dat (binnen 15 minuten) door Adobe Analytics op uw website wordt gevolgd.

In Adobe Experience Cloud kunt u verschillende &#39;triggers&#39; definiëren. Dat wil zeggen: het gedrag van de klant dat u wilt monitoren, zoals bijvoorbeeld alle klanten die uw website hebben verlaten of klanten die een zoekopdracht op uw website hebben uitgevoerd maar niets gekocht, en zelfs klanten van wie de sessie is verlopen. Wanneer u een trigger maakt, definieert u de voorwaarde van de trigger en de data die in de gebeurtenis(upload) naar Adobe Campaign worden verzonden.

In Adobe Campaign selecteert u de trigger die eerder is gemaakt. U verrijkt u de gebeurtenisdata met datamart-data en u definieert een transactieberichtsjabloon die aan de trigger is gekoppeld. Wanneer een klant bijvoorbeeld uw website verlaat, wordt een gebeurtenis naar Adobe Campaign verzonden. Op basis van deze gebeurtenis stuurt Adobe Campaign binnen 15 minuten een e-mailbericht voor remarketing naar het clientapparaat van de klant.

In het volgende diagram wordt beschreven hoe deze integratie werkt.

![](assets/triggers_diagram.png)

**Verwante onderwerpen:**

* Meer informatie over de verschillende typen triggers: [Adobe Experience Cloud-documentatie](https://docs.adobe.com/content/help/nl-NL/core-services/interface/activation/triggers.html).
* Bekijk de video over [triggers voor remarketingberichten op basis van websiteactiviteiten](https://helpx.adobe.com/nl/marketing-cloud/how-to/email-marketing.html#step-two).
* Verken onze twee [gebruiksscenario&#39;s voor triggers bij afbrekingsacties](../../integrating/using/abandonment-triggers-use-cases.md).

## Gebruikersproces voor triggers {#triggers-user-process}

>[!CAUTION]
>
>Voordat de hoofdstappen van de gebruiker worden uitgevoerd, moet de functionaliteit worden geconfigureerd. Voor meer informatie hierover gaat u naar [De functionaliteit activeren](../../integrating/using/configuring-triggers-in-experience-cloud.md#activating-the-functionality), [Oplossingen en services configureren](../../integrating/using/configuring-triggers-in-experience-cloud.md#configuring-solutions-and-services) en het [Een toegewezen trigger maken in Campaign](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign).

De belangrijkste stappen van het gebruikersproces in Adobe Campaign zijn:

1. Maak een triggergebeurtenis die is gekoppeld aan een bestaande Adobe Experience Cloud-trigger.
1. Publiceer de triggergebeurtenis.
1. Definieer de content van de sjabloon voor het transationele bericht.
1. Test de sjabloon (maak een testprofiel en verstuur een proefversie).
1. Publiceer de sjabloon voor het transationele bericht.

Voltooi de gebruiksscenario&#39;s die in [deze sectie](../../integrating/using/abandonment-triggers-use-cases.md) zijn beschreven.

## Belangrijke opmerkingen {#important-notes}

Hier volgen enkele belangrijke punten waarmee u rekening moet houden voordat u de Triggers-integratie voor Campaign gebruikt:

* Pushmeldingen worden niet ondersteund voor triggers. Alleen e-mail en sms worden ondersteund.
* U kunt de trigger verrijken met metadata die via Analytics zijn vastgelegd, zoals een e-mail-id, paginanaam, enzovoort.
* U kunt de trigger afstemmen met een profiel dat is opgeslagen in Campaign Standaard en de velden van het profiel gebruiken om het bericht te personaliseren.
* Zodra een trigger is ontvangen, wordt deze verwerkt, afgestemd en verzonden. Het hele proces duurt zo&#39;n 5 tot 15 minuten, afhankelijk van het aantal ontvangen triggers en het aantal personalisatievelden die in de sjabloon worden gebruikt.

>[!NOTE]
>
>Raadpleeg [Best practices en beperkingen voor triggers](../../integrating/using/configuring-triggers-in-experience-cloud.md#triggers-best-practices-and-limitations) voor meer informatie over aanbevolen procedures en technische beperkingen.

