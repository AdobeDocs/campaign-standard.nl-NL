---
title: Levering via SMS
description: De de leveringsactiviteit van SMS staat u toe om het verzenden van één enkel te vormen verzend SMS of terugkomende SMS in een werkschema.
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
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Levering via SMS{#sms-delivery}

## Beschrijving {#description}

![](assets/sms.png)

![](assets/recurrentsms.png)

De **[!UICONTROL SMS delivery]** activiteit staat u toe om het verzenden van SMS in een werkschema te vormen. Dit kan **één enkel verzenden** SMS zijn en slechts één keer worden verzonden, of het kan een **terugkomende** SMS zijn.

SMS-berichten voor één verzending zijn standaard-SMS-berichten die één keer worden verzonden.

Het terugkeren van SMS berichten staat u toe om het zelfde SMS veelvoudige tijden naar verschillende doelstellingen over een bepaalde periode te verzenden. U kunt de leveringen per periode samenvoegen om rapporten te krijgen die aan uw behoeften beantwoorden.

## Gebruikscontext {#context-of-use}

De **[!UICONTROL SMS delivery]** activiteit wordt over het algemeen gebruikt om het verzenden van SMS naar een doel te automatiseren dat in de zelfde werkschema wordt berekend.

Wanneer verbonden met een planner, kunt u terugkomende berichten van SMS bepalen.

De ontvangers van SMS worden bepaald stroomopwaarts van de activiteit in het zelfde werkschema, via het richten van activiteiten zoals vragen, snijpunten, enz.

De voorbereiding van berichten wordt geactiveerd volgens de parameters voor workflowuitvoering. Van het berichtdashboard, kunt u selecteren of om een manuele bevestiging te verzoeken of niet om het bericht te verzenden (die door gebrek wordt vereist). U kunt de workflow handmatig starten of een planneractiviteit in de workflow plaatsen om de uitvoering te automatiseren.

## Configuratie {#configuration}

1. Sleep een **[!UICONTROL SMS delivery]** activiteit naar uw werkstroom.
1. Selecteer de activiteit, dan open het gebruikend de ![](assets/edit_darkgrey-24px.png) knoop van de snelle acties die verschijnen.

   >[!NOTE]
   >
   >U kunt de algemene eigenschappen en geavanceerde opties van de activiteit (en niet van de levering zelf) via de ![](assets/dlv_activity_params-24px.png) knoop in de de actiebar van het werkschema toegang hebben. Deze knop is specifiek voor de **[!UICONTROL SMS delivery]** activiteit. De eigenschappen van SMS kunnen via de actiebar in het dashboard van SMS worden betreden.

1. Selecteer de verzendmodus voor SMS:

   * **[!UICONTROL SMS]**: het SMS één keer wordt verzonden. U kunt hier specificeren of u al dan niet een uitgaande overgang aan de activiteit wilt toevoegen. De verschillende overgangstypen worden beschreven in stap 7 van deze procedure.
   * **[!UICONTROL Recurring SMS]**: het SMS verscheidene keren wordt verzonden, volgens de frequentie die in een **[!UICONTROL Scheduler]** activiteit wordt bepaald. Selecteer de samenvoegingsperiode van de verzendingen. Dit staat u toe om al te groeperen verzendt die tijdens de bepaalde periode in één enkele mening voorkomen die ook **Terugkerende uitvoering** wordt genoemd en van de marketing van de toepassing activiteitenlijst kan worden betreden.

      Bijvoorbeeld, voor een terugkerende verjaardag SMS, dat dagelijks wordt verzonden, kunt u verkiezen om verzendt per maand samen te voegen. Op deze manier kunt u maandelijks rapporten over uw levering ontvangen, hoewel het SMS elke dag wordt verzonden.

1. Selecteer een type SMS. De typen SMS zijn afkomstig van SMS-sjablonen die zijn gedefinieerd in het menu **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]** .
1. Voer de algemene eigenschappen van het SMS in. U kunt het aan een bestaande campagne ook vastmaken. Het label van de leveringsactiviteit van de workflow wordt bijgewerkt met het SMS-label.
1. Definieer de inhoud van SMS. Raadpleeg de sectie over het [maken van een SMS-bericht](../../channels/using/creating-an-sms-message.md).
1. Standaard bevat de **[!UICONTROL SMS delivery]** activiteit geen uitgaande overgangen. Als u een uitgaande overgang aan uw **[!UICONTROL SMS delivery]** activiteit wilt toevoegen, ga naar het **[!UICONTROL General]** lusje van de geavanceerde activiteitenopties ( ![](assets/dlv_activity_params-24px.png) knoop in de snelle acties van de activiteit) dan controleren één van de volgende opties:

   * **[!UICONTROL Add outbound transition without the population]**: dit laat u een uitgaande overgang produceren die de nauwkeurige zelfde bevolking zoals de binnenkomende overgang bevat.
   * **[!UICONTROL Add outbound transition with the population]**: dit laat u een uitgaande overgang produceren die de bevolking bevat aan wie SMS werd verzonden. De leden van de doelgroep die tijdens de voorbereiding van de levering werden uitgesloten (quarantaine, ongeldig aantal, enz.) zijn uitgesloten van deze overgang.

