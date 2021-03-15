---
solution: Campaign Standard
product: campaign
title: E-mailweergave
description: Ontdek de functie voor het weergeven van e-mail.
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
feature: Tijdoptimalisatie verzenden
role: Zakelijke praktiserer
level: Intermediair
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '519'
ht-degree: 82%

---


# E-mailweergave{#email-rendering}

Controleer of uw bericht optimaal wordt weergegeven op verschillende webclients, in webmails en op apparaten voordat u op de knop **[!UICONTROL Send]** drukt.

Om dit mogelijk te maken, legt Adobe Campaign de weergave vast en stelt deze beschikbaar in een specifiek rapport. Op deze manier kunt u het voorbeeld van het verzonden bericht bekijken in de verschillende contexten waarin het bericht mogelijk wordt ontvangen.

De clients voor mobiele apparaten, berichten en webmail die beschikbaar zijn voor **e-mailweergave** in Adobe Campaign, worden vermeld op de Litmus-[website](https://litmus.com/email-testing) (klik op **View all email clients**).

## E-mailrendering genereren {#checking-the-email-rendering-report}

Voer onderstaande stappen uit als u de e-maillevering hebt gemaakt en de content en de doelpopulatie ervan hebt bepaald.

1. Klik op **Audience** om het tabblad **[!UICONTROL Test profiles]** te openen.

   ![](assets/email_rendering_05.png)

1. Gebruik de query-editor om de testprofielen die u wilt gebruiken te definiëren, inclusief de testprofielen voor gebruik in **Email rendering**. Zie [Informatie over testprofielen](../../audiences/using/managing-test-profiles.md).

   ![](assets/email_rendering_06.png)

1. Controleer en bevestig uw query en sla uw wijzigingen op.
1. Klik op de knop **[!UICONTROL Test]** op de actiebalk.

   ![](assets/email_rendering_07.png)

1. Selecteer de optie **[!UICONTROL Email rendering]** en klik op **[!UICONTROL OK]**.

   ![](assets/email_rendering_08.png)

   >[!NOTE]
   >
   >Met de optie **[!UICONTROL Proof + Email rendering]** kunt u tegelijkertijd een proef verzenden en de functie voor e-mailweergave gebruiken. U kunt uw bericht laten goedkeuren door de proefontvangers en tegelijkertijd kunt u testen hoe uw bericht afhankelijk van de beoogde inboxes wordt ontvangen. In dit geval moet u ook Proof test profiles selecteren. Zie [Informatie over testprofielen](../../audiences/using/managing-test-profiles.md).

   De testlevering vindt plaats.

1. De weergaveminiaturen zijn enkele minuten na het verzenden van de berichten beschikbaar. U kunt deze openen door **[!UICONTROL Proofs]** te selecteren in de keuzelijst **[!UICONTROL Summary]**.

   ![](assets/email_rendering_03.png)

1. Klik in de lijst **[!UICONTROL Proofs]** op het pictogram **[!UICONTROL Access email rendering]**.

   ![](assets/email_rendering_04.png)

Het speciale rapport voor het weergeven van e-mail wordt getoond. Zie [Beschrijving van rapport voor e-mailweergave](#email-rendering-report-description).

**Verwante onderwerpen**:

* [Een e-mail maken](../../channels/using/creating-an-email.md)
* [Proeven verzenden](../../sending/using/sending-proofs.md)
* [Query-editor](../../automating/using/editing-queries.md#about-query-editor)

## E-mailrenderrapport {#email-rendering-report-description}

In dit rapport ziet u de e-mailweergave zoals de ontvanger deze te zien krijgt. E-mailweergaven kunnen verschillen, afhankelijk van de manier waarop de ontvanger de e-maillevering opent: in een browser, op een mobiel apparaat of via een e-mailapplicatie.

### E-mailrenderingtokens

Het aantal beschikbare weergaven vindt u terug in uw licentieovereenkomst. Bij elke levering waarvoor **Email rendering** is ingeschakeld, neemt uw aantal beschikbare weergaven (ook wel tokens genoemd) af met één.

Tokens maken voor elke afzonderlijke rendering en niet voor het hele e-mailrenderrapport. Dit houdt in dat:

* **Elke** keer dat het rapport E-mail renderen wordt gegenereerd, wordt één token per berichtclient afgetrokken: één token voor de rendering van Outlook 2000, één token voor de rendering van Outlook, één token voor de rendering van Apple Mail, enzovoort.

* **Als u voor dezelfde levering** de rendering via e-mail opnieuw genereert, wordt het aantal beschikbare tokens opnieuw verminderd met het aantal gegenereerde renderingen.

### Overzicht van rapport

Het rapportoverzicht toont het aantal ontvangen berichten, ongewenste berichten (spam), niet ontvangen berichten of berichten die nog niet zijn bezorgd.

![](assets/inbox_rendering_report.png)

Het rapport bestaat uit drie delen: **[!UICONTROL Mobile]**, **[!UICONTROL Messaging clients]** en **[!UICONTROL Webmails]**. Blader omlaag door het rapport om alle weergaven gegroepeerd in deze drie categorieën te bekijken.

![](assets/inbox_rendering_report_3.png)

Klik op de bijbehorende kaart om de informatie voor elk rapport op te halen. De weergave wordt getoond voor de geselecteerde ontvangstmethode.

![](assets/inbox_rendering_report_2.png)

In het tabblad **[!UICONTROL Technical data]** kunt u meer informatie ophalen zoals de ontvangst- en vastlegdata en de volledige kopteksten van e-mailberichten.
