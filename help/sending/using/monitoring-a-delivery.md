---
title: Een levering controleren in Adobe Campagne Standard
description: Ontdek hoe u een levering kunt controleren in Adobe Campaign Standard.
page-status-flag: never-activated
uuid: 7772c607-debd-40fd-8322-4d49119979b4
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: monitoring-messages
discoiquuid: eb9fa216-4568-423a-9396-8f7b82181ae9
context-tags: delivery,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 54612511de07edc3e6f3eea34ef095c26b35f4af

---


# Toezicht op levering{#monitoring-a-delivery}

Er zijn verschillende manieren om een levering te controleren en de impact ervan te meten:

* **Berichtenlogbestanden**: Deze logboeken kunnen direct van het berichtdashboard worden betreden. Zij tonen de details van het verzenden, die doel is uitgesloten en waarom, evenals de het volgen informatie zoals opent en klikt.

   Klik op het pictogram rechtsonder in het **[!UICONTROL Deployment]** blok om de berichtenlogboeken weer te geven.

   Verschillende tabbladen bevatten informatie (indien aanwezig) over de tabbladen **[!UICONTROL Sending logs]**, **[!UICONTROL Exclusion logs]**, **[!UICONTROL Exclusion causes]** en **[!UICONTROL Tracking logs]** **[!UICONTROL Tracked URLs]**. Zie [Leveringslogboeken](#delivery-logs).

   ![](assets/sending_delivery1.png)

   Het logboek bevat alle berichten met betrekking tot de levering en de proefdrukken. Met specifieke pictogrammen kunt u fouten of waarschuwingen identificeren. Zie [Berichten](../../sending/using/previewing-messages.md)goedkeuren voor meer informatie hierover.

   U kunt het logboek exporteren door op de **[!UICONTROL Export list]** knop te klikken.

   ![](assets/sending_delivery2.png)

* **Afleveringswaarschuwingen**: Adobe Campaign biedt een e-mailwaarschuwingssysteem dat meldingen verzendt om gebruikers op de hoogte te stellen van belangrijke systeemactiviteiten, zodat u de successen of mislukkingen van de levering kunt bijhouden.
* **Rapporten**: Van het berichtdashboard, kunt u tot verscheidene rapporten voor dit specifieke bericht toegang hebben. U hebt ook een **[!UICONTROL Reports]** menu dat u toestaat om tot een volledige lijst van ingebouwde of douanerapporten toegang te hebben die u kunt gebruiken om specifieke metriek met betrekking tot uw bericht of campagne te schetsen.
* Een beheerder kan logbestanden ook exporteren in een afzonderlijk bestand dat kan worden verwerkt in uw eigen rapportage- of BI-gereedschappen. Zie Logboeken [exporteren voor meer informatie](../../automating/using/exporting-logs.md).

**Verwante onderwerpen:**

* [Waarschuwingen ontvangen wanneer fouten optreden](../../sending/using/receiving-alerts-when-failures-happen.md)
* [Rapporten](../../reporting/using/about-dynamic-reports.md)

## Leveringslogboeken {#delivery-logs}

### Logboeken verzenden {#sending-logs}

Op het **[!UICONTROL Sending logs]** tabblad vindt u een geschiedenis van elk exemplaar van deze levering. De lijst met verzonden berichten en hun status wordt hier opgeslagen. Het staat u toe om de leveringsstatus voor elke ontvanger te bekijken.

Voor elk profiel met een **[!UICONTROL Sent]** status, toont de **[!UICONTROL Date]** kolom wanneer het bericht werd verzonden.

![](assets/sending_delivery3.png)

Klik op het potloodpictogram rechts van de desbetreffende rij om de details van een specifiek verzendingslogboek te openen.

![](assets/sending_access-sending-log.png)

Alle verzendende logboekdetails zijn read-only. U kunt ook een voorvertoning van de spiegelpagina zien.

![](assets/sending_sending-log.png)

>[!NOTE]
>
>Om de spiegelpagina die in het gebruikersinterface van de Campagne teruggeeft te tonen, moet de spiegelpaginaserver URL veilig zijn. In dat geval gebruikt u https:// in plaats van http:// om deze URL in te stellen bij het [configureren van uw merk](../../administration/using/branding.md#configuring-and-using-brands).

### Uitsluitingslogboeken {#exclusion-logs}

Het **[!UICONTROL Exclusion logs]** lusje maakt een lijst van alle berichten die van het verzonden doel zijn uitgesloten en specificeert de reden voor de verzendmislukking.

![](assets/sending_delivery4.png)

### Uitsluiting veroorzaakt {#exclusion-causes}

Het **[!UICONTROL Exclusion causes]** lusje toont het volume (in aantal berichten) van berichten die van het doel werden uitgesloten verzendt.

![](assets/sending_delivery5.png)
