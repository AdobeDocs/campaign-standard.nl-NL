---
title: Samenvoegen
description: Met de activiteit Samenvoegen kunt u het resultaat van meerdere activiteiten hergroeperen in één doel.
page-status-flag: never-activated
uuid: fafc3ce9-2212-4403-8754-cfbb28ba6e26
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 99a8c3a5-7d90-4dbb-aa37-1d0a84719cf6
context-tags: union,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 98%

---


# Samenvoegen{#union}

## Beschrijving {#description}

![](assets/union.png)

Met de activiteit **[!UICONTROL Union]** kunt u het resultaat van meerdere activiteiten hergroeperen in één doel.

>[!NOTE]
>
>De sets hoeven niet noodzakelijkerwijs homogeen te zijn.

## Gebruikscontext {#context-of-use}

De activiteit **[!UICONTROL Union]** wordt gebruikt om de populaties van binnenkomende overgangen te combineren, bijvoorbeeld bij het uitvoeren van een segmentatie, het definiëren van een doelgroep of het voorbereiden van het berichtdoel.

**Verwante onderwerpen:**

* [Hoofdlettergebruik: Unie op twee verfijnde doelgroepen](../../automating/using/union-on-two-refined-audiences.md)

## Configuratie {#configuration}

1. Sleep een activiteit **[!UICONTROL Union]** en zet deze neer in uw workflow.
1. Verbind de activiteit met de andere activiteiten die eraan voorafgaan, zoals query’s.
1. Selecteer de activiteit en open deze met de knop ![](assets/edit_darkgrey-24px.png) vanuit de snelle acties die verschijnen.
1. Selecteer het **[!UICONTROL Reconciliation type]** om te bepalen hoe duplicaten die resulteren uit de confrontatie tussen binnenkomende populaties worden verwerkt:

   * **[!UICONTROL Keys only]**: Dit is de standaardmodus. De activiteit behoudt slechts één element wanneer elementen van de verschillende binnenkomende overgangen dezelfde sleutel hebben. Deze optie kan alleen worden gebruikt als de binnenkomende populaties homogeen zijn.
   * **[!UICONTROL All shared columns]**: De data worden afgestemd op basis van alle kolommen die overeenkomen met de binnenkomende overgangen. Daarom moet u de primaire set selecteren die in het geval van een duplicaat behouden blijft. Deze optie kan worden gebruikt als de doeldimensies van de binnenkomende populatie verschillend zijn.
   * **[!UICONTROL A selection of columns]**: Selecteer deze optie om de lijst met kolommen te definiëren waarop de afstemming van data wordt toegepast. U moet eerst de primaire set (de set met de brondata) selecteren en vervolgens de kolommen die u voor de samenvoeging wilt gebruiken.

1. Schakel het selectievakje **[!UICONTROL Use common additional data only]** in als u alleen de aanvullende data wilt behouden die in alle binnenkomende overgangen voorkomen.
1. Als u de grootte van de uiteindelijke populatie wilt beperken, schakelt u het selectievakje **[!UICONTROL Limit size of generated population]** in. De grootte kan in het veld **[!UICONTROL Maximum number of records]** worden opgegeven.
1. Beheer indien nodig de [Overgangen](../../automating/using/activity-properties.md) van de activiteit om tot de geavanceerde opties voor de berekende populatie toegang te krijgen.
1. Bevestig de configuratie van uw activiteit en sla de workflow op.

## Voorbeeld {#example}

In het volgende voorbeeld wordt het resultaat getoond van twee queryactiviteiten die gericht zijn op het opnieuw groeperen van profielen uit de Adobe Campaign-database die tussen de 18 en 27 jaar oud zijn en van profielen tussen de 34 en 40 jaar oud. Het resultaat bevat alle profielen van de twee query’s of het maximumaantal records, indien van toepassing, zoals gespecificeerd tijdens de configuratie.

![](assets/wkf_union_example.png)