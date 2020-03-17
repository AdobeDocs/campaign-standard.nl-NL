---
title: Levering pushmelding
description: Met de activiteit voor het leveren van pushberichten kunt u het verzenden van één pushmelding of een terugkerend pushbericht in een workflow configureren.
page-status-flag: never-activated
uuid: 994d8fe3-29f0-4b5c-89ee-c6be7c60a31b
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: channel-activities
discoiquuid: e61bdaee-4b48-4845-a2a5-574b577ea796
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: accc382ca1543d648e60d53cab338537fd9ea3ef

---


# Levering pushmelding{#push-notification-delivery}

## Beschrijving {#description}

![](assets/push.png)

![](assets/recurrentpush.png)

Met de **[!UICONTROL Push notification]** activiteit kunt u het verzenden van een pushmelding in een workflow configureren. Dit kan **één enkel verzend** bericht zijn en slechts één keer verzonden, of het kan een **terugkerend** bericht zijn.

Meldingen voor één verzending zijn standaard mobiele pushberichten voor apps, die één keer worden verzonden.

Met terugkerende meldingen kunt u dezelfde pushmelding voor mobiele apps gedurende een bepaalde periode meerdere keren verzenden naar verschillende doelen. U kunt de leveringen per periode samenvoegen om rapporten te krijgen die aan uw behoeften beantwoorden.

## Gebruikscontext {#context-of-use}

De **[!UICONTROL Push notification]** activiteit wordt over het algemeen gebruikt om het verzenden van een bericht naar een doel te automatiseren dat in de zelfde werkschema wordt berekend.

Wanneer verbonden met een planner, kunt u terugkomende dupberichten bepalen.

De ontvangers worden vóór de activiteit in de zelfde werkschema gedefinieerd, via het richten van activiteiten zoals vragen, snijpunten, enz.

De voorbereiding van berichten wordt geactiveerd volgens de parameters voor workflowuitvoering. Van het berichtdashboard, kunt u selecteren of om een manuele bevestiging te verzoeken of niet om het bericht te verzenden (die door gebrek wordt vereist). U kunt de workflow handmatig starten of een planneractiviteit in de workflow plaatsen om de uitvoering te automatiseren.

## Configuratie {#configuration}

1. Sleep een **[!UICONTROL Push notification]** activiteit naar uw werkstroom.
1. Selecteer de activiteit, dan open het gebruikend de ![](assets/edit_darkgrey-24px.png) knoop van de snelle acties die verschijnen.

   >[!NOTE]
   >
   >U kunt de algemene eigenschappen en geavanceerde opties van de activiteit (en niet van de levering zelf) via de ![](assets/dlv_activity_params-24px.png) knoop van de snelle acties van de activiteit toegang hebben. Deze knop is specifiek voor de **[!UICONTROL Push notification]** activiteit. De eigenschappen van de pushmelding zijn toegankelijk via de actiebalk in het pushdashboard.

1. Selecteer de verzendmodus voor pushmeldingen:

   * **[!UICONTROL Single notification]**: de pushmelding wordt één keer verzonden. U kunt hier specificeren of u al dan niet een uitgaande overgang aan de activiteit wilt toevoegen. De verschillende overgangstypen worden beschreven in stap 7 van deze procedure.
   * **[!UICONTROL Recurring notification]**: de pushmelding wordt verschillende keren verzonden volgens de frequentie die in een **[!UICONTROL Scheduler]** activiteit is gedefinieerd. Selecteer de samenvoegingsperiode van de verzendingen. Dit staat u toe om al te hergroeperen verzendt die tijdens de bepaalde periode in één enkel duw bericht voorkomen dat ook **terugkerende uitvoering** wordt genoemd en van de marketing van de toepassing activiteitenlijst kan worden betreden.

      Bijvoorbeeld, voor een terugkerend verjaardagsbericht, dat dagelijks wordt verzonden, kunt u verkiezen om samen te voegen verzendt per maand. Op deze manier kunt u maandelijks rapporten over uw levering ontvangen, hoewel het bericht elke dag wordt verzonden.

1. Selecteer een berichttype. Deze typen zijn afkomstig van de sjablonen voor pushmeldingen die zijn gedefinieerd in het menu **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]** .
1. Voer de algemene eigenschappen voor de pushmelding in. U kunt het aan een bestaande campagne ook vastmaken. Het label van de leveringsactiviteit van de workflow wordt bijgewerkt met het label voor pushmeldingen.
1. Definieer de inhoud van het pushbericht. Zie [Een pushmelding maken](../../channels/using/preparing-and-sending-a-push-notification.md)
1. Standaard bevat de **[!UICONTROL Push notification]** activiteit geen uitgaande overgangen. Als u een uitgaande overgang aan uw **[!UICONTROL Push Notification]** activiteit wilt toevoegen, ga naar het **[!UICONTROL General]** lusje van de geavanceerde activiteitenopties ( ![](assets/dlv_activity_params-24px.png) knoop in de snelle acties van de activiteit) dan controleren één van de volgende opties:

   * **[!UICONTROL Add outbound transition without the population]**: dit laat u een uitgaande overgang produceren die de nauwkeurige zelfde bevolking zoals de binnenkomende overgang bevat.
   * **[!UICONTROL Add outbound transition with the population]**: dit laat u een uitgaande overgang produceren die de bevolking bevat aan wie de kennisgeving werd verzonden. De leden van het doel die tijdens de voorbereiding van de levering zijn uitgesloten, zijn van deze overgang uitgesloten.

1. Bevestig de configuratie van uw activiteit en sla uw werkschema op.

