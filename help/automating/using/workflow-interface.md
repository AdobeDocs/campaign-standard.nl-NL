---
title: Workflowinterface
description: Leer de interface en opties voor het maken, bewerken en uitvoeren van een workflow.
page-status-flag: never-activated
uuid: aafe33ed-fa07-4dd9-825e-242099334f1a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
discoiquuid: 147fbb0d-17d2-444b-a215-9ad14179c549
context-tags: workflow,main;workflow,overview
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '802'
ht-degree: 4%

---


# Workflowinterface{#workflow-interface}

U kunt workflows maken om volledige processen in uw campagnes en programma&#39;s te beheren.

Het werkstroombewerkingsscherm bestaat uit de volgende elementen:

* Het [palet](#palette), waarin wordt verwezen naar de beschikbare activiteiten.
* De [werkruimte](#workspace)waarin de activiteiten zijn geconfigureerd en georganiseerd.
* De [actiebalk](#action-bar)bestaat uit knoppen waarmee u kunt communiceren met de workflow en/of de componenten ervan.
* Met de [snelle acties](#quick-actions), die rond een geselecteerde activiteit verschijnen, kunt u ermee werken.

![](assets/wkf_overview.png)

## Palet {#palette}

Het palet bevindt zich aan de linkerkant van het scherm. Alle beschikbare activiteiten worden ingedeeld in verschillende categorieën:

* [Doelstelling](../../automating/using/about-targeting-activities.md): activiteiten die specifiek gericht zijn op doelgerichte activiteiten, manipulatie van bevolkingsgegevens en filteractiviteiten
* [Uitvoering](../../automating/using/about-execution-activities.md): specifieke activiteiten voor het organiseren en uitvoeren van workflows
* [Kanalen](../../automating/using/about-channel-activities.md): activiteiten die de verschillende beschikbare communicatiekanalen vertegenwoordigen
* [Gegevensbeheer (ETL)](../../automating/using/about-data-management-activities.md): specifieke activiteiten voor het manipuleren van gegevens

Als u een activiteit wilt gebruiken vanuit het palet in uw workflow, sleept u deze naar de werkruimte.

U moet elke activiteit vormen die vanaf het palet wordt toegevoegd alvorens het werkschema te beginnen.

![](assets/workflow_palette.png)

## Werkruimte {#workspace}

De werkruimte is de centrale zone in de werkstroomeditor. Het is in deze streek dat u uw activiteiten kunt laten vallen, hen verbinden samen gebruikend overgangen, en hen vormen.

Als u twee activiteiten wilt koppelen, verplaatst u het einde van de pijl van de eerste activiteit naar de volgende activiteit totdat ze verbinding maken. U kunt de activiteit naar het punt van de pijl achter het bewegen om het aan de voorafgaande activiteit te verbinden. Als u een van de activiteiten verplaatst, blijven deze gekoppeld.

Overgangen na activiteiten die gegevens verwerken, bevatten de intermediaire populaties. U kunt ze openen door de **[!UICONTROL Keep interim results]** optie in het **[!UICONTROL Execution]** gedeelte van de workfloweigenschappen te selecteren.

>[!CAUTION]
>
>Deze optie verbruikt veel schijfruimte en is ontworpen om u te helpen een workflow te maken en een correcte configuratie en functionaliteit te garanderen. Laat deze optie uitgeschakeld op productie-instanties.


Wanneer een activiteit wordt geselecteerd, verschijnen de snelle acties rond de activiteit, toestaand u om met het in wisselwerking te staan. Als u bijvoorbeeld een activiteit wilt configureren, selecteert u deze en opent u deze vervolgens met de ![](assets/edit_darkgrey-24px_table.png) knop in de snelle handelingen.

Bepaalde functies zijn alleen beschikbaar in de werkruimte:

* Selecteer verschillende activiteiten en overgangen door er een zone omheen te tekenen.
* Druk op **Ctrl** en klik met de linkermuisknop om meerdere handelingen en/of overgangen te selecteren.
* Druk op **Enter** om de details van de geselecteerde activiteit of overgang weer te geven.
* Druk op **Delete** om de geselecteerde activiteit te verwijderen.
* Druk op **Ctrl + C** om de geselecteerde activiteiten te kopiëren en op **Ctrl + V** om deze in de werkruimte te plakken.

![](assets/workflow_workspace.png)

## Actiebalk {#action-bar}

Afhankelijk van de elementen die zijn geselecteerd in de werkruimte of de uitvoeringsstatus van de workflow, kunnen de knoppen in de actiebalk afwijken.

<img height="21px" src="assets/edit_darkgrey-24px.png" /> **[!UICONTROL Open activity]**<br/>Hiermee kunt u de eigenschappen van de workflow bewerken.

<img height="21px" src="assets/play_darkgrey-24px_table.png" /> **[!UICONTROL Start]**<br/>Start de workflow.

<img height="21px" src="assets/pause_darkgrey-24px_table.png" /> **[!UICONTROL Pause]**<br/>Pauzeert de workflow.

<img height="21px" src="assets/stop_darkgrey-24px_table.png" /> **[!UICONTROL Stop]**<br/>Onderbreekt de uitvoering van de workflow. Kan niet worden hervat vanwaar het werd gestopt.

<img height="21px" src="assets/pauseplay_darkgrey-24px_table.png" /> **[!UICONTROL Restart]**<br/>Start de workflow opnieuw.

<img height="21px" src="assets/printpreview_darkgrey-24px_table.png" /> **[!UICONTROL Log and tasks]**<br/>Hiermee opent u het uitvoeringslogboek van de workflow.

<img height="21px" src="assets/checkcircle_darkgrey-24px_table.png" /> **[!UICONTROL Enable multi-selection]**<br/>Schakelt de modus voor meerdere selecties in. De workflow moet uit ten minste twee activiteiten bestaan.

<img height="21px" src="assets/closecircle_darkgrey-24px_table.png" /> **[!UICONTROL Disable multi-selection]**<br/>Schakelt de multi-selectiemodus uit.<br />

<img height="21px" src="assets/targeted.png" /> **[!UICONTROL Open transition]**<br/>Hiermee opent u de geselecteerde overgang.<br />

<img height="21px" src="assets/check_darkgrey-24px_table.png" />  **[!UICONTROL Normal execution]**<br/>Hiermee wordt de selectie opnieuw ingeschakeld als deze eerder is uitgeschakeld of gemarkeerd als gepauzeerd.<br />

<img height="21px" src="assets/check_pause_darkgrey-24px_table.png" /> **[!UICONTROL Execution suspended]**<br/>Hiermee onderbreekt u de workflow bij de geselecteerde activiteit.<br />

<img height="21px" src="assets/checkdisable.png" /> **[!UICONTROL No execution]**<br/>Hiermee wordt de activiteit uitgeschakeld.<br />

<img height="21px" src="assets/delete_darkgrey-24px_table.png" /> **[!UICONTROL Delete selection]**<br/>Hiermee verwijdert u de geselecteerde activiteiten.<br />

<img height="21px" src="assets/copy_24px.png" /> **[!UICONTROL Copy selection]**<br/>Kopieert de geselecteerde activiteiten.

<img height="21px" src="assets/paste_24px.png" /> **[!UICONTROL Paste]**<br/>Hiermee plakt u de gekopieerde activiteiten.

## Snelle acties {#quick-actions}

Wanneer een activiteit wordt geselecteerd, verschijnen de snelle actieknopen rond de activiteit, die u toestaat om met het in wisselwerking te staan.

<img height="21px" src="assets/edit_darkgrey-24px.png" /> **[!UICONTROL Open activity]**<br/>Hiermee opent u de geselecteerde activiteit.

<img height="21px" src="assets/copy_24px.png" /> **[!UICONTROL Copy selection]**<br/>Hiermee kopieert u de geselecteerde activiteit.

<img height="21px" src="assets/wkf_dlv_act_params_icon.png" /> **[!UICONTROL Open the activity's advanced options]**<br/>Hiermee opent u de geavanceerde opties voor de geselecteerde verzending via e-mail of SMS.

<img height="21px" src="assets/check_darkgrey-24px_table.png" /> **[!UICONTROL Normal execution]**<br/>Hiermee wordt de selectie opnieuw ingeschakeld als deze eerder is uitgeschakeld of gemarkeerd als gepauzeerd.

<img height="21px" src="assets/check_pause_darkgrey-24px_table.png" /> **[!UICONTROL Execution suspended]**<br/>Hiermee onderbreekt u de workflow bij de geselecteerde activiteit.

<img height="21px" src="assets/checkdisable.png" /> **[!UICONTROL No execution]**<br/>Hiermee wordt de activiteit uitgeschakeld.

<img height="21px" src="assets/pending_darkgrey-24px_table.png" /> **[!UICONTROL Immediate execution]**<br/>Hiermee wordt de selectie onmiddellijk verwerkt. Deze knoop is slechts beschikbaar voor de<span class="uicontrol">Planner</span>en<span class="uicontrol">Wacht</span>activiteiten.

<img height="21px" src="assets/delete_darkgrey-24px_table.png" /> **[!UICONTROL Delete selection]**<br/>Hiermee verwijdert u de geselecteerde activiteiten.

## Dubbele werkstroomactiviteiten {#duplicating-workflow-activities}

Met de werkruimte kunt u workflowactiviteiten dupliceren door deze naar dezelfde workflow te kopiëren en te plakken, of naar een andere workflow vanuit dezelfde Campagne-instantie.

Zodra een activiteit wordt gedupliceerd, wordt zijn volledige configuratie gehouden. Voor leveringsactiviteiten (e-mail, SMS, pushmelding...) wordt het leveringsobject dat aan de activiteit is gekoppeld, gedupliceerd.

>[!NOTE]
>
>Workflowactiviteiten kunnen niet van een instantie naar een andere worden gedupliceerd. Activiteiten uit technische werkstromen kunnen niet worden gedupliceerd.

Voer de volgende stappen uit om een activiteit te dupliceren:

1. Selecteer de activiteit, dan klik de **[!UICONTROL Copy selection]** knoop van de snelle acties.

   U kunt ook de sneltoets **Ctrl + C** gebruiken.

   ![](assets/wkf_copypaste1.png)

1. Klik met de rechtermuisknop in de werkruimte van de doelworkflow en klik vervolgens op de **[!UICONTROL Paste]** knop.

   U kunt ook de sneltoets **CTRL + V** gebruiken.

   ![](assets/wkf_copypaste2.png)

1. De activiteit wordt gedupliceerd, met alle montages die aanvankelijk zijn gevormd.

Het is ook mogelijk om meerdere activiteiten te kopiëren en te plakken, zodat u een volledige werkstroom kunt dupliceren.

U doet dit door de activiteiten te selecteren door er een zone omheen te tekenen. Klik vervolgens op de **[!UICONTROL Copy selection]** knop op de actiebalk (of druk op **Ctrl + C**). U kunt ze vervolgens op de gewenste locatie plakken.

![](assets/wkf_copypaste3.png)

