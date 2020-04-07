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
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: ec0af8c06e36f51ddaf6e3d4190fa6acd56d2da6

---


# Typologieën beheren {#managing-typologies}

## Over typologieën {#about-typologies}

Typologieën zijn reeksen regels die u toestaan om de geldigheid van uw bericht te controleren alvorens het te verzenden. Bijvoorbeeld: De inhoud van het bericht is niet leeg, er is geen abonnement, er zijn geen duplicaten beschikbaar, enzovoort.

Typologieën zijn toegankelijk via het menu **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Typologies]** . Standaard is er een standaardtypologie beschikbaar in de toepassing. Gebaseerd op uw behoeften, kunt u uw eigen typologieën tot stand brengen of bestaande degenen wijzigen.

![](assets/typologies-list.png)

Voor elke typologie wordt in de **[!UICONTROL Typology rules]** sectie een lijst weergegeven met regels die worden uitgevoerd wanneer de typologie met een bericht wordt gebruikt.

![](assets/typology_typo-rule-list.png)

>[!NOTE]
>
>Als u meer details wilt over een van de typologische regels, dubbelklikt u erop. De regel wordt alleen-lezen weergegeven.

## Typologie maken {#creating-a-typology}

Voer de volgende stappen uit om een nieuwe typologie te maken:

1. Open het menu **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Typologies]** .

1. De lijst met typologieën wordt weergegeven. Klik op de **[!UICONTROL Create]** knop.

   ![](assets/typologies-list.png)

1. Definieer de typologie **[!UICONTROL Label]** en klik vervolgens op de **[!UICONTROL Add an element]** knop om de typologische regels te selecteren die u in de typologie wilt opnemen. For more on typology rules, refer to [this section](../../sending/using/managing-typology-rules.md).

   ![](assets/typology_addrules.png)

   >[!NOTE]
   >
   >In het **[!UICONTROL IP affinity]** veld kunt u de affiniteiten beheren op basis van uw configuratie. Ze worden gedefinieerd in het configuratiebestand van de instantie. Neem contact op met de beheerder als u de affiniteiten wilt gebruiken.

1. Klik **[!UICONTROL Create]** om uw selectie te bevestigen. Uw typologie kan nu worden gebruikt in berichten.

## Typologieën toepassen op berichten {#applying-typologies-to-messages}

Wanneer het associëren van een typologie met een bericht of berichtmalplaatje, zullen de typologische regels inbegrepen in de typologie worden uitgevoerd om de berichtgeldigheid te controleren.

>[!NOTE]
>
>Aan elk bericht of elke berichtsjabloon kan slechts één typologie worden toegewezen.

Voer de volgende stappen uit om een typologie aan een bericht te koppelen:

1. Heb toegang tot de berichteigenschappen. Bericht sjablonen zijn toegankelijk via het navigatiemenu **[!UICONTROL Resources]** > **[!UICONTROL Templates]** .

1. Selecteer in de sectie **[!UICONTROL Advanced parameters]** > **[!UICONTROL Prearation]** de typologie die u aan het bericht wilt koppelen.

   ![](assets/typology_message.png)

1. Klik op **[!UICONTROL Confirm]**.

   De geselecteerde typologie is nu gekoppeld aan het bericht. Alle bijbehorende typologische regels worden uitgevoerd om de geldigheid van het bericht te controleren.
