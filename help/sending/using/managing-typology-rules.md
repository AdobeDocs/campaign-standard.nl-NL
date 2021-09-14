---
title: Typologieregels beheren
description: Leer hoe u typologieregels gebruikt.
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
context-tags: typology,overview;typologyRule,main;typologyRule,overview
feature: Typology Rules
role: User
level: Intermediate
exl-id: 5ef66b1b-1c81-42fb-a18c-fcf7f21e1ff7
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '552'
ht-degree: 96%

---

# Typologieregels beheren {#managing-typology-rules}

## Typologieregels {#about-typology-rules}

Typologieregels zijn bedrijfsregels die het mogelijk maken om controles en filtering op uw bericht uit te voeren voordat het verzonden wordt. Beschikbare soorten typologieregels zijn:

* **Filterregels**: Met deze regels kunt u één deel van het berichtdoel uitsluiten volgens criteria die in een query zijn gedefinieerd, zoals profielen in quarantaine of profielen die al een bepaald aantal e-mailberichten hebben ontvangen. Zie [deze sectie](../../sending/using/filtering-rules.md) voor meer informatie.

* **Moeheidsregels**: Met deze regels kunt u een maximum aantal berichten per profiel definiëren om te voorkomen dat de profielen te vaak worden benaderd. Zie [deze sectie](../../sending/using/fatigue-rules.md) voor meer informatie.

* **Controleregels**: Met deze regels kan de gebruiker de geldigheid en kwaliteit van de berichten controleren voordat ze worden verzonden, zoals de weergave van tekens, de grootte van sms-berichten, de adresnotatie, enzovoort. Zie [deze sectie](../../sending/using/control-rules.md) voor meer informatie.

Typologieregels zijn beschikbaar in het menu **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Typologies]** > **[!UICONTROL Typology rules]**.

Standaard zijn verscheidene kant-en-klare typologieregels voor **filteren** en **controleren** beschikbaar. Deze worden in detail behandeld in de secties [Filterregels](../../sending/using/fatigue-rules.md) en [Controleregels](../../sending/using/control-rules.md).

Afhankelijk van wat u wilt, kunt u bestaande typologieregels wijzigen of nieuwe regels maken, met uitzondering van **[!UICONTROL Control]** regels, die alleen-lezen zijn en niet kunnen worden gewijzigd.

## Een typologieregel maken {#creating-a-typology-rule}

De belangrijkste stappen om een typologieregel te maken:

1. Open het menu **[!UICONTROL Administration]** / **[!UICONTROL Channels]** / **[!UICONTROL Typologies]** / **[!UICONTROL Typology rules]** en klik op **[!UICONTROL Create]**.

   ![](assets/typology_create-rule.png)

1. Voer het **[!UICONTROL Label]** van de typologie in en specifieer het **[!UICONTROL Channel]** waarop de regel op van toepassing moet zijn.

   ![](assets/typology-rule-label.png)

1. Geef het **[!UICONTROL Type]** van de typologieregel op en configureer deze op basis van uw behoeften. De configuratie van typologieregels is afhankelijk van het type regel. Zie de secties **[Filterregels](../../sending/using/filtering-rules.md)** en **[Moeheidsregels](../../sending/using/fatigue-rules.md)** voor meer informatie.

1. Selecteer de typologieën waarin u de nieuwe regel wilt opnemen. U doet dit door het tabblad **[!UICONTROL Typologies]** te selecteren en vervolgens op de knop **[!UICONTROL Create element]** te klikken.

   ![](assets/typology-typologies-tab.png)

1. Selecteer de gewenste typologie en klik op **[!UICONTROL Confirm]**.

   ![](assets/typology-link.png)

1. Wanneer alle typologieën zijn geselecteerd, klikt u op **[!UICONTROL Create]** om het maken van de typologieregel te bevestigen.

## Uitvoeringsvolgorde van typologieregels {#typology-rules-execution-order}

De typologieregels worden uitgevoerd in de volgorde die wordt opgegeven tijdens de targeting-, analyse- en personalisatiefasen van het bericht.

In de standaardbewerkingsmodus worden de regels in de volgende volgorde toegepast:

1. Controleregels, indien toegepast aan het begin van targeting.
1. Filterregels:

   * Native toepassingsregels voor adreskwalificatie: bepaald adres / niet-geverifieerd adres / adres op lijst van gewezen personen / quarantined adres / adreskwaliteit.
   * Filterregels die door de gebruiker zijn gedefinieerd.

1. Controleregels, indien toegepast aan het einde van targeting.
1. Controleregels, indien toegepast aan het begin van personalisatie.
1. Controleregels, indien toegepast aan het einde van personalisatie.

U kunt echter de uitvoeringsvolgorde van hetzelfde type regels in elke typologie aanpassen. Wanneer meerdere regels worden uitgevoerd tijdens dezelfde berichtverwerkingsfase, kunt u de volgorde kiezen waarin ze worden toegepast.

Een filterregel waarvan de uitvoeringsvolgorde bijvoorbeeld op nummer 20 wordt geplaatst, wordt uitgevoerd vóór een filterregel met de uitvoeringsvolgorde op nummer 30.

Bij de **[!UICONTROL Properties]** van een typologieregel kunt u de uitvoeringsvolgorde instellen. Wanneer verscheidene regels moeten worden toegepast, bepaalt de uitvoeringsvolgorde van elke regel welke eerst verwerkt moet worden. Raadpleeg de sectie [Uitvoeringsvolgorde van typologieregels](#typology-rules-execution-order) voor meer informatie.

![](assets/typology_rule-active.png)

Een typologieregel kan worden uitgeschakeld via de **[!UICONTROL Properties]** als u niet wilt dat de regel wordt toegepast op het moment dat de desbetreffende berichten worden geanalyseerd.

![](assets/typology_rule-order.png)
