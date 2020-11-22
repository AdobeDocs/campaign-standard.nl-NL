---
solution: Campaign Standard
product: campaign
title: De verzendtijd optimaliseren
description: Ontdek hoe u de verzendtijd instelt en het percentage geopende berichten verbetert.
audience: sending
content-type: reference
topic-tags: sheduling-messages
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 100%

---


# De verzendtijd optimaliseren{#optimizing-the-sending-time}

Om het percentage geopende berichten te verbeteren, kunt u handmatig per ontvanger een verzendtijd definiëren. Elk profiel ontvangt het bericht dan op de opgegeven datum en tijd, indien mogelijk.

U kunt de verzendtijd definiëren op leveringsniveau of met gebruik van een workflow.

Voor e-mails zal ernaar gestreefd worden om, afhankelijk van de serverbelasting en het aantal nieuwe pogingen, het bericht te verzenden op de datum en de tijd die voor elke ontvanger is gepland.

* Nieuwe pogingen zijn afhankelijk van de internetprovider en uw reputatie. Het bericht wordt mogelijk niet geaccepteerd bij de eerste poging en er kunnen verschillende nieuwe pogingen worden uitgevoerd. Zie de [Lijst met e-mailkanaalparameters](../../administration/using/configuring-email-channel.md).
* Vertragingen bij het ontvangen van de e-mail kunnen optreden vanwege onvoldoende bandbreedte.

In de [verzendingslogboeken](../../sending/using/monitoring-a-delivery.md#sending-logs) kunt u controleren wanneer het bericht naar elke ontvanger is verzonden.

Er zijn verschillende opties beschikbaar:

* **[!UICONTROL No optimization]**: Berichten worden in de tijdzone van de gebruiker verzonden.

   Als uw tijdzone bijvoorbeeld GMT+1 is en u 9.00 uur invoert in het veld **[!UICONTROL Start sending from]**, zal een ontvanger die in de tijdzone GMT+3 is gevestigd, het bericht om 11.00 uur lokale tijd voor die ontvanger ontvangen.

* **[!UICONTROL Send at the recipient's time zone]**: Alle ontvangers ontvangen het bericht met inachtneming van hun tijdzone.

   Als u bijvoorbeeld 9.00 uur invoert in het veld **[!UICONTROL Start sending from]**, zal een ontvanger die in de tijdzone GMT+3 is gevestigd, het bericht om 9.00 uur lokale tijd voor die ontvanger ontvangen.

   Zie [Berichten verzenden in de tijdzone van de ontvanger](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md).

* **[!UICONTROL Send at a custom date defined by a formula]**: Elke ontvanger zal het bericht ontvangen op de datum en de tijd die door de opgegeven formule is geconfigureerd.

   Zie [De verzenddatum berekenen](../../sending/using/computing-the-sending-date.md).

