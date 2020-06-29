---
title: Verrijking
description: De verrijkingsactiviteit is een geavanceerde activiteit die u toestaat om extra gegevens te bepalen in uw werkschema te verwerken.
page-status-flag: never-activated
uuid: 8c1693ef-1312-422c-b05d-263553113f8f
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: f67c1caf-3284-4c34-a5b0-8654a95640ae
context-tags: enrichment,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 87e0611fae0560aca276caa3c4cf793e9c095d72
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 0%

---


# Verrijking{#enrichment}

## Beschrijving {#description}

![](assets/enrichment.png)

De **[!UICONTROL Enrichment]** activiteit is een geavanceerde activiteit die u toestaat om extra gegevens te bepalen in uw werkschema te verwerken.

## Gebruikscontext {#context-of-use}

De **[!UICONTROL Enrichment]** activiteit wordt over het algemeen gebruikt na doelactiviteiten of na het importeren van een bestand en vóór activiteiten die het gebruik van gerichte gegevens mogelijk maken.

Deze activiteit bevat meer geavanceerde verrijkingsfuncties dan de **[!UICONTROL Query]** activiteit. Sommige eenvoudige gevallen van verrijking kunnen direct in de activiteit [van de](../../automating/using/query.md#enriching-data)Vraag worden uitgevoerd.

Met de **[!UICONTROL Enrichment]** activiteit, kunt u hefboomwerking de binnenkomende overgang en de activiteit vormen om de outputovergang met extra gegevens te voltooien. Het staat toe om gegevens te combineren die uit veelvoudige reeksen komen, of verbindingen aan een tijdelijke middel tot stand te brengen.

**Verwante onderwerpen**

* [Hoofdlettergebruik: Profielgegevens worden verrijkt met gegevens in een bestand](../../automating/using/enriching-profile-data-file.md).
* [Hoofdlettergebruik: Een e-mail verzenden met verrijkte velden](../../automating/using/sending-email-enriched-fields.md)

## Configuratie {#configuration}

Een **[!UICONTROL Enrichment]** activiteit configureren:

1. Sleep een **[!UICONTROL Enrichment]** activiteit naar uw werkstroom.
1. Selecteer de activiteit, dan open het gebruikend de ![](assets/edit_darkgrey-24px.png) knoop van de snelle acties die verschijnen.
1. Als de activiteit verscheidene binnenkomende overgangen heeft, selecteer **[!UICONTROL Primary set]**. De extra gegevens die in deze activiteit worden gevormd zullen aan deze primaire reeks in de uitgaande overgang worden toegevoegd.

   Als de primaire set al aanvullende gegevens bevat, kunt u deze behouden of verwijderen. Als u de **[!UICONTROL Keep all additional data from the main set]** optie uncheck, slechts worden de extra gegevens die in **[!UICONTROL Enrichment]** worden gevormd gehouden in de uitgaande overgang.

1. Als er verscheidene binnenkomende overgangen zijn, bepaal relaties tussen de primaire reeks en de andere binnenkomende gegevens op het **[!UICONTROL Advanced Relations]** lusje van de activiteit. U kunt meerdere relaties toevoegen met de **[!UICONTROL Add element]** knop.

   Wanneer u een nieuwe relatie definieert, selecteert u de set binnenkomende gegevens die u wilt koppelen aan de primaire set. Definieer vervolgens het type relatie. Afhankelijk van de binnenkomende gegevens en uw gegevensmodel zijn er verschillende soorten relaties beschikbaar:

   * **[!UICONTROL 1 cardinality simple link]**: elke record van de binnenkomende gegevens is gekoppeld aan één record uit de primaire set. Elke record uit de primaire set heeft één gekoppelde record in de gekoppelde gegevens.
   * **[!UICONTROL N cardinality collection link]**: 0, 1 of meer (N) records van de gekoppelde gegevens kunnen worden gekoppeld aan 1 record van de primaire set.
   * **[!UICONTROL 0 or 1 cardinality simple link]**: records uit de primaire set kunnen worden gekoppeld aan 0 of 1 record uit de gekoppelde gegevens, maar niet meer dan één record.
   Als de definitie eenmaal **[!UICONTROL Cardinality]** is opgegeven, definieert u een **[!UICONTROL Reconciliation criteria]**. De afstemmingscriteria **[!UICONTROL Source expression]** kunnen een veld zijn van de doelbron, een [expressie](../../automating/using/advanced-expression-editing.md) of rechtstreeks een waarde tussen aanhalingstekens.

   Definieer een **[!UICONTROL Label]** en een bestand **[!UICONTROL ID]** dat later in de workflow gemakkelijk kan worden herkend.

   >[!NOTE]
   >
   >U kunt alleen relaties definiëren tussen de primaire set en de andere binnenkomende overgangen die verbonden zijn met de **[!UICONTROL Enrichment]** activiteit. Voor eenvoudigere gevallen die bedoeld zijn om relaties met databasebronnen te definiëren, gebruikt u een [afstemmingsactiviteit](../../automating/using/reconciliation.md) .

1. Definieer de aanvullende gegevens op het **[!UICONTROL Additional data]** tabblad van de activiteit. U kunt aanvullende gegevens (eenvoudige velden, aggregaten en verzamelingen) definiëren die betrekking hebben op de doeldimensie van de primaire set of die zijn gebaseerd op de koppelingen die zijn gemaakt op het **[!UICONTROL Advanced relations]** tabblad van de **[!UICONTROL Enrichment]** activiteit.

   Raadpleeg de sectie [Verrijkende gegevens](../../automating/using/query.md#enriching-data) .

1. Bevestig de configuratie van uw activiteit en sla uw werkschema op.

De gegevens zijn nu beschikbaar voor gebruik in de activiteiten die na de **[!UICONTROL Enrichment]** verbinding zijn verbonden. U vindt deze bijvoorbeeld onder de **[!UICONTROL Additional data (targetData)]** koppeling van de verpersoonlijkingsvelden in een e-mailinhoud.