1. Bevestig de configuratie van uw activiteit en sla uw werkschema op.

Wanneer u de activiteit opnieuw opent, wordt u genomen rechtstreeks aan het dashboard van SMS. Alleen de inhoud kan worden bewerkt.

Door gebrek, leidt het beginnen van een leveringswerkschema slechts tot de berichtvoorbereiding. Het verzenden van berichten die op basis van een workflow zijn gemaakt, moet nog worden bevestigd nadat de workflow is gestart. Maar van het berichtdashboard, en slechts als het bericht van een werkschema werd gecreeerd, kunt u de **[!UICONTROL Request confirmation before sending messages]** optie onbruikbaar maken. Als u deze optie uitschakelt, worden berichten zonder verdere kennisgeving verzonden zodra de voorbereiding is voltooid.

## Opmerkingen {#remarks}

De leveringen die in een workflow worden gemaakt, zijn toegankelijk in de lijst met marketingactiviteiten van de toepassing. U kunt de uitvoeringsstatus van de workflow weergeven via het dashboard. Met de koppelingen in het overzichtsvenster van SMS hebt u rechtstreeks toegang tot gekoppelde elementen (workflow, campagne, bovenliggende levering in het geval van een terugkerend SMS).

De uitvoeringen van terugkerende leveringen worden echter standaard gemaskeerd. U kunt deze weergeven door de **[!UICONTROL Show recurring executions]** optie in het zoekvenster voor marketingactiviteiten te selecteren.

In de ouderleveranties, die van de marketing activiteitenlijst of direct via de bijbehorende terugkomende uitvoeringen kunnen worden betreden, kunt u het totale aantal verzenden bekijken die zijn verwerkt (volgens de samenvoegingsperiode die wordt gespecificeerd toen de **[!UICONTROL SMS delivery]** activiteit werd gevormd). U doet dit door de detailweergave van het **[!UICONTROL Deployment]** blok van de bovenliggende levering te openen door ![](assets/wkf_dlv_detail_button.png)te selecteren.

## Voorbeeld {#example}

![](assets/wkf_sms_example_1.png)

Dit voorbeeld is een verjaardagsworkflow. Elke dag wordt een SMS verzonden naar profielen waarvan de verjaardag op die dag is. Dit doet u als volgt:

* Met dit **[!UICONTROL Scheduler]** programma kunt u elke dag om 8.00 uur de workflow starten.

   ![](assets/wkf_delivery_example_2.png)

* Met deze **[!UICONTROL Query]** activiteit kunt u de profielen berekenen die een mobiel telefoonnummer hebben opgegeven en waarvan de verjaardag op de huidige dag plaatsvindt, telkens wanneer de workflow wordt uitgevoerd. De verjaardagsberekening wordt uitgevoerd gebruikend een vooraf bepaald filter beschikbaar in het palet in het vraaguitgevende hulpmiddel.

   ![](assets/wkf_delivery_example_3.png)

* Het **[!UICONTROL SMS]** is terugkerend. De verzendingen worden samengevoegd per maand. Alle SMS-berichten die in een maand worden verzonden, worden dus samengevoegd tot één weergave. In één jaar worden er daarom 365 leveringen uitgevoerd, maar deze worden in de interface van Adobe Campagne gerangschikt in 12 weergaven (ook wel **terugkerende uitvoeringen** genoemd). De geschiedenis en rapportdetails worden getoond elke maand en niet voor elke verzend.

   ![](assets/wkf_sms_example_4.png)

Voor een ander voorbeeld van levering van SMS in een werkschema, zie [Gebruik geval: Workflows opnieuw toewijzen om een nieuwe levering naar niet-openers](../../automating/using/workflow-cross-channel-retargeting.md)te verzenden.
