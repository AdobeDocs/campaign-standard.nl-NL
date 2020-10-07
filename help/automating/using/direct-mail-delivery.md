---
title: Direct-maillevering
description: Met de activiteit Direct-maillevering kunt u het verzenden van één e-mail of een terugkerende e-mail in een workflow configureren.
page-status-flag: never-activated
uuid: bfa7b176-a17c-4079-a073-64b8ce4788ed
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: channel-activities
discoiquuid: b9ddb2a0-54ff-4ada-be6f-8109fa06d461
context-tags: directMail,workflow,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '914'
ht-degree: 99%

---


# Direct-maillevering{#direct-mail-delivery}

## Beschrijving {#description}

![](assets/paper.png)

![](assets/recurrentpaper.png)

Met de activiteit **[!UICONTROL Direct mail delivery]** kunt u een bestand configureren en voorbereiden met profieldata die u wilt gebruiken voor een direct-mailcampagne. Dit kan een direct mail zijn die slechts eenmaal wordt gebruikt, of het kan een terugkerende direct mail zijn.

* **Standaard direct mails worden één keer verzonden.**
* **Met terugkerende mails kunt u dezelfde direct mail meerdere malen naar verschillende targets sturen gedurende een bepaalde periode.** U kunt de leveringen per periode samenvoegen om rapporten te krijgen die voldoen aan uw behoeften.

## Gebruikscontext {#context-of-use}

De activiteit **[!UICONTROL Direct mail delivery]** wordt over het algemeen gebruikt om de voorbereiding van een bestand met profieldata te automatiseren. Dit bestand kan vervolgens worden verzonden naar een partner/provider die verantwoordelijk is voor de mailing.

Indien gekoppeld aan een planner, kunt u terugkerende direct mails definiëren.

De ontvangers van direct mail worden stroomopwaarts van de activiteit in dezelfde workflow gedefinieerd via targetingactiviteiten zoals query&#39;s, doorsnedes, enz. Profielen waarvan het mailadres niet is opgegeven, worden automatisch uitgesloten wanneer de direct mail wordt voorbereid.

De berichtvoorbereiding wordt geactiveerd op basis van de uitvoeringsparameters van de workflow. Op het berichtdashboard kunt u kiezen of u al dan niet handmatig wilt bevestigen of u het bericht wilt versturen (standaard vereist). U kunt de workflow handmatig starten of een planneractiviteit in de workflow plaatsen om de uitvoering te automatiseren.

**Verwante onderwerpen:**

* [Hoofdlettergebruik: Koppeling van e-mail- en direct-mailleveringen](../../automating/using/coupling-email-direct-mail.md)
* [Informatie over direct mail](../../channels/using/about-direct-mail.md)

## Configuratie {#configuration}

1. Sleep een activiteit **[!UICONTROL Direct mail delivery]** en zet deze neer in uw workflow.
1. Selecteer de activiteit en open deze met de knop ![](assets/edit_darkgrey-24px.png) vanuit de snelle acties die verschijnen.

   >[!NOTE]
   >
   >U kunt de algemene eigenschappen en geavanceerde opties van de activiteit (niet van de levering zelf) raadplegen via de knop ![](assets/dlv_activity_params-24px.png) van de snelle acties van de activiteit. Deze knop is specifiek voor de kanaalactiviteiten. De eigenschappen van de direct mail zijn toegankelijk via de actiebalk in het direct mail-dashboard.

1. Selecteer de verzendmodus voor de direct mail:

   * **[!UICONTROL Direct mail]**: De direct mail wordt één keer verzonden. U kunt hier opgeven of u al dan niet een uitgaande overgang aan de activiteit wilt toevoegen. De verschillende overgangstypen worden beschreven in stap 7 van deze procedure.
   * **[!UICONTROL Recurring direct mail]**: De direct-mail wordt verscheidene keren verzonden, volgens de frequentie die in een activiteit **[!UICONTROL Scheduler]** wordt bepaald. Selecteer de aggregatieperiode van de verzendingen. Zo kunt u alle verzendingen die tijdens de vastgestelde periode plaatsvinden hergroeperen in één direct mail die ook wel **Periodieke uitvoering** wordt genoemd en die toegankelijk is via de lijst met marketingactiviteiten van de applicatie.

      Voor een terugkerende verjaardagsmail, die dagelijks wordt verwerkt, kunt u er bijvoorbeeld voor kiezen om de verzendingen per maand samen te voegen. Op deze manier kunt u maandelijks rapporten over uw levering ontvangen, hoewel de e-mail elke dag wordt verwerkt.

      >[!NOTE]
      >
      >Voor terugkerende direct mails wordt bij elke uitvoering van de workflow een nieuw bestand gegenereerd. De geselecteerde aggregatieperiode heeft geen invloed op dit gedrag.

