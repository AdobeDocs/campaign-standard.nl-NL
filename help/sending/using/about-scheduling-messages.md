---
solution: Campaign Standard
product: campaign
title: Informatie over het plannen van berichten
description: Leer hoe u uw berichten kunt plannen.
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: Tijdoptimalisatie verzenden
role: User
exl-id: 6b26615b-4aa6-401d-a12d-25cef4cd0524
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '271'
ht-degree: 98%

---

# Informatie over berichten plannen{#about-scheduling-messages}

>[!IMPORTANT]
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

>[!IMPORTANT]
>
>Bij het dupliceren van een levering worden alle planningsinstellingen verwijderd. Tenzij u een nieuwe contactdatum plant, wordt de gedupliceerde levering verzonden zodra het verzenden wordt bevestigd.

**Verwante onderwerpen**:

* [De verzendtijd optimaliseren](../../sending/using/optimizing-the-sending-time.md)
* [Berichten verzenden in de tijdzone van de ontvanger](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)
* [De verzenddatum berekenen](../../sending/using/computing-the-sending-date.md)
