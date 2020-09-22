---
title: Sms-levering
description: Met de activiteit Sms-levering kunt u het verzenden van één sms of een terugkerende sms in een workflow configureren.
page-status-flag: never-activated
uuid: 736078c6-ac91-4440-825b-4a6ae31894ef
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: channel-activities
discoiquuid: 978592b8-989a-446a-8a84-12b7fecfc130
context-tags: sms,main;delivery,smsContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: eac45f6e5491703a39c19a4787be6f285e841e14
workflow-type: tm+mt
source-wordcount: '784'
ht-degree: 100%

---


# Sms-levering{#sms-delivery}

## Beschrijving {#description}

![](assets/sms.png)

![](assets/recurrentsms.png)

Met de activiteit **[!UICONTROL SMS delivery]** kunt u het verzenden van een sms in een workflow configureren. Dit kan het eenmalig verzenden van één sms zijn of het kan een terugkerende sms zijn.

* **Sms-berichten voor eenmalige verzending zijn standaard sms-berichten die één keer worden verzonden.**
* **Met terugkerende sms-berichten kunt u dezelfde sms meerdere keren naar verschillende doelen verzenden over een bepaalde periode.** U kunt de leveringen per periode samenvoegen om rapporten te krijgen die voldoen aan uw behoeften.

## Gebruikscontext {#context-of-use}

De activiteit **[!UICONTROL SMS delivery]** wordt over het algemeen gebruikt voor de configuratie van het verzenden van een sms naar een doel dat in dezelfde workflow wordt berekend.

Wanneer dit verbonden is met een planner, kunt u terugkerende sms-berichten definiëren.

De sms-ontvangers worden stroomopwaarts van de activiteit in dezelfde workflow bepaald via targetingactiviteiten zoals query&#39;s, doorsneden, enzovoort.

De voorbereiding van berichten wordt geactiveerd volgens de parameters voor workflowuitvoering. Op het berichtdashboard kunt u kiezen of u al dan niet handmatig wilt bevestigen of u het bericht wilt versturen (standaard vereist). U kunt de workflow handmatig starten of een planneractiviteit in de workflow plaatsen om de uitvoering te automatiseren.

## Configuratie {#configuration}

1. Sleep een activiteit **[!UICONTROL SMS delivery]** en zet deze neer in uw workflow.
1. Selecteer de activiteit en open deze met de knop ![](assets/edit_darkgrey-24px.png) vanuit de snelle acties die verschijnen.

   >[!NOTE]
   >
   >U kunt de algemene eigenschappen en geavanceerde opties van de activiteit (en niet van de levering zelf) openen via de knop ![](assets/dlv_activity_params-24px.png) in de actiebalk van de workflow. Deze knop is specifiek voor de activiteit **[!UICONTROL SMS delivery]**. De sms-eigenschappen kunnen via de actiebalk in het sms-dashboard worden geopend.

1. Selecteer de sms-verzendmodus:

   * **[!UICONTROL SMS]**: De sms wordt één keer verzonden. U kunt hier opgeven of u al dan niet een uitgaande overgang aan de activiteit wilt toevoegen. De verschillende overgangstypen worden beschreven in stap 7 van deze procedure.
   * **[!UICONTROL Recurring SMS]**: De sms wordt verscheidene keren verzonden, volgens de frequentie die in een activiteit **[!UICONTROL Scheduler]** is bepaald. Selecteer de aggregatieperiode van de verzendingen. Zo kunt u alle verzendingen die tijdens de gedefinieerde periode plaatsvinden, hergroeperen in één enkele weergave die ook wel **Periodieke uitvoering** wordt genoemd en via de lijst met marketingactiviteiten van de applicatie kan worden geopend.

      Voor een terugkerende verjaardags-sms die dagelijks wordt verzonden, kunt u er bijvoorbeeld voor kiezen om de verzendingen per maand samen te voegen. Op deze manier ontvangt u maandelijks rapporten over uw levering, hoewel de sms elke dag wordt verzonden.

1. Selecteer een sms-type. De sms-typen zijn afkomstig van sms-sjablonen die zijn gedefinieerd in het menu **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**.
1. Voer de algemene eigenschappen van de sms in. U kunt deze ook aan een bestaande campagne koppelen. Het label van de leveringsactiviteit van de workflow wordt bijgewerkt met het sms-label.
1. Definieer de content van de sms. Raadpleeg de sectie over het [maken van een sms-bericht](../../channels/using/creating-an-sms-message.md).
1. Standaard bevat de activiteit **[!UICONTROL SMS delivery]** geen uitgaande overgangen. Als u een uitgaande overgang wilt toevoegen aan uw activiteit **[!UICONTROL SMS delivery]**, ga dan naar het tabblad **[!UICONTROL General]** van de geavanceerde opties voor activiteiten (de knop ![](assets/dlv_activity_params-24px.png) in de snelle acties van de activiteit) en vink een van de volgende opties aan:

   * **[!UICONTROL Add outbound transition without the population]**: Hiermee kunt u een uitgaande overgang genereren die exact dezelfde populatie als de binnenkomende overgang bevat.
   * **[!UICONTROL Add outbound transition with the population]**: Hiermee kunt u een uitgaande overgang genereren die de populatie bevat aan wie de sms is verzonden. De leden van de doelgroep die tijdens de voorbereiding van de levering werden uitgesloten (quarantaine, ongeldig nummer, enzovoort) zijn uitgesloten van deze overgang.

1. Bevestig de configuratie van uw activiteit en sla de workflow op.

Wanneer u de activiteit opnieuw opent, wordt u rechtstreeks naar het sms-dashboard geleid. Alleen de content kan worden bewerkt.

Standaard wordt bij het starten van een leveringsworkflow alleen de berichtvoorbereiding geactiveerd. Het verzenden van berichten die op basis van een workflow zijn gemaakt, moet nog worden bevestigd nadat de workflow is gestart. U kunt echter vanaf het berichtdashboard de optie **[!UICONTROL Request confirmation before sending messages]** uitschakelen, maar alleen als het bericht vanuit een workflow is gemaakt. Als u deze optie uitschakelt, worden berichten zonder verdere kennisgeving verzonden zodra de voorbereiding is voltooid.

## Opmerkingen {#remarks}

De leveringen die in een workflow zijn gemaakt, zijn toegankelijk in de lijst met marketingactiviteiten van de applicatie. U kunt de uitvoeringsstatus van de workflow bekijken via het dashboard. Met de koppelingen in het sms-overzichtsvenster hebt u rechtstreeks toegang tot gekoppelde elementen (workflow, campagne, bovenliggende levering in het geval van een terugkerende sms).

De uitvoeringen van terugkerende leveringen worden echter standaard gemaskeerd. U kunt deze weergeven door de optie **[!UICONTROL Show recurring executions]** in het zoekvenster voor marketingactiviteiten te selecteren.

In de bovenliggende leveringen, die toegankelijk zijn via de lijst met marketingactiviteiten of rechtstreeks via de bijbehorende periodieke uitvoeringen, kunt u het totale aantal verzendingen bekijken die zijn verwerkt (volgens de aggregatieperiode die is opgegeven toen de activiteit **[!UICONTROL SMS delivery]** werd geconfigureerd). U doet dit door de detailweergave van het blok **[!UICONTROL Deployment]** van de bovenliggende levering te openen door ![](assets/wkf_dlv_detail_button.png) te selecteren.
