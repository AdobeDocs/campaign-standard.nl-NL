---
title: Interne meldingen verzenden
description: Leer hoe u realtime systeemmeldingen naar Adobe Campaign-gebruikers kunt verzenden
audience: administration
role: Admin
level: Experienced
exl-id: 7e04275a-5413-4f03-b18c-b64ab482d7d5
source-git-commit: bfba6b156d020e8d2656239e713d2d24625bda54
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 2%

---

# Interne meldingen verzenden{#sending-internal-notifications}

Adobe Campaign biedt u de mogelijkheid om meldingen over belangrijke systeemactiviteiten rechtstreeks in de toepassing te ontvangen. Kennisgevingen in realtime houden relevante belanghebbenden op de hoogte en bieden gebruikers de mogelijkheid om onmiddellijk en rechtstreeks te reageren op activiteitenmeldingen vanuit de toepassing. Het resultaat voor teams is geavanceerde behendigheid, efficiency en vlottere uitvoering van campagnes.

![](assets/pulse_3.png)

U kunt meldingen configureren voor de volgende objecten:

* **[!UICONTROL A/B Test emails]**: de maker van de e-mail en de modifier(s) worden ervan op de hoogte gebracht dat een variant is gekozen (automatische modus) of dat een variant moet worden gekozen (handmatige modus). Als u op het bericht klikt, wordt het bijbehorende e-mailbericht weergegeven. Meldingen worden standaard geactiveerd in de testsjabloon voor de uit-van-de-box A/B. Als u deze wilt deactiveren, bewerkt u de eigenschappen van de e-mail- of e-mailsjabloon en schakelt u het selectievakje onder **Algemeen > Meldingen**. Voor meer informatie over e-mails over A/B-tests raadpleegt u [Een AB-test maken](../../channels/using/designing-an-a-b-test-email.md). Zie voor meer informatie over e-maileigenschappen [Lijst met e-maileigenschappen](../../administration/using/configuring-email-channel.md#list-of-email-properties).

  ![](assets/pulse_2.png)

* **[!UICONTROL Workflows]**: elk lid van de geselecteerde beveiligingsgroep wordt op de hoogte gesteld (e-mail en In-App-melding) wanneer er een fout optreedt in de workflow. Als u op de melding of op de e-mailkoppeling klikt, wordt de bijbehorende workflow weergegeven. Meldingen worden standaard gedeactiveerd in de werkstroomsjabloon buiten de box. Als u deze wilt activeren, bewerkt u de eigenschappen van de workflow of het werkstroomsjabloon en voegt u een beveiligingsgroep toe onder **Algemeen > Uitvoering > Foutbeheer > Supervisors**. Raadpleeg voor meer informatie over beveiligingsgroepen [Groepen en gebruikers beheren](../../administration/using/managing-groups-and-users.md). Raadpleeg voor meer informatie over workfloweigenschappen [Workflow-eigenschappen](../../automating/using/managing-execution-options.md).

  ![](assets/pulse_1.png)
