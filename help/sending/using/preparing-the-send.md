---
solution: Campaign Standard
product: campaign
title: De verzending voorbereiden
description: Leer hoe u voorbereiding definieert voordat u gaat verzenden.
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
feature: Tijdoptimalisatie verzenden
role: Zakelijke praktiserer
level: Intermediair
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 2%

---


# De verzending voorbereiden{#preparing-the-send}

De voorbereiding komt overeen met de stap voor het berekenen van de doelpopulatie en het genereren van de berichtinhoud voor elk profiel dat in het doel is opgenomen. Zodra de voorbereiding wordt gebeëindigd, zijn de berichten klaar om worden verzonden, of onmiddellijk of om [de geplande datum en tijd](../../sending/using/about-scheduling-messages.md).

1. Als u wilt beginnen met het voorbereiden van de verzending, klikt u op de knop **Voorbereiden** op de actiebalk.

   ![](assets/preparing_delivery_2.png)

1. In het **[!UICONTROL Deployment]**-blok wordt de voortgang van de voorbereiding weergegeven, daarna worden de voorbereidingsstatistieken weergegeven: aantal gerichte berichten, aantal te verzenden berichten, enz.

   Afhankelijk van de omvang van de doelpopulatie kan deze operatie enige tijd in beslag nemen.

   ![](assets/preparing_delivery.png)

1. Stop de voorbereiding op elk ogenblik gebruikend **Stop** knoop, die in de actiebar wordt gevestigd.

   Tijdens de voorbereidingsfase worden geen berichten verzonden. U kunt dit daarom starten of stoppen zonder het risico te lopen iets te beïnvloeden.

   ![](assets/preparing_delivery_6.png)

1. Uw bericht wordt automatisch opgeslagen tijdens de voorbereiding voor de leveringsfase. Als u om het even welke veranderingen in het programma van uw bericht na de voorbereidingsstap moet aanbrengen, zult u ervoor moeten zorgen dat u opnieuw de **[!UICONTROL Prepare]** knoop voor die veranderingen klikt om in aanmerking te worden genomen. Voor meer informatie over hoe te om een bericht te plannen, verwijs naar deze [pagina](../../sending/using/about-scheduling-messages.md).

   ![](assets/preparing_delivery_5.png)

1. Klik op de knop rechtsonder in het blok om de bereidingslogboeken weer te geven.

   ![](assets/preparing_delivery_4.png)

1. Het venster **[!UICONTROL Deployment]** wordt geopend, corrigeert eventuele fouten en start de voorbereiding opnieuw.

   In het laatste logbericht worden foutberichten en het aantal fouten weergegeven. Een specifiek pictogram geeft het aangetroffen fouttype weer: als het gele pictogram een niet-kritieke verwerkingsfout aangeeft, geeft het rode pictogram een kritieke fout aan die voorkomt dat de levering wordt gestart.

   ![](assets/preparing_delivery_3.png)

1. Controleer de voorbereidingsstatistieken alvorens het verzenden van de berichten te bevestigen. Als het aantal te verzenden berichten niet aan uw configuratie beantwoordt, geef de gerichte bevolking (zie [Selecterend een publiek in een bericht](../../audiences/using/selecting-an-audience-in-a-message.md)) uit en herstart de voorbereiding.

Zodra de voorbereiding is voltooid, is uw bericht klaar om te worden verzonden. Zie [Verzenden bevestigen](../../sending/using/confirming-the-send.md) voor meer informatie.

**Typologieregels**

Adobe Campaign wordt geleverd met een reeks ingebouwde typologische regels die worden toegepast tijdens de voorbereiding van berichten. Ze worden gebruikt om te controleren of een bericht geldig is en aan uw kwaliteitscriteria voldoet. Zie [Typologieën](../../sending/using/about-typology-rules.md). U kunt bijvoorbeeld uw eigen typologieregels definiëren. Met deze regels kunt u bijvoorbeeld algemene regels voor vermoeidheid tussen kanalen instellen die overbelaste profielen automatisch uitsluiten van campagnes. Zie [Moeheidsregels](../../sending/using/fatigue-rules.md).

**SMS-berichtcontrole**

Als u verpersoonlijkingsgebieden of voorwaardelijke tekst in de inhoud van uw SMS-bericht hebt opgenomen, kunnen deze factoren karakters introduceren die niet in aanmerking worden genomen door de GSM-codering. Wanneer de voorbereiding in werking wordt gesteld, wordt de berichtlengte gecontroleerd en een waarschuwingsbericht zal worden getoond als het de grens overgaat.

Raadpleeg de secties [SMS-codering, -lengte en -transliteratie](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration) en [SMS-berichten aanpassen](../../channels/using/personalizing-sms-messages.md) voor meer informatie.
