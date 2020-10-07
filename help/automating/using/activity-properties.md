---
title: Eigenschappen van activiteiten beheren
description: Leer hoe u de eigenschappen van workflowactiviteiten beheert.
page-status-flag: never-activated
uuid: ff02b74e-53e8-49c6-bf8e-0c729eaa7d25
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: 906c85ea-83b7-4268-86da-cd353f1dc591
context-tags: workflow,overview;workflow,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '675'
ht-degree: 0%

---


# Eigenschappen van activiteiten beheren {#activity-properties}

## Algemene eigenschappen van een activiteit {#global-properties-of-an-activity}

Elke activiteit heeft een **[!UICONTROL General]** lusje, dat u toestaat om algemene parameters te wijzigen die voor de activiteit specifiek zijn.

![](assets/activity-properties.png)

Op het **[!UICONTROL Properties]** tabblad kunt u de algemene parameters van de activiteit wijzigen, met name het label en de id. Het configureren van dit tabblad is optioneel.

![](assets/activity-properties2.png)

## De uitgaande overgangen van een activiteit beheren {#managing-an-activity-s-outbound-transitions}

Door gebrek, hebben bepaalde activiteiten geen uitgaande overgang. U kunt een proces toevoegen vanaf het **[!UICONTROL Transitions]** tabblad of vanaf het **[!UICONTROL Properties]** tabblad Activiteit om andere processen toe te passen op uw populatie in dezelfde workflow.

Afhankelijk van de activiteiten kunt u verschillende typen uitgaande overgangen toevoegen:

* **Standaardovergang**: populatie berekend door de activiteit
* **Overgang zonder populatie**: dit type uitgaande overgang kan worden toegevoegd om de werkstroom voort te zetten en bevat geen populatie om geen onnodige ruimte op het systeem te verbruiken.
* **verwerpt**: de bevolking werd verworpen. Bijvoorbeeld, als de binnenkomende gegevens van de activiteit niet konden worden verwerkt omdat het onjuist of onvolledig was.
* **Complementeren**: populatie die overblijft na uitvoering van de activiteit. Bijvoorbeeld, als een segmentatieactiviteit wordt gevormd om slechts een percentage van de binnenkomende bevolking te bewaren.

Geef, indien van toepassing, een **[!UICONTROL Segment code]** voor de uitgaande overgang van de activiteit. Deze segmentcode zal u toestaan om te identificeren waar de ondergroepen van de doelbevolking van komen, en kan, later, voor de doeleinden van de berichtverpersoonlijking dienen.

## Opties voor het uitvoeren van activiteiten {#activity-execution-options}

In het eigenschappenscherm van de activiteit, is er een **[!UICONTROL Advanced options]** lusje dat u de de uitvoeringswijze en gedrag van de activiteit in het geval van fouten laat bepalen.

Als u deze opties wilt openen, selecteert u een activiteit in een workflow en opent u deze met de ![](assets/edit_darkgrey-24px.png) knop op de actiebalk.

![](assets/wkf_advanced_parameters.png)

In het **[!UICONTROL Execution]** veld kunt u de actie definiëren die moet worden uitgevoerd wanneer de taak wordt gestart. Hiervoor zijn drie opties beschikbaar:

* **Normaal**: de activiteit wordt normaal uitgevoerd.
* **Inschakelen maar niet uitvoeren**: de activiteit wordt gepauzeerd , en als gevolg daarvan zijn er ook toekomstige processen die volgen . Dit kan nuttig blijken als u aanwezig wilt zijn wanneer de taak wordt begonnen.
* **Niet inschakelen**: de activiteit wordt niet uitgevoerd en bijgevolg zijn ook niet alle activiteiten die volgen (in dezelfde tak).

In het **[!UICONTROL In case of error]** veld kunt u opgeven welke actie moet worden uitgevoerd als er een fout optreedt. Hiervoor zijn twee opties beschikbaar:

* **Het proces** onderbreken: de workflow wordt automatisch opgeschort. De workflowstatus is dan **fout** en de bijbehorende kleur wordt rood. Start de workflow opnieuw als het probleem is opgelost.
* **Negeren**: de activiteit wordt niet uitgevoerd, en bijgevolg zijn er ook geen van de activiteiten die daarop volgen (in dezelfde tak). Dit kan handig zijn voor terugkerende taken. Als de tak een eerder geplaatste planner heeft, zou dit op de volgende uitvoeringsdatum moeten teweegbrengen.

In het **[!UICONTROL Behavior]** veld kunt u de procedure definiëren die moet worden gevolgd wanneer asynchrone taken worden gebruikt. Hiervoor zijn twee opties beschikbaar:

* **Meerdere geoorloofde** taken: meerdere taken kunnen tegelijkertijd worden uitgevoerd, zelfs als de eerste niet is voltooid.
* **De huidige taak heeft prioriteit**: zodra een taak is uitgevoerd , krijgt deze prioriteit . Zolang één taak nog bezig is, zal geen andere taak worden uitgevoerd.

In het **[!UICONTROL Max. execution duration]** veld kunt u een duur opgeven, zoals &#39;30&#39; of &#39;1 uur&#39;. Als de activiteit niet wordt gebeëindigd nadat de gespecificeerde duur is verstreken, wordt een alarm teweeggebracht. Dit heeft geen invloed op de werking van de workflow.

In het **[!UICONTROL Affinity]** veld kunt u een workflow of een werkstroomactiviteit op een bepaalde computer uitvoeren. Hiervoor moet u een of meer affiniteiten opgeven voor de workflow of activiteit in kwestie.

In het **[!UICONTROL Time zone]** veld kunt u de tijdzone van de activiteit selecteren. Met Adobe Campaign kunt u de tijdsverschillen tussen meerdere landen op hetzelfde moment beheren. De toegepaste instelling wordt geconfigureerd wanneer de instantie wordt gemaakt.

>[!NOTE]
>
>Als er standaard geen tijdzone is geselecteerd, wordt voor de activiteit de tijdzone gebruikt die is gedefinieerd in de workfloweigenschappen.

Het veld **Opmerking** is een gratis veld waarin u een notitie kunt toevoegen.
