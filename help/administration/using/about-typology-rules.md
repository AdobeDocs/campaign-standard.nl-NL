---
title: Typologische regels
description: Ontdek hoe typologische regels werken in Adobe Campaign.
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
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Typologische regels{#about-typology-rules}

Een typologie is een reeks regels, uitgevoerd tijdens de fase van de berichtanalyse, die het doel, de inhoud, en de configuratie van de volgende te bevestigen elementen toestaan: het onderwerp, de URL, de afbeeldingen, de koppeling om geen abonnement te nemen, de proefdrukgrootte, enz.

In Adobe Campaign bevat elk bericht een koppeling naar een typologie. Deze verbinding wordt bepaald in de geavanceerde parameters van de eigenschappen van het leveringsmalplaatje (voor meer op dit, verwijs naar de sectie van de [Voorbereiding](../../administration/using/configuring-email-channel.md#preparation) ).

>[!NOTE]
>
>Aan elk bericht kan slechts één typologie worden toegewezen.

Voor elke typologie geeft de **[!UICONTROL Typology rules]** sectie de set regels voor deze typologie weer.

![](assets/typology_typo-rule-list.png)

## Typologieën beheren {#managing-typologies}

De toepassing bevat standaard verschillende typologieën. Gebaseerd op uw behoeften, kunt u uw eigen typologieën tot stand brengen of bestaande degenen wijzigen.

1. Open het menu **[!UICONTROL List of typologies]** via **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Typologies]** .
1. Selecteer een typologie om de inhoud en eigenschappen ervan te wijzigen of om een nieuwe te maken.

   ![](assets/typology_list.png)

1. Definieer het type typologie. Typologieën kunnen Standard of Filtrerend typologieën zijn.
1. Voeg de typologische regels toe die u nodig hebt met de **[!UICONTROL Add an element]** knop of verwijder de regels die u niet wilt gebruiken.

   U kunt de volgorde wijzigen waarin de regels worden toegepast voor een bepaalde typologie. Hiervoor verplaatst u de elementen om de volgorde te wijzigen waarin ze op het scherm worden weergegeven. De getallen die overeenkomen met de uitvoeringsvolgorde worden vervolgens automatisch opnieuw berekend. De toepassingsmodus van de regel wordt weergegeven in de sectie voor de uitvoeringsvolgorde van de [Typologieregels](#typology-rules-execution-order) .

   De regels die op dit scherm worden weergegeven, zijn alleen-lezen.

Uw typologie is klaar om te worden gebruikt. U kunt het in berichteigenschappen of in de eigenschappen van het berichtmalplaatje selecteren.

>[!NOTE]
>
>In het **[!UICONTROL IP affinity]** veld kunt u de affiniteiten beheren op basis van uw configuratie. Deze worden gedefinieerd in het configuratiebestand van de instantie. Neem contact op met de beheerder als u de affiniteiten wilt gebruiken.

## Typologieregels {#typology-rules}

De regels van de typologie zijn bedrijfsregels die tijdens de berichtvoorbereiding worden toegepast. Ze worden gebruikt om te controleren of een bericht geldig is en aan uw kwaliteitscriteria voldoet. Zij controleren ook of elk lid van het doelpubliek verkiesbaar is om het bericht te ontvangen.

Typologische regels zijn beschikbaar in het menu **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Typologies]** > **[!UICONTROL Typology rules]** .

Er zijn twee soorten regels:

* **Filterregels** : staat u toe om één deel van het berichtdoel volgens criteria uit te sluiten die in een vraag worden bepaald, zoals quarantined profielen of profielen die reeds een bepaald aantal e-mails zijn verzonden. Zie [Filterregels](../../administration/using/filtering-rules.md).
* **Regels voor vermoeidheid** : Hiermee kunt u een maximum aantal berichten per profiel definiëren om te voorkomen dat er te veel wordt gevraagd. Zie [Vermoeidheidsregels](../../administration/using/fatigue-rules.md).
* **Regels voor controle** : de gebruiker toestaan de geldigheid en kwaliteit van de berichten te controleren voordat deze worden verzonden, zoals tekenweergave, grootte van SMS-berichten, adresindeling enz. Zie [Regels](../../administration/using/control-rules.md)voor besturing.

Een typologieregel kan op slechts één kanaal of op alle kanalen worden toegepast.

![](assets/typology_channel.png)

In het geval **[!UICONTROL Properties]** van een typologieregel kunt u de uitvoeringsvolgorde instellen. Wanneer verscheidene regels moeten worden toegepast, bepaalt de uitvoeringsorde van elke regel degenen eerst te verwerken. Raadpleeg voor meer informatie de sectie over de uitvoeringsvolgorde van de [Typologieregels](#typology-rules-execution-order) .

![](assets/typology_rule-active.png)

Een typologieregel kan via de regel worden gedeactiveerd **[!UICONTROL Properties]** als u niet wilt dat de regel wordt toegepast op het moment dat de berichten waarop de regel betrekking heeft, worden geanalyseerd.

![](assets/typology_rule-order.png)

In de **[!UICONTROL Targeting context]** categorie kunt u de **doeldimensie** en de **filterdimensie** selecteren, afhankelijk van de gegevens die u als doel wilt instellen.

Filteren wordt standaard uitgevoerd op de **[!UICONTROL Profiles]** knop. Als de regel bijvoorbeeld op een mobiele toepassing is gericht, **[!UICONTROL Filtering dimension]** kan deze worden gewijzigd in **[!UICONTROL Subscriptions to an application]**.

![](assets/typology_rule-order_2.png)

## Uitvoeringsvolgorde van typologieregels {#typology-rules-execution-order}

De typologieregels worden uitgevoerd in een orde die tijdens de het richten, analyse, en de fasen van de berichtverpersoonlijking wordt gespecificeerd.

In de standaardbewerkingsmodus worden de regels in de volgende volgorde toegepast:

1. Controlevoorschriften, als zij bij het begin van het richten worden toegepast.
1. Filterregels:

   * Native toepassingsregels voor adreskwalificatie: gedefinieerd adres / niet-geverifieerd adres / adres / adres op de zwarte lijst / kwaliteit van het quarantaineadres / adres.
   * Filterregels die door de gebruiker zijn gedefinieerd.

1. Controlevoorschriften, als zij aan het eind van het richten worden toegepast.
1. Regels van de controle, als zij bij het begin van verpersoonlijking worden toegepast.
1. Regels van de controle, als zij aan het eind van verpersoonlijking worden toegepast.

U kunt echter de uitvoeringsvolgorde van hetzelfde type regels in elke typologie aanpassen. Wanneer meerdere regels worden uitgevoerd tijdens dezelfde verwerkingsfase van berichten, kunt u de volgorde kiezen waarin ze worden toegepast.

Bijvoorbeeld, zal een het filtreren regel de waarvan uitvoeringsorde bij aantal 20 wordt geplaatst vóór een het filtreren regel worden uitgevoerd de waarvan uitvoeringsorde bij aantal 30 wordt geplaatst.
