---
title: Traps gebruiken
description: Leer hoe u overvullingen in berichten kunt gebruiken.
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
context-tags: seedMember,overview
feature: Seed Address
role: User
level: Intermediate
exl-id: 0482a946-35b1-426f-8505-42adcd1c3bbb
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 2%

---

# Traps gebruiken {#using-traps}

Wanneer u overvullingen gebruikt, wordt het bericht verzonden naar de [testprofiel](../../audiences/using/managing-test-profiles.md) net zoals het naar het hoofddoel wordt verzonden, als middel om te identificeren of uw cliëntdossier frauduleus wordt gebruikt.

De overvullingen waren oorspronkelijk ontworpen voor direct-mailleveringen. U kunt hiermee:

* Verifieer dat uw direct-mailleverancier echt de mededeling verzendt.
* Ontvang de post tezelfdertijd en in de zelfde voorwaarden zoals uw klanten.
* Een exacte kopie bewaren van de verzonden e-mail.
* Controleer of uw clientlijst niet wordt misbruikt door uw directe-mailprovider. Als er andere communicatie naar het adres van uw testprofiel wordt verzonden, is het mogelijk dat uw clientbestand zonder uw medeweten is gebruikt. Daarom mag het adres van het testprofiel alleen voor dit doel worden gebruikt.

Voor meer informatie over het toevoegen van overvullingen aan het publiek van een directe e-mail raadpleegt u [Testen- en overvulprofielen toevoegen](../../channels/using/defining-the-direct-mail-audience.md#adding-test-and-trap-profiles).

Voor de andere communicatiekanalen kunt u testprofielen voor overvulling toevoegen aan het hoofddoel:

* Controleer of je bericht is verzonden.
* Haal een exacte kopie van uw bericht op en houd deze bij.
* Bijhouden wanneer deze is verzonden en ontvangen.

Als u een testprofiel als een overvulling wilt gebruiken, moet dit deel uitmaken van het publiek van uw bericht.

>[!NOTE]
>
>In tegenstelling tot testprofielen voor [proefdrukken](../../sending/using/sending-proofs.md) of [e-mailrendering](../../sending/using/email-rendering.md), wordt het bericht tegelijkertijd verzonden naar het hoofddoel en naar de testprofielen die als vallen worden gebruikt.

Bij het definiëren van het publiek van een bericht:

1. Van de **[!UICONTROL Test profiles]** selecteert u een testprofiel. Zorg ervoor dat het **[!UICONTROL Trap]** als het beoogde gebruik.

   ![](assets/trap_select.png)

1. Als de inhoud van uw bericht gereed is, klikt u op de knop **[!UICONTROL Prepare]** knop. Zie [De verzending voorbereiden](../../sending/using/preparing-the-send.md).
   >[!NOTE]
   >
   >Zorg ervoor dat u een hoofddoel hebt geselecteerd. Anders kan uw bericht niet worden verzonden.

1. Klik op de knop **[!UICONTROL Confirm]**. Zie [De verzending bevestigen](../../sending/using/confirming-the-send.md).

   ![](assets/trap_confirm.png)

Het bericht wordt naar het hoofddoel en naar het testprofiel verzonden.

U kunt overvullingen gebruiken bij het verzenden van transactieberichten. In dit geval ontvangt het testprofiel één bericht per gebeurtenisconfiguratie. Voor meer op transactieoverseinen, zie dit [sectie](../../channels/using/getting-started-with-transactional-msg.md).

>[!NOTE]
>
>Wanneer u een testprofiel als overvulling gebruikt, worden voor alle verrijkte velden in een bericht de bijbehorende aanvullende gegevens willekeurig gekozen uit een echt doelprofiel en toegewezen aan het testprofiel voor overvulling. Zie voor meer informatie over verrijking [dit voorbeeld](../../automating/using/enriching-profile-data-file.md).
