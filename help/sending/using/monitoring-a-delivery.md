---
solution: Campaign Standard
product: campaign
title: Een levering controleren in Adobe Campaign Standard
description: Ontdek hoe u een levering kunt controleren in Adobe Campaign Standard.
audience: sending
content-type: reference
topic-tags: monitoring-messages
context-tags: delivery,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '461'
ht-degree: 89%

---


# Een levering controleren{#monitoring-a-delivery}

Er zijn verschillende manieren om een levering te controleren en de impact ervan te meten. Als functionele beheerder, kunt u berichtlogboeken en leveringslogboeken toegang hebben.
>[!CAUTION]
>
>Alleen functionele [beheerders](../../administration/using/users-management.md#functional-administrators)met **[!UICONTROL Administration]** rol en toegang tot **alle** eenheden hebben toegang tot verzendende logboeken, berichtlogbestanden, trackinglogboeken, uitsluitings- of abonnementlogbestanden. Een gebruiker zonder beheerdersrechten kan zich richten op deze logbestanden, maar begint met een gekoppelde tabel (profielen, levering).

* **Berichtenlogbestanden**: Deze logboeken kunnen direct vanuit het berichtdashboard worden geopend. Zij tonen de details van de verzending, welk doel is uitgesloten en waarom, evenals de tracking-informatie zoals aantal geopend en aantal klikken.

   Klik op het pictogram rechtsonder in het blok **[!UICONTROL Deployment]** om de berichtenlogboeken weer te geven.

   Verschillende tabbladen bevatten informatie (indien aanwezig) over de **[!UICONTROL Sending logs]**, **[!UICONTROL Exclusion logs]**, **[!UICONTROL Exclusion causes]**, **[!UICONTROL Tracking logs]** en **[!UICONTROL Tracked URLs]**. Zie [Leveringslogboeken](#delivery-logs).

   ![](assets/sending_delivery1.png)

   Het logboek bevat alle berichten met betrekking tot de levering en de proeven. Met specifieke pictogrammen kunt u fouten of waarschuwingen identificeren. Zie [Berichten goedkeuren](../../sending/using/previewing-messages.md) voor meer informatie.

   U kunt het logboek exporteren door op de knop **[!UICONTROL Export list]** te klikken.

   ![](assets/sending_delivery2.png)

* **Leveringswaarschuwingen**: Adobe Campaign biedt een e-mailwaarschuwingssysteem dat meldingen verzendt om gebruikers op de hoogte te stellen van belangrijke systeemactiviteiten, zodat ze het slagen of mislukken van leveringen kunnen bijhouden.
* **Rapporten**: Vanuit het berichtdashboard kunt u verscheidene rapporten voor dit specifieke bericht openen. U hebt ook een **[!UICONTROL Reports]**-menu dat toegang biedt tot een volledige lijst van ingebouwde of aangepaste rapporten waarmee u specifieke metriek met betrekking tot uw bericht of campagne kunt definiëren.
* Een beheerder kan logbestanden ook exporteren naar een afzonderlijk bestand dat kan worden verwerkt in uw eigen rapportage- of BI-tools. Zie [Logboeken exporteren](../../automating/using/exporting-logs.md) voor meer informatie.

**Verwante onderwerpen:**

* [Waarschuwingen ontvangen wanneer fouten optreden](../../sending/using/receiving-alerts-when-failures-happen.md)
* [Rapporten](../../reporting/using/about-dynamic-reports.md)

## Leveringslogboeken {#delivery-logs}

### Verzendlogboeken {#sending-logs}

Op het tabblad **[!UICONTROL Sending logs]** vindt u een geschiedenis van elke keer dat deze levering heeft plaatsgevonden. De lijst met verzonden berichten en hun status is hier opgeslagen. Op dit tabblad kunt u de leveringsstatus voor elke ontvanger bekijken.

Voor elk profiel met de status **[!UICONTROL Sent]** wordt in de kolom **[!UICONTROL Date]** aangegeven wanneer het bericht is verzonden.

![](assets/sending_delivery3.png)

Klik op het potloodpictogram rechts van een rij om de details van het corresponderende specifieke verzendlogboek weer te geven.

![](assets/sending_access-sending-log.png)

Alle verzendlogboekdetails zijn alleen-lezen. U kunt ook een voorvertoning van de spiegelpagina zien.

![](assets/sending_sending-log.png)

>[!NOTE]
>
>Als u de weergave van de spiegelpagina in de gebruikersinterface van Campaign wilt tonen, moet de URL van de spiegelpaginaserver beveiligd zijn. In dat geval gebruikt u https:// in plaats van http:// om deze URL in te stellen bij het [configureren van uw merk](../../administration/using/branding.md#configuring-and-using-brands).

### Uitsluitingslogboeken {#exclusion-logs}

Op het tabblad **[!UICONTROL Exclusion logs]** worden alle berichten weergegeven die van de verzending zijn uitgesloten en wordt de reden voor het mislukken van de verzending aangegeven.

![](assets/sending_delivery4.png)

### Oorzaken van uitsluiting {#exclusion-causes}

Het tabblad **[!UICONTROL Exclusion causes]** toont het aantal berichten dat van de verzending is uitgesloten.

![](assets/sending_delivery5.png)
