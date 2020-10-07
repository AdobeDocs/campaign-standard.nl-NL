---
title: Typologieën beheren
description: Ontdek hoe u typologieën kunt gebruiken.
page-status-flag: never-activated
uuid: a98ebc36-172d-4f46-b6ee-b2636a1007c9
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
discoiquuid: 2590d94c-51ef-4c0f-b1ec-c2837e94da40
context-tags: typology,overview;typologyRule,main;typologyRule,overview
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 100%

---


# Typologieën beheren {#managing-typologies}

## Typologieën {#about-typologies}

Typologieën zijn reeksen regels waarmee u de geldigheid van uw bericht kunt controleren alvorens het te verzenden. Bijvoorbeeld: de content van het bericht is niet leeg, er is een uitschrijving, uitsluiting van duplicaten enzovoort.

Typologieën zijn toegankelijk via het menu **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Typologies]**. Standaard is er een standaardtypologie beschikbaar in de applicatie. Op basis van uw behoeften kunt u uw eigen typologieën maken of bestaande typologieën wijzigen.

![](assets/typologies-list.png)

Voor elke typologie bevat de sectie **[!UICONTROL Typology rules]** de lijst met regels die worden uitgevoerd wanneer de typologie met een bericht wordt gebruikt.

![](assets/typology_typo-rule-list.png)

>[!NOTE]
>
>Als u meer details over een van de typologieregels wilt weergeven, dubbelklikt u erop. De regel wordt in de modus Alleen-lezen weergegeven.

## Een typologie maken {#creating-a-typology}

Voer de volgende stappen uit om een nieuwe typologie te maken:

1. Open het menu **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Typologies]**.

1. De lijst met typologieën wordt weergegeven. Klik op de knop **[!UICONTROL Create]**.

   ![](assets/typologies-create.png)

1. Definieer de typologie **[!UICONTROL Label]** en klik vervolgens op de knop **[!UICONTROL Add an element]** om de typologieregels te selecteren die u erin wilt opnemen. Raadpleeg [deze sectie](../../sending/using/managing-typology-rules.md) voor meer informatie over typologieregels.

   ![](assets/typology_addrules.png)

   >[!NOTE]
   >
   >In het veld **[!UICONTROL IP affinity]** kunt u de affiniteiten beheren op basis van uw configuratie. Ze worden gedefinieerd in het configuratiebestand van de instantie. Neem contact op met de beheerder als u de affiniteiten wilt gebruiken.

1. Klik op **[!UICONTROL Create]** om uw selectie te bevestigen. Uw typologie kan nu worden gebruikt in berichten.

## Typologieën toepassen op berichten {#applying-typologies-to-messages}

Wanneer u een typologie aan een bericht of berichtsjabloon koppelt, worden de typologieregels die in de typologie zijn opgenomen, uitgevoerd om de berichtgeldigheid te controleren.

>[!NOTE]
>
>Aan elk bericht of elke berichtsjabloon kan slechts één typologie worden toegewezen.

Voer de volgende stappen uit om een typologie aan een bericht te koppelen:

1. Open de berichteigenschappen. Berichtsjablonen zijn toegankelijk via het navigatiemenu **[!UICONTROL Resources]** > **[!UICONTROL Templates]**.

1. Selecteer in de sectie **[!UICONTROL Advanced parameters]** > **[!UICONTROL Preparation]** de typologie die u aan het bericht wilt koppelen.

   ![](assets/typology_message.png)

1. Klik op **[!UICONTROL Confirm]**.

   De geselecteerde typologie is nu gekoppeld aan het bericht. Alle bijbehorende typologieregels worden uitgevoerd om de geldigheid van het bericht te controleren.
