---
title: Traps gebruiken
description: Leer hoe u overvullingen in berichten kunt gebruiken.
page-status-flag: never-activated
uuid: eb4d893b-3724-4b15-9312-1ec74784368d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
discoiquuid: 37320ec5-196c-4260-8156-98932da3e4a5
context-tags: seedMember,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1efcd646f4af86175b3b09b53185c792cb4cf7dd
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 2%

---


# Traps gebruiken {#using-traps}

Wanneer u overvullingen gebruikt, wordt het bericht naar het [testprofiel](../../audiences/using/managing-test-profiles.md) verzonden, net zoals het naar het hoofddoel wordt verzonden, om te bepalen of uw clientbestand op frauduleuze wijze wordt gebruikt.

De overvullingen waren oorspronkelijk ontworpen voor direct-mailleveringen. U kunt hiermee:

* Verifieer dat uw direct-mailleverancier echt de mededeling verzendt.
* Ontvang de post tezelfdertijd en in de zelfde voorwaarden zoals uw klanten.
* Een exacte kopie bewaren van de verzonden e-mail.
* Controleer of uw clientlijst niet wordt misbruikt door uw directe-mailprovider. Als er andere communicatie naar het adres van uw testprofiel wordt verzonden, is het mogelijk dat uw clientbestand zonder uw medeweten is gebruikt. Daarom mag het adres van het testprofiel alleen voor dit doel worden gebruikt.

Zie Testen- en overvulprofielen [](../../channels/using/defining-the-direct-mail-audience.md#adding-test-and-trap-profiles)toevoegen voor meer informatie over het toevoegen van overvullingen aan het publiek van een directe e-mail.

Voor de andere communicatiekanalen kunt u testprofielen voor overvulling toevoegen aan het hoofddoel:

* Controleer of je bericht is verzonden.
* Haal een exacte kopie van uw bericht op en houd deze bij.
* Bijhouden wanneer deze is verzonden en ontvangen.

Als u een testprofiel als een overvulling wilt gebruiken, moet dit deel uitmaken van het publiek van uw bericht.

>[!NOTE]
>
>In tegenstelling tot testprofielen die worden gebruikt voor [proefdrukken](../../sending/using/sending-proofs.md) of [e-mailrendering](../../sending/using/email-rendering.md), wordt het bericht tegelijkertijd verzonden naar het hoofddoel en naar de testprofielen die worden gebruikt als overvulling.

Bij het definiëren van het publiek van een bericht:

1. Selecteer op het **[!UICONTROL Test profiles]** tabblad een testprofiel. Zorg ervoor dat dit het **[!UICONTROL Trap]** gewenste gebruik heeft.

   ![](assets/trap_select.png)

1. Klik op de **[!UICONTROL Prepare]** knop als de inhoud van het bericht gereed is. See [Preparing the send](../../sending/using/preparing-the-send.md).
   >[!NOTE]
   >
   >Controleer of u een hoofddoel hebt geselecteerd. Anders kan uw bericht niet worden verzonden.

1. Klik op de knop **[!UICONTROL Confirm]**. Zie [De verzending bevestigen](../../sending/using/confirming-the-send.md).

   ![](assets/trap_confirm.png)

Het bericht wordt naar het hoofddoel en naar het testprofiel verzonden.

U kunt overvullingen gebruiken bij het verzenden van transactieberichten. In dit geval ontvangt het testprofiel één bericht per gebeurtenisconfiguratie. For more on transactional messaging, see this [section](../../channels/using/getting-started-with-transactional-msg.md).

>[!NOTE]
>
>Wanneer u een testprofiel als overvulling gebruikt, worden voor alle verrijkte velden in een bericht de bijbehorende aanvullende gegevens willekeurig gekozen uit een echt doelprofiel en toegewezen aan het testprofiel voor overvulling. Zie [dit voorbeeld](../../automating/using/enrichment.md#example--enriching-profile-data-with-data-contained-in-a-file)voor meer informatie over verrijking.