Wanneer u de activiteit opnieuw opent, wordt u rechtstreeks genomen aan het dashboard van het dupmelding. Alleen de inhoud kan worden bewerkt.

Door gebrek, leidt het beginnen van een leveringswerkschema slechts tot de berichtvoorbereiding. Het verzenden van berichten die op basis van een workflow zijn gemaakt, moet nog worden bevestigd nadat de workflow is gestart. Maar van het berichtdashboard, en slechts als het bericht van een werkschema werd gecreeerd, kunt u de **[!UICONTROL Request confirmation before sending messages]** optie onbruikbaar maken. Als u deze optie uitschakelt, worden berichten zonder verdere kennisgeving verzonden zodra de voorbereiding is voltooid.

## Opmerkingen {#remarks}

De leveringen die in een workflow worden gemaakt, zijn toegankelijk in de lijst met marketingactiviteiten van de toepassing. U kunt de uitvoeringsstatus van de workflow weergeven via het dashboard. Via koppelingen in het overzichtsvenster voor pushmeldingen hebt u rechtstreeks toegang tot gekoppelde elementen (workflow, campagne, enz.).

In de ouderleveringen, die van de marketing activiteitenlijst kunnen worden betreden, kunt u het totale aantal verzenden bekijken die zijn verwerkt (volgens de samenvoegingsperiode die wordt gespecificeerd toen de **[!UICONTROL Push notification]** activiteit werd gevormd). U doet dit door de detailweergave van het **[!UICONTROL Deployment]** blok van de bovenliggende levering te openen door ![](assets/wkf_dlv_detail_button.png)te selecteren.

## Een terugkerende pushmelding verzenden met een workflow {#sending-a-recurring-push-notification-with-a-workflow}

![](assets/wkf_push_example_1.png)

In dit voorbeeld wordt elke eerste dag van de maand om 21.00 uur een persoonlijke pushmelding verzonden naar de abonnees van uw mobiele toepassing, afhankelijk van hun tijdzone. Dit doet u als volgt:

1. Met de **[!UICONTROL Scheduler]** activiteit kunt u de workflowdagen vóór het begin van de levering starten om het bericht naar elke abonnee om 20:00 uur in een bepaalde tijdzone te kunnen verzenden:

   * Selecteer Maandelijks in het **[!UICONTROL Execution frequency]** veld.
   * Selecteer 8 pm in het **[!UICONTROL Time]** veld.
   * Kies op welke dag de levering elke maand wordt verzonden.
   * Selecteer een begindatum voor de workflow, ten minste één dag voor het begin van de levering. Anders, zouden sommige ontvangers het bericht een dag later kunnen ontvangen als de geselecteerde tijd reeds in hun tijdzones is overgegaan.
   * Selecteer op het **[!UICONTROL Execution options]** tabblad in welke tijdzone de workflow in het **[!UICONTROL Time zone]** veld moet beginnen. Hier begint de workflow bijvoorbeeld om 20.00 uur Stille-Oceaantijd, één week voor de eerste dag van de maand, zodat er enige tijd is om de leveringen voor alle toepasselijke tijdzones te maken.
   >[!NOTE]
   >
   >Standaard is de geselecteerde tijdzone de tijdzone die is gedefinieerd in de workfloweigenschappen (zie [Een workflow](../../automating/using/building-a-workflow.md)maken).

   ![](assets/wkf_push_example_5.png)

1. Met de activiteit **Query** kunt u zich richten op uw VIP-klanten tussen de 20 en 30 jaar die zich hebben geabonneerd op uw mobiele toepassing en die de door u verzonden e-mail niet hebben geopend:

   * Selecteer een publiek (uw klanten van VIP) en filter op hun leeftijd.
   * Sleep de **abonnementen naar een toepassingselement** en zet ze neer in de werkruimte. Selecteer **Bestaat** en selecteer de mobiele toepassing die u wilt gebruiken.
   * Selecteer het e-mailbericht dat u naar uw klanten hebt verzonden.
   * Sleep het element **Leveringslogboeken (logboeken)** naar de werkruimte en selecteer **Bestaat** om alle klanten aan te wijzen die de e-mail hebben ontvangen.
   * Sleep het element Logbestanden **bijhouden (bijhouden)** naar de werkruimte en selecteer **Bestaat** niet voor alle klanten die de e-mail niet hebben geopend.

      ![](assets/wkf_push_example_2.png)

1. Met de **pushmeldingsactiviteit** kunt u de inhoud van uw bericht invoeren en de personalisatievelden selecteren die u wilt gebruiken:

   * Selecteer de **[!UICONTROL Recurring notification]** optie.
   * Definieer de inhoud van het pushbericht. Raadpleeg deze [sectie](../../channels/using/preparing-and-sending-a-push-notification.md)voor meer informatie over de inhoud van pushberichten.
   * Selecteer in het **[!UICONTROL Schedule]** blok **[!UICONTROL Messages to be sent automatically on the time zone specified below]**. Hier hebben we de **[!UICONTROL Time zone of the contact date]** Pacific gekozen zoals in de workflow **[!UICONTROL Scheduler]**.
   * Selecteer in het **[!UICONTROL Optimize the sending time per recipient]** veld **[!UICONTROL Send at the recipient's time zone]**.

      ![](assets/wkf_push_example_4.png)

1. Klik op de **[!UICONTROL Start]** knop om de terugkerende workflow te starten.

   ![](assets/wkf_push_example_3.png)

Uw workflow is nu actief. Het zal bij de gekozen begindatum van de **[!UICONTROL Scheduler]** om 22.00 uur Pacific tijd beginnen, zal de terugkomende duw dan elke eerste dag van de maand om 8.00 uur afhankelijk van de klantentijdzone worden verzonden.
