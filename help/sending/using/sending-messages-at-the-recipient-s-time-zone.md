---
title: Berichten verzenden in de tijdzone van de ontvanger
description: Ontdek hoe u berichten kunt verzenden in de tijdzone van de ontvanger.
page-status-flag: never-activated
uuid: 70228c07-451f-4ddb-8d26-92a5a4814e3a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: sheduling-messages
discoiquuid: daa980ba-8c7c-4673-a68f-379d63e4b8bd
internal: n
snippet: y
translation-type: ht
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e
workflow-type: ht
source-wordcount: '375'
ht-degree: 100%

---


# Berichten verzenden in de tijdzone van de ontvanger{#sending-messages-at-the-recipient-s-time-zone}

Wanneer u een campagne beheert waarbij de datum en de tijd belangrijk zijn, kunt u een levering plannen die rekening houdt met de lokale tijd van elke ontvanger. Elke ontvanger ontvangt dan e-mails, sms&#39;en of pushmeldingen op het door u geplande tijdstip in hun eigen tijdzone.

>[!NOTE]
>
>Om deze functionaliteit te kunnen gebruiken, dient u voor alle profielen die als doel zijn ingesteld voor uw levering een tijdzone op te geven in de sectie **[!UICONTROL Address]** van hun eigenschappen. Raadpleeg deze [sectie](../../audiences/using/editing-profiles.md)voor meer informatie over het openen van profieleigenschappen.

Als u een levering in de tijdzone van de ontvanger wilt verzenden, kunt u ook de activiteit **[!UICONTROL Scheduler]** in een workflow gebruiken. Raadpleeg [deze pagina](../../automating/using/scheduler.md) voor meer informatie.

In het volgende voorbeeld willen we aan alle klanten over de hele wereld een promotiecode sturen die alleen geldig is op Valentijnsdag. Om voldoende tijd te bieden om de code die dag dag te gebruiken, moeten alle klanten uw bericht op 14 februari om 8.00 uur volgens hun tijdzone ontvangen.

1. Start op het tabblad **[!UICONTROL Marketing activities]** met het maken van de levering, in dit geval een e-mail. Raadpleeg deze [sectie](../../channels/using/creating-an-email.md) voor meer informatie over het maken van een levering.
1. Nadat u de e-mail voor Valentijnsdag hebt ontworpen, klikt u op **[!UICONTROL Create]** om het leveringsdashboard te openen. Raadpleeg deze [pagina](../../designing/using/personalization.md#example-email-personalization) voor meer informatie over het ontwerpen van e-mails.

   ![](assets/send-time_opt_valentine_1.png)

1. Selecteer het blok **[!UICONTROL Schedule]** in het leveringsdashboard.

   ![](assets/send-time_opt_valentine_2.png)

1. Selecteer de hieronder opgegeven optie **[!UICONTROL Messages to be sent automatically on the date]**. Stel vervolgens in het veld **[!UICONTROL Start sending from]** de contactdatum in, in dit geval 14 februari om 08.00 uur, zodat elke ontvanger de e-mail op Valentijnsdag ontvangt.

   ![](assets/send-time_opt_valentine.png)

1. Selecteer in het veld **[!UICONTROL Time zone of the contact date]** in welke tijdzone uw levering standaard moet worden verzonden.

   Als de **[!UICONTROL Time zone]** van een profiel ingesteld blijft op **[!UICONTROL Default]**, zullen de ontvangers de levering ontvangen afhankelijk van de hier gekozen tijdzone.

1. Kies in het vervolgkeuzemenu **[!UICONTROL Optimize the sending time per recipient]** de optie **[!UICONTROL Send at the recipient's time zone]**. Hierdoor zullen ontvangers de e-mail voor Valentijnsdag ontvangen op 14 februari volgens hun tijdzone.

   ![](assets/send-time_opt_valentine_3.png)

1. Nadat u de planning voor uw levering hebt bevestigd, klikt u op de knop **[!UICONTROL Prepare]** en vervolgens op **[!UICONTROL Confirm]** voor uw levering.

   Bevestig de verzending ten minste 24 uur van tevoren. Anders ontvangen sommige ontvangers, afhankelijk van hun locatie, de levering mogelijk vóór Valentijnsdag.

   ![](assets/send-time_opt_valentine_4.png)

Waar de ontvangers zich ook bevinden, zij ontvangen allemaal het bericht op 14 februari om 8.00 uur lokale tijd.
