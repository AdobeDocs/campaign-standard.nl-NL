---
title: Interne meldingen verzenden
description: Leer hoe u realtime systeemmeldingen naar Adobe Campaign-gebruikers kunt verzenden.
page-status-flag: never-activated
uuid: f196f025-dbb9-4268-9d7d-ff626994b447
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: application-settings
discoiquuid: 4d51229a-745a-4f24-b1c2-22fa203b499c
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 2%

---


# Interne meldingen verzenden{#sending-internal-notifications}

Adobe Campaign biedt u de mogelijkheid om meldingen over belangrijke systeemactiviteiten rechtstreeks in de toepassing te ontvangen. Kennisgevingen in realtime houden relevante belanghebbenden op de hoogte en bieden gebruikers de mogelijkheid om onmiddellijk en rechtstreeks te reageren op activiteitenmeldingen vanuit de toepassing. Het resultaat voor teams is geavanceerde behendigheid, efficiency en vlottere uitvoering van campagnes.

![](assets/pulse_3.png)

U kunt meldingen configureren voor de volgende objecten:

* **[!UICONTROL A/B Test emails]**: de maker van de e-mail en de modifier(s) ervan in kennis worden gesteld dat een variant is gekozen (automatische modus) of dat een variant moet worden gekozen (handmatige modus). Als u op de melding klikt, wordt de bijbehorende e-mail weergegeven. Meldingen worden standaard geactiveerd in de testsjabloon voor de uit-van-de-box A/B. Als u deze wilt deactiveren, bewerkt u de eigenschappen van de e-mailsjabloon of de e-mailsjabloon en schakelt u het selectievakje onder **Algemeen > Meldingen** uit. Voor meer informatie over A/B test e-mails, verwijs naar het [Creëren van een Test](../../channels/using/designing-an-a-b-test-email.md)van AB. Zie [Lijst met e-maileigenschappen](../../administration/using/configuring-email-channel.md#list-of-email-properties)voor meer informatie over e-maileigenschappen.

   ![](assets/pulse_2.png)

* **[!UICONTROL Workflows]**: elk lid van de geselecteerde beveiligingsgroep wordt op de hoogte gesteld (e-mail en In-App-melding) wanneer er een fout optreedt in de workflow. Als u op de melding of op de e-mailkoppeling klikt, wordt de bijbehorende workflow weergegeven. Meldingen worden standaard gedeactiveerd in de werkstroomsjabloon buiten de box. Als u deze wilt activeren, bewerkt u de eigenschappen van de workflow of werkstroomsjabloon en voegt u een beveiligingsgroep toe onder **Algemeen > Uitvoering > Foutbeheer > Supervisors**. Voor meer informatie over veiligheidsgroepen, verwijs naar het [Leiden groepen en gebruikers](../../administration/using/managing-groups-and-users.md). Zie [Workfloweigenschappen](../../automating/using/managing-execution-options.md)voor meer informatie over workfloweigenschappen.

   ![](assets/pulse_1.png)
