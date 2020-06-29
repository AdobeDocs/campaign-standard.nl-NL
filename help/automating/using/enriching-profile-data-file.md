---
title: Profielgegevens verrijken met gegevens in een bestand
description: In dit voorbeeld wordt getoond hoe u profielgegevens verrijkt met aankoopgegevens in een bestand.
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
source-git-commit: 7ffa48365875883a98904d6b344ac005afe26e18
workflow-type: tm+mt
source-wordcount: '528'
ht-degree: 0%

---


# Profielgegevens verrijken met gegevens in een bestand {#enriching-profile-data-with-data-contained-in-a-file}

In dit voorbeeld ziet u hoe u profielgegevens verrijkt met aankoopgegevens in een bestand. De aankoopgegevens worden hier opgeslagen in een systeem van derden. Voor elk profiel kunnen meerdere aankopen in het bestand worden opgeslagen. Het uiteindelijke doel van de workflow is een e-mail te sturen naar de doelprofielen die ten minste twee items hebben aangeschaft om ze te bedanken voor hun loyaliteit.

De workflow is als volgt geconfigureerd:

![](assets/enrichment_example_workflow.png)

* Een activiteit van de [Vraag](../../automating/using/query.md) die de profielen richt die het bericht zullen ontvangen.
* Een [activiteit van het Dossier](../../automating/using/load-file.md) van de Lading die de aankoopgegevens laadt. Bijvoorbeeld:

   ```
   tcode;tdate;customer;product;tamount
   aze123;21/05/2017;dannymars@example.com;TV;799
   aze124;28/05/2017;dannymars@example.com;Headphones;8
   aze125;31/07/2017;john.smith@example.com;Headphones;8
   aze126;14/12/2017;john.smith@example.com;Plastic Cover;4
   aze127;02/01/2018;dannymars@example.com;Case Cover;79
   aze128;04/03/2017;clara.smith@example.com;Phone;149
   ```

   Met dit voorbeeldbestand gebruiken we het e-mailadres om de gegevens in overeenstemming te brengen met de databaseprofielen. U kunt ook unieke id&#39;s inschakelen, zoals beschreven in [dit document](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources).

* Een [verrijkingsactiviteit](../../automating/using/enrichment.md) die tot een verbinding tussen de transactiegegevens leidt die van het dossier worden geladen en de profielen in **[!UICONTROL Query]**. De koppeling wordt gedefinieerd op het **[!UICONTROL Advanced relations]** tabblad van de activiteit. De koppeling is gebaseerd op de overgang die uit de **[!UICONTROL Load file]** activiteit komt. Het veld E-mail van de profielbron en de kolom &quot;klant&quot; van het geïmporteerde bestand worden gebruikt als afstemmingscriteria.

   ![](assets/enrichment_example_workflow2.png)

   Nadat de koppeling is gemaakt, worden twee sets **[!UICONTROL Additional data]** toegevoegd:

   * Een verzameling van twee regels die overeenkomen met de twee laatste transacties van elk profiel. Voor deze verzameling worden de productnaam, de transactiedatum en de prijs van het product toegevoegd als aanvullende gegevens. Op de gegevens wordt een aflopende sortering toegepast. Als u de verzameling wilt maken, klikt u op het **[!UICONTROL Additional data]** tabblad:

      Selecteer de koppeling die eerder is gedefinieerd op het **[!UICONTROL Advanced relations]** tabblad van de activiteit.

      ![](assets/enrichment_example_workflow3.png)

      Controleer **[!UICONTROL Collection]** en geef het aantal regels op dat moet worden opgehaald (2 in dit voorbeeld). In dit scherm, kunt u de **[!UICONTROL Alias]** en de **[!UICONTROL Label]** van de inzameling aanpassen. Deze waarden zijn zichtbaar in de volgende activiteiten van de workflow wanneer wordt verwezen naar deze verzameling.

      ![](assets/enrichment_example_workflow4.png)

      Als u voor de verzameling wilt bewaren, selecteert u de kolommen die in de uiteindelijke levering worden gebruikt. **[!UICONTROL Data]**

      ![](assets/enrichment_example_workflow6.png)

      Pas een aflopende sortering toe op de transactiedatum om ervoor te zorgen dat u de meest recente transacties ophaalt.

      ![](assets/enrichment_example_workflow7.png)

   * Een geaggregeerd getal waarbij het totale aantal transacties voor elk profiel wordt geteld. Dit aggregaat wordt later gebruikt om profielen te filteren waarvoor ten minste twee transacties zijn opgenomen. Om het aggregaat tot stand te brengen, van het **[!UICONTROL Additional data]** lusje:

      Selecteer de koppeling die eerder is gedefinieerd op het **[!UICONTROL Advanced relations]** tabblad van de activiteit.

      ![](assets/enrichment_example_workflow3.png)

      Selecteer **[!UICONTROL Aggregate]**.

      ![](assets/enrichment_example_workflow8.png)

      Definieer een aggregaat **[!UICONTROL Data]** Alles **** tellen als u wilt behouden. Geef desgewenst een aangepaste alias op om deze sneller te vinden in de volgende activiteiten.

      ![](assets/enrichment_example_workflow9.png)

* Een [Segmenteringsactiviteit](../../automating/using/segmentation.md) met slechts één segment, die profielen van het aanvankelijke doel terugwint die minstens twee geregistreerde transacties hebben. Profielen met slechts één transactie worden uitgesloten. Om dat te doen, wordt de vraag van de segmentatie gemaakt op het eerder bepaalde aggregaat.

   ![](assets/enrichment_example_workflow5.png)

* An [Email delivery](../../automating/using/email-delivery.md) activity that uses the additional data defined in the **[!UICONTROL Enrichment]** to dynamisch retrieve the two last purchase by the profile. De extra gegevens kunnen in de **Extra knoop van Gegevens (TargetData)** worden gevonden wanneer het toevoegen van een verpersoonlijkingsgebied.

   ![](assets/enrichment_example_workflow10.png)

**Verwant onderwerp:**

* [Klantenprofielen verrijken met externe gegevens](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Managedatatofuelengagingexperiences)
