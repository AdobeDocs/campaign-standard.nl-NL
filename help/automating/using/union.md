---
title: Unie
description: De activiteit van de Unie staat u toe om het resultaat van veelvoudige activiteiten in één enkel doel te hergroeperen.
page-status-flag: never-activated
uuid: fafc3ce9-2212-4403-8754-cfbb28ba6e26
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 99a8c3a5-7d90-4dbb-aa37-1d0a84719cf6
context-tags: union,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 87e0611fae0560aca276caa3c4cf793e9c095d72
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 0%

---


# Unie{#union}

## Beschrijving {#description}

![](assets/union.png)

De **[!UICONTROL Union]** activiteit staat u toe om het resultaat van veelvoudige activiteiten in één enkel doel te hergroeperen.

>[!NOTE]
>
>De sets hoeven niet noodzakelijkerwijs homogeen te zijn.

## Gebruikscontext {#context-of-use}

De **[!UICONTROL Union]** activiteit wordt gebruikt om de populaties van binnenkomende overgangen te combineren wanneer het uitvoeren van een segmentatie, het bepalen van een publiek, of wanneer het voorbereiden van het berichtdoel bijvoorbeeld.

**Verwante onderwerpen:**

* [Hoofdlettergebruik: Unie op twee verfijnde doelgroepen](../../automating/using/union-on-two-refined-audiences.md)

## Configuratie {#configuration}

1. Sleep een **[!UICONTROL Union]** activiteit naar uw werkstroom.
1. Sluit het aan de andere activiteiten aan die voor het komen, zoals vragen.
1. Selecteer de activiteit, dan open het gebruikend de ![](assets/edit_darkgrey-24px.png) knoop van de snelle acties die verschijnen.
1. Selecteer de **[!UICONTROL Reconciliation type]** methode om te bepalen hoe duplicaten worden verwerkt vanuit de confrontatie tussen binnenkomende populaties:

   * **[!UICONTROL Keys only]**: dit is de standaardmodus. De activiteit houdt slechts één element wanneer de elementen van de verschillende binnenkomende overgangen de zelfde sleutel hebben. Deze optie kan alleen worden gebruikt als de binnenkomende populaties homogeen zijn.
   * **[!UICONTROL All shared columns]**: De gegevens worden afgestemd op basis van alle kolommen die overeenkomen met de binnenkomende overgangen. Daarom moet u de primaire reeks selecteren die in het geval van een duplicaat zal worden gehouden. Deze optie kan worden gebruikt als de binnenkomende populatie verschillende doeldimensies heeft.
   * **[!UICONTROL A selection of columns]**: Selecteer deze optie om de lijst met kolommen te definiëren waarop de afstemming van gegevens wordt toegepast. U moet eerst de primaire set selecteren (die de brongegevens bevat) en vervolgens de kolommen die u voor de samenvoeging wilt gebruiken.

1. Schakel het **[!UICONTROL Use common additional data only]** selectievakje in als u alleen de aanvullende gegevens in alle binnenkomende overgangen wilt behouden.
1. Als u de grootte van de uiteindelijke populatie wilt beperken, schakelt u het **[!UICONTROL Limit size of generated population]** selectievakje in. De grootte kan in het **[!UICONTROL Maximum number of records]** veld worden opgegeven.
1. Indien nodig, beheer de [Overgangen](../../automating/using/activity-properties.md) van de activiteit om tot de geavanceerde opties voor de berekende bevolking toegang te hebben.
1. Bevestig de configuratie van uw activiteit en sla uw werkschema op.

## Voorbeeld {#example}

Het volgende voorbeeld toont het resultaat van twee vraagactiviteiten die erop gericht zijn profielen van de gegevensbank van Adobe Campaign te hergroeperen die tussen 18 en 27 jaar oud zijn en die tussen 34 en 40 jaar oud zijn. Het resultaat bevat alle profielen van de twee vragen of het maximumaantal verslagen, indien van toepassing, zoals gespecificeerd tijdens de configuratie.

![](assets/wkf_union_example.png)