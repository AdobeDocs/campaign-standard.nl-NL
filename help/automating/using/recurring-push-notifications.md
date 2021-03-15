---
solution: Campaign Standard
product: campaign
title: Een terugkerende pushmelding verzenden met een workflow
description: In dit voorbeeld wordt elke eerste dag van de maand om 21.00 uur een persoonlijke pushmelding verzonden naar de abonnees van uw mobiele toepassing, afhankelijk van hun tijdzone.
audience: automating
content-type: reference
topic-tags: channel-activities
feature: Workflows
role: Gegevensarchitect
level: Intermediair
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '479'
ht-degree: 4%

---


# Een terugkerende pushmelding verzenden met een workflow {#sending-a-recurring-push-notification-with-a-workflow}

![](assets/wkf_push_example_1.png)

In dit voorbeeld wordt elke eerste dag van de maand om 21.00 uur een persoonlijke pushmelding verzonden naar de abonnees van uw mobiele toepassing, afhankelijk van hun tijdzone.

Voer de volgende stappen uit om de workflow te maken:

1. Met de [Scheduler](../../automating/using/scheduler.md)-activiteit kunt u de workflowdagen voor het begin van de levering starten en het bericht naar elke abonnee om 20:00 uur in een bepaalde tijdzone verzenden:

   * Selecteer Maandelijks in het veld **[!UICONTROL Execution frequency]**.
   * Selecteer 8 pm in het **[!UICONTROL Time]** gebied.
   * Kies op welke dag de levering elke maand wordt verzonden.
   * Selecteer een begindatum voor de workflow, ten minste één dag voor het begin van de levering. Anders, zouden sommige ontvangers het bericht een dag later kunnen ontvangen als de geselecteerde tijd reeds in hun tijdzones is overgegaan.
   * Selecteer op het tabblad **[!UICONTROL Execution options]** in welk tijdzone uw workflow begint in het veld **[!UICONTROL Time zone]**. Hier begint de workflow bijvoorbeeld om 20.00 uur Stille-Oceaantijd, één week voor de eerste dag van de maand, zodat er enige tijd is om de leveringen voor alle toepasselijke tijdzones te maken.

   >[!NOTE]
   >
   >Standaard is de geselecteerde tijdzone de tijdzone die is gedefinieerd in de workfloweigenschappen (zie [Een workflow maken](../../automating/using/building-a-workflow.md)).

   ![](assets/wkf_push_example_5.png)

1. Met de activiteit [Query](../../automating/using/query.md) kunt u zich richten op uw VIP klanten tussen 20 en 30 jaar die zich hebben geabonneerd op uw mobiele toepassing en die de door u verzonden e-mail niet hebben geopend:

   * Selecteer een publiek (uw VIP klanten) en filter op hun leeftijd.
   * Sleep **Abonnementen aan een toepassing** element in de werkruimte. Selecteer **Bestaat** en selecteer de mobiele toepassing die u wilt gebruiken.
   * Selecteer het e-mailbericht dat u naar uw klanten hebt verzonden.
   * Sleep het element **Leveringslogboeken (logs)** naar de werkruimte en selecteer **Bestaat** om alle klanten aan te wijzen die de e-mail hebben ontvangen.
   * Sleep het element **Logbestanden bijhouden (bijhouden)** naar de werkruimte en selecteer **Bestaat niet?** om alle klanten aan te wijzen die het e-mailbericht niet hebben geopend.

      ![](assets/wkf_push_example_2.png)

1. Met de activiteit [Push notification delivery](../../automating/using/push-notification-delivery.md) kunt u de inhoud van uw bericht invoeren en de velden voor personalisatie selecteren die u wilt gebruiken:

   * Selecteer de optie **[!UICONTROL Recurring notification]**.
   * Definieer de inhoud van het pushbericht. Raadpleeg deze [sectie](../../channels/using/preparing-and-sending-a-push-notification.md) voor meer informatie over de inhoud van pushberichten.
   * Selecteer **[!UICONTROL Messages to be sent automatically on the time zone specified below]** in het blok **[!UICONTROL Schedule]**. Hier, kozen wij **[!UICONTROL Time zone of the contact date]** Stille Oceaan zoals in het werkschema **[!UICONTROL Scheduler]**.
   * Selecteer in het veld **[!UICONTROL Optimize the sending time per recipient]** de optie **[!UICONTROL Send at the recipient's time zone]**.

      ![](assets/wkf_push_example_4.png)

1. Klik op de knop **[!UICONTROL Start]** om uw terugkerende workflow te starten.

   ![](assets/wkf_push_example_3.png)

Uw workflow is nu actief. Het zal bij de gekozen begindatum van **[!UICONTROL Scheduler]** om 22:00 uur Pacific tijd beginnen, zal de terugkomende duw dan elke eerste dag van de maand om 20:00 uur afhankelijk van de klantentijdzone worden verzonden.
