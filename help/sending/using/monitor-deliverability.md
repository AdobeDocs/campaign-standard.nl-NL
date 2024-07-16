---
title: Leverbaarheid in Adobe Campaign Standard bewaken
description: Gebruik de tools die Adobe Campaign Standard aanbiedt om de prestaties van uw platform te controleren.
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: Deliverability
role: User
level: Intermediate
exl-id: 683341fb-fef5-4aa1-8606-9526d9ae6290
source-git-commit: 449187bba167f9ce00e644d44a124b36030ba001
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 9%

---

# Leverbaarheid controleren{#monitor-deliverability}

Hieronder vindt u meer informatie over het **[!UICONTROL Delivery throughput]** -rapport en de verschillende door Adobe Campaign aangeboden controlemiddelen. Hier volgen enkele aanvullende richtlijnen voor het controleren van de leverbaarheid:

* Controleer regelmatig de leveringsproductie voor het gehele platform om te verifiëren of het met de originele opstelling verenigbaar is.
* Controleer of het opnieuw proberen correct is ingesteld (30 minuten voor herbestellingsperiode en meer dan 20 pogingen) in leveringssjablonen.
* Verifieer regelmatig dat de stuiterende brievenbus toegankelijk is en dat de rekening niet op het punt staat te verlopen.
* Controleer elke leveringsproductie om ervoor te zorgen dat het met de geldigheid van de leveringsinhoud verenigbaar is (bijv. &quot;flitsverkoop&quot;zou in notulen, niet dagen moeten worden geleverd).
* Controleer of het aantal fouten en nieuwe quarantines consistent zijn met andere leveringen.
* Raadpleeg zorgvuldig de leveringslogboeken in detail om het soort fouten te controleren die worden benadrukt (lijsten van gewezen personen, DNS kwesties, anti-spamregels, enz.).

## Leveringsdoorvoer {#delivery-throughput}

Dit verslag bevat informatie over de leveringstijd van het gehele platform gedurende een bepaalde periode om de snelheid te meten waarop de berichten worden geleverd.

Voor meer op dit, zie [ productie van de Levering ](../../reporting/using/delivery-throughput.md).

![](assets/delivery_reports_1.png)

U kunt de weergegeven waarden configureren door de tijdschaal te wijzigen.

Er zijn andere rapporten beschikbaar, zoals **[!UICONTROL Delivery summary]** of **[!UICONTROL Non-deliverables and bounces]** . Voor meer op dit, zie [ Dynamische rapporten ](../../reporting/using/about-dynamic-reports.md).

## Bewaking van leveringen {#monitoring-deliveries}

Het berichtdashboard geeft u toegang tot de leveringslogboeken: **[!UICONTROL Sending logs]**, **[!UICONTROL Exclusion logs]**, **[!UICONTROL Exclusion causes]**, **[!UICONTROL Tracking logs]** en **[!UICONTROL Tracked URLs]** . Zij tonen de details van de verzending, welk doel is uitgesloten en waarom, evenals de tracking-informatie zoals aantal geopend en aantal klikken.

Voor meer op dit, zie [ Controle een levering ](../../sending/using/monitoring-a-delivery.md).

![](assets/sending_delivery1.png)

## Ontvangen van waarschuwingen {#receiving-alerts}

De functie **[!UICONTROL Delivery alerting]** is een waarschuwingssysteem waarmee een groep gebruikers automatisch meldingen kan ontvangen met informatie over de uitvoering van hun leveringen.

Voor meer op dit, zie [ Ontvangend alarm wanneer de mislukkingen ](../../sending/using/receiving-alerts-when-failures-happen.md) gebeuren.

<!--## External tools (#external-tools)

### Signal Spam {#signal-spam}

Signal Spam is a French service which offers anonymized feedback loop reporting for French ISPs (Orange, SFR).

This service allows you to follow the reputation of the French ISPs and track customers' activity evolution.

Signal Spam also provides direct complaints that end users log through a dedicated interface. Those complaints are then quarantined from the email address database.

### 250ok {#solution-250ok}

250ok is a monitoring solution which provides IP and domain denylists, as well as reputation indicators.

The information provided is real-time, which allows for a pro-active assistance. 250ok a complementary solution to the Adobe deliverability internal tools.-->
