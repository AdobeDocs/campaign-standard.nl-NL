---
title: De verzending voorbereiden
description: Leer hoe u voorbereiding definieert voordat u gaat verzenden.
page-status-flag: never-activated
uuid: 1038dae2-164c-4579-9294-bdf2a4eb12d6
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
discoiquuid: 003abc83-7f07-471f-ab2f-1d352d22c26f
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 3b40a9bba79d04f1635b7522cfc99f9e7566c3c0

---


# De verzending voorbereiden{#preparing-the-send}

De voorbereiding komt overeen met de stap voor het berekenen van de doelpopulatie en het genereren van de berichtinhoud voor elk profiel dat in het doel is opgenomen. Zodra de voorbereiding is voltooid, zijn de berichten klaar om te worden verzonden, of onmiddellijk of op [de geplande datum en tijd](../../sending/using/about-scheduling-messages.md).

1. Klik op de knop **Voorbereiden** op de actiebalk om het verzenden voor te bereiden.

   ![](assets/preparing_delivery_2.png)

1. In het **[!UICONTROL Deployment]** blok wordt de voortgang van de voorbereiding getoond en vervolgens worden de voorbereidende statistieken: aantal gerichte berichten, aantal te verzenden berichten, enz.

   Afhankelijk van de omvang van de doelpopulatie kan deze operatie enige tijd in beslag nemen.

   ![](assets/preparing_delivery.png)

1. Stop de voorbereiding op elk ogenblik gebruikend de knoop van het **Einde** , die in de actiebar wordt gevestigd.

   Tijdens de voorbereidingsfase worden geen berichten verzonden. U kunt dit daarom starten of stoppen zonder het risico te lopen iets te beïnvloeden.

   ![](assets/preparing_delivery_6.png)

1. Uw bericht wordt automatisch opgeslagen tijdens de voorbereiding voor de leveringsfase. Als u wijzigingen in het schema van uw bericht na de voorbereidingsstap moet aanbrengen, moet u ervoor zorgen dat u nogmaals op de **[!UICONTROL Prepare]** knop klikt om met deze wijzigingen rekening te houden. Voor meer informatie over hoe te om een bericht te plannen, verwijs naar deze [pagina](../../sending/using/about-scheduling-messages.md).

   ![](assets/preparing_delivery_5.png)

1. Klik op de knop rechtsonder in het blok om de bereidingslogboeken weer te geven.

   ![](assets/preparing_delivery_4.png)

1. Het **[!UICONTROL Deployment]** venster wordt geopend, u corrigeert eventuele fouten en start de voorbereiding opnieuw.

   In het laatste logbericht worden foutberichten en het aantal fouten weergegeven. Een specifiek pictogram geeft het aangetroffen fouttype weer: als het gele pictogram een niet-kritieke verwerkingsfout aangeeft, geeft het rode pictogram een kritieke fout aan die voorkomt dat de levering wordt gestart.

   ![](assets/preparing_delivery_3.png)

1. Controleer de voorbereidingsstatistieken alvorens het verzenden van de berichten te bevestigen. Als het aantal te verzenden berichten niet aan uw configuratie beantwoordt, geef de gerichte bevolking (zie het [Selecteren van een publiek in een bericht](../../audiences/using/selecting-an-audience-in-a-message.md)) uit en herstart de voorbereiding.

Zodra de voorbereiding is voltooid, is uw bericht klaar om te worden verzonden. Zie [Verzenden](../../sending/using/confirming-the-send.md)bevestigen voor meer informatie.

**Typologieregels**

De Campagne van Adobe komt met een reeks ingebouwde typologieregels die tijdens de berichtvoorbereiding worden toegepast. Ze worden gebruikt om te controleren of een bericht geldig is en aan uw kwaliteitscriteria voldoet. Zie [Typologieën](../../sending/using/about-typology-rules.md). U kunt bijvoorbeeld uw eigen typologieregels definiëren. Met deze regels kunt u bijvoorbeeld algemene regels voor vermoeidheid tussen kanalen instellen die overbelaste profielen automatisch uitsluiten van campagnes. Zie [Vermoeidheidsregels](../../sending/using/fatigue-rules.md).

**SMS-berichtcontrole**

Als u verpersoonlijkingsgebieden of voorwaardelijke tekst in de inhoud van uw SMS-bericht hebt opgenomen, kunnen deze factoren karakters introduceren die niet in aanmerking worden genomen door de GSM-codering. Wanneer de voorbereiding in werking wordt gesteld, wordt de berichtlengte gecontroleerd en een waarschuwingsbericht zal worden getoond als het de grens overgaat.

Raadpleeg voor meer informatie de secties [SMS-codering, -lengte en -transliteratie](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration) en [SMS-berichten](../../channels/using/personalizing-sms-messages.md) personaliseren.
