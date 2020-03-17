---
title: E-mailrendering
description: Ontdek de functie voor het renderen van e-mail.
page-status-flag: never-activated
uuid: c423e237-ad39-4797-ac3a-4320894a8f99
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
discoiquuid: 2b5b13c8-2e51-4985-a161-c1d7f0fc32b4
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 07d68b5bf8d800ebd95919f491e98f1b7a015705

---


# E-mailrendering{#email-rendering}

Voordat u op de **[!UICONTROL Send]** knop drukt, controleert u of uw bericht optimaal wordt weergegeven op verschillende webclients, webmails en apparaten.

Om dit toe te staan, vangt de Campagne van Adobe de teruggave en stelt het ter beschikking in een specifiek rapport. Op deze manier kunt u het verzonden bericht voorvertonen in de verschillende contexten waarin het kan worden ontvangen.

De clients voor mobiele apparaten, berichten en webmail die beschikbaar zijn voor **e-mailrendering** in Adobe Campaign, worden weergegeven op de Litmus- [website](https://litmus.com/email-testing) (klik op Alle e-mailclients **** weergeven).

## Het rapport E-mail renderen controleren {#checking-the-email-rendering-report}

Nadat u de e-maillevering hebt gemaakt en de inhoud ervan en de doelgroep hebt gedefinieerd, volgt u de onderstaande stappen.

1. Klik op **Publiek** om het **[!UICONTROL Test profiles]** tabblad te openen.

   ![](assets/email_rendering_05.png)

1. Gebruik de query-editor om de testprofielen te definiëren die u wilt gebruiken, inclusief de testprofielen die zijn bedoeld voor gebruik in de rendermethode **E-mail** . Zie [Informatie over testprofielen](../../audiences/using/managing-test-profiles.md).

   ![](assets/email_rendering_06.png)

1. Controleer en bevestig uw query en sla uw wijzigingen op.
1. Klik op de **[!UICONTROL Test]** knop op de actiebalk.

   ![](assets/email_rendering_07.png)

1. Selecteer de **[!UICONTROL Email rendering]** optie en klik op **[!UICONTROL OK]**.

   ![](assets/email_rendering_08.png)

   >[!NOTE]
   >
   >Met de **[!UICONTROL Proof + Email rendering]** optie kunt u een proefdruk verzenden en de functie voor het renderen van e-mail tegelijk gebruiken. U kunt uw bericht laten goedkeuren door de proefontvangers en tezelfdertijd kunt u testen hoe uw bericht afhankelijk van de beoogde inboxes zal worden ontvangen. In dit geval moet u ook Testprofielen voor proef selecteren. Zie [Informatie over testprofielen](../../audiences/using/managing-test-profiles.md).

   De testlevering wordt verzonden.

1. De renderingminiaturen zijn enkele minuten na het verzenden van de berichten beschikbaar. U kunt ze openen door ze **[!UICONTROL Proofs]** in de **[!UICONTROL Summary]** vervolgkeuzelijst te selecteren.

   ![](assets/email_rendering_03.png)

1. Klik in de **[!UICONTROL Proofs]** lijst op het **[!UICONTROL Access email rendering]** pictogram.

   ![](assets/email_rendering_04.png)

Het speciale rapport voor het renderen van e-mail wordt weergegeven. Zie Beschrijving [van](#email-rendering-report-description)het rapport E-mailrendering.

**Verwante onderwerpen**:

* [Een e-mail maken](../../channels/using/creating-an-email.md)
* [Proefdrukken verzenden](../../sending/using/sending-proofs.md)
* [Query-editor](../../automating/using/editing-queries.md#about-query-editor)

## Beschrijving van e-mailrenderingrapport {#email-rendering-report-description}

In dit rapport worden de e-mailresultaten weergegeven zoals deze naar de ontvanger worden weergegeven. E-mailweergaven kunnen afwijken, afhankelijk van de manier waarop de ontvanger de e-maillevering opent: in een browser, op een mobiel apparaat of via een e-mailtoepassing.

>[!NOTE]
>
>Het aantal beschikbare weergaven wordt vermeld in uw licentieovereenkomst. Bij elke levering waarvoor rendering via **e-mail** is ingeschakeld, worden de beschikbare renderingen (tokens genoemd) met één verminderd. Als u een Litmus-client bent, kunt u uw eigen Litmus-account gebruiken om gegevens te verschaffen en e-mailrendering te gebruiken in Adobe Campaign. Neem voor meer informatie hierover contact op met de manager van uw Adobe-account.

De rapportsamenvatting geeft het aantal ontvangen, ongewenste (spam), niet ontvangen, of hangende ontvangst weer.

![](assets/inbox_rendering_report.png)

Het verslag bestaat uit drie delen: **[!UICONTROL Mobile]**, **[!UICONTROL Messaging clients]**, en **[!UICONTROL Webmails]**. Schuif omlaag het rapport om alle renderingen weer te geven die in deze drie categorieën zijn gegroepeerd.

![](assets/inbox_rendering_report_3.png)

Klik op de bijbehorende kaart om de details voor elk rapport op te halen. De rendering wordt weergegeven voor de geselecteerde ontvangstmethode.

![](assets/inbox_rendering_report_2.png)

Op het **[!UICONTROL Technical data]** tabblad kunt u meer informatie ophalen, zoals de datum van ontvangst en vastlegging, en de volledige koppen van e-mailberichten.
