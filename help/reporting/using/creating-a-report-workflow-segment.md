---
solution: Campaign Standard
product: campaign
title: Een rapport maken op basis van workflowsegmenten
description: Leer hoe te om het succes van uw levering afhankelijk van de segmenten van uw werkschema's in uw rapporten te controleren.
audience: reporting
content-type: reference
topic-tags: customizing-reports
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '617'
ht-degree: 2%

---


# Een rapport maken op basis van workflowsegmenten{#creating-a-report-workflow-segment}

Nadat u een workflow hebt gemaakt en uw populatie hebt gefilterd in verschillende doelgroepen, kunt u de efficiëntie van uw marketingcampagnes meten op basis van segmenten die zijn gedefinieerd in deze doelworkflow.
Om deze segmenten in uw rapporten te richten:

* [Stap 1: Profielen bijwerken, aangepaste bron met segmenten](#step-1--update-profiles-custom-resource-segments)
* [Stap 2: Een workflow met segmenten maken](#step-2--create-a-workflow-segments)
* [Stap 3: Een dynamisch rapport maken om segmenten te filteren](#step-3--create-a-dynamic-report-filter-segments)

>[!CAUTION]
>De dynamische gebruiksovereenkomst voor rapportage moet worden geaccepteerd om te beginnen met het verzamelen van deze gegevens.
>For more on this agreement, refer to this [page](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

## Stap 1: Profielen bijwerken, aangepaste bron met segmenten{#step-1--update-profiles-custom-resource-segments}

Alvorens op uw segmentcode te melden, moet u uw **[!UICONTROL Profiles]** douanemiddel voor uw segmentcodes bijwerken die moeten worden opgeslagen.

1. From the advanced menu, via the Adobe Campaign logo, select **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom resources]**, then select the **[!UICONTROL Profile (profile)]** resource.
1. In het **[!UICONTROL Sending logs extension]** menu van het **[!UICONTROL Data structure]** lusje, controleer **[!UICONTROL Add segment code]** om opslag van uw segmentcodes toe te staan van het richten van werkschema&#39;s en het te verzenden naar dynamische rapportering.

   Het **[!UICONTROL Segment code]** zal dan in de **[!UICONTROL Profile]** afmetingssectie van uw rapport beschikbaar zijn.

   ![](assets/report_segment_4.png)

1. Sla uw aangepaste bron op.

1. U moet nu uw aangepaste bron publiceren.
Selecteer in het menu Geavanceerd **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Publishing]**.

   ![](assets/custom_profile_7.png)

1. Klik **[!UICONTROL Prepare publication]** vervolgens op de **[!UICONTROL Publish]** knop wanneer de voorbereiding is voltooid. For more information on custom resource, refer to this [page](../../developing/using/updating-the-database-structure.md).

U kunt nu uw workflow maken met segmentcodes.

Merk op dat de segmentcodes zullen worden verzameld zodra u de segmentcode in **[!UICONTROL Sending logs extension]** toelaat.

## Stap 2: Een workflow met segmenten maken {#step-2--create-a-workflow-segments}

>[!NOTE]
>Als de invoerovergang van de e-maillevering leeg is, wordt de segmentcode van de vorige overgang standaard toegevoegd.

Eerst moet u een workflow maken met verschillende doelgroepen. Hier, willen wij een e-mail verzenden die afhankelijk van de leeftijd van ons publiek zal worden gepersonaliseerd: één levering voor profielen van 20 tot 30 jaar oud en een andere voor profielen van 30 tot 40 jaar oud.

1. Maak uw workflow. For more details on how to create your workflow, refer to this [page](../../automating/using/building-a-workflow.md).

1. Add a **[!UICONTROL Query]** activity by dragging it from the palette and dropping it in the workspace.

1. Doelprofielen van 20 tot 40 jaar oud om ze later in meer doelgroepen te segmenteren.

   ![](assets/report_segment_1.png)

1. Voeg een **[!UICONTROL Segmentation]** activiteit toe om uw vraagresultaten in twee gerichte populaties te verdelen. For more on segmentation, refer to this [page](../../automating/using/segmentation.md).

1. Dubbelklik op de **[!UICONTROL Segmentation]** activiteit om deze te configureren. Bewerk het eerste segment door op **[!UICONTROL Edit properties]** te klikken.

   ![](assets/report_segment_7.png)

1. Zoekprofielen tussen 20 en 30 jaar en klik **[!UICONTROL Confirm]** als u klaar bent.

   ![](assets/report_segment_8.png)

1. Klik **[!UICONTROL Add an element]** om uw tweede segment te maken en het te configureren zoals in de bovenstaande stappen wordt beschreven voor de doelprofielen tussen 30 en 40 jaar.

1. Bewerk de gegevens **[!UICONTROL Segment code]** voor elke populatie die via dynamische rapportage worden doorgegeven.

   >[!NOTE]
   >Deze stap is verplicht of anders kunt u niet begrijpen over welke segmenten moet worden gerapporteerd.

   ![](assets/report_segment_9.png)

1. Drag and drop an **[!UICONTROL Email delivery]** activity after your segments.

   ![](assets/report_segment_3.png)

1. Pas uw leveringen aan, afhankelijk van de verschillende doelgroepen. For more on email creation, refer to this [page](../../designing/using/designing-content-in-adobe-campaign.md).

1. Sla de workflow op.

1. Klik **[!UICONTROL Start]** wanneer uw werkstroom klaar is.

U kunt tot uw rapporten nu toegang hebben om uw segmentcodes te volgen.

## Stap 3: Een dynamisch rapport maken om segmenten te filteren {#step-3--create-a-dynamic-report-filter-segments}

Nadat u leveringen met uw workflow hebt verzonden, kunt u rapporten splitsen aan de hand van uw segmentcodes uit uw workflow.

1. Selecteer op het **[!UICONTROL Reports]** tabblad een rapport uit de doos of klik op de **[!UICONTROL Create new project]** knop om een rapport helemaal opnieuw te beginnen.

   ![](assets/custom_profile_18.png)
1. Sleep de **[!UICONTROL Delivery]** dimensie naar de vrije-vormtabel.

   ![](assets/report_segment_5.png)

1. Sleep verschillende metriek naar de tabel, zoals de metriek **[!UICONTROL Open]** **[!UICONTROL Click]** en de metriek, om te beginnen met het filteren van de gegevens.
1. Klik in de **[!UICONTROL Dimensions]** categorie op de **[!UICONTROL Profile]** dimensie en sleep de **[!UICONTROL Segment code]** dimensie op de levering van de workflow om het succes van de e-maillevering te meten, afhankelijk van de doelpopulaties.

   ![](assets/report_segment_6.png)

1. Sleep indien nodig een visualisatie naar de werkruimte.

   ![](assets/report_segment_10.png)
