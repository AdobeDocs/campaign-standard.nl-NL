---
title: Typologieregels beheren
description: Ontdek hoe u de typologische regels moet gebruiken.
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
source-git-commit: 7f5bc442b1dae467a6b6de3e048531940f75031f
workflow-type: tm+mt
source-wordcount: '554'
ht-degree: 0%

---


# Typologieregels beheren {#managing-typology-rules}

## Typologische regels {#about-typology-rules}

De regels van de typologie zijn bedrijfsregels die u toestaan om controles en het filtreren op uw bericht uit te voeren alvorens het te verzenden. Beschikbare typen typologische regels zijn:

* **Filterregels** : Met dit type regel kunt u één deel van het berichtdoel uitsluiten volgens criteria die in een query zijn gedefinieerd, zoals quarantined profielen of profielen die al een bepaald aantal e-mailberichten hebben ontvangen. For more on this, refer to [this section](../../sending/using/filtering-rules.md).

* **Regels voor vermoeidheid** : Met dit type regels kunt u een maximum aantal berichten per profiel definiëren om te voorkomen dat er te veel wordt gevraagd. For more on this, refer to [this section](../../sending/using/fatigue-rules.md).

* **Regels voor controle** : Met dit type regels kan de gebruiker de geldigheid en kwaliteit van de berichten controleren voordat ze worden verzonden, zoals de weergave van tekens, de grootte van SMS-berichten, de adresindeling, enzovoort. For more on this, refer to [this section](../../sending/using/control-rules.md).

Typologische regels zijn beschikbaar in het menu **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Typologies]** > **[!UICONTROL Typology rules]** .

Door gebrek, zijn verscheidene uit-van-de-doos het **filtreren** en **controle** typologische regels beschikbaar. Zij zijn gedetailleerd in de het [Filtreren regels](../../sending/using/fatigue-rules.md) en de secties van de Regels [van de](../../sending/using/control-rules.md) Controle.

Afhankelijk van uw behoeften kunt u bestaande typologische regels wijzigen of nieuwe regels maken, met uitzondering van **[!UICONTROL Control]** regels, die alleen-lezen zijn en niet kunnen worden gewijzigd.

## Een typologieregel maken {#creating-a-typology-rule}

De belangrijkste stappen om een typologieregel tot stand te brengen zijn als volgt:

1. Open het menu / **[!UICONTROL Administration]** / **[!UICONTROL Channels]** / **[!UICONTROL Typologies]** / **[!UICONTROL Typology rules]** en klik op **[!UICONTROL Create]**.

   ![](assets/typology_create-rule.png)

1. Voer de typologie in **[!UICONTROL Label]** en geef op **[!UICONTROL Channel]** op welke regel u wilt toepassen.

   ![](assets/typology-rule-label.png)

1. Geef de typologieregel op **[!UICONTROL Type]** en configureer deze op basis van uw behoeften. De configuratie van typologische regels is afhankelijk van het type. Raadpleeg de secties **[Filterregels](../../sending/using/filtering-rules.md)**en**[ Vermoeidheidsregels](../../sending/using/fatigue-rules.md)** voor meer informatie.

1. Selecteer de typologieën waarin u de nieuwe regel wilt omvatten. U doet dit door het **[!UICONTROL Typologies]** tabblad te selecteren en vervolgens op de **[!UICONTROL Create element]** knop te klikken.

   ![](assets/typology-typologies-tab.png)

1. Selecteer de gewenste typologie en klik op **[!UICONTROL Confirm]**.

   ![](assets/typology-link.png)

1. Wanneer alle typologieën zijn geselecteerd, klikt u **[!UICONTROL Create]** om het maken van de typologieregel te bevestigen.

## Uitvoeringsvolgorde van typologieregels {#typology-rules-execution-order}

De regels van de typologie worden uitgevoerd in een orde die tijdens de het richten, analyse, en de fasen van de berichtverpersoonlijking wordt gespecificeerd.

In de standaardbewerkingsmodus worden de regels in de volgende volgorde toegepast:

1. Controlevoorschriften, als zij bij het begin van het richten worden toegepast.
1. Filterregels:

   * Native toepassingsregels voor adreskwalificatie: gedefinieerd adres / niet-geverifieerd adres / adres in de bloklijst / quarantineadres / adreskwaliteit.
   * Filterregels die door de gebruiker zijn gedefinieerd.

1. Controlevoorschriften, als zij aan het eind van het richten worden toegepast.
1. Regels van de controle, als zij bij het begin van verpersoonlijking worden toegepast.
1. Regels van de controle, als zij aan het eind van verpersoonlijking worden toegepast.

U kunt echter de uitvoeringsvolgorde van hetzelfde type regels in elke typologie aanpassen. Wanneer meerdere regels worden uitgevoerd tijdens dezelfde verwerkingsfase van berichten, kunt u de volgorde kiezen waarin ze worden toegepast.

Bijvoorbeeld, zal een het filtreren regel de waarvan uitvoeringsorde bij aantal 20 wordt geplaatst vóór een het filtreren regel worden uitgevoerd de waarvan uitvoeringsorde bij aantal 30 wordt geplaatst.

In het geval **[!UICONTROL Properties]** van een typologieregel kunt u de uitvoeringsvolgorde instellen. Wanneer verscheidene regels moeten worden toegepast, bepaalt de uitvoeringsorde van elke regel degenen eerst te verwerken. Raadpleeg voor meer informatie de sectie over de uitvoeringsvolgorde van de [Typologieregels](#typology-rules-execution-order) .

![](assets/typology_rule-active.png)

Een typologieregel kan via de regel worden gedeactiveerd **[!UICONTROL Properties]** als u niet wilt dat de regel wordt toegepast op het moment dat de berichten waarop de regel betrekking heeft, worden geanalyseerd.

![](assets/typology_rule-order.png)