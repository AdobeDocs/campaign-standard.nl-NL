---
solution: Campaign Standard
product: campaign
title: E-maillevering
description: Met de activiteit E-maillevering kunt u het verzenden van één e-mail of een terugkerende e-mail in een workflow configureren.
audience: automating
content-type: reference
topic-tags: channel-activities
context-tags: delivery,workflow,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '857'
ht-degree: 94%

---


# E-maillevering{#email-delivery}

## Beschrijving {#description}

![](assets/email.png)

![](assets/recurrentemail.png)

Met de activiteit **[!UICONTROL Email delivery]** kunt u het verzenden van een e-mail configureren in een workflow. Dit kan een **enkelvoudige e-mail** zijn die slechts één keer wordt verzonden, of het kan een **terugkerende** e-mail zijn.

E-mails voor enkelvoudige verzending zijn standaard e-mails die eenmaal worden verzonden.

Met terugkerende e-mails kunt u dezelfde e-mail meerdere malen naar verschillende doelen sturen gedurende een bepaalde periode. U kunt de leveringen per periode samenvoegen om rapporten te verkrijgen die aan uw behoeften voldoen.

## Gebruikscontext {#context-of-use}

De activiteit **[!UICONTROL Email delivery]** wordt over het algemeen gebruikt voor het automatiseren van het verzenden van een e-mail naar een doel dat in dezelfde workflow wordt berekend.

Indien gekoppeld aan een planner, kunt u terugkerende e-mails definiëren.

E-mailontvangers worden stroomopwaarts van de activiteit in dezelfde workflow gedefinieerd via targetingactiviteiten zoals query&#39;s, doorsnedes, enz.

De berichtvoorbereiding wordt geactiveerd op basis van de uitvoeringsparameters van de workflow. Op het berichtdashboard kunt u kiezen of u al dan niet handmatig wilt bevestigen of u het bericht wilt versturen (standaard vereist). U kunt de workflow handmatig starten of een planneractiviteit in de workflow plaatsen om de uitvoering te automatiseren.

**Verwante onderwerpen:**

* [Gebruiksscenario: Eenmaal per week een e-maillevering maken](../../automating/using/workflow-weekly-offer.md)
* [Gebruiksscenario: Een levering maken die is gesegmenteerd op locatie](../../automating/using/workflow-segmentation-location.md)
* [Gebruiksscenario: Leveringen maken met een aanvulling](../../automating/using/workflow-created-query-with-complement.md)
* [Gebruiksscenario: Retargeting van een workflow om een nieuwe levering te zenden naar personen die het bericht niet hebben geopend](../../automating/using/workflow-cross-channel-retargeting.md)
* [Hoofdlettergebruik: Geboortedatum](../../automating/using/birthday-delivery.md)

## Configuratie {#configuration}

1. Sleep een activiteit **[!UICONTROL Email delivery]** en zet deze neer in uw workflow.
1. Selecteer de activiteit en open deze met de knop ![](assets/edit_darkgrey-24px.png) vanuit de snelle acties die verschijnen.

   >[!NOTE]
   >
   >U kunt de algemene eigenschappen en geavanceerde opties van de activiteit (niet van de levering zelf) raadplegen via de knop ![](assets/dlv_activity_params-24px.png) van de snelle acties van de activiteit. Deze knop is specifiek voor de activiteit **[!UICONTROL Email delivery]**. De eigenschappen van de e-mail zijn toegankelijk via de actiebalk in het e-maildashboard.

1. Selecteer de modus voor het verzenden van e-mail:

   * **[!UICONTROL Email]**: het e-mailbericht wordt één keer verzonden. U kunt hier opgeven of u al dan niet een uitgaande overgang aan de activiteit wilt toevoegen. De verschillende overgangstypen worden beschreven in stap 7 van deze procedure.
   * **[!UICONTROL Recurring email]**: De e-mail wordt verscheidene keren verzonden, volgens de frequentie die in een activiteit **[!UICONTROL Scheduler]** wordt bepaald. Selecteer de aggregatieperiode van de verzendingen. Zo kunt u alle verzendingen die tijdens de vastgestelde periode plaatsvinden hergroeperen in één enkele e-mail die ook wel **Periodieke uitvoering** wordt genoemd en die toegankelijk is via de lijst met marketingactiviteiten van de applicatie.

      Voor een terugkerende verjaardagsmail, die dagelijks wordt verstuurd, kunt u er bijvoorbeeld voor kiezen om de verzendingen per maand samen te voegen. Op deze manier kunt u maandelijks rapporten over uw levering ontvangen, hoewel de e-mail elke dag wordt verzonden.
   >[!NOTE]
   >
   >Terugkerende leveringen worden voorbereid op basis van de **aggregatieperiode**. Als de samenvoegingsperiode bijvoorbeeld &quot;op dag&quot; is, wordt de levering slechts eenmaal per dag opnieuw voorbereid. Als u deze workflow meerdere keren per dag wilt aanroepen, gebruikt u [!UICONTROL No aggregation].

