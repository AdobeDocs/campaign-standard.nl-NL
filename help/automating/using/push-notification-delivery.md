---
title: Levering van pushmeldingen
description: Met de activiteit voor het leveren van pushberichten kunt u het verzenden van één pushmelding of een terugkerend pushbericht in een workflow configureren.
audience: automating
content-type: reference
topic-tags: channel-activities
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: b6a43d51-32d4-4806-b4e4-33236f1e27f5
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '772'
ht-degree: 47%

---

# Levering van pushmeldingen{#push-notification-delivery}

## Beschrijving {#description}

![](assets/push.png)

![](assets/recurrentpush.png)

De **[!UICONTROL Push notification]** U kunt een pushmelding in een workflow configureren. Dit kan één enkel zijn verzendt bericht en slechts één keer verzonden, of het kan een terugkerend bericht zijn.

* **Enkel** Verzend berichten zijn standaard levering van pushberichten voor mobiele apps, die één keer wordt verzonden.
* **Terugkeren** met meldingen kunt u dezelfde pushmelding voor mobiele apps gedurende een bepaalde periode meerdere keren naar verschillende doelen verzenden. U kunt de leveringen per periode samenvoegen om rapporten te krijgen die voldoen aan uw behoeften.

## Gebruikscontext {#context-of-use}

De **[!UICONTROL Push notification]** activiteit wordt over het algemeen gebruikt om het verzenden van een bericht naar een doel te automatiseren dat in de zelfde werkschema wordt berekend.

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

   * **[!UICONTROL Single notification]**: de pushmelding wordt één keer verzonden. U kunt hier opgeven of u al dan niet een uitgaande overgang aan de activiteit wilt toevoegen. De verschillende overgangstypen worden beschreven in stap 7 van deze procedure.
   * **[!UICONTROL Recurring notification]**: de pushmelding verscheidene keren wordt verzonden, volgens de frequentie die in een **[!UICONTROL Scheduler]** activiteit. Selecteer de aggregatieperiode van de verzendingen. Dit staat u toe om al te groeperen verzendt die tijdens de bepaalde periode in één enkel duw bericht voorkomen dat ook wordt geroepen **terugkerende uitvoering** en kan worden benaderd vanuit de lijst met marketingactiviteiten van de toepassing.

      Bijvoorbeeld, voor een terugkerend verjaardagsbericht, dat dagelijks wordt verzonden, kunt u verkiezen om samen te voegen verzendt per maand. Op deze manier kunt u maandelijks rapporten over uw levering ontvangen, hoewel het bericht elke dag wordt verzonden.

1. Selecteer een berichttype. Deze typen zijn afkomstig van de sjablonen voor pushmeldingen die zijn gedefinieerd in het dialoogvenster **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]** -menu.
1. Voer de algemene eigenschappen voor de pushmelding in. U kunt deze ook aan een bestaande campagne koppelen. Het label van de leveringsactiviteit van de workflow wordt bijgewerkt met het label voor pushmeldingen.
1. Definieer de inhoud van het pushbericht. Zie [Een pushmelding maken](../../channels/using/preparing-and-sending-a-push-notification.md)
1. Standaard bevat de activiteit **[!UICONTROL Push notification]** geen uitgaande overgangen. Als u een uitgaande overgang wilt toevoegen aan uw activiteit **[!UICONTROL Push Notification]**, ga dan naar het tabblad **[!UICONTROL General]** van de geavanceerde opties voor activiteiten (de knop ![](assets/dlv_activity_params-24px.png) in de snelle acties van de activiteit) en vink een van de volgende opties aan:

   * **[!UICONTROL Add outbound transition without the population]**: Hiermee kunt u een uitgaande overgang genereren die exact dezelfde populatie als de binnenkomende overgang bevat.
   * **[!UICONTROL Add outbound transition with the population]**: dit laat u een uitgaande overgang produceren die de bevolking bevat aan wie de kennisgeving werd verzonden. De leden van het doel die tijdens de voorbereiding van de levering zijn uitgesloten, zijn van deze overgang uitgesloten.

1. Bevestig de configuratie van uw activiteit en sla de workflow op.

Wanneer u de activiteit opnieuw opent, wordt u rechtstreeks genomen aan het dashboard van het dupmelding. Alleen de content kan worden bewerkt.

Standaard wordt bij het starten van een leveringsworkflow alleen de berichtvoorbereiding geactiveerd. Het verzenden van berichten die op basis van een workflow zijn gemaakt, moet nog worden bevestigd nadat de workflow is gestart. U kunt echter vanaf het berichtdashboard de optie **[!UICONTROL Request confirmation before sending messages]** uitschakelen, maar alleen als het bericht vanuit een workflow is gemaakt. Als u deze optie uitschakelt, worden berichten zonder verdere kennisgeving verzonden zodra de voorbereiding is voltooid.

## Opmerkingen {#remarks}

De leveringen die in een workflow zijn gemaakt, zijn toegankelijk in de lijst met marketingactiviteiten van de applicatie. U kunt de uitvoeringsstatus van de workflow bekijken via het dashboard. Via koppelingen in het overzichtsvenster voor pushmeldingen hebt u rechtstreeks toegang tot gekoppelde elementen (workflow, campagne, enz.).

In de bovenliggende items, die toegankelijk zijn vanuit de lijst met marketingactiviteiten, kunt u het totale aantal verzonden dat is verwerkt, weergeven (volgens de bij het **[!UICONTROL Push notification]** activiteit is geconfigureerd). U doet dit door de detailweergave van het blok **[!UICONTROL Deployment]** van de bovenliggende levering te openen door ![](assets/wkf_dlv_detail_button.png) te selecteren.
