---
title: De verzendtijd optimaliseren
description: Leer hoe u verzendtijd instelt en de open snelheid van uw berichten verbetert.
page-status-flag: never-activated
uuid: c2c13934-9819-4e18-b5c7-60915c907f37
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: sheduling-messages
discoiquuid: 609355f6-9003-41b9-9981-ea787419fbf5
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# De verzendtijd optimaliseren{#optimizing-the-sending-time}

Om het open tarief van uw berichten te verbeteren, kunt u een verzendende tijd per ontvanger manueel bepalen. Elk profiel ontvangt het bericht op de opgegeven datum en tijd, indien mogelijk.

Het bepalen van een verzendende tijd kan op het leveringsniveau of het gebruiken van een werkschema worden gedaan.

Voor e-mailberichten, afhankelijk van de serverlading en de hoeveelheid herpogingen, zullen de best inspanning worden gedaan om het bericht op de datum en de tijd te verzenden die voor elke ontvanger wordt gepland.

* De pogingen hangen van de leverancier van Internet en uw reputatie af. Het bericht wordt mogelijk niet geaccepteerd bij de eerste poging en er kunnen verschillende keren opnieuw pogingen worden uitgevoerd. Zie [Lijst met parameters](../../administration/using/configuring-email-channel.md)voor e-mailkanalen.
* Vertragingen bij het ontvangen van de e-mail kunnen optreden vanwege onvoldoende bandbreedte.

U kunt bekijken wanneer het bericht werd verzonden naar elke ontvanger in de [verzendende logboeken](../../sending/using/monitoring-a-delivery.md#sending-logs).

Er zijn verschillende opties beschikbaar:

* **[!UICONTROL No optimization]**: Berichten worden op het moment van de gebruiker verzonden.

   Bijvoorbeeld, als uw tijdzone GMT+1 is en als u 9:00 AM op het **[!UICONTROL Start sending from]** gebied ingaat, zal een ontvanger die in de GMT+3 tijdzone wordt gevestigd het bericht bij 11:00 lokale tijd AM voor die ontvanger ontvangen.

* **[!UICONTROL Send at the recipient's time zone]**: Alle ontvangers zullen het bericht met hun tijdzone in acht nemen ontvangen.

   Bijvoorbeeld, als u 9:00 AM op het **[!UICONTROL Start sending from]** gebied ingaat, zal een ontvanger die in de GMT+3 tijdzone wordt gevestigd het bericht bij 9:00 AM lokale tijd voor die ontvanger ontvangen.

   Zie het [Verzenden van berichten bij de tijdzone](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)van de ontvanger.

* **[!UICONTROL Send at a custom date defined by a formula]**: Elke ontvanger zal het bericht op de datum en de tijd ontvangen die door de gespecificeerde formule wordt gevormd.

   Zie De verzenddatum [berekenen](../../sending/using/computing-the-sending-date.md).

