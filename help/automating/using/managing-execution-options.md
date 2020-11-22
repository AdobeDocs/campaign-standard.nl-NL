---
solution: Campaign Standard
product: campaign
title: Uitvoeringsopties beheren
description: Leer hoe u opties voor het uitvoeren van workflows beheert.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 13%

---


# Uitvoeringsopties beheren {#managing-execution-options}

Als u de uitvoeringsopties van een workflow wilt wijzigen, gebruikt u de ![](assets/edit_darkgrey-24px.png) knop om de workfloweigenschappen te openen en selecteert u de **[!UICONTROL Execution]** sectie.

![](assets/wkf_execution_6.png)

Mogelijke opties zijn:

* **[!UICONTROL Default affinity]**: in dit veld kunt u ervoor zorgen dat een workflow of een werkstroomactiviteit op een bepaalde computer wordt uitgevoerd.

* **[!UICONTROL History in days]**: geeft het aantal dagen aan waarna de historie moet worden gewist. De geschiedenis bevat elementen die gerelateerd zijn aan de workflow: logbestanden, taken, gebeurtenissen (technische objecten die zijn gekoppeld aan de workflowbewerking), en bestanden die door de **[!UICONTROL Transfer file]** activiteit zijn gedownload. De standaardwaarde is 30 dagen voor workflowsjablonen buiten de box.

   De geschiedenis wordt gewist door het technische werkschema van de Opschoonmaakbeurt van het Gegevensbestand, dat door gebrek dagelijks wordt uitgevoerd (zie [Lijst van technische werkschema](../../administration/using/technical-workflows.md).)

   >[!IMPORTANT]
   >
   >Als het **[!UICONTROL History in days]** veld leeg blijft, wordt de waarde ervan beschouwd als &quot;1&quot;, wat betekent dat de historie na 1 dag wordt gewist.

* **[!UICONTROL Save SQL queries in the log]**: Hiermee kunt u de SQL-query&#39;s uit de workflow opslaan in de logbestanden.

* **[!UICONTROL Keep interim results]**: Schakel deze optie in als u de details van de overgangen wilt bekijken.

   >[!CAUTION]
   >
   >Deze optie verbruikt veel schijfruimte en is ontworpen om u te helpen een workflow te maken en een correcte configuratie en functionaliteit te garanderen. Laat deze optie uitgeschakeld op productie-instanties.

* **[!UICONTROL Execute in the engine (do not use in production)]**: Hiermee kunt u de workflow lokaal uitvoeren voor testdoeleinden in de ontwikkelomgeving.

* **[!UICONTROL Severity]**: kunt u een prioriteitsniveau opgeven voor het uitvoeren van workflows in uw Adobe Campaign-instantie. Dit veld wordt alleen voor monitoringdoeleinden gebruikt door Adobe-teams.

Het **[!UICONTROL Error management]** gedeelte bevat aanvullende opties waarmee u kunt bepalen hoe workflows zich gedragen bij fouten. Deze opties worden beschreven in de sectie [Foutbeheer](../../automating/using/monitoring-workflow-execution.md#error-management) .
