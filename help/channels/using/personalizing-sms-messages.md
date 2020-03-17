---
title: SMS-berichten aanpassen
description: Ontdek de specificiteit van de vertalingsopties wanneer het personaliseren van SMS berichten.
page-status-flag: never-activated
uuid: 123fe70c-c279-40a3-88b6-6bfb2453ec83
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: sms-messages
discoiquuid: 7c64785c-e3c2-4caa-a547-002990aae3f9
delivercontext-tags: deliveryCreation,wizard;delivery,smsContent,back;delivery,smsContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# SMS-berichten aanpassen{#personalizing-sms-messages}

De beginselen voor het personaliseren van SMS-berichten zijn dezelfde als die voor [e-mails](../../designing/using/personalization.md#inserting-a-personalization-field). U moet echter op de hoogte zijn van de omzettingsopties, aangezien deze van invloed kunnen zijn op de codering en daarmee op het aantal sms-berichten dat moet worden verzonden. Raadpleeg het gedeelte [Vertaling en sms-lengte](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration) voor meer informatie.

Hier nemen we een voorbeeld-SMS-bericht met personalisatievelden die, afhankelijk van of transliteratie al dan niet is geselecteerd, niet hetzelfde aantal verzendingen genereren:

**Hee &lt; Voornaam > &lt; Achternaam >, nieuwe producten zijn nu beschikbaar. Kom en controleer ze in de winkel!**

* Voor een ontvanger met de naam &#39;John Smith&#39;, omdat deze geen speciale tekens bevat, kiest Adobe Campaign GSM-codering waarmee maximaal 160 tekens per SMS-bericht worden geautoriseerd. De boodschap zal derhalve in één deel worden verzonden.
* Voor een ontvanger met de naam &#39;Raphaël Forêt&#39; kunnen de tekens &#39;ë&#39; en &#39;ê&#39; niet in GSM worden gecodeerd. Afhankelijk van het feit of transliteratie is ingeschakeld, kan Adobe Campaign kiezen uit twee gedragingen:

   * Als transliteratie is geautoriseerd, worden &#39;ë&#39; en &#39;ê&#39; vervangen door &#39;e&#39;, wat betekent dat GSM-codering kan worden gebruikt en dat in het SMS maximaal 160 tekens kunnen worden gebruikt. Dit bericht wordt als één SMS-bericht verzonden, maar het wordt enigszins gewijzigd.
   * Als transliteratie niet is geautoriseerd, kiest Adobe Campaign ervoor het bericht in binaire notatie (Unicode) te verzenden: alle tekens worden daarom als zodanig verzonden . Aangezien de SMS-berichten in Unicode beperkt zijn tot 70 tekens, moet Adobe Campagne het bericht in twee delen verzenden.

>[!NOTE]
>
>Het algoritme dat automatisch de beste codering kiest, wordt onafhankelijk uitgevoerd voor elk bericht, geval voor geval. Op deze manier worden alleen de gepersonaliseerde berichten die Unicode-codering vereisen, verzonden in Unicode. alle anderen gebruiken GSM-codering.

## SMS-afzender {#sms-sender}

U kunt de naam van de afzender van SMS personaliseren. Voor meer op dit, verwijs naar de de configuratiesectie [van](../../administration/using/configuring-sms-channel.md#configuring-sms-properties) SMS.
