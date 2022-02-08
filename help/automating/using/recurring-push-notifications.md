---
title: Een terugkerende pushmelding verzenden met een workflow
description: In dit voorbeeld wordt elke eerste dag van de maand om 21.00 uur een gepersonaliseerd pushbericht verzonden naar de abonnees van uw mobiele toepassing, afhankelijk van hun tijdzones
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: d5e6034c-3673-4069-ac0b-49c7ad07259d
source-git-commit: 0ab950d4124bf459ba889e2f1c2954210dd350e0
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 4%

---

# Een terugkerende pushmelding verzenden met een workflow {#sending-a-recurring-push-notification-with-a-workflow}

![](assets/wkf_push_example_1.png)

In dit voorbeeld wordt elke eerste dag van de maand om 21.00 uur een persoonlijke pushmelding verzonden naar de abonnees van uw mobiele toepassing, afhankelijk van hun tijdzone.

Voer de volgende stappen uit om de workflow te maken:

1. De [Planner](../../automating/using/scheduler.md) de activiteit staat u toe om de werkschemadagen vóór het begin van de levering te beginnen om het bericht aan elke abonnee te kunnen verzenden om 8 pm in om het even welke bepaalde tijdzone:

   * In de **[!UICONTROL Execution frequency]** veld, selecteert u Maandelijks.
   * Selecteer 8 pm in de **[!UICONTROL Time]** veld.
   * Kies op welke dag de levering elke maand wordt verzonden.
   * Selecteer een begindatum voor de workflow, ten minste één dag voor het begin van de levering. Anders, zouden sommige ontvangers het bericht een dag later kunnen ontvangen als de geselecteerde tijd reeds in hun tijdzones is overgegaan.
   * In de **[!UICONTROL Execution options]** -tabblad selecteert u in welke tijdzone uw workflow begint in het dialoogvenster **[!UICONTROL Time zone]** veld. Hier begint de workflow bijvoorbeeld om 20.00 uur Stille-Oceaantijd, één week voor de eerste dag van de maand, zodat er enige tijd is om de leveringen voor alle toepasselijke tijdzones te maken.

   >[!NOTE]
   >
   >Standaard is de geselecteerde tijdzone de tijdzone die is gedefinieerd in de workfloweigenschappen (zie [Een workflow maken](../../automating/using/building-a-workflow.md)).

   ![](assets/wkf_push_example_5.png)

1. De [Query](../../automating/using/query.md) Met activiteit kunt u zich richten op uw VIP klanten tussen de 20 en 30 jaar oud die zich op uw mobiele toepassing hebben geabonneerd en die het door u verzonden e-mailbericht niet hebben geopend:

   * Selecteer een publiek (uw VIP klanten) en filter op hun leeftijd.
   * Sleep de **Abonnementen op een toepassing** in de werkruimte. Selecteren **Exists** en selecteer de mobiele toepassing die u wilt gebruiken.
   * Selecteer het e-mailbericht dat u naar uw klanten hebt verzonden.
   * Sleep de **Leveringslogboeken (logboeken)** -element in de werkruimte en selecteer **Exists** om zich te richten op alle klanten die het e-mailbericht hebben ontvangen.
   * Sleep de **Logbestanden bijhouden (bijhouden)** -element in de werkruimte en selecteer **Is niet bestaand** om zich te richten op alle klanten die het e-mailbericht niet hebben geopend.

      ![](assets/wkf_push_example_2.png)

1. De [Levering pushmelding](../../automating/using/push-notification-delivery.md) Met activiteit kunt u de inhoud van uw bericht invoeren en de velden voor personalisatie selecteren die u wilt gebruiken:

   * Selecteer **[!UICONTROL Recurring notification]** optie.
   * Definieer de inhoud van het pushbericht. Raadpleeg deze voor meer informatie over inhoud van pushberichten [sectie](../../channels/using/preparing-and-sending-a-push-notification.md).
   * In de **[!UICONTROL Schedule]** blok, selecteren **[!UICONTROL Messages to be sent automatically on the time zone specified below]**. Hier hebben we de **[!UICONTROL Time zone of the contact date]** Stille Oceaan zoals in de workflow **[!UICONTROL Scheduler]**.
   * Selecteer in het veld **[!UICONTROL Optimize the sending time per recipient]** de optie **[!UICONTROL Send at the recipient's time zone]**.

      ![](assets/wkf_push_example_4.png)

1. Klik op de knop **[!UICONTROL Start]** om uw terugkerende workflow te starten.

   ![](assets/wkf_push_example_3.png)

Uw workflow is nu actief. Het begint op de gekozen begindatum van de **[!UICONTROL Scheduler]** om 22:00 uur Pacific time zal de terugkerende push vervolgens elke eerste dag van de maand om 23.00 uur worden verzonden, afhankelijk van de tijdzone van de klant.
