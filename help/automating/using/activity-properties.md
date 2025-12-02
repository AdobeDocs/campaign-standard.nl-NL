---
title: Eigenschappen van activiteiten beheren
description: Leer hoe u de eigenschappen van workflowactiviteiten beheert.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 9c47ef72-59af-4b55-8e65-d8f687fb5fbe
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '675'
ht-degree: 0%

---

# Eigenschappen van activiteiten beheren {#activity-properties}

## Algemene eigenschappen van een activiteit {#global-properties-of-an-activity}

Elke activiteit heeft een tab **[!UICONTROL General]** , waarmee u algemene parameters kunt wijzigen die specifiek zijn voor de activiteit.

![](assets/activity-properties.png)

Op het tabblad **[!UICONTROL Properties]** kunt u de algemene parameters van de activiteit wijzigen, met name het label en de id. U kunt dit tabblad niet configureren.

![](assets/activity-properties2.png)

## De uitgaande overgangen van een activiteit beheren {#managing-an-activity-s-outbound-transitions}

Door gebrek, hebben bepaalde activiteiten geen uitgaande overgang. U kunt er een toevoegen vanaf het tabblad **[!UICONTROL Transitions]** of vanaf het tabblad **[!UICONTROL Properties]** van de activiteit om andere processen toe te passen op uw populatie in dezelfde workflow.

Afhankelijk van de activiteiten kunt u verschillende typen uitgaande overgangen toevoegen:

* **Standaard overgang**: populatie die door de activiteit wordt gegevens verwerkt
* **Overgang zonder bevolking**: dit type van uitgaande overgang kan worden toegevoegd om het werkschema voort te zetten en bevat geen bevolking om geen onnodige ruimte op het systeem te verbruiken.
* **verwerpt**: Verworpen bevolking. Bijvoorbeeld, als de binnenkomende gegevens van de activiteit niet konden worden verwerkt omdat het onjuist of onvolledig was.
* **Complement**: populatie die na het uitvoeren van de activiteit blijft. Bijvoorbeeld, als een segmentatieactiviteit wordt gevormd om slechts een percentage van de binnenkomende bevolking te bewaren.

Geef, indien van toepassing, een **[!UICONTROL Segment code]** op voor de uitgaande overgang van de activiteit. Deze segmentcode zal u toestaan om te identificeren waar de ondergroepen van de doelbevolking van komen, en kan, later, voor de doeleinden van de berichtverpersoonlijking dienen.

## Opties voor het uitvoeren van activiteiten {#activity-execution-options}

In het eigenschappenscherm van de activiteit, is er een **[!UICONTROL Advanced options]** lusje dat u de de uitvoeringswijze en gedrag van de activiteit in het geval van fouten laat bepalen.

Als u toegang wilt krijgen tot deze opties, selecteert u een activiteit in een workflow en opent u deze met de knop ![](assets/edit_darkgrey-24px.png) op de actiebalk.

![](assets/wkf_advanced_parameters.png)

In het veld **[!UICONTROL Execution]** kunt u de handeling definiëren die moet worden uitgevoerd wanneer de taak wordt gestart. Hiervoor zijn drie opties beschikbaar:

* **Normaal**: de activiteit wordt normaal uitgevoerd.
* **laat toe maar voert niet** uit: de activiteit wordt gepauzeerd, en bijgevolg zijn om het even welke toekomstige processen die volgen. Dit kan nuttig blijken als u aanwezig wilt zijn wanneer de taak wordt begonnen.
* **laat** niet toe: de activiteit wordt niet uitgevoerd, en bijgevolg zijn geen van beide activiteiten die (in de zelfde tak) volgen.

In het veld **[!UICONTROL In case of error]** kunt u opgeven welke actie moet worden uitgevoerd als er een fout optreedt. Hiervoor zijn twee opties beschikbaar:

* **Onderbreek het proces**: het werkschema wordt automatisch opgeschort. De werkschemastatus is dan **Onjuiste** en de kleur verbonden wordt rood. Start de workflow opnieuw als het probleem is opgelost.
* **negeert**: de activiteit wordt niet uitgevoerd, en dientengevolge zijn geen van beide activiteiten die het (in de zelfde tak) volgen. Dit kan handig zijn voor terugkerende taken. Als de tak een eerder geplaatste planner heeft, zou dit op de volgende uitvoeringsdatum moeten teweegbrengen.

In het veld **[!UICONTROL Behavior]** kunt u de procedure definiëren die moet worden gevolgd wanneer asynchrone taken worden gebruikt. Hiervoor zijn twee opties beschikbaar:

* **Veelvoudige geoorloofde taken**: de veelvoudige taken kunnen tezelfdertijd worden uitgevoerd zelfs als eerste niet beëindigde.
* **de huidige taak heeft prioriteit**: zodra een taak lopend is, neemt dit prioriteit. Zolang één taak nog bezig is, zal geen andere taak worden uitgevoerd.

In het veld **[!UICONTROL Max. execution duration]** kunt u een duur opgeven, zoals &#39;30&#39; of &#39;1 uur&#39;. Als de activiteit niet wordt gebeëindigd nadat de gespecificeerde duur is verstreken, wordt een alarm teweeggebracht. Dit heeft geen invloed op de werking van de workflow.

Met het veld **[!UICONTROL Affinity]** kunt u een workflow of een werkstroomactiviteit op een bepaalde computer uitvoeren. Hiervoor moet u een of meer affiniteiten opgeven voor de workflow of activiteit in kwestie.

In het veld **[!UICONTROL Time zone]** kunt u de tijdzone van de activiteit selecteren. Met Adobe Campaign kunt u de tijdsverschillen tussen meerdere landen op hetzelfde moment beheren. De toegepaste instelling wordt geconfigureerd wanneer de instantie wordt gemaakt.

>[!NOTE]
>
>Als er standaard geen tijdzone is geselecteerd, wordt voor de activiteit de tijdzone gebruikt die is gedefinieerd in de workfloweigenschappen.

Het **gebied van de Commentaar** is een vrij gebied dat u toestaat om een nota toe te voegen.
