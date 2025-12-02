---
title: Workflowuitvoering controleren
description: Leer hoe u de uitvoering van een workflow kunt controleren.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: d2ce702b-92d1-4b94-bd47-34ef46a8bd9f
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '578'
ht-degree: 3%

---

# Workflowuitvoering controleren {#monitoring}

## Workflowlogboek en taken {#workflow-log-and-tasks}

Met het pictogram ![](assets/printpreview_darkgrey-24px.png) opent u het workflowlogboek en het taakmenu.

De werkschemageschiedenis wordt bewaard voor de duur die in de opties van de werkschemauitvoering wordt gespecificeerd (verwijs naar [&#x200B; eigenschappen van het Werkschema &#x200B;](../../automating/using/managing-execution-options.md)). Tijdens deze duur, worden alle berichten daarom bewaard, zelfs na een nieuw begin. Als u de berichten van een vorige uitvoering niet wilt opslaan, moet u de geschiedenis wissen door op de knop ![](assets/delete_darkgrey-24px.png) te klikken.

Het tabblad **[!UICONTROL Log]** bevat de uitvoeringsgeschiedenis van alle activiteiten of van alle geselecteerde activiteiten. De uitgevoerde bewerkingen en uitvoeringsfouten worden chronologisch geïndexeerd.

![](assets/wkf_execution_4.png)

Het tabblad **[!UICONTROL Tasks]** bevat details over de uitvoeringsvolgorde van de activiteiten. Klik op een taak voor meer informatie.

![](assets/wkf_execution_5.png)

In deze twee lijsten:

* Klik op de teller om het totale aantal activiteiten weer te geven op basis van het toegepaste filter. De teller wordt standaard weergegeven als het aantal elementen in de lijst kleiner is dan 30.
* Met de knop **[!UICONTROL Configure list]** kunt u de weergegeven informatie kiezen, de kolomvolgorde definiëren en de lijst sorteren.
* Met filters kunt u sneller de informatie vinden die u nodig hebt. Gebruik het zoekveld om te zoeken naar een specifieke tekst in namen van workflowactiviteiten (bijvoorbeeld: &quot;query&quot;) en logbestanden.

## Foutbeheer {#error-management}

Wanneer een fout optreedt, wordt de werkstroom gepauzeerd en de activiteit die werd uitgevoerd toen de fout flitsrood werd aangetroffen.

De workflowstatus wordt rood en de fout wordt opgenomen in het logbestand.

U kunt de workflow zodanig configureren dat deze niet wordt gepauzeerd en verder wordt uitgevoerd zonder fouten. Dit doen, ga naar de werkschemaeigenschappen via de ![](assets/edit_darkgrey-24px.png) knoop en, in de **[!UICONTROL Execution]** sectie, selecteer **negeren** optie in het **In geval van fout** gebied.

In dit geval wordt de onjuiste taak afgebroken. Deze modus is vooral geschikt voor workflows die zijn ontworpen om de bewerking later opnieuw te proberen (periodieke handelingen).

>[!NOTE]
>
>U kunt deze configuratie afzonderlijk toepassen voor elke activiteit. U doet dit door een activiteit te selecteren en deze te openen met de snelle actie ![](assets/edit_darkgrey-24px.png) . Dan selecteer de wijze van het foutenbeheer op de **opties van de Uitvoering** tabel. Zie [&#x200B; de uitvoeringsopties van de Activiteit &#x200B;](../../automating/using/activity-properties.md).

In de [&#x200B; eigenschappen van het werkschema &#x200B;](../../automating/using/managing-execution-options.md), zijn de extra opties met betrekking tot foutenbeheer beschikbaar.

![](assets/wkf_execution_error.png)

Mogelijke opties zijn:

* **[!UICONTROL Supervisors]**: hiermee kunt u de groep personen definiëren die een melding moeten ontvangen (e-mail en meldingen in de app) als er een fout optreedt in de workflow. Als er geen groep wordt gedefinieerd, wordt niemand op de hoogte gebracht. Voor meer informatie over Adobe Campaign-notificaties raadpleegt u [Adobe Campaign-notificaties](../../administration/using/sending-internal-notifications.md).

* **[!UICONTROL In case of error]** : hiermee kunt u opgeven welke actie moet worden uitgevoerd als de activiteit een fout aantreft. Hiervoor zijn twee opties beschikbaar:

   * **Onderbreek het proces**: het werkschema wordt automatisch opgeschort. De werkschemastatus is dan **Onjuiste** en de kleur verbonden wordt rood. Start de workflow opnieuw als het probleem is opgelost.
   * **negeert**: de activiteit wordt niet uitgevoerd, en dientengevolge zijn geen van beide activiteiten die het (in de zelfde tak) volgen. Dit kan handig zijn voor terugkerende taken. Als de tak een eerder geplaatste planner heeft, zou dit op de volgende uitvoeringsdatum moeten teweegbrengen.

* **[!UICONTROL Consecutive errors]** : hiermee kunt u een aantal opeenvolgende fouten definiëren die zijn geautoriseerd voordat de uitvoering van de workflow automatisch wordt onderbroken.

   * Wanneer het opgegeven getal **[!UICONTROL 0]** is of zolang het opgegeven getal niet wordt bereikt, worden activiteiten die fouten tegenkomen, genegeerd. De andere werkstroomvertakkingen worden normaal uitgevoerd.

   * Als het opgegeven nummer is bereikt, wordt de gehele workflow onderbroken en wordt deze **[!UICONTROL Erroneous]** . Als toezichthouders zijn gedefinieerd, worden ze automatisch via e-mail op de hoogte gesteld. Zie [Adobe Campaign-meldingen](../../administration/using/sending-internal-notifications.md).
