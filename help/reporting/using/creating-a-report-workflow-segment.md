---
solution: Campaign Standard
product: campaign
title: Een rapport maken op basis van workflowsegmenten
description: Leer hoe te om het succes van uw levering afhankelijk van de segmenten van uw werkschema's in uw rapporten te controleren.
audience: reporting
content-type: reference
topic-tags: customizing-reports
feature: Rapportage
role: Leader
level: Intermediate
exl-id: 514bffa0-2413-4212-b1b9-e070031c462f
source-git-commit: c001aaba50bdce8d949acc6daf74f3c7738bd117
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 2%

---

# Een rapport maken op basis van workflowsegmenten{#creating-a-report-workflow-segment}

>[!CAUTION]
> **[!UICONTROL Segment code]**kan alleen e-mail- en SMS-leveringen als doel hebben.

Nadat u een workflow hebt gemaakt en uw populatie hebt gefilterd in verschillende doelgroepen, kunt u de efficiëntie van uw marketingcampagnes meten op basis van segmenten die zijn gedefinieerd in deze doelworkflow.
Om deze segmenten in uw rapporten te richten:

* [Stap 1: Profielen bijwerken, aangepaste bron met segmenten](#step-1--update-profiles-custom-resource-segments)
* [Stap 2: Een workflow met segmenten maken](#step-2--create-a-workflow-segments)
* [Stap 3: Een dynamisch rapport maken om segmenten te filteren](#step-3--create-a-dynamic-report-filter-segments)

>[!CAUTION]
>De dynamische gebruiksovereenkomst voor rapportage moet worden geaccepteerd om te beginnen met het verzamelen van deze gegevens.
>
>Raadpleeg deze [pagina](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement) voor meer informatie over deze overeenkomst.

## Stap 1: Profielen bijwerken, aangepaste bron met segmenten{#step-1--update-profiles-custom-resource-segments}

Alvorens op uw segmentcode te melden, moet u uw **[!UICONTROL Profiles]** douanemiddel voor uw te bewaren segmentcodes bijwerken.

1. Selecteer in het geavanceerde menu via het Adobe Campaign-logo **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom resources]** en selecteer vervolgens de **[!UICONTROL Profile (profile)]**-bron.
1. Schakel in het menu **[!UICONTROL Sending logs extension]** op het tabblad **[!UICONTROL Data structure]** **[!UICONTROL Add segment code]** in om ervoor te zorgen dat de segmentcodes niet bestemd zijn voor workflows en om deze naar dynamische rapportage te verzenden.

   **[!UICONTROL Segment code]** zal dan in **[!UICONTROL Profile]** de afmetingssectie van uw rapport beschikbaar zijn.

   ![](assets/report_segment_4.png)

1. Sla uw aangepaste bron op.

1. U moet nu uw aangepaste bron publiceren.
Selecteer **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Publishing]** in het geavanceerde menu.

   ![](assets/custom_profile_7.png)

1. Klik **[!UICONTROL Prepare publication]** dan wanneer de voorbereiding wordt gedaan, klik **[!UICONTROL Publish]** knoop. Voor meer informatie over douanemiddel, verwijs naar deze [pagina](../../developing/using/updating-the-database-structure.md).

U kunt nu uw workflow maken met segmentcodes.

Merk op dat de segmentcodes zullen worden verzameld zodra u de segmentcode in **[!UICONTROL Sending logs extension]** toelaat.

## Stap 2: Een workflow met segmenten maken {#step-2--create-a-workflow-segments}

>[!NOTE]
>Als de invoerovergang van de e-maillevering leeg is, wordt de segmentcode van de vorige overgang standaard toegevoegd.

Eerst moet u een workflow maken met verschillende doelgroepen. Hier, willen wij een e-mail verzenden die afhankelijk van de leeftijd van ons publiek zal worden gepersonaliseerd: één levering voor profielen van 20 tot 30 jaar oud en een andere voor profielen van 30 tot 40 jaar oud.

1. Maak uw workflow. Raadpleeg deze [pagina](../../automating/using/building-a-workflow.md) voor meer informatie over het maken van uw workflow.

1. Voeg een **[!UICONTROL Query]** activiteit toe door het van het palet te slepen en het te laten vallen in de werkruimte.

1. Doelprofielen van 20 tot 40 jaar oud om ze later in meer doelgroepen te segmenteren.

   ![](assets/report_segment_1.png)

1. Voeg een **[!UICONTROL Segmentation]** activiteit toe om uw vraagresultaten in twee gerichte populaties te verdelen. Raadpleeg deze [pagina](../../automating/using/segmentation.md) voor meer informatie over segmentatie.

1. Dubbelklik op de **[!UICONTROL Segmentation]**-activiteit om deze te configureren. Bewerk het eerste segment door op **[!UICONTROL Edit properties]** te klikken.

   ![](assets/report_segment_7.png)

1. De profielen van de vraag tussen de leeftijd van 20 tot 30 en klikken **[!UICONTROL Confirm]** wanneer gedaan.

   ![](assets/report_segment_8.png)

1. Klik **[!UICONTROL Add an element]** om uw tweede segment te creëren en het te vormen zoals die in de stappen hierboven wordt beschreven aan doelprofielen tussen de leeftijd van 30 tot 40.

1. Bewerk **[!UICONTROL Segment code]** voor elke populatie die via dynamische rapportage wordt doorgegeven.

   >[!NOTE]
   >Deze stap is verplicht of anders kunt u niet begrijpen over welke segmenten moet worden gerapporteerd.

   ![](assets/report_segment_9.png)

1. Sleep een **[!UICONTROL Email delivery]** activiteit na uw segmenten.

   ![](assets/report_segment_3.png)

1. Pas uw leveringen aan, afhankelijk van de verschillende doelgroepen. Raadpleeg deze [pagina](../../designing/using/designing-content-in-adobe-campaign.md) voor meer informatie over het maken van e-mail.

1. Sla de workflow op.

1. Klik **[!UICONTROL Start]** wanneer uw werkschema klaar is.

U kunt tot uw rapporten nu toegang hebben om uw segmentcodes te volgen.

## Stap 3: Een dynamisch rapport maken om segmenten te filteren {#step-3--create-a-dynamic-report-filter-segments}

Nadat u leveringen met uw workflow hebt verzonden, kunt u rapporten splitsen aan de hand van uw segmentcodes uit uw workflow.

1. Selecteer op het tabblad **[!UICONTROL Reports]** een rapport uit de doos of klik op de knop **[!UICONTROL Create new project]** om een rapport helemaal opnieuw te beginnen.

   ![](assets/custom_profile_18.png)
1. Sleep de **[!UICONTROL Delivery]** dimensie aan uw vrije vormlijst.

   ![](assets/report_segment_5.png)

1. Sleep verschillende metriek aan uw lijst zoals **[!UICONTROL Open]** en **[!UICONTROL Click]** metriek beginnen uw gegevens te filtreren.
1. Klik in de categorie **[!UICONTROL Dimensions]** op de **[!UICONTROL Profile]**-dimensie en sleep de **[!UICONTROL Segment code]**-dimensie op de levering van uw workflow om het succes van de e-maillevering te meten, afhankelijk van de doelpopulaties.

   ![](assets/report_segment_6.png)

1. Sleep indien nodig een visualisatie naar de werkruimte.

   ![](assets/report_segment_10.png)