1. Selecteer een type direct mail. De typen direct mail zijn afkomstig van sjablonen die u hebt gedefinieerd in het menu **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**.
1. Voer de algemene eigenschappen voor de direct mail in. U kunt deze ook koppelen aan een bestaande campagne. Het label van de leveringsactiviteit van de workflow wordt bijgewerkt met het direct-maillabel.
1. Definieer de content van de direct mail. Raadpleeg de sectie over het [bewerken van content](../../designing/using/personalization.md).
1. Standaard bevat de activiteit **[!UICONTROL Direct mail delivery]** geen uitgaande overgangen. Als u een uitgaande overgang wilt toevoegen aan uw activiteit **[!UICONTROL Direct mail delivery]**, ga dan naar het tabblad **[!UICONTROL General]** van de geavanceerde opties voor activiteiten (de knop ![](assets/dlv_activity_params-24px.png) in de snelle acties van de activiteit) en vink een van de volgende opties aan:

   * **[!UICONTROL Add outbound transition without the population]**: Zo kunt u een uitgaande overgang genereren die exact dezelfde populatie bevat als de binnenkomende overgang. Deze overgang bevat het bestand dat door de direct-mailactiviteit wordt gegenereerd en de onbewerkte populatie die door de direct-mailactiviteit is ontvangen.
   * **[!UICONTROL Add outbound transition with the population]**: Zo kunt u een uitgaande overgang genereren met de populatie naar wie de direct mail wordt gestuurd. De leden van het doel die tijdens de voorbereiding van de direct mail waren uitgesloten (quarantaine, ongeldige e-mail, enz.), zijn uitgesloten van deze overgang. De overgang bevat ook het bestand dat door de direct mail wordt gegenereerd.

1. Bevestig de configuratie van uw activiteit en sla de workflow op.

Als u de activiteit opnieuw opent, wordt het direct-maildashboard meteen weergegeven. Alleen de content kan worden bewerkt.

Standaard wordt bij het starten van een leveringsworkflow alleen de berichtvoorbereiding geactiveerd. Het verzenden van berichten die op basis van een workflow zijn gemaakt, moet nog worden bevestigd nadat de workflow is gestart. U kunt echter vanaf het berichtdashboard de optie **[!UICONTROL Request confirmation before sending messages]** uitschakelen, maar alleen als het bericht vanuit een workflow is gemaakt. Als u deze optie uitschakelt, worden berichten zonder verdere kennisgeving verzonden zodra de voorbereiding is voltooid.

## Opmerkingen {#remarks}

De leveringen die in een workflow zijn gemaakt, zijn toegankelijk in de lijst met marketingactiviteiten van de applicatie. U kunt de uitvoeringsstatus van de workflow weergeven via het dashboard. Via koppelingen in het overzichtsvenster voor direct mail hebt u rechtstreeks toegang tot gekoppelde elementen (workflow, campagne, bovenliggende levering in het geval van een terugkerende direct mail).

![](assets/wkf_display_parent_elements_direct_mail.png)

De uitvoering van terugkerende leveringen wordt standaard gemaskeerd. U kunt deze weergeven door de optie **[!UICONTROL Show recurring executions]** in het zoekvenster voor marketingactiviteiten te selecteren.

![](assets/wkf_display_recurrent_executions_direct_mail.png)

In de bovenliggende leveringen, die toegankelijk zijn vanuit de lijst met marketingactiviteiten of rechtstreeks via de bijbehorende periodieke uitvoeringen, kunt u het totale aantal mails bekijken dat is verwerkt (volgens de aggregatieperiode die bij de configuratie van de activiteit **[!UICONTROL Direct mail delivery]** is opgegeven.). U doet dit door de detailweergave van het blok **[!UICONTROL Deployment]** van de bovenliggende levering te openen door de knop ![](assets/wkf_dlv_detail_button.png) te selecteren.

![](assets/wkf_display_recurrent_executions_3_direct_mail.png)
