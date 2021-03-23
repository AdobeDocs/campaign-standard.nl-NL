---
solution: Campaign Standard
product: campaign
title: Leverbaarheid in Adobe Campaign Standard bewaken
description: Gebruik de tools die Adobe Campaign Standard aanbiedt om de prestaties van uw platform te controleren.
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: Bezorging
role: Business Practitioner
level: Intermediair
translation-type: tm+mt
source-git-commit: fb9a6218bb754f803affde1fdf6c6fc01570126f
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 10%

---


# Leverbaarheid controleren{#monitor-deliverability}

Hieronder vindt u meer informatie over het **[!UICONTROL Delivery throughput]**-rapport en de verschillende door Adobe Campaign aangeboden monitoringtools. Hier volgen enkele aanvullende richtlijnen voor het controleren van de leverbaarheid:
* Controleer regelmatig de leveringsproductie voor het gehele platform om te verifiëren of het met de originele opstelling verenigbaar is.
* Controleer of het opnieuw proberen correct is ingesteld (30 minuten voor herbestellingsperiode en meer dan 20 pogingen) in leveringssjablonen.
* Verifieer regelmatig dat de stuiterende brievenbus toegankelijk is en dat de rekening niet op het punt staat te verlopen.
* Controleer elke leveringsproductie om ervoor te zorgen dat het met de geldigheid van de leveringsinhoud (b.v. &#39;Flash-verkoop&#39; moet in minuten worden geleverd, niet in dagen).
* Controleer of het aantal fouten en nieuwe quarantines consistent zijn met andere leveringen.
* Raadpleeg zorgvuldig de leveringslogboeken in detail om het soort fouten te controleren die worden benadrukt (lijsten van gewezen personen, DNS kwesties, anti-spamregels, enz.).

## Leveringsdoorvoer {#delivery-throughput}

Dit verslag bevat informatie over de leveringstijd van het gehele platform gedurende een bepaalde periode om de snelheid te meten waarop de berichten worden geleverd.

Zie [Productie-doorvoer](../../reporting/using/delivery-throughput.md) voor meer informatie.

![](assets/delivery_reports_1.png)

U kunt de weergegeven waarden configureren door de tijdschaal te wijzigen.

Andere rapporten zijn beschikbaar, zoals **[!UICONTROL Delivery summary]** of **[!UICONTROL Non-deliverables and bounces]**. Zie [Dynamische rapporten](../../reporting/using/about-dynamic-reports.md) voor meer informatie.

## Leveringen controleren{#monitoring-deliveries}

Het berichtdashboard geeft u toegang tot de leveringslogboeken: **[!UICONTROL Sending logs]**, **[!UICONTROL Exclusion logs]**, **[!UICONTROL Exclusion causes]**, **[!UICONTROL Tracking logs]** en **[!UICONTROL Tracked URLs]**. Zij tonen de details van de verzending, welk doel is uitgesloten en waarom, evenals de tracking-informatie zoals aantal geopend en aantal klikken.

Zie [Een levering controleren](../../sending/using/monitoring-a-delivery.md) voor meer informatie.

![](assets/sending_delivery1.png)

## Bezig met ontvangen van waarschuwingen {#receiving-alerts}

De functie **[!UICONTROL Delivery alerting]** is een waarschuwingssysteem waarmee een groep gebruikers automatisch meldingen kan ontvangen die informatie bevatten over de uitvoering van hun leveringen.

Zie [Waarschuwingen ontvangen wanneer fouten optreden](../../sending/using/receiving-alerts-when-failures-happen.md) voor meer informatie.

<!--## External tools (#external-tools)

### Signal Spam {#signal-spam}

Signal Spam is a French service which offers anonymized feedback loop reporting for French ISPs (Orange, SFR).

This service allows you to follow the reputation of the French ISPs and track customers' activity evolution.

Signal Spam also provides direct complaints that end users log through a dedicated interface. Those complaints are then quarantined from the email address database.

### 250ok {#solution-250ok}

250ok is a monitoring solution which provides IP and domain denylists, as well as reputation indicators.

The information provided is real-time, which allows for a pro-active assistance. 250ok a complementary solution to the Adobe deliverability internal tools.-->
