---
title: Levering van pushmeldingen
description: Met de activiteit voor het leveren van pushberichten kunt u het verzenden van één pushmelding of een terugkerend pushbericht in een workflow configureren.
audience: automating
content-type: reference
topic-tags: channel-activities
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: b6a43d51-32d4-4806-b4e4-33236f1e27f5
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '773'
ht-degree: 46%

---

# Levering van pushmeldingen{#push-notification-delivery}

## Beschrijving {#description}

![](assets/push.png)

![](assets/recurrentpush.png)

Met de **[!UICONTROL Push notification]** -activiteit kunt u het verzenden van een pushmelding in een workflow configureren. Dit kan één enkel zijn verzendt bericht en slechts één keer verzonden, of het kan een terugkerend bericht zijn.

* **Enige** verzendt berichten zijn standaard mobiele die het berichtleveringen van de app, één keer wordt verzonden.
* **Terugkomende** berichten staan u toe om de zelfde mobiele toepassing te verzenden duw berichtlevering veelvoudige tijden aan verschillende doelstellingen over een bepaalde periode. U kunt de leveringen per periode samenvoegen om rapporten te krijgen die voldoen aan uw behoeften.

## Gebruikscontext {#context-of-use}

De **[!UICONTROL Push notification]** -activiteit wordt doorgaans gebruikt om het verzenden van een melding naar een doel dat in dezelfde workflow is berekend, te automatiseren.

Wanneer verbonden met een planner, kunt u terugkomende dupberichten bepalen.

De ontvangers worden vóór de activiteit in de zelfde werkschema gedefinieerd, via het richten van activiteiten zoals vragen, snijpunten, enz.

De voorbereiding van berichten wordt geactiveerd volgens de parameters voor workflowuitvoering. Op het berichtdashboard kunt u kiezen of u al dan niet handmatig wilt bevestigen of u het bericht wilt versturen (standaard vereist). U kunt de workflow handmatig starten of een planneractiviteit in de workflow plaatsen om de uitvoering te automatiseren.

**Verwante onderwerpen**

* [Een terugkerende pushmelding verzenden met een workflow](../../automating/using/recurring-push-notifications.md)

## Configuratie {#configuration}

1. Sleep een activiteit **[!UICONTROL Push notification]** en zet deze neer in uw workflow.
1. Selecteer de activiteit en open deze met de knop ![](assets/edit_darkgrey-24px.png) vanuit de snelle acties die verschijnen.

   >[!NOTE]
   >
   >U kunt de algemene eigenschappen en geavanceerde opties van de activiteit (niet van de levering zelf) raadplegen via de knop ![](assets/dlv_activity_params-24px.png) van de snelle acties van de activiteit. Deze knop is specifiek voor de activiteit **[!UICONTROL Push notification]**. De eigenschappen van de pushmelding zijn toegankelijk via de actiebalk in het pushdashboard.

1. Selecteer de verzendmodus voor pushmeldingen:

   * **[!UICONTROL Single notification]** : de pushmelding wordt één keer verzonden. U kunt hier opgeven of u al dan niet een uitgaande overgang aan de activiteit wilt toevoegen. De verschillende overgangstypen worden beschreven in stap 7 van deze procedure.
   * **[!UICONTROL Recurring notification]** : de pushmelding wordt verschillende keren verzonden, afhankelijk van de frequentie die is gedefinieerd in een **[!UICONTROL Scheduler]** -activiteit. Selecteer de aggregatieperiode van de verzendingen. Dit staat u toe om allen te hergroeperen die tijdens de bepaalde periode in één enkel duw bericht voorkomen dat ook **terugkomende uitvoering** wordt genoemd en van de marketing van de toepassing activiteitenlijst kan worden betreden.

     Bijvoorbeeld, voor een terugkerend verjaardagsbericht, dat dagelijks wordt verzonden, kunt u verkiezen om samen te voegen verzendt per maand. Op deze manier kunt u maandelijks rapporten over uw levering ontvangen, hoewel het bericht elke dag wordt verzonden.

1. Selecteer een berichttype. Deze typen zijn afkomstig van de sjablonen voor pushmeldingen die zijn gedefinieerd in het menu **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]** .
1. Voer de algemene eigenschappen voor de pushmelding in. U kunt deze ook aan een bestaande campagne koppelen. Het label van de leveringsactiviteit van de workflow wordt bijgewerkt met het label voor pushmeldingen.
1. Definieer de inhoud van het pushbericht. Zie [&#x200B; Creërend een duw- bericht &#x200B;](../../channels/using/preparing-and-sending-a-push-notification.md)
1. Standaard bevat de activiteit **[!UICONTROL Push notification]** geen uitgaande overgangen. Als u een uitgaande overgang wilt toevoegen aan uw activiteit **[!UICONTROL Push Notification]**, ga dan naar het tabblad **[!UICONTROL General]** van de geavanceerde opties voor activiteiten (de knop ![](assets/dlv_activity_params-24px.png) in de snelle acties van de activiteit) en vink een van de volgende opties aan:

   * **[!UICONTROL Add outbound transition without the population]**: Hiermee kunt u een uitgaande overgang genereren die exact dezelfde populatie als de binnenkomende overgang bevat.
   * **[!UICONTROL Add outbound transition with the population]**: hiermee kunt u een uitgaande overgang genereren met de populatie waarnaar de melding is verzonden. De leden van het doel die tijdens de voorbereiding van de levering zijn uitgesloten, zijn van deze overgang uitgesloten.

1. Bevestig de configuratie van uw activiteit en sla de workflow op.

Wanneer u de activiteit opnieuw opent, wordt u rechtstreeks genomen aan het dashboard van het dupmelding. Alleen de content kan worden bewerkt.

Standaard wordt bij het starten van een leveringsworkflow alleen de berichtvoorbereiding geactiveerd. Het verzenden van berichten die op basis van een workflow zijn gemaakt, moet nog worden bevestigd nadat de workflow is gestart. U kunt echter vanaf het berichtdashboard de optie **[!UICONTROL Request confirmation before sending messages]** uitschakelen, maar alleen als het bericht vanuit een workflow is gemaakt. Als u deze optie uitschakelt, worden berichten zonder verdere kennisgeving verzonden zodra de voorbereiding is voltooid.

## Opmerkingen {#remarks}

De leveringen die in een workflow zijn gemaakt, zijn toegankelijk in de lijst met marketingactiviteiten van de applicatie. U kunt de uitvoeringsstatus van de workflow bekijken via het dashboard. Via koppelingen in het overzichtsvenster voor pushmeldingen hebt u rechtstreeks toegang tot gekoppelde elementen (workflow, campagne, enz.).

In de ouderleveringen, die van de marketing activiteitenlijst kunnen worden betreden, kunt u het totale aantal verzenden bekijken die zijn verwerkt (volgens de samenvoegingsperiode die wordt gespecificeerd toen **[!UICONTROL Push notification]** activiteit werd gevormd). U doet dit door de detailweergave van het blok **[!UICONTROL Deployment]** van de bovenliggende levering te openen door ![](assets/wkf_dlv_detail_button.png) te selecteren.
