---
title: Sms-berichten personaliseren
description: Ontdek de specificiteit van de transliteratie-opties bij het personaliseren van sms-berichten.
page-status-flag: never-activated
uuid: 123fe70c-c279-40a3-88b6-6bfb2453ec83
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: sms-messages
discoiquuid: 7c64785c-e3c2-4caa-a547-002990aae3f9
delivercontext-tags: deliveryCreation,wizard;delivery,smsContent,back;delivery,smsContent,back
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 100%

---


# Sms-berichten personaliseren{#personalizing-sms-messages}

De principes voor het personaliseren van sms-berichten zijn dezelfde als die voor [e-mails](../../designing/using/personalization.md#inserting-a-personalization-field). U moet echter op de hoogte zijn van de transliteratie-opties, aangezien deze van invloed kunnen zijn op de codering en daarmee op het aantal sms-berichten dat moet worden verzonden. Raadpleeg de sectie [Transliteratie en sms-lengte](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration) voor meer informatie.

Hier bespreken we een voorbeeld van een sms-bericht met personalisatievelden dat, afhankelijk van het feit of er al dan niet voor transliteratie wordt gekozen, niet hetzelfde aantal verzendingen zal genereren:

**Hallo &lt; FirstName > &lt; LastName >, er zijn nu nieuwe producten beschikbaar. Kom maar eens kijken in de winkel!**

* Voor een ontvanger met de naam John Smith waarin geen speciale tekens voorkomen, kiest Adobe Campaign voor GSM-codering met maximaal 160 tekens per sms-bericht. Het bericht wordt dus in één keer verzonden.
* Voor een ontvanger met de naam Raphaël Forêt kunnen de tekens &#39;ë&#39; en &#39;ê&#39; niet worden gecodeerd in GSM. Afhankelijk van het feit of transliteratie is ingeschakeld, zijn er in Adobe Campaign twee mogelijkheden:

   * Als transliteratie is geautoriseerd, worden &#39;ë&#39; en &#39;ê&#39; vervangen door &#39;e&#39;, wat betekent dat GSM-codering kan worden gebruikt en dat de sms uit maximaal 160 tekens kan bestaan. Dit bericht wordt als één sms-bericht verzonden, maar het wordt enigszins gewijzigd.
   * Als transliteratie niet is geautoriseerd, kiest Adobe Campaign ervoor het bericht in binaire notatie (Unicode) te verzenden: alle tekens worden daarom als zodanig verzonden. Aangezien er in Unicode een beperking geldt van 70 tekens per sms-bericht, moet Adobe Campagne het bericht in twee delen verzenden.

>[!NOTE]
>
>Het algoritme dat automatisch de beste codering kiest, wordt onafhankelijk uitgevoerd voor elk bericht, geval voor geval. Op deze manier worden alleen de gepersonaliseerde berichten die Unicode-codering vereisen in Unicode verzonden; voor alle andere wordt GSM-codering gebruikt.

## Sms-afzender {#sms-sender}

U kunt de naam van de afzender van de sms personaliseren. Zie de sectie [Sms-configuratie](../../administration/using/configuring-sms-channel.md#configuring-sms-properties) voor meer informatie hierover.
