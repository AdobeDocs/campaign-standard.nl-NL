---
title: Informatie over het plannen van berichten
description: Leer hoe u uw berichten kunt plannen.
page-status-flag: never-activated
uuid: 286fceee-65a9-4cb9-b205-9ce5d024675c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: sheduling-messages
discoiquuid: 9c7fd670-bba9-4f3c-8cb1-87397a1acd27
context-tags: delivery,schedule,back
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 100%

---


# Informatie over het plannen van berichten{#about-scheduling-messages}

>[!CAUTION]
>
>Wanneer u wijzigingen aanbrengt in de planning van een levering, moet u de levering opnieuw voorbereiden door op de knop **Voorbereiden** te klikken voordat u op **Bevestigen** klikt.

In het berichtdashboard kunt u met het blok **[!UICONTROL Schedule]** bepalen wanneer berichten (e-mail-, sms- of pushmeldingen) worden verzonden.

![](assets/delivery_dashboard.png)

Met de **[!UICONTROL Schedule]**-eigenschappen kunt u verzendopties instellen voor e-mails, sms- of pushmeldingen:

* **[!UICONTROL Messages to be sent once confirmed]**: Berichten worden verzonden zodra de verzending wordt bevestigd. Zie [De verzending bevestigen](../../sending/using/confirming-the-send.md).

   ![](assets/delivery_planning_1.png)

* **[!UICONTROL Messages to be sent automatically on the date specified below]**: Berichten worden op een latere datum en tijd verzonden. Geef de **contactdatum** op in het veld **Beginnen met verzenden vanaf**.

   U kunt het verzenden voorbereiden en bevestigen, maar berichten worden pas verzonden vanaf de geselecteerde datum en tijd. Het voorbereiden en het bevestigen van de verzending worden gepresenteerd in de secties [De verzending voorbereiden](../../sending/using/preparing-the-send.md) en [De verzending bevestigen](../../sending/using/confirming-the-send.md).

   Met behulp van de vervolgkeuzelijst **[!UICONTROL Time zone of the contact date]** kunt u de tijdzone wijzigen die voor de verzendtijd in aanmerking wordt genomen. Als u bijvoorbeeld 09:00 uur in het veld **[!UICONTROL Start sending from]** invoert en als u Brussel, Kopenhagen, Madrid, Parijs (GMT+1) selecteert in de vervolgkeuzelijst **[!UICONTROL Time zone of the contact date]**, ontvangen alle ontvangers het bericht om 09:00 uur Parijse tijd. Daarom zal een ontvanger in Moskou (GMT+3) het bericht om 11:00 uur Moskouse tijd ontvangen.

   Als u het verzenden handmatig wilt bevestigen, schakelt u de optie **[!UICONTROL Request confirmation before sending messages]** in. Deze optie is standaard ingeschakeld.

   ![](assets/delivery_planning.png)

>[!CAUTION]
>
>Bij het dupliceren van een levering worden alle planningsinstellingen verwijderd. Tenzij u een nieuwe contactdatum plant, wordt de gedupliceerde levering verzonden zodra het verzenden wordt bevestigd.

**Verwante onderwerpen**:

* [De verzendtijd optimaliseren](../../sending/using/optimizing-the-sending-time.md)
* [Berichten verzenden in de tijdzone van de ontvanger](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)
* [De verzenddatum berekenen](../../sending/using/computing-the-sending-date.md)

