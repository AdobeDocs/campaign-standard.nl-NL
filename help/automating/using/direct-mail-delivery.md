---
title: Directe postbezorging
description: Met de leveringsactiviteit Direct mail kunt u het verzenden van één verzendend direct mail of een terugkomende direct mail in een werkschema configureren.
page-status-flag: never-activated
uuid: bfa7b176-a17c-4079-a073-64b8ce4788ed
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: channel-activities
discoiquuid: b9ddb2a0-54ff-4ada-be6f-8109fa06d461
context-tags: directMail,workflow,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c3911232a3cce00c2b9a2e619f090a7520382dde
workflow-type: tm+mt
source-wordcount: '914'
ht-degree: 0%

---


# Directe postbezorging{#direct-mail-delivery}

## Beschrijving {#description}

![](assets/paper.png)

![](assets/recurrentpaper.png)

Met deze **[!UICONTROL Direct mail delivery]** activiteit kunt u een bestand configureren en voorbereiden dat profielgegevens bevat die u wilt gebruiken voor een campagne voor direct mail. Dit kan een directe post zijn die slechts eenmaal wordt gebruikt, of het kan een **terugkomende** directe post zijn.

Standaard directe mails worden één keer verzonden.

Het terugkeren van post staat u toe om de zelfde directe post veelvoudige tijden naar verschillende doelstellingen over een bepaalde periode te verzenden. U kunt de leveringen per periode samenvoegen om rapporten te krijgen die aan uw behoeften beantwoorden.

## Gebruikscontext {#context-of-use}

De **[!UICONTROL Direct mail delivery]** activiteit wordt over het algemeen gebruikt om het voorbereiden van een dossier te automatiseren dat profielgegevens bevat. Dit bestand kan vervolgens worden verzonden naar een partner/provider die verantwoordelijk is voor de mailing.

Wanneer verbonden met een planner, kunt u terugkomende directe brievenbussen bepalen.

Directe e-mailontvangers worden vóór de activiteit in dezelfde werkstroom gedefinieerd, via doelactiviteiten zoals query&#39;s, snijpunten, enz. Profielen waarvan het mailadres niet is opgegeven, worden automatisch uitgesloten wanneer het e-mailadres wordt voorbereid.

De voorbereiding van berichten wordt geactiveerd volgens de parameters voor workflowuitvoering. Van het berichtdashboard, kunt u selecteren of om een manuele bevestiging te verzoeken of niet om het bericht te verzenden (die door gebrek wordt vereist). U kunt de workflow handmatig starten of een planneractiviteit in de workflow plaatsen om de uitvoering te automatiseren.

**Verwante onderwerpen:**

* [Hoofdlettergebruik: Koppeling van e-mail- en direct-mailleveringen](../../automating/using/coupling-email-direct-mail.md)
* [Over direct mail](../../channels/using/about-direct-mail.md)

## Configuratie {#configuration}

1. Sleep een **[!UICONTROL Direct mail delivery]** activiteit naar uw werkstroom.
1. Selecteer de activiteit, dan open het gebruikend de ![](assets/edit_darkgrey-24px.png) knoop van de snelle acties die verschijnen.

   >[!NOTE]
   >
   >U kunt de algemene eigenschappen en geavanceerde opties van de activiteit (en niet van de levering zelf) via de ![](assets/dlv_activity_params-24px.png) knoop van de snelle acties van de activiteit toegang hebben. Deze knop is specifiek voor de kanaalactiviteiten. De eigenschappen van de directe mail kunnen via de actiebar in het directe postdashboard worden betreden.

1. Selecteer de modus Direct verzenden:

   * **[!UICONTROL Direct mail]**: de directe post wordt één keer verzonden. U kunt hier specificeren of u al dan niet een uitgaande overgang aan de activiteit wilt toevoegen. De verschillende overgangstypen worden beschreven in stap 7 van deze procedure.
   * **[!UICONTROL Recurring direct mail]**: het direct mail wordt verscheidene keren verzonden, volgens de frequentie die in een **[!UICONTROL Scheduler]** activiteit wordt bepaald. Selecteer de samenvoegingsperiode van de verzendingen. Dit staat u toe om al te hergroeperen verzendt die tijdens de bepaalde periode in één enkele directe post voorkomen die ook **Terugkerende uitvoering** wordt genoemd en van de de marketing activiteitenlijst van de toepassing kan worden betreden.

      Bijvoorbeeld, voor een terugkomende verjaardagspost, die dagelijks wordt verwerkt, kunt u verkiezen om samen te voegen verzendt per maand. Op deze manier kunt u maandelijks rapporten over uw levering ontvangen, hoewel de e-mail elke dag wordt verwerkt.

      >[!NOTE]
      >
      >Voor terugkerende directe mails wordt bij elke uitvoering van de workflow een nieuw bestand gegenereerd. De geselecteerde samenvoegingsperiode heeft geen invloed op dit gedrag.

