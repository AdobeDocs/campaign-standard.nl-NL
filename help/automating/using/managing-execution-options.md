---
title: Uitvoeringsopties beheren
description: Leer hoe u opties voor het uitvoeren van workflows beheert.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Beginner
exl-id: b0cc38fe-cf71-4350-8b4e-7daf0bf94066
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 6%

---

# Uitvoeringsopties beheren {#managing-execution-options}

Als u de uitvoeropties van een workflow wilt wijzigen, gebruikt u de knop ![](assets/edit_darkgrey-24px.png) om de workfloweigenschappen te openen en selecteert u de sectie **[!UICONTROL Execution]** .

![](assets/wkf_execution_6.png)

Mogelijke opties zijn:

* **[!UICONTROL Default affinity]**: in dit veld kunt u een workflow of een werkstroomactiviteit op een bepaalde computer uitvoeren.

* **[!UICONTROL History in days]**: geeft het aantal dagen aan waarna de historie moet worden gewist. De historie bevat elementen die verwant zijn aan de workflow: logbestanden, taken, gebeurtenissen (technische objecten die zijn gekoppeld aan de workflowbewerking) en bestanden die door de **[!UICONTROL Transfer file]** -activiteit zijn gedownload. De standaardwaarde is 30 dagen voor workflowsjablonen buiten de box.

  Wis van de geschiedenis wordt uitgevoerd door het technische werkschema van de schoonmaakbeurt van het Gegevensbestand, dat door gebrek dagelijks (zie [ Lijst van technische werkschema&#39;s ](../../administration/using/technical-workflows.md) wordt uitgevoerd.)

  >[!IMPORTANT]
  >
  >Als het veld **[!UICONTROL History in days]** leeg blijft, wordt de waarde ervan beschouwd als &quot;1&quot;, wat betekent dat de historie na 1 dag wordt gewist.

* **[!UICONTROL Save SQL queries in the log]**: hiermee kunt u de SQL-query&#39;s uit de workflow opslaan in de logbestanden.

* **[!UICONTROL Diagnostic mode (Log execution plan of long running queries and give recommendations)]**: controleer deze optie als u het volledige uitvoeringsplan wilt worden geregistreerd. Deze optie is standaard uitgeschakeld.

  Voor meer informatie over deze optie, verwijs naar deze [ sectie ](#diagnostic-mode).

* **[!UICONTROL Keep interim results]**: controleer deze optie als u de details van overgangen wilt kunnen bekijken.

  >[!CAUTION]
  >
  >Deze optie verbruikt veel schijfruimte en is ontworpen om u te helpen een workflow te maken en een correcte configuratie en functionaliteit te garanderen. Laat deze optie uitgeschakeld op productie-instanties.

* **[!UICONTROL Execute in the engine (do not use in production)]**: hiermee kunt u de workflow lokaal uitvoeren voor testdoeleinden in de ontwikkelomgeving.

* **[!UICONTROL Severity]**: hiermee kunt u een prioriteitsniveau opgeven voor het uitvoeren van workflows in uw Adobe Campaign-instantie. Dit veld wordt door Adobe-teams alleen gebruikt voor bewakingsdoeleinden.

De sectie **[!UICONTROL Error management]** bevat aanvullende opties waarmee u kunt bepalen hoe workflows zich gedragen bij fouten. Deze opties worden gedetailleerd in de [ het beheersings ](../../automating/using/monitoring-workflow-execution.md#error-management) sectie van de Fout.

## Diagnosemodus {#diagnostic-mode}

>[!CAUTION]
>
>Deze optie kan de workflowprestaties aanzienlijk beïnvloeden en moet spaarzaam worden gebruikt.

Als deze optie is ingeschakeld, wordt het hele uitvoeringsplan door de optie **[!UICONTROL Diagnostic mode (Log execution plan of long running queries and give recommendations)]** in de **[!UICONTROL Execution]** -sectie van de workfloweigenschappen geregistreerd als een query meer dan een minuut in beslag neemt.

![](assets/wkf_diagnostic.png)

Nadat u deze optie hebt ingeschakeld en uw workflow hebt gestart, wordt het uitvoeringsplan geregistreerd als uw query meer dan één minuut duurt. U kunt uw uitvoeringsplan dan terugwinnen door EXPLAIN ANALYZE te gebruiken.

Voor meer informatie over dit, verwijs naar [ documentatie PostgreSQL ](https://www.postgresql.org/docs/9.4/using-explain.html).

Als deze query een reeks-scan bevat, geeft **[!UICONTROL Diagnostic mode]** ook aanbevelingen om een index te maken met behulp van een filterexpressie.

>[!NOTE]
>
> Deze aanbevelingen zijn uitsluitend bedoeld voor referentiedoeleinden en dienen zorgvuldig te worden gebruikt, afhankelijk van uw gebruiksgeval.

![](assets/wkf_diagnostic_4.png)

Tijdens de uitvoering van de workflow moet aan de volgende twee voorwaarden worden voldaan om aanbevelingen te activeren:

* De opeenvolgingsaftasten neemt meer dan 40% tijd van de vraag.

* De resulterende rijen na de opeenvolgingsaftasten zijn minder dan 1 % van de totale rijen aanwezig in de lijst.

U kunt de optie vanuit het geavanceerde menu beheren door **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]** te selecteren:

* **[!UICONTROL Time of query execution (in milliseconds)(DiagnosticModeQueryTime)]**: Vanuit het veld **[!UICONTROL Value]** kunt u een nieuwe tijd voor de uitvoering van de query instellen. Als uw vraaguitvoering deze waarde overschrijdt, zal het uitvoeringsplan worden geregistreerd.

  ![](assets/wkf_diagnostic_2.png)

* **[!UICONTROL Percentage of seq scan time (DiagnosticModeSeqScanPercentage)]**: Vanuit het veld **[!UICONTROL Value]** kunt u het percentage wijzigen van de querytijd die de scans van reeksen moet doorlopen voordat de aanbeveling wordt gegenereerd.

  ![](assets/wkf_diagnostic_3.png)