1. Selecteer een e-mailtype. De e-mailtypen zijn afkomstig van e-mailsjablonen die u hebt gedefinieerd in het menu **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**.
1. Voer de algemene eigenschappen voor de e-mail in. U kunt deze ook koppelen aan een bestaande campagne. Het label van de leveringsactiviteit van de workflow wordt bijgewerkt met het e-maillabel.
1. Geef de e-mailcontent op. Raadpleeg de sectie over het [bewerken van content](../../designing/using/designing-content-in-adobe-campaign.md).
1. Standaard bevat de activiteit **[!UICONTROL Email delivery]** geen uitgaande overgangen. Als u een uitgaande overgang wilt toevoegen aan uw activiteit **[!UICONTROL Email delivery]**, ga dan naar het tabblad **[!UICONTROL General]** van de geavanceerde opties voor activiteiten (de knop ![](assets/dlv_activity_params-24px.png) in de snelle acties van de activiteit) en vink een van de volgende opties aan:

   * **[!UICONTROL Add outbound transition without the population]**: Zo kunt u een uitgaande overgang genereren die exact dezelfde populatie bevat als de binnenkomende overgang.
   * **[!UICONTROL Add outbound transition with the population]**: Zo kunt u een uitgaande overgang genereren met de populatie naar wie de e-mail is gestuurd. De leden van het doel die tijdens de voorbereiding van de levering waren uitgesloten (quarantaine, ongeldige e-mail, enz.),  zijn uitgesloten van deze overgang.

1. Bevestig de configuratie van uw activiteit en sla de workflow op.

Als u de activiteit opnieuw opent, wordt het e-maildashboard meteen weergegeven. Alleen de content kan worden bewerkt.

Standaard wordt bij het starten van een leveringsworkflow alleen de berichtvoorbereiding geactiveerd. Het verzenden van berichten die op basis van een workflow zijn gemaakt, moet nog worden bevestigd nadat de workflow is gestart. U kunt echter vanaf het berichtdashboard de optie **[!UICONTROL Request confirmation before sending messages]** uitschakelen, maar alleen als het bericht vanuit een workflow is gemaakt. Als u deze optie uitschakelt, worden berichten zonder verdere kennisgeving verzonden zodra de voorbereiding is voltooid.

## Opmerkingen {#remarks}

De leveringen die in een workflow zijn gemaakt, zijn toegankelijk in de lijst met marketingactiviteiten van de applicatie. U kunt de uitvoeringsstatus van de workflow weergeven via het dashboard. Via koppelingen in het overzichtsvenster voor e-mail hebt u rechtstreeks toegang tot gekoppelde elementen (workflow, campagne, bovenliggende levering in het geval van een terugkerende e-mail).

![](assets/wkf_display_recurrent_executions_2.png)

De uitvoeringen van terugkerende leveringen worden echter standaard gemaskeerd. U kunt deze weergeven door de optie **[!UICONTROL Show recurring executions]** in het zoekvenster voor marketingactiviteiten te selecteren.

![](assets/wkf_display_recurrent_executions.png)

In de bovenliggende leveringen, die toegankelijk zijn via de lijst met marketingactiviteiten of rechtstreeks via de bijbehorende periodieke uitvoeringen, kunt u het totale aantal verzendingen bekijken die zijn verwerkt (volgens de aggregatieperiode die is opgegeven toen de activiteit **[!UICONTROL Email delivery]** werd geconfigureerd). U doet dit door de detailweergave van het blok **[!UICONTROL Deployment]** van de bovenliggende levering te openen door ![](assets/wkf_dlv_detail_button.png) te selecteren.

![](assets/wkf_display_recurrent_executions_3.png)
