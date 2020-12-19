---
solution: Campaign Standard
product: campaign
title: Workflowuitvoering controleren
description: Leer hoe u de uitvoering van een workflow kunt controleren.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '577'
ht-degree: 3%

---


# Workflowuitvoering controleren {#monitoring}

## Workflowlogboek en taken {#workflow-log-and-tasks}

Met het pictogram ![](assets/printpreview_darkgrey-24px.png) opent u het workflowlogboek en het taakmenu.

De workflowgeschiedenis wordt opgeslagen voor de duur die is opgegeven in de opties voor workflowuitvoering (zie [Workfloweigenschappen](../../automating/using/managing-execution-options.md)). Tijdens deze duur, worden alle berichten daarom bewaard, zelfs na een nieuw begin. Als u niet de berichten van een vorige uitvoering wilt bewaren, moet u de geschiedenis zuiveren door ![](assets/delete_darkgrey-24px.png) knoop te klikken.

Het tabblad **[!UICONTROL Log]** bevat de uitvoeringsgeschiedenis van alle activiteiten of van alle geselecteerde activiteiten. De uitgevoerde bewerkingen en uitvoeringsfouten worden in chronologische volgorde geïndexeerd.

![](assets/wkf_execution_4.png)

Op het tabblad **[!UICONTROL Tasks]** vindt u de volgorde van uitvoering van de activiteiten. Klik op een taak voor meer informatie.

![](assets/wkf_execution_5.png)

In deze twee lijsten:

* Klik op de teller om het totale aantal activiteiten weer te geven op basis van het toegepaste filter. De teller wordt standaard weergegeven als het aantal elementen in de lijst kleiner is dan 30.
* Met de knop **[!UICONTROL Configure list]** kunt u de weergegeven informatie kiezen, de kolomvolgorde definiëren en de lijst sorteren.
* Met filters kunt u sneller de informatie vinden die u nodig hebt. Gebruik het zoekveld om te zoeken naar een specifieke tekst in namen van workflowactiviteiten (bijvoorbeeld: &quot;query&quot;) en logbestanden.

## Foutbeheer {#error-management}

Wanneer een fout optreedt, wordt de werkstroom gepauzeerd en de activiteit die werd uitgevoerd toen de fout flitsrood werd aangetroffen.

De workflowstatus wordt rood en de fout wordt opgenomen in het logbestand.

U kunt de workflow zodanig configureren dat deze niet wordt gepauzeerd en verder wordt uitgevoerd zonder fouten. Hiervoor gaat u naar de workfloweigenschappen via de knop ![](assets/edit_darkgrey-24px.png) en selecteert u in de sectie **[!UICONTROL Execution]** de optie **Negeren** in het veld **In geval van fout**.

In dit geval wordt de onjuiste taak afgebroken. Deze modus is vooral geschikt voor workflows die zijn ontworpen om de bewerking later opnieuw te proberen (periodieke handelingen).

>[!NOTE]
>
>U kunt deze configuratie afzonderlijk toepassen voor elke activiteit. U doet dit door een activiteit te selecteren en deze te openen met de snelle actie ![](assets/edit_darkgrey-24px.png). Selecteer vervolgens de modus voor foutbeheer op het tabblad **Uitvoeropties**. Zie [Opties voor het uitvoeren van activiteiten](../../automating/using/activity-properties.md).

In de [eigenschappen van de werkstroom](../../automating/using/managing-execution-options.md), zijn de extra opties met betrekking tot foutenbeheer beschikbaar.

![](assets/wkf_execution_error.png)

Mogelijke opties zijn:

* **[!UICONTROL Supervisors]**: Hiermee kunt u de groep personen definiëren die op de hoogte moeten worden gesteld (e-mail en meldingen in de app) als de workflow een fout aantreft. Als er geen groep wordt gedefinieerd, wordt niemand op de hoogte gebracht. Raadpleeg [Adobe Campaign-meldingen](../../administration/using/sending-internal-notifications.md) voor meer informatie over Adobe Campaign-berichten.

* **[!UICONTROL In case of error]**: kunt u opgeven welke actie moet worden uitgevoerd als de activiteit een fout aantreft. Hiervoor zijn twee opties beschikbaar:

   * **Het proces** onderbreken: de workflow wordt automatisch opgeschort. De workflowstatus is dan **Onjuist** en de bijbehorende kleur wordt rood. Start de workflow opnieuw als het probleem is opgelost.
   * **Negeren**: de activiteit wordt niet uitgevoerd, en bijgevolg zijn er ook geen van de activiteiten die daarop volgen (in dezelfde tak). Dit kan handig zijn voor terugkerende taken. Als de tak een eerder geplaatste planner heeft, zou dit op de volgende uitvoeringsdatum moeten teweegbrengen.

* **[!UICONTROL Consecutive errors]** : Hiermee kunt u een aantal opeenvolgende fouten definiëren die zijn geautoriseerd voordat de uitvoering van de workflow automatisch wordt onderbroken.

   * Als het opgegeven getal **[!UICONTROL 0]** is, of zolang het opgegeven getal niet wordt bereikt, worden activiteiten die fouten tegenkomen, genegeerd. De andere werkstroomvertakkingen worden normaal uitgevoerd.

   * Als het opgegeven getal wordt bereikt, wordt de gehele workflow onderbroken en **[!UICONTROL Erroneous]**. Als toezichthouders zijn gedefinieerd, worden ze automatisch via e-mail op de hoogte gesteld. Zie [Adobe Campaign-meldingen](../../administration/using/sending-internal-notifications.md).
