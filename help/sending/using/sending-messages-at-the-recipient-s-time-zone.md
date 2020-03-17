---
title: Het verzenden van berichten bij de tijdzone van de ontvanger
description: Leer hoe te om berichten bij de tijdzone van de ontvanger te verzenden.
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
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Het verzenden van berichten bij de tijdzone van de ontvanger{#sending-messages-at-the-recipient-s-time-zone}

Wanneer het leiden van een campagne waarin de datum en de tijd belangrijk zijn, kunt u een levering plannen die de lokale tijd van elke ontvanger rekening houdt: ze ontvangen e-mail-, SMS- of pushberichten op het geplande tijdstip in hun eigen tijdzone.

>[!NOTE]
>
>Om deze functionaliteit te gebruiken, zorg ervoor dat alle profielen die door uw levering worden bedoeld een tijdzone hebben die in de **[!UICONTROL Address]** sectie van hun eigenschappen wordt gespecificeerd. Raadpleeg deze [sectie](../../audiences/using/editing-profiles.md)voor meer informatie over het benaderen van profieleigenschappen.

Om een levering bij de tijdzone van de ontvanger te verzenden, kunt u de **[!UICONTROL Scheduler]** activiteit in een werkschema ook gebruiken. Raadpleeg deze [pagina](../../automating/using/scheduler.md)voor meer informatie.

In het volgende voorbeeld willen we een promotiecode sturen die alleen geldig is op Valentijnsdag aan alle klanten over de hele wereld. Om voldoende tijd te verstrekken om het tijdens de dag te gebruiken, moeten alle klanten uw bericht op 14 Februari om 8:00 AM afhankelijk van hun tijdzones ontvangen.

1. Start op het **[!UICONTROL Marketing activities]** tabblad de levering, in ons geval een e-mail. Raadpleeg deze [sectie](../../channels/using/creating-an-email.md)voor meer informatie over het maken van de aflevering.
1. Nadat u de Valentijnsdag-e-mail hebt ontworpen, klikt u **[!UICONTROL Create]** om het dashboard voor levering te openen. Raadpleeg deze [pagina](../../designing/using/personalization.md#example-email-personalization)voor meer informatie over ontwerpen via e-mail.

   ![](assets/send-time_opt_valentine_1.png)

1. Selecteer het **[!UICONTROL Schedule]** blok in het leveringsdashboard.

   ![](assets/send-time_opt_valentine_2.png)

1. Selecteer de hieronder opgegeven **[!UICONTROL Messages to be sent automatically on the date]** optie. Stel vervolgens in het **[!UICONTROL Start sending from]** veld de contactdatum in, in ons geval op 14 februari om 8.00 uur, zodat elke ontvanger het op Valentijnsdag ontvangt.

   ![](assets/send-time_opt_valentine.png)

1. Selecteer in het **[!UICONTROL Time zone of the contact date]** veld in welke tijdzone uw levering standaard moet worden verzonden.

   Als een profiel als **[!UICONTROL Time zone]** wordt verlaten **[!UICONTROL Default]**, zullen de ontvangers de levering afhankelijk van de gekozen tijdzone hier ontvangen.

1. Kies in het **[!UICONTROL Optimize the sending time per recipient]** keuzemenu de optie **[!UICONTROL Send at the recipient's time zone]**. Hierdoor kunnen ontvangers de dag-e-mail van Valentine ontvangen op 14 februari, afhankelijk van hun tijdzone.

   ![](assets/send-time_opt_valentine_3.png)

1. Na bevestiging van uw leveringsschema, klik de **[!UICONTROL Prepare]** knoop dan **[!UICONTROL Confirm]** uw levering.

   Bevestig de verzending ten minste 24 uur van tevoren. Anders, afhankelijk van hun plaats, zouden sommige ontvangers de levering vóór de daadwerkelijke de daggebeurtenis van Valentine kunnen ontvangen.

   ![](assets/send-time_opt_valentine_4.png)

Geen kwestie waar zij worden gevestigd, zullen alle ontvangers het bericht op 14 Februari om 8:00 hun lokale tijd ontvangen.
