---
title: Segmentatie
description: Met de activiteit Segmentatie kunt u een of meer segmenten maken van een populatie die is berekend door activiteiten die eerder in de workflow zijn geplaatst.
page-status-flag: never-activated
uuid: 77796f18-cad5-4e7a-9d7b-4ed0dd8943bf
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 0ccd9d02-772e-406b-874a-5381dd0c8709
context-tags: segmentation,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '849'
ht-degree: 92%

---


# Segmentatie{#segmentation}

## Beschrijving {#description}

![](assets/segmentation.png)

Met de activiteit **[!UICONTROL Segmentation]** kunt u een of meer segmenten maken van een populatie die wordt berekend door activiteiten die eerder in de workflow zijn geplaatst. Aan het eind van de activiteit kunnen zij in één enkele overgang of verschillende overgangen worden verwerkt.

>[!NOTE]
>
>Standaard kan een lid van de binnenkomende populatie slechts tot één segment behoren. De filters worden toegepast op basis van de volgorde van de segmenten in de activiteit.

**Verwante onderwerpen:**
* [Hoofdlettergebruik: Segmentatie op locatie](../../automating/using/workflow-segmentation-location.md)
* [Hoofdlettergebruik: Segmentering volgens leeftijdsgroepen](../../automating/using/segmentation-age-groups.md)

## Gebruikscontext {#context-of-use}

De activiteit **[!UICONTROL Segmentation]** wordt over het algemeen na targetingactiviteiten (query, doorsnede, samenvoeging, uitsluiting, enz.) geplaatst om de standaardpopulatie te bepalen op basis waarvan de segmenten worden gevormd.

**Verwante onderwerpen**

* [Hoofdlettergebruik: Segmenteringsprofielen op basis van hun leeftijdsgroepen](../../automating/using/segmentation-age-groups.md).

## Configuratie {#configuration}

1. Sleep een activiteit **[!UICONTROL Segmentation]** en zet deze neer in uw workflow.
1. Selecteer de activiteit en open deze met de knop ![](assets/edit_darkgrey-24px.png) vanuit de snelle acties die verschijnen.
1. In the **[!UICONTROL General]** tab, select the **[!UICONTROL Resource type]** on which the segmentation has to be carried out:

   * **[!UICONTROL Database resource]** als de segmentatie wordt uitgevoerd op data die al in de database aanwezig zijn. Selecteer de **[!UICONTROL Filtering dimension]** afhankelijk van de data die u wilt segmenteren. Segmentatie wordt standaard uitgevoerd op de **profielen**.
   * **[!UICONTROL Temporary resource]** indien de segmentatie wordt uitgevoerd op de tijdelijke data van de workflow: selecteer de **[!UICONTROL Targeted set]** met de data die u wilt segmenteren. Deze gebruikssituatie kan optreden na het importeren van een bestand of als de data in de database verrijkt zijn.

1. Selecteer het type uitgaande overgang dat u wilt gebruiken:

   * **[!UICONTROL Generate one transition per segment]**: Eén uitgaande overgang wordt toegevoegd voor elk geconfigureerd segment aan het eind van de activiteit.
   * **[!UICONTROL Generate all segments in one transition]**: Alle geconfigureerde segmenten worden opnieuw gegroepeerd in één uitgaande overgang. Geef het overgangslabel op. De leden van elk segment behouden de segmentcode die aan hen is toegewezen.

1. Voeg een segment toe met behulp van de knop ![](assets/add_darkgrey-24px.png) of **[!UICONTROL Add an element]** en geef de standaardeigenschappen op:

   * **[!UICONTROL Do not activate the transition if the population is empty]**: Het segment is alleen actief als data zijn opgehaald.
   * **[!UICONTROL Filter initial population (query)]**: Hiermee kunt u de populatie van dit segment filteren.
   * **[!UICONTROL Limit segment population]**: Hiermee kunt u de segmentgrootte beperken.
   * **[!UICONTROL Filter and limit segment population]**: Hiermee kunt u de segmentpopulatie filteren en de grootte ervan beperken.
   * **[!UICONTROL Label]**: segmentlabel.
   * **[!UICONTROL Segment code]**: code toegewezen aan de segmentpopulatie.De segmentcode kan worden gepersonaliseerd met behulp van een standaardexpressie en gebeurtenisvariabelen (zie [](../../automating/using/customizing-workflow-external-parameters.md)).
   * **[!UICONTROL Exclude segment from population]**: Hiermee sluit u het opgegeven segment uit van de uitgaande populatie van de activiteit. Deze optie kan alleen worden gebruikt als de optie **[!UICONTROL Generate all segments in the same transition]** is geselecteerd.

   ![](assets/wkf_segment_new_segment.png)

