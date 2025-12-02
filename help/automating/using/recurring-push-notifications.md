---
title: Een terugkerende pushmelding verzenden met een workflow
description: In dit voorbeeld wordt elke eerste dag van de maand om 21.00 uur een gepersonaliseerd pushbericht verzonden naar de abonnees van uw mobiele toepassing, afhankelijk van hun tijdzones
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: d5e6034c-3673-4069-ac0b-49c7ad07259d
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '484'
ht-degree: 4%

---

# Een terugkerende pushmelding verzenden met een workflow {#sending-a-recurring-push-notification-with-a-workflow}

![](assets/wkf_push_example_1.png)

In dit voorbeeld wordt elke eerste dag van de maand om 21.00 uur een persoonlijke pushmelding verzonden naar de abonnees van uw mobiele toepassing, afhankelijk van hun tijdzone.

Voer de volgende stappen uit om de workflow te maken:

1. De [ Planner ](../../automating/using/scheduler.md) activiteit staat u toe om het werkschemadagen vóór het begin van de levering te beginnen om het bericht aan elke abonnee bij 8 pm in om het even welke bepaalde tijdzone te kunnen verzenden:

   * Selecteer Maandelijks in het veld **[!UICONTROL Execution frequency]** .
   * Selecteer 8 pm in het veld **[!UICONTROL Time]** .
   * Kies op welke dag de levering elke maand wordt verzonden.
   * Selecteer een begindatum voor de workflow, ten minste één dag voor het begin van de levering. Anders, zouden sommige ontvangers het bericht een dag later kunnen ontvangen als de geselecteerde tijd reeds in hun tijdzones is overgegaan.
   * Selecteer op het tabblad **[!UICONTROL Execution options]** in het veld **[!UICONTROL Time zone]** de tijdzone waarin de workflow moet beginnen. Hier begint de workflow bijvoorbeeld om 20.00 uur Stille-Oceaantijd, één week voor de eerste dag van de maand, zodat er enige tijd is om de leveringen voor alle toepasselijke tijdzones te maken.

   >[!NOTE]
   >
   >Standaard is de geselecteerde tijdzone de tijdzone die is gedefinieerd in de workfloweigenschappen (zie [Een workflow maken](../../automating/using/building-a-workflow.md)).

   ![](assets/wkf_push_example_5.png)

1. De [ activiteit van de Vraag ](../../automating/using/query.md) staat u toe om uw klanten van VIP te richten die tussen 20-30 worden gerijpt, die aan uw mobiele toepassing zijn ingetekend en die niet e-mail open u verzond:

   * Selecteer een publiek (uw klanten van VIP) en filter op hun leeftijd.
   * Sleep en laat vallen de **Abonnementen aan een toepassings** element in de werkruimte. Selecteer **bestaat** en selecteer de mobiele toepassing die u wilt gebruiken.
   * Selecteer het e-mailbericht dat u naar uw klanten hebt verzonden.
   * De belemmering en laat vallen het **Logboeken van de Levering (logboeken)** element in de werkruimte en selecteert **bestaat** om alle klanten te richten die e-mail ontvingen.
   * De belemmering en laat vallen het **Volgen logboeken (het volgen)** element in de werkruimte en selecteert **bestaat niet** om alle klanten te richten die niet e-mail openden.

     ![](assets/wkf_push_example_2.png)

1. De [ activiteit van de het berichtlevering van de duw ](../../automating/using/push-notification-delivery.md) staat u toe om de inhoud van uw bericht in te gaan en de verpersoonlijkingsgebieden te selecteren die u wilt gebruiken:

   * Selecteer de optie **[!UICONTROL Recurring notification]** .
   * Definieer de inhoud van het pushbericht. Voor meer informatie over de inhoud van het duw- bericht, verwijs naar deze [ sectie ](../../channels/using/preparing-and-sending-a-push-notification.md).
   * Selecteer **[!UICONTROL Schedule]** in het blok **[!UICONTROL Messages to be sent automatically on the time zone specified below]** . Hier kiezen we de **[!UICONTROL Time zone of the contact date]** Pacific zoals in de workflow **[!UICONTROL Scheduler]** .
   * Selecteer in het veld **[!UICONTROL Optimize the sending time per recipient]** de optie **[!UICONTROL Send at the recipient's time zone]**.

     ![](assets/wkf_push_example_4.png)

1. Klik op de knop **[!UICONTROL Start]** om de terugkerende workflow te starten.

   ![](assets/wkf_push_example_3.png)

Uw workflow is nu actief. Het begint op de gekozen begindatum van **[!UICONTROL Scheduler]** om 22.00 uur Pacific time, zal de terugkomende duw dan elke eerste dag van de maand om 20.00 uur afhankelijk van de klantentijdzone worden verzonden.
