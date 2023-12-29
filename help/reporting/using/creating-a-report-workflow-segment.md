---
title: Een rapport maken op basis van workflowsegmenten
description: Leer hoe te om het succes van uw levering afhankelijk van de segmenten van uw werkschema's in uw rapporten te controleren.
audience: reporting
content-type: reference
topic-tags: customizing-reports
feature: Reporting
role: Leader
level: Intermediate
exl-id: 514bffa0-2413-4212-b1b9-e070031c462f
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '640'
ht-degree: 2%

---

# Een rapport maken op basis van workflowsegmenten{#creating-a-report-workflow-segment}

>[!CAUTION]
> **[!UICONTROL Segment code]** kan alleen e-mail- en SMS-leveringen als doel hebben.

Nadat u een workflow hebt gemaakt en uw populatie hebt gefilterd in verschillende doelgroepen, kunt u de efficiëntie van uw marketingcampagnes meten op basis van segmenten die zijn gedefinieerd in deze doelworkflow.
Om deze segmenten in uw rapporten te richten:

* [Stap 1: Werk Profielen aan douanemiddel met segmenten bij](#step-1--update-profiles-custom-resource-segments)
* [Stap 2: Een workflow met segmenten maken](#step-2--create-a-workflow-segments)
* [Stap 3: Creeer een dynamisch rapport aan filtersegmenten](#step-3--create-a-dynamic-report-filter-segments)

>[!CAUTION]
>De dynamische gebruiksovereenkomst voor rapportage moet worden geaccepteerd om te beginnen met het verzamelen van deze gegevens.
>
>Voor meer informatie over deze overeenkomst raadpleegt u deze [page](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

## Stap 1: Werk Profielen aan douanemiddel met segmenten bij{#step-1--update-profiles-custom-resource-segments}

Voordat u op uw segmentcode rapporteert, moet u de **[!UICONTROL Profiles]** douanemiddel voor uw segmentcodes die moeten worden opgeslagen.

1. Selecteer in het geavanceerde menu via het Adobe Campaign-logo de optie **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom resources]** en selecteert u vervolgens de **[!UICONTROL Profile (profile)]** resource.
1. In de **[!UICONTROL Sending logs extension]** van het menu **[!UICONTROL Data structure]** tab, check **[!UICONTROL Add segment code]** om opslag van uw segmentcodes toe te staan van het richten van werkschema&#39;s en het te verzenden naar dynamische rapportering.

   De **[!UICONTROL Segment code]** zal dan beschikbaar zijn in **[!UICONTROL Profile]** dimensie van uw rapport.

   ![](assets/report_segment_4.png)

1. Sla uw aangepaste bron op.

1. U moet nu uw aangepaste bron publiceren.
Selecteer in het menu Geavanceerd de optie **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Publishing]**.

   ![](assets/custom_profile_7.png)

1. Klikken **[!UICONTROL Prepare publication]** Klik vervolgens wanneer de voorbereiding is voltooid op **[!UICONTROL Publish]** knop. Voor meer informatie over douanemiddel, verwijs naar dit [page](../../developing/using/updating-the-database-structure.md).

U kunt nu uw workflow maken met segmentcodes.

De segmentcodes worden verzameld zodra u de segmentcode in het dialoogvenster **[!UICONTROL Sending logs extension]**.

## Stap 2: Een workflow met segmenten maken {#step-2--create-a-workflow-segments}

>[!NOTE]
>Als de invoerovergang van de e-maillevering leeg is, wordt de segmentcode van de vorige overgang standaard toegevoegd.

Eerst moet u een workflow maken met verschillende doelgroepen. Hier willen we een e-mail sturen die gepersonaliseerd zal zijn afhankelijk van de leeftijd van ons publiek: een levering voor profielen van 20 tot 30 jaar oud en een andere voor profielen van 30 tot 40 jaar oud.

1. Maak uw workflow. Raadpleeg deze voor meer informatie over het maken van uw workflow [page](../../automating/using/building-a-workflow.md).

1. Voeg een **[!UICONTROL Query]** door deze vanuit het palet te slepen en neer te zetten in de werkruimte.

1. Doelprofielen van 20 tot 40 jaar oud om ze later in meer doelgroepen te segmenteren.

   ![](assets/report_segment_1.png)

1. Voeg een **[!UICONTROL Segmentation]** activiteit om uw vraagresultaten in twee gerichte populaties te verdelen. Raadpleeg deze voor meer informatie over segmentatie [page](../../automating/using/segmentation.md).

1. Dubbelklik op de knop **[!UICONTROL Segmentation]** activiteit om het te vormen. Het eerste segment bewerken door op **[!UICONTROL Edit properties]**.

   ![](assets/report_segment_7.png)

1. Zoekprofielen tussen 20 en 30 jaar en klik op **[!UICONTROL Confirm]** wanneer gereed.

   ![](assets/report_segment_8.png)

1. Klikken **[!UICONTROL Add an element]** om uw tweede segment te maken en het te configureren zoals beschreven in de bovenstaande stappen, voor doelprofielen tussen 30 en 40 jaar.

1. Bewerk de **[!UICONTROL Segment code]** voor elke populatie die via dynamische rapportage moet worden doorgegeven.

   >[!NOTE]
   >Deze stap is verplicht of anders kunt u niet begrijpen over welke segmenten moet worden gerapporteerd.

   ![](assets/report_segment_9.png)

1. Sleep een **[!UICONTROL Email delivery]** activiteit na uw segmenten.

   ![](assets/report_segment_3.png)

1. Pas uw leveringen aan, afhankelijk van de verschillende doelgroepen. Raadpleeg deze voor meer informatie over het maken van e-mailberichten [page](../../designing/using/designing-content-in-adobe-campaign.md).

1. Sla de workflow op.

1. Klikken **[!UICONTROL Start]** als uw workflow gereed is.

U kunt tot uw rapporten nu toegang hebben om uw segmentcodes te volgen.

## Stap 3: Creeer een dynamisch rapport aan filtersegmenten {#step-3--create-a-dynamic-report-filter-segments}

Nadat u leveringen met uw workflow hebt verzonden, kunt u rapporten splitsen aan de hand van uw segmentcodes uit uw workflow.

1. Van de **[!UICONTROL Reports]** selecteert u een rapport dat buiten de doos valt of klikt u op de knop **[!UICONTROL Create new project]** om een geheel nieuwe knop te starten.

   ![](assets/custom_profile_18.png)
1. Sleep de **[!UICONTROL Delivery]** dimensie van uw vrije-vormlijst.

   ![](assets/report_segment_5.png)

1. Sleep verschillende meetgegevens naar uw tabel, zoals de **[!UICONTROL Open]** en **[!UICONTROL Click]** metriek om te beginnen met het filteren van uw gegevens.
1. In de **[!UICONTROL Dimensions]** categorie, klikt u op de **[!UICONTROL Profile]** dimensie en sleep vervolgens de **[!UICONTROL Segment code]** Afhankelijk van de doelpopulaties, kunt u de mate van succes van uw e-maillevering afmeten aan de hand van de levering van uw workflow.

   ![](assets/report_segment_6.png)

1. Sleep indien nodig een visualisatie naar de werkruimte.

   ![](assets/report_segment_10.png)