1. Open de detailweergave van het segment voor toegang tot de configuratieopties van het segment. Hiervoor schakelt u het relevante vakje in de segmentlijst van de activiteit in en selecteert u ![](assets/wkf_segment_parameters_24px.png).
1. Als de optie om de aanvankelijke populatie te filteren, ingeschakeld is, opent u het tabblad **[!UICONTROL Filter]** en specificeert u de populatie van uw segment. De filters zijn gebaseerd op de filterdimensie die in stap 4 is geselecteerd. Raadpleeg de sectie [Query’s bewerken](../../automating/using/editing-queries.md) voor meer informatie over populatiefiltering.

   Als de segmentatie wordt uitgevoerd op een tijdelijke resource, zijn aantal en voorvertoning voor de populatie niet beschikbaar op dit tabblad.

1. Als de optie voor het beperken van de segmentgrootte is ingeschakeld, opent u het tabblad **[!UICONTROL Limitation]**.

   Selecteer eerst het **[!UICONTROL Type of limit]** dat u wilt gebruiken:

   * **[!UICONTROL Random sampling]**: De segmentpopulatie wordt willekeurig geselecteerd, waarbij zo nodig rekening wordt gehouden met de configuratie van het tabblad **[!UICONTROL Filter]**.
   * **[!UICONTROL Ordered sampling]**: De segmentpopulatie wordt op geordende wijze geselecteerd. Daarom moet u aangeven welke kolommen in aanmerking moeten worden genomen en welk type sortering moet worden toegepast. Als u bijvoorbeeld het veld **Leeftijd** als sorteerkolom selecteert terwijl u **[!UICONTROL Descending sort]** toepast en een limiet van 100 instelt, blijven alleen de profielen van de 100 oudste personen behouden.

   Geef nu de **[!UICONTROL Limit]** van de segmentgrootte op:

   * **[!UICONTROL Size (as a % of the initial population)]**: Specificeer de segmentgrootte door een percentage van de aanvankelijke populatie van de activiteit te gebruiken.
   * **[!UICONTROL Maximum size]**: Geef het maximum aantal leden voor de segmentpopulatie op.
   * **[!UICONTROL By data grouping]**: U kunt de segmentpopulatie beperken op basis van de waarden van een specifiek veld van de binnenkomende populatie. Selecteer het veld voor groepering en geef de waarden op die u wilt gebruiken.
   * **[!UICONTROL By data grouping (as a %)]**: U kunt de segmentpopulatie beperken op basis van de waarden van een specifiek veld van de binnenkomende populatie door een percentage te gebruiken. Selecteer het veld waarop u de groepering wilt toepassen en geef de waarden op die u wilt gebruiken.

      >[!NOTE]
      >
      >U kunt verschillende beperkingen voor elke waarde gebruiken. U kunt bijvoorbeeld een groepering voor het veld **[!UICONTROL Gender]** opgeven en de populatie met leden van het **[!UICONTROL Male]** geslacht beperken tot 10, en de populatie met leden van het **[!UICONTROL Female]** geslacht tot 30 personen. Als u meerdere velden voor datagroepering gebruikt, moeten alle groeperingen dezelfde grootte hebben.
   ![](assets/wkf_segment_limit_by_grouping.png)

1. Bevestig de configuratie van uw segment.
1. Voeg zoveel segmenten toe als nodig is door stap 6 tot en met 10 van deze procedure te herhalen.
1. Bewerk indien nodig de parameters op het tabblad **[!UICONTROL Advanced options]**:

   * Schakel de optie **[!UICONTROL Enable overlapping of outbound populations]** in als u wilt dat een lid van de binnenkomende populatie tot verscheidene segmenten tegelijk behoort. De uitgaande populatie van de activiteit kan groter zijn dan de binnenkomende populatie.
   * Schakel de optie **[!UICONTROL Concatenate the code of each segment]** in als aan de binnenkomende populatie reeds een segmentcode is toegewezen die u wilt houden. De segmentcode die in de activiteit wordt opgegeven, wordt toegevoegd aan de oorspronkelijke segmentcode.
   * Schakel de optie **[!UICONTROL Generate complement]** in als u de resterende populatie wilt benutten. See [Use case: Creating deliveries with a complement](../../automating/using/workflow-created-query-with-complement.md).

1. Bevestig de configuratie van uw activiteit en sla de workflow op.
