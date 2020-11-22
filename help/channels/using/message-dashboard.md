---
solution: Campaign Standard
product: campaign
title: Berichtdashboard
description: Ontdek waar het berichtdashboard uit bestaat, inclusief de actiebalk en de verschillende functionele blokken.
audience: channels
content-type: reference
topic-tags: about-communication-channels
context-tags: delivery,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '587'
ht-degree: 4%

---


# Berichtdashboard{#message-dashboard}

Het berichtdashboard is een werkruimte die uit verschillende pictogrammen - in een actiebar wordt gegroepeerd - en diverse functionele blokken bestaat die u toestaan om de parameters van uw bericht te vestigen en het te verzenden. Deze elementen worden hierna weergegeven.

![](assets/delivery_dashboard_2.png)

## Grijsbalk {#gray-bar}

De grijze balk groepeert verschillende pictogrammen die aan uw bericht zijn gekoppeld.

* **[!UICONTROL Summary]**: toont/verbergt de belangrijkste informatie betreffende het bericht.
* **[!UICONTROL Edit properties]**: Hiermee kunt u de [geavanceerde parameters](../../administration/using/configuring-email-channel.md#list-of-email-properties)van het bericht bewerken.
* **[!UICONTROL Reports]**: geeft u toegang tot de rapporten met betrekking tot het bericht.

**Verwante onderwerpen:**

* [Kanalen configureren](../../administration/using/about-channel-configuration.md)
* [Toegang tot rapporten](../../reporting/using/about-dynamic-reports.md)

## Actiebalk {#action-bar}

De actiebalk heeft verschillende pictogrammen waarmee u kunt communiceren met uw bericht.

![](assets/delivery_dashboard_4.png)

Afhankelijk van de ingestelde parameters en de geboekte vooruitgang zijn bepaalde pictogrammen mogelijk niet beschikbaar.

* **[!UICONTROL Show proofs]**: toont/verbergt de lijst van bewijzen die zijn verzonden, als zij bestaan. Deze knop wordt alleen ingeschakeld nadat u proefdrukken hebt verzonden.

   Zie Proefdrukken [verzenden voor meer informatie over proefdrukken](../../sending/using/sending-proofs.md).

* **[!UICONTROL Send a test]**: Hiermee kunt u de goedkeuringsmodus selecteren die u wilt gebruiken: **[!UICONTROL Email rendering]** (Alleen e-mail) **[!UICONTROL Proof]** of beide. Zie Proefdrukken [verzenden voor meer informatie over testprofielen](../../sending/using/sending-proofs.md). Deze knop wordt alleen ingeschakeld nadat u testprofielen hebt gemaakt.

* **[!UICONTROL Prepare send]**: begint de verzending voor te bereiden. Het **[!UICONTROL Deployment]** blok verschijnt en toont het resultaat van de voorbereiding. Deze knop wordt alleen weergegeven wanneer het doel is ingevoerd. U kunt de voorbereiding op elk gewenst moment stoppen met de bijbehorende knop. For more on message preparation, refer to [Preparing the send](../../sending/using/preparing-the-send.md).

* **[!UICONTROL Confirm send]**: bevestigt het verzenden van het bericht. De verzendende statistieken verschijnen in het **[!UICONTROL Deployment]** blok. Deze knop wordt alleen weergegeven nadat het verzenden is voorbereid. U kunt het verzenden op elk gewenst moment stoppen of pauzeren met de **knoppen Stoppen** en **[!UICONTROL Pause]** Stoppen. Voor meer bij het bevestigen van het verzenden, verwijs naar het [Verzenden van berichten](../../sending/using/confirming-the-send.md).

## Blokken {#blocks}

Het hoofdscherm bestaat uit verschillende blokken. Klik in een blok om het bijbehorende parameterscherm te openen:

![](assets/delivery_dashboard_3.png)

* **[!UICONTROL Deployment]**: Hiermee kunt u de voortgang van het voorbereiden of verzenden van berichten volgen. Klik op de knop in de rechterbenedensectie van dit blok voor toegang tot de logboeken voor verzenden en analyse. Dit blok verschijnt slechts zodra het verzenden is voorbereid. Meer hierover. See [Confirming send](../../sending/using/confirming-the-send.md).
* **[!UICONTROL Audience]**: Hiermee kunt u zowel het hoofddoel van het bericht als de testprofielen vaststellen. Zie [Doelgroepen maken](../../audiences/using/creating-audiences.md).
* **[!UICONTROL Schedule]**: kunt u opgeven op welke datum uw bericht wordt verzonden. Zie [Planning](../../sending/using/about-scheduling-messages.md).
* **[!UICONTROL Content]**: Hiermee kunt u de inhoud van het bericht definiëren en er een voorvertoning van weergeven. See [Key steps to send a message](../../channels/using/key-steps-to-send-a-message.md).

## Waarschuwingen {#warnings}

In sommige gevallen kan een waarschuwing in een gele banner boven op het berichtdashboard worden weergegeven.

![](assets/delivery_dashboard_warnings.png)

Hieronder volgt een lijst met de berichten die kunnen worden weergegeven:

* *&quot;De optie voor de SMTP-testmodus is ingeschakeld voor deze e-mail: er worden geen berichten verzonden.&quot;*

   Zie [deze sectie](../../administration/using/configuring-email-channel.md#smtp-test-mode)voor meer informatie.

* *&quot;Het verpletteren van externe rekening is onbruikbaar gemaakt.&quot;*

   Zie [Externe rekeningen](../../administration/using/external-accounts.md)voor meer informatie.

* *&quot;De berichten kunnen niet worden verzonden omdat de huidige IP affiniteit niet door om het even welk verzendend proces wordt behandeld.&quot;*

   Als u dit bericht ziet, is er een kwestie op het IP niveau van de affiniteitdefinitie of op het verzendende procesniveau. Neem contact op met de beheerder van de Adobe.

* *&quot;Dit is een uit-van-de-doos transactionele berichtmalplaatje. Als u het wilt wijzigen, moet u het dupliceren en aan uw exemplaar werken.&quot;*

   Sommige van deze uit-van-de-doos transactionele berichtmalplaatjes zijn ingebouwde het landen paginasjablonen. Zie [deze sectie](../../channels/using/landing-page-templates.md)voor meer informatie.

* *&quot;Dit bericht is een sjabloon voor technische transactieberichten. U kunt deze niet wijzigen of publiceren.&quot;*

   Deze waarschuwing wordt weergegeven in lege transactiemalplaatjes die niet bewerkbaar zijn. For more on transactional messages, see [this section](../../channels/using/getting-started-with-transactional-msg.md).
