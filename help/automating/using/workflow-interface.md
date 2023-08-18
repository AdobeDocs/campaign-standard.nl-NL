---
title: Workflowinterface
description: Leer de interface en opties voor het maken, bewerken en uitvoeren van een workflow.
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
context-tags: workflow,main;workflow,overview
feature: Workflows
role: Data Architect
level: Beginner
exl-id: a3f35bb9-e61e-4f3f-b855-1d677422f75a
source-git-commit: 13d419c5fc51845ee14f8a3b288f4c467e0a60d9
workflow-type: tm+mt
source-wordcount: '802'
ht-degree: 4%

---

# Workflowinterface{#workflow-interface}

U kunt workflows maken om volledige processen in uw campagnes en programma&#39;s te beheren.

Het werkstroombewerkingsscherm bestaat uit de volgende elementen:

* De [Palet](#palette), waarin wordt verwezen naar de beschikbare activiteiten.
* De [Werkruimte](#workspace), waarin de activiteiten zijn geconfigureerd en georganiseerd.
* De [Actiebalk](#action-bar), die bestaat uit knoppen waarmee u kunt communiceren met de workflow en/of de onderdelen ervan.
* De [Snelle acties](#quick-actions), die rond een geselecteerde activiteit verschijnen, staat u toe om met het in wisselwerking te staan.

![](assets/wkf_overview.png)

## Palet {#palette}

Het palet bevindt zich aan de linkerkant van het scherm. Alle beschikbare activiteiten worden ingedeeld in verschillende categorieën:

* [Targeting](../../automating/using/about-targeting-activities.md)Betreft: Activiteiten die specifiek gericht zijn op doelgerichtheid, manipulatie van bevolkingsgegevens en filteractiviteiten
* [Uitvoering](../../automating/using/about-execution-activities.md): specifieke activiteiten voor het organiseren en uitvoeren van workflows
* [Kanalen](../../automating/using/about-channel-activities.md): activiteiten die de verschillende beschikbare communicatiekanalen vertegenwoordigen
* [Gegevensbeheer (ETL)](../../automating/using/about-data-management-activities.md)Betreft: Specifieke activiteiten voor het manipuleren van gegevens

Als u een activiteit wilt gebruiken vanuit het palet in uw workflow, sleept u deze naar de werkruimte.

U moet elke activiteit vormen die vanaf het palet wordt toegevoegd alvorens het werkschema te beginnen.

![](assets/workflow_palette.png)

## Werkruimte {#workspace}

De werkruimte is de centrale zone in de werkstroomeditor. Het is in deze streek dat u uw activiteiten kunt laten vallen, hen verbinden samen gebruikend overgangen, en hen vormen.

Als u twee activiteiten wilt koppelen, verplaatst u het einde van de pijl van de eerste activiteit naar de volgende activiteit totdat ze verbinding maken. U kunt de activiteit naar het punt van de pijl achter het bewegen om het aan de voorafgaande activiteit te verbinden. Als u een van de activiteiten verplaatst, blijven deze gekoppeld.

Overgangen na activiteiten die gegevens verwerken, bevatten de intermediaire populaties. U hebt toegang tot de **[!UICONTROL Keep interim results]** in de **[!UICONTROL Execution]** van de workfloweigenschappen.

>[!CAUTION]
>
>Deze optie verbruikt veel schijfruimte en is ontworpen om u te helpen een workflow te maken en een correcte configuratie en functionaliteit te garanderen. Laat deze optie uitgeschakeld op productie-instanties.


Wanneer een activiteit wordt geselecteerd, verschijnen de snelle acties rond de activiteit, toestaand u om met het in wisselwerking te staan. Als u bijvoorbeeld een activiteit wilt configureren, selecteert u deze en opent u deze met de opdracht ![](assets/edit_darkgrey-24px_table.png) in de snelle handelingen.

Bepaalde functies zijn alleen beschikbaar in de werkruimte:

* Selecteer verschillende activiteiten en overgangen door er een zone omheen te tekenen.
* Druk **Ctrl** + klik met de linkermuisknop om meerdere activiteiten en/of overgangen te selecteren.
* Druk **Enter** om de details van de momenteel geselecteerde activiteit of overgang weer te geven.
* Druk **Verwijderen** om de geselecteerde activiteit te verwijderen.
* Druk **Ctrl + C** de geselecteerde activiteiten te kopiëren, en **Ctrl + V** plakken in de werkruimte.

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

<img height="21px" src="assets/wkf_dlv_act_params_icon.png" /> **[!UICONTROL Open the activity's advanced options]**<br/>Hiermee opent u de geavanceerde opties voor de geselecteerde e-mail- of sms-leveringsactiviteit.

<img height="21px" src="assets/check_darkgrey-24px_table.png" /> **[!UICONTROL Normal execution]**<br/>Hiermee wordt de selectie opnieuw ingeschakeld als deze eerder is uitgeschakeld of gemarkeerd als gepauzeerd.

<img height="21px" src="assets/check_pause_darkgrey-24px_table.png" /> **[!UICONTROL Execution suspended]**<br/>Hiermee onderbreekt u de workflow bij de geselecteerde activiteit.

<img height="21px" src="assets/checkdisable.png" /> **[!UICONTROL No execution]**<br/>Hiermee wordt de activiteit uitgeschakeld.

<img height="21px" src="assets/pending_darkgrey-24px_table.png" /> **[!UICONTROL Immediate execution]**<br/>Hiermee wordt de selectie onmiddellijk verwerkt. Deze knop is alleen beschikbaar voor de <span class="uicontrol">Planner</span> en <span class="uicontrol">Wachten</span> activiteiten.

<img height="21px" src="assets/delete_darkgrey-24px_table.png" /> **[!UICONTROL Delete selection]**<br/>Hiermee verwijdert u de geselecteerde activiteiten.

## Dupliceren van workflowactiviteiten {#duplicating-workflow-activities}

Met de werkruimte kunt u workflowactiviteiten dupliceren door deze naar dezelfde workflow te kopiëren en te plakken, of naar een andere workflow vanuit dezelfde Campagne-instantie.

Zodra een activiteit wordt gedupliceerd, wordt zijn volledige configuratie gehouden. Voor leveringsactiviteiten (e-mail, SMS, pushmelding...) wordt het leveringsobject dat aan de activiteit is gekoppeld, gedupliceerd.

>[!NOTE]
>
>Workflowactiviteiten kunnen niet van een instantie naar een andere worden gedupliceerd. Activiteiten uit technische werkstromen kunnen niet worden gedupliceerd.

Voer de volgende stappen uit om een activiteit te dupliceren:

1. Selecteer de activiteit en klik op de knop **[!UICONTROL Copy selection]** uit de snelle handelingen.

   U kunt ook de opdracht **Ctrl + C** sneltoets.

   ![](assets/wkf_copypaste1.png)

1. Klik met de rechtermuisknop in de werkruimte van de doelworkflow en klik vervolgens op de knop **[!UICONTROL Paste]** knop.

   U kunt ook de opdracht **CTRL + V** sneltoets.

   ![](assets/wkf_copypaste2.png)

1. De activiteit wordt gedupliceerd, met alle montages die aanvankelijk zijn gevormd.

Het is ook mogelijk om veelvoudige activiteiten te kopiëren-kleven, toelatend u om een volledige werkstroom te dupliceren.

U doet dit door de activiteiten te selecteren door er een zone omheen te tekenen. Klik vervolgens op de knop **[!UICONTROL Copy selection]** van de actiebalk (of druk op **Ctrl + C**). U kunt ze vervolgens op de gewenste locatie plakken.

![](assets/wkf_copypaste3.png)