1. Selecteer een type direct-mail. De directe-mailtypen zijn afkomstig van sjablonen die u hebt gedefinieerd in het menu **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]** .
1. Voer de algemene eigenschappen voor de directe e-mail in. U kunt het aan een bestaande campagne ook vastmaken. Het label van de leveringsactiviteit van de werkstroom wordt bijgewerkt met het direct-maillabel.
1. De inhoud van de directe e-mail definiëren. Raadpleeg de sectie over het bewerken van [inhoud](../../designing/using/personalization.md).
1. Standaard bevat de **[!UICONTROL Direct mail delivery]** activiteit geen uitgaande overgangen. Als u een uitgaande overgang aan uw **[!UICONTROL Direct mail delivery]** activiteit wilt toevoegen, ga naar het **[!UICONTROL General]** lusje van de geavanceerde activiteitenopties ( ![](assets/dlv_activity_params-24px.png) knoop in de snelle acties van de activiteit) dan controleren één van de volgende opties:

   * **[!UICONTROL Add outbound transition without the population]**: dit laat u een uitgaande overgang produceren die de nauwkeurige zelfde bevolking zoals de binnenkomende overgang bevat. Deze overgang bevat het bestand dat is gegenereerd door de activiteit direct mail en de onbewerkte populatie die is ontvangen door de activiteit direct mail.
   * **[!UICONTROL Add outbound transition with the population]**: dit laat u een uitgaande overgang produceren die de bevolking bevat waarnaar de directe post zal worden verzonden. De leden van het doel die tijdens de voorbereiding van direct mail (quarantaine, ongeldig adres, enz.) worden uitgesloten zijn uitgesloten van deze overgang. De overgang bevat ook het bestand dat door de directe mail wordt gegenereerd.

1. Bevestig de configuratie van uw activiteit en sla uw werkschema op.

Wanneer u de activiteit opnieuw opent, wordt u rechtstreeks genomen aan het directe postdashboard. Alleen de inhoud kan worden bewerkt.

Door gebrek, leidt het beginnen van een leveringswerkschema slechts tot de berichtvoorbereiding. Het verzenden van berichten die op basis van een workflow zijn gemaakt, moet nog worden bevestigd nadat de workflow is gestart. Maar van het berichtdashboard, en slechts als het bericht van een werkschema werd gecreeerd, kunt u de **[!UICONTROL Request confirmation before sending messages]** optie onbruikbaar maken. Als u deze optie uitschakelt, worden berichten zonder verdere kennisgeving verzonden zodra de voorbereiding is voltooid.

## Opmerkingen {#remarks}

De leveringen die in een workflow worden gemaakt, zijn toegankelijk in de lijst met marketingactiviteiten van de toepassing. U kunt de uitvoeringsstatus van de workflow weergeven via het dashboard. Met de koppelingen in het overzichtsvenster Direct mail hebt u rechtstreeks toegang tot gekoppelde elementen (workflow, campagne, bovenliggende verzending in het geval van een terugkerende directe mail).

![](assets/wkf_display_parent_elements_direct_mail.png)

De uitvoering van terugkerende leveringen wordt standaard gemaskeerd. U kunt deze weergeven door de **[!UICONTROL Show recurring executions]** optie in het zoekvenster voor marketingactiviteiten te selecteren.

![](assets/wkf_display_recurrent_executions_direct_mail.png)

In de ouderleveranties, die van de marketing activiteitenlijst of direct via de bijbehorende terugkomende uitvoeringen kunnen worden betreden, kunt u het totale aantal post bekijken die (volgens de samenvoegingsperiode die wordt gespecificeerd toen de **[!UICONTROL Direct mail delivery]** activiteit werd gevormd) is verwerkt. U doet dit door de detailweergave van het **[!UICONTROL Deployment]** blok van de bovenliggende levering te openen door de ![](assets/wkf_dlv_detail_button.png) knop te selecteren.

![](assets/wkf_display_recurrent_executions_3_direct_mail.png)
