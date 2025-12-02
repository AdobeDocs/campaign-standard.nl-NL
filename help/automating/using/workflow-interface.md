---
title: Workflowinterface
description: Leer de interface en opties voor het maken, bewerken en uitvoeren van een workflow.
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
context-tags: workflow,main;workflow,overview
feature: Workflows
old-role: Data Architect
role: Developer
level: Beginner
exl-id: a3f35bb9-e61e-4f3f-b855-1d677422f75a
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '829'
ht-degree: 4%

---

# Workflowinterface{#workflow-interface}

U kunt workflows maken om volledige processen in uw campagnes en programma&#39;s te beheren.

Het werkstroombewerkingsscherm bestaat uit de volgende elementen:

* Het [&#x200B; Palet &#x200B;](#palette), dat verwijzingen de beschikbare activiteiten.
* [&#x200B; Workspace &#x200B;](#workspace), waarin de activiteiten worden gevormd en georganiseerd.
* De [&#x200B; bar van de Actie &#x200B;](#action-bar), die uit knopen wordt samengesteld die u toestaan om met het werkschema en/of zijn componenten in wisselwerking te staan.
* De [&#x200B; Snelle acties &#x200B;](#quick-actions), die rond een geselecteerde activiteit verschijnen, staan u toe om met het in wisselwerking te staan.

![](assets/wkf_overview.png)

![](assets/do-not-localize/how-to-video.png) [&#x200B; ontdekt hoe te om een werkschema in video &#x200B;](#video) te bouwen

## Palet {#palette}

Het palet bevindt zich aan de linkerkant van het scherm. Alle beschikbare activiteiten worden ingedeeld in verschillende categorieën:

* [&#x200B; het richten &#x200B;](../../automating/using/about-targeting-activities.md): activiteiten specifiek voor het richten, het manipuleren van populatiegegevens, en het filtreren activiteiten
* [&#x200B; Uitvoering &#x200B;](../../automating/using/about-execution-activities.md): activiteiten specifiek voor het organiseren van en het uitvoeren van werkschema&#39;s
* [&#x200B; Kanalen &#x200B;](../../automating/using/about-channel-activities.md): activiteiten die de verschillende beschikbare communicatiekanalen vertegenwoordigen
* [&#x200B; Beheer van Gegevens (ETL) &#x200B;](../../automating/using/about-data-management-activities.md): activiteiten specifiek voor het manipuleren van gegevens

Als u een activiteit wilt gebruiken vanuit het palet in uw workflow, sleept u deze naar de werkruimte.

U moet elke activiteit vormen die vanaf het palet wordt toegevoegd alvorens het werkschema te beginnen.

![](assets/workflow_palette.png)

## Workspace {#workspace}

De werkruimte is de centrale zone in de werkstroomeditor. Het is in deze streek dat u uw activiteiten kunt laten vallen, hen verbinden samen gebruikend overgangen, en hen vormen.

Als u twee activiteiten wilt koppelen, verplaatst u het einde van de pijl van de eerste activiteit naar de volgende activiteit totdat ze verbinding maken. U kunt de activiteit naar het punt van de pijl achter het bewegen om het aan de voorafgaande activiteit te verbinden. Als u een van de activiteiten verplaatst, blijven deze gekoppeld.

Overgangen na activiteiten die gegevens verwerken, bevatten de intermediaire populaties. U kunt ze openen door de optie **[!UICONTROL Keep interim results]** in het gedeelte **[!UICONTROL Execution]** van de workfloweigenschappen te selecteren.

>[!CAUTION]
>
>Deze optie verbruikt veel schijfruimte en is ontworpen om u te helpen een workflow te maken en een correcte configuratie en functionaliteit te garanderen. Laat deze optie uitgeschakeld op productie-instanties.


Wanneer een activiteit wordt geselecteerd, verschijnen de snelle acties rond de activiteit, toestaand u om met het in wisselwerking te staan. Als u bijvoorbeeld een activiteit wilt configureren, selecteert u deze en opent u deze vervolgens met de knop ![](assets/edit_darkgrey-24px_table.png) in de snelle handelingen.

Bepaalde functies zijn alleen beschikbaar in de werkruimte:

* Selecteer verschillende activiteiten en overgangen door er een zone omheen te tekenen.
* Pers **CTRL** + linkerklik om verscheidene activiteiten en/of overgangen te selecteren.
* Pers **gaat** binnen om het detail van de momenteel geselecteerde activiteit of overgang te bekijken.
* Pers **Schrapping** om de momenteel geselecteerde activiteit te schrappen.
* Pers **CTRL + C** om de geselecteerde activiteiten te kopiëren, en **CTRL + V** om hen in de werkruimte te kleven.

![](assets/workflow_workspace.png)

## Actiebalk {#action-bar}

Afhankelijk van de elementen die zijn geselecteerd in de werkruimte of de uitvoeringsstatus van de workflow, kunnen de knoppen in de actiebalk afwijken.

<img height="21px" src="assets/edit_darkgrey-24px.png" /> **[!UICONTROL Open activity]**<br/>staat u toe om de eigenschappen van het werkschema uit te geven.

<img height="21px" src="assets/play_darkgrey-24px_table.png" /> **[!UICONTROL Start]**<br/>begint het werkschema.

<img height="21px" src="assets/pause_darkgrey-24px_table.png" /> **[!UICONTROL Pause]**<br/>pauzeert het werkschema.

<img height="21px" src="assets/stop_darkgrey-24px_table.png" /> **[!UICONTROL Stop]**<br/>onderbreekt werkschemauitvoering. Kan niet worden hervat vanwaar het werd gestopt.

<img height="21px" src="assets/pauseplay_darkgrey-24px_table.png" /> **[!UICONTROL Restart]**<br/>herstart het werkschema.

<img height="21px" src="assets/printpreview_darkgrey-24px_table.png" /> **[!UICONTROL Log and tasks]**<br/>opent het de uitvoeringslogboek van het werkschema.

<img height="21px" src="assets/checkcircle_darkgrey-24px_table.png" /> **[!UICONTROL Enable multi-selection]**<br/>laat multi-selectiemodus toe. De workflow moet uit ten minste twee activiteiten bestaan.

<img height="21px" src="assets/closecircle_darkgrey-24px_table.png" /> **[!UICONTROL Disable multi-selection]**<br/>maakt multi-selectiemodus onbruikbaar.<br />

<img height="21px" src="assets/targeted.png" /> **[!UICONTROL Open transition]**<br/>opent de geselecteerde overgang.<br />

<img height="21px" src="assets/check_darkgrey-24px_table.png" />  **[!UICONTROL Normal execution]**<br/>laat selectie opnieuw toe als het eerder onbruikbaar gemaakt of zoals gepauzeerd is geweest.<br />

<img height="21px" src="assets/check_pause_darkgrey-24px_table.png" /> **[!UICONTROL Execution suspended]**<br/>pauzeert het werkschema bij de geselecteerde activiteit.<br />

<img height="21px" src="assets/checkdisable.png" /> **[!UICONTROL No execution]**<br/>maakt de activiteit onbruikbaar.<br />

<img height="21px" src="assets/delete_darkgrey-24px_table.png" /> **[!UICONTROL Delete selection]**<br/>schrapt de activiteiten die worden geselecteerd.<br />

<img height="21px" src="assets/copy_24px.png" /> **[!UICONTROL Copy selection]**<br/>kopieert de activiteiten die worden geselecteerd.

<img height="21px" src="assets/paste_24px.png" /> **[!UICONTROL Paste]**<br/>kleeft de activiteiten die zijn gekopieerd.

## Snelle acties {#quick-actions}

Wanneer een activiteit wordt geselecteerd, verschijnen de snelle actieknopen rond de activiteit, die u toestaat om met het in wisselwerking te staan.

<img height="21px" src="assets/edit_darkgrey-24px.png" /> **[!UICONTROL Open activity]**<br/>opent de geselecteerde activiteit.

<img height="21px" src="assets/copy_24px.png" /> **[!UICONTROL Copy selection]**<br/>kopieert de geselecteerde activiteit.

<img height="21px" src="assets/wkf_dlv_act_params_icon.png" /> **[!UICONTROL Open the activity's advanced options]**<br/>opent de geavanceerde opties van de geselecteerde e-mail of de leveringsactiviteit van SMS.

<img height="21px" src="assets/check_darkgrey-24px_table.png" /> **[!UICONTROL Normal execution]**<br/>laat selectie opnieuw toe als het eerder onbruikbaar gemaakt of zoals gepauzeerd is geweest.

<img height="21px" src="assets/check_pause_darkgrey-24px_table.png" /> **[!UICONTROL Execution suspended]**<br/>pauzeert het werkschema bij de geselecteerde activiteit.

<img height="21px" src="assets/checkdisable.png" /> **[!UICONTROL No execution]**<br/>maakt de activiteit onbruikbaar.

<img height="21px" src="assets/pending_darkgrey-24px_table.png" /> **[!UICONTROL Immediate execution]**<br/>dwingt directe verwerking van de selectie. Deze knoop is slechts beschikbaar voor de <span class="uicontrol"> Planner </span> en <span class="uicontrol"> wacht </span> activiteiten.

<img height="21px" src="assets/delete_darkgrey-24px_table.png" /> **[!UICONTROL Delete selection]**<br/>schrapt de activiteiten die worden geselecteerd.

## Dupliceren van workflowactiviteiten {#duplicating-workflow-activities}

Met de werkruimte kunt u workflowactiviteiten dupliceren door deze naar dezelfde workflow te kopiëren en te plakken, of naar een andere workflow vanuit dezelfde Campagne-instantie.

Zodra een activiteit wordt gedupliceerd, wordt zijn volledige configuratie gehouden. Voor leveringsactiviteiten (e-mail, SMS, pushmelding...) wordt het leveringsobject dat aan de activiteit is gekoppeld, gedupliceerd.

>[!NOTE]
>
>Workflowactiviteiten kunnen niet van een instantie naar een andere worden gedupliceerd. Activiteiten uit technische werkstromen kunnen niet worden gedupliceerd.

Voer de volgende stappen uit om een activiteit te dupliceren:

1. Selecteer de activiteit, dan klik de **[!UICONTROL Copy selection]** knoop van de snelle acties.

   U kunt **CTRL + C** toetsenbordkortere weg ook gebruiken.

   ![](assets/wkf_copypaste1.png)

1. Klik met de rechtermuisknop in de werkruimte van de doelworkflow en klik vervolgens op de knop **[!UICONTROL Paste]** .

   U kunt **CTRL + V** toetsenbordkortere weg ook gebruiken.

   ![](assets/wkf_copypaste2.png)

1. De activiteit wordt gedupliceerd, met alle montages die aanvankelijk zijn gevormd.

Het is ook mogelijk om veelvoudige activiteiten te kopiëren-kleven, toelatend u om een volledige werkstroom te dupliceren.

U doet dit door de activiteiten te selecteren door er een zone omheen te tekenen. dan klik de **[!UICONTROL Copy selection]** knoop van de actiebar (of druk **CTRL + C**). U kunt ze vervolgens op de gewenste locatie plakken.

![](assets/wkf_copypaste3.png)

## Video over zelfstudie {#video}

In deze video wordt getoond hoe u een workflow kunt maken.

>[!VIDEO](https://video.tv.adobe.com/v/23937?quality=12)

De extra hoe te video&#39;s van Campaign Standard zijn beschikbaar [&#x200B; hier &#x200B;](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=nl).
