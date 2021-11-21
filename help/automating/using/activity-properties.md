---
title: Eigenschappen van activiteiten beheren
description: Leer hoe u de eigenschappen van workflowactiviteiten beheert.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 9c47ef72-59af-4b55-8e65-d8f687fb5fbe
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '675'
ht-degree: 0%

---

# Eigenschappen van activiteiten beheren {#activity-properties}

## Algemene eigenschappen van een activiteit {#global-properties-of-an-activity}

Elke activiteit heeft een **[!UICONTROL General]** , waarmee u algemene parameters kunt wijzigen die specifiek zijn voor de activiteit.

![](assets/activity-properties.png)

De **[!UICONTROL Properties]** kunt u de algemene parameters van de activiteit wijzigen, met name het label en de id. Het configureren van dit tabblad is optioneel.

![](assets/activity-properties2.png)

## De uitgaande overgangen van een activiteit beheren {#managing-an-activity-s-outbound-transitions}

Door gebrek, hebben bepaalde activiteiten geen uitgaande overgang. U kunt er een toevoegen vanuit het menu **[!UICONTROL Transitions]** of van de activiteit **[!UICONTROL Properties]** om andere processen in dezelfde workflow op uw bevolking toe te passen.

Afhankelijk van de activiteiten kunt u verschillende typen uitgaande overgangen toevoegen:

* **Standaardovergang**: populatie berekend door de activiteit
* **Overgang zonder populatie**: dit type uitgaande overgang kan worden toegevoegd om de werkstroom voort te zetten en bevat geen populatie om geen onnodige ruimte op het systeem te verbruiken.
* **Afwijzingen**: de bevolking werd verworpen. Bijvoorbeeld, als de binnenkomende gegevens van de activiteit niet konden worden verwerkt omdat het onjuist of onvolledig was.
* **Complementeren**: populatie die overblijft na uitvoering van de activiteit. Bijvoorbeeld, als een segmentatieactiviteit wordt gevormd om slechts een percentage van de binnenkomende bevolking te bewaren.

Geef, indien van toepassing, een **[!UICONTROL Segment code]** voor de uitgaande overgang van de activiteit. Deze segmentcode zal u toestaan om te identificeren waar de ondergroepen van de doelbevolking van komen, en kan, later, voor de doeleinden van de berichtverpersoonlijking dienen.

## Opties voor het uitvoeren van activiteiten {#activity-execution-options}

In het eigenschappenscherm van de activiteit is er een **[!UICONTROL Advanced options]** tabblad waarin u de uitvoeringsmodus en het gedrag van de activiteit kunt definiëren in het geval van fouten.

Als u toegang wilt krijgen tot deze opties, selecteert u een activiteit in een workflow en opent u deze vervolgens met de knop ![](assets/edit_darkgrey-24px.png) in de actiebalk.

![](assets/wkf_advanced_parameters.png)

De **[!UICONTROL Execution]** in het veld kunt u de actie definiëren die moet worden uitgevoerd wanneer de taak wordt gestart. Hiervoor zijn drie opties beschikbaar:

* **Normaal**: de activiteit wordt normaal uitgevoerd.
* **Inschakelen maar niet uitvoeren**: de activiteit wordt gepauzeerd , en als gevolg daarvan zijn er ook toekomstige processen die volgen . Dit kan nuttig blijken als u aanwezig wilt zijn wanneer de taak wordt begonnen.
* **Niet inschakelen**: de activiteit wordt niet uitgevoerd en bijgevolg zijn ook niet alle activiteiten die volgen (in dezelfde tak).

De **[!UICONTROL In case of error]** in dit veld kunt u opgeven welke actie moet worden uitgevoerd als er een fout optreedt. Hiervoor zijn twee opties beschikbaar:

* **Het proces onderbreken**: de workflow wordt automatisch opgeschort. De workflowstatus is dan **Onjuist** en de bijbehorende kleur wordt rood. Start de workflow opnieuw als het probleem is opgelost.
* **Negeren**: de activiteit wordt niet uitgevoerd, en bijgevolg zijn er ook geen van de activiteiten die daarop volgen (in dezelfde tak). Dit kan handig zijn voor terugkerende taken. Als de tak een eerder geplaatste planner heeft, zou dit op de volgende uitvoeringsdatum moeten teweegbrengen.

De **[!UICONTROL Behavior]** kunt u in het veld de procedure definiëren die moet worden gevolgd wanneer asynchrone taken worden gebruikt. Hiervoor zijn twee opties beschikbaar:

* **Meerdere taken geautoriseerd**: meerdere taken kunnen tegelijkertijd worden uitgevoerd, zelfs als de eerste niet is voltooid.
* **De huidige taak heeft prioriteit**: zodra een taak is uitgevoerd , krijgt deze prioriteit . Zolang één taak nog bezig is, zal geen andere taak worden uitgevoerd.

De **[!UICONTROL Max. execution duration]** kunt u een duur opgeven, bijvoorbeeld &#39;&#39;30s&#39;&#39; of &#39;&#39;1h&#39;&#39;. Als de activiteit niet wordt gebeëindigd nadat de gespecificeerde duur is verstreken, wordt een alarm teweeggebracht. Dit heeft geen invloed op de werking van de workflow.

De **[!UICONTROL Affinity]** kunt u een workflow of een werkstroomactiviteit forceren om op een bepaalde computer uit te voeren. Hiervoor moet u een of meer affiniteiten opgeven voor de workflow of activiteit in kwestie.

De **[!UICONTROL Time zone]** kunt u de tijdzone van de activiteit selecteren. Met Adobe Campaign kunt u de tijdsverschillen tussen meerdere landen op hetzelfde moment beheren. De toegepaste instelling wordt geconfigureerd wanneer de instantie wordt gemaakt.

>[!NOTE]
>
>Als er standaard geen tijdzone is geselecteerd, wordt voor de activiteit de tijdzone gebruikt die is gedefinieerd in de workfloweigenschappen.

De **Opmerking** Veld is een gratis veld waarmee u een notitie kunt toevoegen.
