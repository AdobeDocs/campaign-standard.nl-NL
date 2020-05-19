---
title: Uitvoeropties beheren
description: Leer hoe u opties voor het uitvoeren van workflows beheert.
page-status-flag: never-activated
uuid: ff02b74e-53e8-49c6-bf8e-0c729eaa7d25
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: 906c85ea-83b7-4268-86da-cd353f1dc591
context-tags: workflow,overview;workflow,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 422f5eb7011dfcc1d923079e7346394a64934a9a
workflow-type: tm+mt
source-wordcount: '241'
ht-degree: 0%

---


# Uitvoeropties beheren {#managing-execution-options}

Als u de uitvoeringsopties van een workflow wilt wijzigen, gebruikt u de ![](assets/edit_darkgrey-24px.png) knop om de workfloweigenschappen te openen en selecteert u de **[!UICONTROL Execution]** sectie.

![](assets/wkf_execution_6.png)

Mogelijke opties zijn:

* **[!UICONTROL Default affinity]**: in dit veld kunt u ervoor zorgen dat een workflow of een werkstroomactiviteit op een bepaalde computer wordt uitgevoerd.

* **[!UICONTROL History in days]**: geeft het aantal dagen aan waarna de historie moet worden gewist. De geschiedenis bevat elementen die gerelateerd zijn aan de workflow: logbestanden, taken, gebeurtenissen (technische objecten die zijn gekoppeld aan de workflowbewerking), en bestanden die door de **[!UICONTROL Transfer file]** activiteit zijn gedownload. De standaardwaarde is 30 dagen voor workflowsjablonen buiten de box.

   De geschiedenis wordt gewist door het technische werk van de Opschoonmaakbeurt van het Gegevensbestand, dat door gebrek dagelijks wordt uitgevoerd (zie [Lijst van technische werkschema](../../administration/using/technical-workflows.md).)

   >[!IMPORTANT]
   >
   >Als het **[!UICONTROL History in days]** veld leeg blijft, wordt de waarde ervan beschouwd als &quot;1&quot;, wat betekent dat de historie na 1 dag wordt gewist.

* **[!UICONTROL Save SQL queries in the log]**: Hiermee kunt u de SQL-query&#39;s uit de workflow opslaan in de logbestanden.

* **[!UICONTROL Keep interim results]**: Schakel deze optie in als u de details van de overgangen wilt bekijken. Waarschuwing: Als u deze optie inschakelt, kan de uitvoering van de workflow aanzienlijk worden vertraagd.

* **[!UICONTROL Execute in the engine (do not use in production)]**: Hiermee kunt u de workflow lokaal uitvoeren voor testdoeleinden in de ontwikkelomgeving.

* **[!UICONTROL Severity]**: kunt u een prioriteitsniveau opgeven voor het uitvoeren van workflows in uw Adobe Campagne-instantie. Kritieke workflows worden eerst uitgevoerd.

Het **[!UICONTROL Error management]** gedeelte bevat aanvullende opties waarmee u kunt bepalen hoe workflows zich gedragen bij fouten. Deze opties worden beschreven in de sectie [Foutbeheer](#error-management) .
