---
title: De verzending bevestigen
description: Leer hoe u de berichtvoorbereiding voltooit.
page-status-flag: never-activated
uuid: 1eaecb32-ffd2-45d0-a8b4-f97bee59a1bd
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: sending-and-tracking-messages
discoiquuid: 8bb160b1-7de9-4c1f-bb89-b2e5fdafed41
context-tags: delivery,deployment,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# De verzending bevestigen{#confirming-the-send}

Nadat u de berichten hebt voorbereid en de goedkeuringsstappen zijn uitgevoerd, kunt u deze verzenden. Raadpleeg [Verzenden](../../sending/using/preparing-the-send.md)voorbereiden voor meer informatie over het voorbereiden van berichten.

Alleen gebruikers met de **[!UICONTROL Start deliveries]** rol kunnen verzenden bevestigen. Raadpleeg voor meer informatie de sectie [Lijst met rollen](../../administration/using/list-of-roles.md) .

Gebruikers zonder deze rol zien het volgende bericht:

![](assets/confirm_delivery_2.png)

Klik op de **[!UICONTROL Confirm send]** knop op de actiebalk van het bericht om de levering te verzenden.

![](assets/confirm_delivery.png)

Je wordt gevraagd de verzending definitief af te ronden door op de **[!UICONTROL OK]** knop te klikken.

![](assets/confirm_delivery1.png)

Het bericht wordt verzonden.

>[!NOTE]
>
>Als het bericht gepland is, zal het worden verzonden wanneer het verzenden van tijd wordt bereikt. For more on scheduling messages, refer to [this section](../../sending/using/about-scheduling-messages.md).

Als u een terugkerende levering zonder samenvoegingsperiode gebruikt, kunt u een bevestiging aanvragen voordat de levering wordt verzonden. Open hiertoe het **[!UICONTROL Schedule]** blok van het leveringsdashboard en activeer de toegewezen optie.

![](assets/confirmation_recurring_deliveries.png)

Het **[!UICONTROL Deployment]** blok toont de vooruitgang van het verzenden.

Zodra het bericht wordt verzonden naar de contacten, toont de **[!UICONTROL Deployment]** streek uw gegevens van KPIs (de Zeer belangrijke Indicator van Prestaties), die omvatten:

* Het aantal te leveren berichten
* Het aantal verzonden berichten
* Het percentage geleverde berichten
* Het percentage fouten en stuitingen
* Het percentage open berichten
* Het percentage klikken in de berichten (voor e-mails)

   >[!NOTE]
   >
   >De **[!UICONTROL Open rate]** en **[!UICONTROL Click-through rate]** worden elk uur bijgewerkt.

![](assets/sending_delivery.png)

Als KPIs te lang duurt om bij te werken of geen rekening te houden met de resultaten van de verzendende logboeken, klik de **[!UICONTROL Compute stats]** knoop in het **[!UICONTROL Deployment]** venster.

![](assets/sending_delivery7.png)

Het bericht kan in de geschiedenis van één van de cliëntprofielen worden bekeken die deel van het publiek uitmaken. Zie [Geïntegreerd klantprofiel](../../audiences/using/integrated-customer-profile.md).

Zodra een bericht wordt verzonden, kunt u het gedrag van zijn ontvangers volgen, en het controleren om zijn effect te meten. Raadpleeg de volgende secties voor meer informatie:

* [Berichten bijhouden](../../sending/using/tracking-messages.md)
* [Toezicht op levering](../../sending/using/monitoring-a-delivery.md)

