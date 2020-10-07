---
title: Verrijking
description: De activiteit Verrijking is een geavanceerde activiteit waarmee u aanvullende data kunt definiëren om in uw workflow te verwerken.
page-status-flag: never-activated
uuid: 8c1693ef-1312-422c-b05d-263553113f8f
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: f67c1caf-3284-4c34-a5b0-8654a95640ae
context-tags: enrichment,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 96%

---


# Verrijking{#enrichment}

## Beschrijving {#description}

![](assets/enrichment.png)

De activiteit **[!UICONTROL Enrichment]** is een geavanceerde activiteit waarmee u aanvullende data kunt definiëren om in uw workflow te verwerken.

## Gebruikscontext {#context-of-use}

De activiteit **[!UICONTROL Enrichment]** wordt over het algemeen gebruikt na targetingactiviteiten of na het importeren van een bestand en vóór activiteiten die het gebruik van getargete data mogelijk maken.

Deze activiteit bevat meer geavanceerde verrijkingsfuncties dan de activiteit **[!UICONTROL Query]**. Sommige eenvoudige scenario’s voor verrijking kunnen direct in de activiteit [Query](../../automating/using/query.md#enriching-data) worden uitgevoerd.

Met de activiteit **[!UICONTROL Enrichment]** kunt u de binnenkomende overgang gebruiken en de activiteit configureren om de uitgaande overgang met aanvullende data te voltooien. Met deze activiteit kunt u data combineren die uit meerdere sets komen of kunt u koppelingen naar een tijdelijke resource maken.

**Verwante onderwerpen**

* [Hoofdlettergebruik: Profielgegevens worden verrijkt met gegevens in een bestand](../../automating/using/enriching-profile-data-file.md).
* [Hoofdlettergebruik: Een e-mail verzenden met verrijkte velden](../../automating/using/sending-email-enriched-fields.md)

## Configuratie {#configuration}

U kunt als volgt een activiteit **[!UICONTROL Enrichment]** configureren:

1. Sleep een activiteit **[!UICONTROL Enrichment]** en zet deze neer in uw workflow.
1. Selecteer de activiteit en open deze met de knop ![](assets/edit_darkgrey-24px.png) vanuit de snelle acties die verschijnen.
1. Als de activiteit verschillende binnenkomende overgangen heeft, selecteert u de **[!UICONTROL Primary set]**. De aanvullende data die in deze activiteit zijn geconfigureerd, worden toegevoegd aan deze primaire set in de uitgaande overgang.

   Als de primaire set al aanvullende data bevat, kunt u deze behouden of verwijderen. Als u de optie **[!UICONTROL Keep all additional data from the main set]** uitschakelt, worden alleen de aanvullende data die in de **[!UICONTROL Enrichment]** zijn geconfigureerd, behouden in de uitgaande overgang.

1. Als er verschillende binnenkomende overgangen zijn, definieert u relaties tussen de primaire set en de andere binnenkomende data op het tabblad **[!UICONTROL Advanced Relations]** van de activiteit. U kunt verschillende relaties toevoegen met de knop **[!UICONTROL Add element]**.

   Wanneer u een nieuwe relatie definieert, selecteert u de set binnenkomende data die u aan de primaire set wilt koppelen. Definieer vervolgens het type relatie. Afhankelijk van de binnenkomende data en uw datamodel zijn er verschillende typen relaties beschikbaar:

   * **[!UICONTROL 1 cardinality simple link]**: Elke record van de binnenkomende data is gekoppeld aan slechts één record uit de primaire set. Elke record uit de primaire set heeft één gekoppelde record in de gekoppelde data.
   * **[!UICONTROL N cardinality collection link]**: 0, 1 of meer (N) records van de gekoppelde data kunnen worden gekoppeld aan 1 record van de primaire set.
   * **[!UICONTROL 0 or 1 cardinality simple link]**: Records uit de primaire set kunnen worden gekoppeld aan 0 of 1 record uit de gekoppelde data, maar niet meer dan één record.

   Zodra de **[!UICONTROL Cardinality]** is gedefinieerd, definieert u een **[!UICONTROL Reconciliation criteria]**. De **[!UICONTROL Source expression]** van de afstemmingscriteria kan een veld zijn van de doelresource, een [expressie](../../automating/using/advanced-expression-editing.md) of rechtstreeks een waarde tussen aanhalingstekens.

   Definieer een **[!UICONTROL Label]** en een **[!UICONTROL ID]** die later in de workflow gemakkelijk kunnen worden geïdentificeerd.

   >[!NOTE]
   >
   >U kunt alleen relaties definiëren tussen de primaire set en de andere binnenkomende overgangen die gekoppeld zijn aan de activiteit **[!UICONTROL Enrichment]**. Voor eenvoudigere scenario’s die bedoeld zijn om relaties met databaseresources te definiëren, gebruikt u een activiteit [Afstemming](../../automating/using/reconciliation.md).

1. Definieer de aanvullende data op het tabblad **[!UICONTROL Additional data]** van de activiteit. U kunt aanvullende data (eenvoudige velden, aggregaten en verzamelingen) definiëren die betrekking hebben op de doeldimensie van de primaire set of die gebaseerd zijn op de koppelingen die zijn gemaakt op het tabblad **[!UICONTROL Advanced relations]** van de activiteit **[!UICONTROL Enrichment]**.

   Raadpleeg de sectie [Data verrijken](../../automating/using/query.md#enriching-data).

1. Bevestig de configuratie van uw activiteit en sla de workflow op.

De data zijn nu beschikbaar voor gebruik in de activiteiten die zijn gekoppeld na de **[!UICONTROL Enrichment]**. U vindt deze bijvoorbeeld onder de koppeling **[!UICONTROL Additional data (targetData)]** van de personalisatievelden in een e-mailcontent.
