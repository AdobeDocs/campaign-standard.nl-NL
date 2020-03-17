---
title: Informatie over Adobe Experience Cloud-triggers
description: Door specifiek gedrag van klanten te volgen met Adobe Analytics, kunt u gepersonaliseerde e-mails naar uw klanten in de Campagne van Adobe nu verzenden.
page-status-flag: never-activated
uuid: 0aa4bd6e-1bb5-4d0b-913b-eca93f050acd
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
discoiquuid: e526b205-2d01-4a8b-9685-ba1d9a1f459f
context-tags: trigger,overview;trigger,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Informatie over Adobe Experience Cloud-triggers{#about-adobe-experience-cloud-triggers}

Dankzij de integratie tussen de Experience Cloud Activation Core-service **[!UICONTROL Triggers]** en Adobe Campaign kunt u persoonlijke e-mails naar uw klanten sturen als reactie op specifieke gedragingen die door Adobe Analytics (binnen 15 minuten) op uw website worden bijgehouden.

In Adobe Experience Cloud definieert u de verschillende triggers, dat wil zeggen het gedrag van de klant dat u wilt controleren, zoals alle klanten die hun bezoek aan uw website hebben stopgezet, die een zoekopdracht op uw website hebben uitgevoerd, maar geen aankoop hebben gedaan, of zelfs de klanten van wie de sessie is verlopen. Wanneer u een trigger maakt, definieert u de voorwaarde van de trigger en de gegevens die in de gebeurtenis (upload) naar Adobe Campagne worden verzonden.

In de Campagne van Adobe, selecteert u de trekker die eerder werd gecreeerd, verrijkt u de gebeurtenisgegevens met datamart gegevens en u bepaalt een transactiemalplaatje verbonden aan die trekker. Wanneer een klant bijvoorbeeld zijn bezoek op uw website verlaat, wordt een gebeurtenis verzonden naar Adobe Campaign die deze gebeurtenis vervolgens kan benutten via een e-mailbericht voor opnieuw marketing dat binnen 15 minuten naar de client wordt verzonden.

**Verwante onderwerpen:**

* Meer informatie over de verschillende typen triggers: documentatie [](https://marketing.adobe.com/resources/help/en_US/mcloud/triggers.html)voor Adobe Experience Cloud.
* Bekijk de [trekkerberichten die op video van de Activiteit](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html#step-two) van de Plaats worden gebaseerd.
* Ontdek onze twee [gevallen](../../integrating/using/abandonment-triggers-use-cases.md)van Afschaffing.

## Triggers-gebruikersproces {#triggers-user-process}

>[!CAUTION]
>
>Voordat de hoofdstappen van de gebruiker worden uitgevoerd, moet de functionaliteit worden geconfigureerd. Voor meer op dit verwijs naar het [Activeren van de functionaliteit](../../integrating/using/configuring-triggers-in-experience-cloud.md#activating-the-functionality), het [Vormen oplossingen en de diensten](../../integrating/using/configuring-triggers-in-experience-cloud.md#configuring-solutions-and-services) en het [Creëren van een in kaart gebrachte trekker in Campagne](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign).

De belangrijkste stappen van het gebruikersproces, in de Campagne van Adobe, zijn:

1. Maak een triggergebeurtenis die is gekoppeld aan een bestaande Adobe Experience Cloud-trigger.
1. Publiceer de triggergebeurtenis.
1. Bepaal de inhoud van het transactiemalplaatje van het bericht.
1. Test de sjabloon (maak een testprofiel en verzend een proefdruk).
1. Publiceer het transactiemalplaatje van het bericht.

Complete gebruiksgevallen worden beschreven in [deze sectie](../../integrating/using/abandonment-triggers-use-cases.md).

## Belangrijke opmerkingen {#important-notes}

Hier volgen enkele belangrijke opmerkingen waarmee u rekening moet houden voordat u de integratie Triggers - Campagne gebruikt:

* Pushmeldingen worden niet ondersteund voor triggers. Alleen e-mail en SMS worden ondersteund.
* U kunt de trigger verrijken met metagegevens die zijn vastgelegd via Analytics, zoals e-mail-id, paginanaam enzovoort.
* U kunt de trigger in overeenstemming brengen met een profiel dat is opgeslagen in Campagnestandaard en de velden van het profiel gebruiken om het bericht aan te passen.
* Zodra een trigger is ontvangen, wordt deze verwerkt, in overeenstemming gebracht en verzonden. Het duurt ongeveer 5 tot 15 minuten afhankelijk van het volume ontvangen triggers, het aantal personalisatievelden die in malplaatje worden gebruikt.

>[!NOTE]
>
>Raadpleeg [Triggers best practices en beperkingen](../../integrating/using/configuring-triggers-in-experience-cloud.md#triggers-best-practices-and-limitations)voor meer informatie over best practices en technische beperkingen.

