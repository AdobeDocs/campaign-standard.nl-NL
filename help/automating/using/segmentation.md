---
title: Segmentering
description: Met de segmenteringsactiviteit kunt u een of meerdere segmenten maken van een populatie die wordt berekend door activiteiten die eerder in de workflow zijn geplaatst.
page-status-flag: never-activated
uuid: 77796f18-cad5-4e7a-9d7b-4ed0dd8943bf
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 0ccd9d02-772e-406b-874a-5381dd0c8709
context-tags: segmentation,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Segmentering{#segmentation}

## Beschrijving {#description}

![](assets/segmentation.png)

Met de **[!UICONTROL Segmentation]** activiteit kunt u een of meerdere segmenten maken van een populatie die wordt berekend door activiteiten die eerder in de workflow zijn geplaatst. Aan het eind van de activiteit, kunnen zij in één enkele overgang of verschillende overgangen worden verwerkt.

>[!NOTE]
>
>Door gebrek, kan een lid van de binnenkomende bevolking slechts tot één enkel segment behoren. De filters worden toegepast op basis van de volgorde van de segmenten in de activiteit.

## Gebruikscontext {#context-of-use}

De **[!UICONTROL Segmentation]** activiteit wordt over het algemeen geplaatst na het richten van activiteiten (vraag, doorsnede, vereniging, uitsluiting, enz.) om de standaardpopulatie te bepalen op basis waarvan de segmenten worden gevormd.

## Configuratie {#configuration}

1. Sleep een **[!UICONTROL Segmentation]** activiteit naar uw werkstroom.
1. Selecteer de activiteit, dan open het gebruikend de ![](assets/edit_darkgrey-24px.png) knoop van de snelle acties die verschijnen.
1. Selecteer de **[!UICONTROL Resource type]** plaats waar de segmentatie moet worden uitgevoerd:

   * **[!UICONTROL Database resource]** als de segmentatie wordt uitgevoerd op gegevens die al in de database aanwezig zijn. Selecteer het **[!UICONTROL Filtering dimension]** afhankelijk van de gegevens die u wilt segmenteren. De segmentatie wordt standaard uitgevoerd op de **profielen**.
   * **[!UICONTROL Temporary resource]** indien de segmentatie wordt uitgevoerd op de tijdelijke gegevens van de werkstroom: Selecteer de gegevens **[!UICONTROL Targeted set]** die de gegevens bevatten die u wilt segmenteren. Dit gebruik kan voorkomen na het invoeren van een dossier of als de gegevens in het gegevensbestand werden verrijkt.

1. Selecteer het uitgaande overgangstype dat u wilt gebruiken:

   * **[!UICONTROL Generate one transition per segment]**: één uitgaande overgang wordt toegevoegd voor elk gevormd segment aan het eind van de activiteit.
   * **[!UICONTROL Generate all segments in one transition]**: alle gevormde segmenten worden opnieuw gegroepeerd in één enkele uitgaande overgang. Geef het overgangslabel op. De leden van elk segment houden de segmentcode die aan hen is toegewezen.

1. Voeg een segment toe met behulp van de ![](assets/add_darkgrey-24px.png) knop of de **[!UICONTROL Add an element]** knop en geef de standaardeigenschappen op:

   * **[!UICONTROL Do not activate the transition if the population is empty]**: het segment zal slechts worden toegelaten als de gegevens worden teruggewonnen.
   * **[!UICONTROL Filter initial population (query)]**: laat je de populatie van dit segment filteren.
   * **[!UICONTROL Limit segment population]**: Hiermee kunt u de segmentgrootte beperken.
   * **[!UICONTROL Filter and limit segment population]**: Hiermee kunt u de segmentpopulatie filteren en de grootte ervan beperken.
   * **[!UICONTROL Label]**: segmentlabel.
   * **[!UICONTROL Segment code]**: code toegewezen aan de segmentpopulatie.De segmentcode kan worden gepersonaliseerd met behulp van een standaardexpressie en gebeurtenisvariabelen (zie Activiteiten [aanpassen met gebeurtenisvariabelen](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables)).
   * **[!UICONTROL Exclude segment from population]**: Hiermee sluit u het opgegeven segment uit van de uitgaande populatie van de activiteit. Deze optie kan alleen worden gebruikt als de **[!UICONTROL Generate all segments in the same transition]** optie is geselecteerd.
   ![](assets/wkf_segment_new_segment.png)

1. Open de detailweergave van het segment voor toegang tot de configuratieopties van het segment. Om dit te doen, controleer het relevante vakje in de de segmentlijst van de activiteit, dan uitgezochte ![](assets/wkf_segment_parameters_24px.png).
1. Als de optie om de aanvankelijke populatie te filteren wordt gecontroleerd, open het **[!UICONTROL Filter]** lusje en specificeer de bevolking van uw segment. De filters zijn gebaseerd op de filterdimensie die in stap 4 is geselecteerd. Raadpleeg de sectie [Query Editing](../../automating/using/editing-queries.md) voor meer informatie over populatiefiltering.

   Als de segmentatie wordt uitgevoerd op een tijdelijke bron, zijn het aantal en de voorvertoning van de populatie niet beschikbaar op dit tabblad.

1. Als de optie voor het beperken van de segmentgrootte is ingeschakeld, opent u het **[!UICONTROL Limitation]** tabblad.

   Selecteer eerst de **[!UICONTROL Type of limit]** gegevens die u wilt gebruiken:

   * **[!UICONTROL Random sampling]**: de segmentpopulatie wordt willekeurig geselecteerd, waarbij zo nodig rekening wordt gehouden met de configuratie van het **[!UICONTROL Filter]** tabblad.
   * **[!UICONTROL Ordered sampling]**: de segmentpopulatie wordt geordend geselecteerd. Daarom moet u aangeven welke kolommen in aanmerking moeten worden genomen en welk type sortering moet worden toegepast. Als u bijvoorbeeld het veld **Leeftijd** als sorteerkolom selecteert terwijl u een waarde toepast **[!UICONTROL Descending sort]** en een limiet van 100 instelt, worden alleen de profielen van de bovenste 100 oudste personen bewaard.
   Geef nu de grootte **[!UICONTROL Limit]** van het segment op:

   * **[!UICONTROL Size (as a % of the initial population)]**: specificeer de segmentgrootte door een percentage van de aanvankelijke bevolking van de activiteit te gebruiken.
   * **[!UICONTROL Maximum size]**: een maximumaantal leden voor de segmentpopulatie specificeren.
   * **[!UICONTROL By data grouping]**: u kunt de segmentpopulatie beperken op basis van de waarden van een specifiek gebied van de binnenkomende populatie. Selecteer het veld voor groepering en geef de waarden op die u wilt gebruiken.
   * **[!UICONTROL By data grouping (as a %)]**: u kunt de segmentpopulatie beperken op basis van de waarden van een specifiek inkomend populatieveld door een percentage te gebruiken. Selecteer het veld waarop u de groepering wilt toepassen en geef de waarden op die u wilt gebruiken.

      >[!NOTE]
      >
      >U kunt verschillende beperkingen voor elke waarde gebruiken. U kunt bijvoorbeeld een groep voor het **[!UICONTROL Gender]** veld opgeven en de populatie met **[!UICONTROL Male]** leden beperken tot 10 en de populatie met **[!UICONTROL Female]** leden tot 30 personen. Als u meerdere velden voor gegevensgroepering gebruikt, moeten alle groepen dezelfde grootte hebben.
   ![](assets/wkf_segment_limit_by_grouping.png)

1. Bevestig de configuratie van uw segment.
1. Voeg zoveel segmenten toe als nodig is door stap 6 tot en met 10 van deze procedure te herhalen.
1. Bewerk indien nodig de parameters op het **[!UICONTROL Advanced options]** tabblad:

   * Controleer de **[!UICONTROL Enable overlapping of outbound populations]** optie als u een lid van de binnenkomende bevolking tot verscheidene segmenten tezelfdertijd wilt behoren. De uitgaande populatie van de activiteit kan groter zijn dan de binnenkomende populatie.
   * Controleer de **[!UICONTROL Concatenate the code of each segment]** optie als de binnenkomende bevolking reeds een segmentcode is toegewezen die u wilt houden. De segmentcode die in de activiteit wordt opgegeven, wordt toegevoegd aan de oorspronkelijke segmentcode.
   * Controleer de **[!UICONTROL Generate complement]** optie als u de resterende bevolking wilt uitbuiten.

1. Bevestig de configuratie van uw activiteit en sla uw werkschema op.

## Voorbeeld {#example}

In het volgende voorbeeld wordt een segmentatie van databaseprofielen weergegeven op basis van hun leeftijdsgroep. Het doel van de workflow is om voor elke leeftijdsgroep een specifieke e-mail te verzenden. Gezien het feit dat deze workflow deel uitmaakt van een testcampagne, kan elk segment slechts maximaal 100 profielen bevatten die willekeurig zijn geselecteerd om een beperkt en representatief publiek te gebruiken.

![](assets/wkf_segment_example_4.png)

De workflow bestaat uit de volgende elementen:

* Een **[!UICONTROL Scheduler]** activiteit om de de uitvoeringsdatum van het werkschema te specificeren. Raadpleeg de sectie [Planner](../../automating/using/scheduler.md) .
* Een **[!UICONTROL Query]** activiteit aan doelprofielen van mensen van wie verjaardag en e-mailadres zijn ingegaan. Raadpleeg de sectie [Query](../../automating/using/query.md) .
* Een **[!UICONTROL Segmentation]** activiteit om 3 segmenten tot stand te brengen die in verschillende uitgaande overgangen worden verdeeld: 18-25 jaar oud, 26-32 jaar oud en profielen ouder dan 32 jaar. De segmenten worden gedefinieerd volgens de volgende parameters:

   ![](assets/wkf_segment_example_3.png)

   * Een filter op de leeftijd om de leeftijdsgroep van het segment te bepalen

      ![](assets/wkf_segment_new_segment.png)

   * Een **[!UICONTROL Random sampling]** typelimiet die is gekoppeld aan een **[!UICONTROL Maximum size]** limiet van 100

      ![](assets/wkf_segment_example_1.png)

* Een **[!UICONTROL Email delivery]** activiteit per segment. Raadpleeg de sectie [E-maillevering](../../automating/using/email-delivery.md) .

