---
solution: Campaign Standard
product: campaign
title: Transactionele berichten configureren
description: Leer hoe te om transactioneel overseinen te vormen.
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
translation-type: tm+mt
source-git-commit: caa41d6c727385bd6e77f64750872f191a5ad040
workflow-type: tm+mt
source-wordcount: '600'
ht-degree: 7%

---


# Een transactionele gebeurtenis {#publishing-transactional-event} publiceren

Nadat [configuration](../../channels/using/configuring-transactional-event.md) is voltooid, kan de gebeurtenis worden gepubliceerd. De stappen voor het voorvertonen, publiceren, publiceren en verwijderen van een gebeurtenis worden hieronder beschreven.

>[!IMPORTANT]
>
>Alleen [Functionele beheerders](../../administration/using/users-management.md#functional-administrators) <!--being part of the **[!UICONTROL All]** [organizational unit](../../administration/using/organizational-units.md) -->hebben de juiste rechten om gebeurtenisconfiguraties te publiceren.

Een grafiek die het volledige transactieoverseinenpublicatieproces, met inbegrip van het publiceren en unpublishing van gebeurtenisconfiguraties illustreert, is beschikbaar in [deze sectie](../../channels/using/publishing-transactional-message.md).

Zodra de publicatie is voltooid:
* Het overeenkomstige transactiemelding wordt automatisch gecreeerd. Zie [Transactieberichten bewerken](../../channels/using/editing-transactional-message.md).
* De API die door uw websiteontwikkelaar wordt gebruikt, wordt opgesteld en de transactionele gebeurtenissen kunnen nu worden verzonden. Zie [De gebeurtenis activeren](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger).

## Een gebeurtenis voorvertonen en publiceren {#previewing-and-publishing-the-event}

Voordat u de gebeurtenis kunt gebruiken, moet u deze voorvertonen en publiceren.

1. Klik op de knop **[!UICONTROL API preview]** om een simulatie van de REST API weer te geven die door uw websiteontwikkelaar wordt gebruikt voordat deze wordt gepubliceerd.

   Nadat de gebeurtenis is gepubliceerd, kunt u met deze knop ook een voorvertoning van de API in productie zien. Zie [De gebeurtenis activeren](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger).

   ![](assets/message-center_api_preview.png)

   >[!NOTE]
   >
   >De REST API varieert afhankelijk van het geselecteerde kanaal en de geselecteerde doeldimensie. Raadpleeg [deze sectie](../../channels/using/configuring-transactional-event.md#transactional-event-specific-configurations) voor meer informatie over de verschillende configuraties.

1. Klik op **[!UICONTROL Publish]** om de publicatie te starten.

   ![](assets/message-center_pub.png)

   De API die door uw websiteontwikkelaar wordt gebruikt, wordt opgesteld en de transactionele gebeurtenissen kunnen nu worden verzonden.

1. U kunt de publicatielogboeken weergeven op het bijbehorende tabblad.

   ![](assets/message-center_logs.png)

   >[!IMPORTANT]
   >
   >Telkens wanneer u de gebeurtenis wijzigt, moet u **[!UICONTROL Publish]** opnieuw klikken om de bijgewerkte REST API te genereren die door uw websiteontwikkelaar zal worden gebruikt.

   Zodra de gebeurtenis is gepubliceerd, wordt een [transactioneel bericht](../../channels/using/editing-transactional-message.md) verbonden aan de nieuwe gebeurtenis automatisch gecreeerd.

1. U kunt tot dit transactiebericht direct toegang hebben door de verbinding die in het linkerzijgebied wordt gevestigd.

   ![](assets/message-center_messagegeneration.png)

   >[!NOTE]
   >
   >Als de gebeurtenis het verzenden van een transactiemelding moet activeren, moet u het bericht wijzigen en publiceren dat net is gemaakt. Zie [Secties Bewerken](../../channels/using/editing-transactional-message.md) en [Een transactioneel bericht](../../channels/using/publishing-transactional-message.md) publiceren. U moet deze triggergebeurtenis [ook integreren in uw website.](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger)

1. Zodra Adobe Campaign gebeurtenissen ontvangt die betrekking hebben op deze gebeurtenisconfiguratie, kunt u op de **[!UICONTROL Latest transactional events]**-koppeling onder de sectie **[!UICONTROL History]** klikken om toegang te krijgen tot de meest recente gebeurtenissen die door uw externe service worden verzonden en door Adobe Campaign worden verwerkt.

![](assets/message-center_latest-events.png)

De gebeurtenissen (in JSON-indeling) worden weergegeven van de meest recente tot de oudste. Met deze lijst kunt u gegevens zoals de inhoud of de status van een gebeurtenis controleren voor controle en foutopsporing.

## Publiceren van een gebeurtenis {#unpublishing-an-event} ongedaan maken

Met de knop **[!UICONTROL Unpublish]** kunt u de publicatie van de gebeurtenis annuleren. Hierdoor wordt de bron die overeenkomt met de gebeurtenis die u eerder hebt gemaakt, verwijderd uit de REST API.

Zelfs als de gebeurtenis via uw website wordt geactiveerd, worden de bijbehorende berichten niet meer verzonden en niet opgeslagen in de database.

![](assets/message-center_unpublish.png)

>[!NOTE]
>
>Als u het overeenkomstige transactiemelding reeds hebt gepubliceerd, wordt de transactieberichtpublicatie ook geannuleerd. Zie [Publicatie van een transactiebericht opheffen](../../channels/using/publishing-transactional-message.md#unpublishing-a-transactional-message).

Klik op de knop **[!UICONTROL Publish]** om een nieuwe REST API te genereren.

<!--## Transactional messaging publication process {#transactional-messaging-pub-process}

The chart below illustrates the transactional messaging publication process.

![](assets/message-center_pub-process.png)

For more on publishing, pausing and unpublishing a transactional message, see [this section](../../channels/using/publishing-transactional-message.md).-->

## Een gebeurtenis {#deleting-an-event} verwijderen

Nadat een gebeurtenis niet gepubliceerd is of nog niet gepubliceerd is, kunt u deze verwijderen uit de lijst met gebeurtenisconfiguraties. Dit doet u als volgt:

1. Klik in de linkerbovenhoek op het logo **[!UICONTROL Adobe Campaign]** en selecteer **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]**.
1. Houd de muis boven de gebeurtenisconfiguratie van uw keuze en selecteer de knop **[!UICONTROL Delete element]**.

   ![](assets/message-center_delete-button.png)

   >[!NOTE]
   >
   >Zorg ervoor de gebeurtenisconfiguratie de **[!UICONTROL Draft]** status heeft, anders zult u niet het kunnen schrappen. De status **[!UICONTROL Draft]** is van toepassing op een gebeurtenis die nog niet is gepubliceerd of die [niet is gepubliceerd](#unpublishing-an-event).

1. Klik op de knop **[!UICONTROL Confirm]**.

   ![](assets/message-center_delete-confirm.png)

>[!IMPORTANT]
>
>Als u een gebeurtenisconfiguratie verwijdert die is gepubliceerd en al wordt gebruikt, worden ook de bijbehorende transactiemeldingen en de bijbehorende verzendings- en trackinglogboeken verwijderd.
