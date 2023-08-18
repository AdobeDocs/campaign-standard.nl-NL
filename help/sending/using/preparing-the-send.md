---
title: De verzending voorbereiden
description: Leer hoe u voorbereiding definieert voordat u gaat verzenden.
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
feature: Send Time Optimization
role: User
level: Intermediate
exl-id: 0140c41a-7255-4b77-a1b7-c6f7b1135e51
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '459'
ht-degree: 2%

---

# De verzending voorbereiden{#preparing-the-send}

De voorbereiding komt overeen met de stap voor het berekenen van de doelpopulatie en het genereren van de berichtinhoud voor elk profiel dat in het doel is opgenomen. Zodra de voorbereiding is voltooid, zijn de berichten klaar om te worden verzonden, of onmiddellijk of bij [de geplande datum en tijd](../../sending/using/about-scheduling-messages.md).

1. Als u het verzenden wilt voorbereiden, klikt u op de knop **Voorbereiden** in de actiebalk.

   ![](assets/preparing_delivery_2.png)

1. De **[!UICONTROL Deployment]** blok geeft de voortgang van de voorbereiding weer en vervolgens de voorbereidingsstatistieken: aantal gerichte berichten, aantal te verzenden berichten, enz.

   Afhankelijk van de omvang van de doelpopulatie kan deze operatie enige tijd duren.

   ![](assets/preparing_delivery.png)

1. Stop op elk moment met het gebruik van de **Stoppen** in de actiebalk.

   Tijdens de voorbereidingsfase worden geen berichten verzonden. U kunt dit daarom starten of stoppen zonder het risico te lopen iets te beïnvloeden.

   ![](assets/preparing_delivery_6.png)

1. Uw bericht wordt automatisch opgeslagen tijdens de voorbereiding voor de leveringsfase. Als u na de voorbereidingsstap wijzigingen wilt aanbrengen in de planning van uw bericht, moet u ervoor zorgen dat u op de knop **[!UICONTROL Prepare]** nogmaals te klikken om met deze wijzigingen rekening te houden. Voor meer informatie over hoe te om een bericht te plannen, verwijs naar dit [page](../../sending/using/about-scheduling-messages.md).

   ![](assets/preparing_delivery_5.png)

1. Klik op de knop rechtsonder in het blok om de bereidingslogboeken weer te geven.

   ![](assets/preparing_delivery_4.png)

1. De **[!UICONTROL Deployment]** wordt geopend, worden eventuele fouten gecorrigeerd en wordt de voorbereiding opnieuw gestart.

   In het laatste logbericht worden foutberichten en het aantal fouten weergegeven. Een specifiek pictogram geeft het aangetroffen fouttype weer: het gele pictogram geeft een niet-kritieke verwerkingsfout aan, het rode pictogram geeft een kritieke fout aan die voorkomt dat de levering wordt gestart.

   ![](assets/preparing_delivery_3.png)

1. Controleer de voorbereidingsstatistieken alvorens het verzenden van de berichten te bevestigen. Als het aantal te verzenden berichten niet aan uw configuratie beantwoordt, geef de gerichte bevolking uit (zie [Een publiek in een bericht selecteren](../../audiences/using/selecting-an-audience-in-a-message.md)) en start de voorbereiding opnieuw.

Zodra de voorbereiding is voltooid, is uw bericht klaar om te worden verzonden. Zie voor meer informatie [Verzenden bevestigen](../../sending/using/confirming-the-send.md).

**Typologieregels**

Adobe Campaign wordt geleverd met een reeks ingebouwde typologische regels die worden toegepast tijdens de voorbereiding van berichten. Ze worden gebruikt om te controleren of een bericht geldig is en aan uw kwaliteitscriteria voldoet. Zie [Typologieën](../../sending/using/about-typology-rules.md). U kunt bijvoorbeeld uw eigen typologieregels definiëren. Met deze regels kunt u bijvoorbeeld algemene regels voor vermoeidheid tussen kanalen instellen die overbelaste profielen automatisch uitsluiten van campagnes. Zie [Moeheidsregels](../../sending/using/fatigue-rules.md).

**SMS-berichtcontrole**

Als u verpersoonlijkingsgebieden of voorwaardelijke tekst in de inhoud van uw SMS-bericht hebt opgenomen, kunnen deze factoren karakters introduceren die niet in aanmerking worden genomen door de GSM-codering. Wanneer de voorbereiding in werking wordt gesteld, wordt de berichtlengte gecontroleerd en een waarschuwingsbericht zal worden getoond als het de grens overgaat.

Raadpleeg voor meer informatie de [SMS-codering, -lengte en -transliteratie](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration) en [SMS-berichten aanpassen](../../channels/using/personalizing-sms-messages.md) secties.
