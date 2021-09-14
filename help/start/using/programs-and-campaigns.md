---
title: Programma’s en campagnes
description: In Adobe Campaign kunt u met programma’s en campagnes de verschillende marketingactiviteiten die aan deze activiteiten zijn gekoppeld, groeperen en ordenen. Dankzij rapporten over programma’s en campagnes kunt u de impact ervan analyseren.
audience: start
content-type: reference
topic-tags: marketing-plans
context-tags: campaign,overview;campaignExplorer,main
feature: Campaigns
role: User
level: Beginner
exl-id: 3f4f9307-c65f-47bb-bc92-ce8b5d06557f
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '641'
ht-degree: 100%

---

# Programma’s en campagnes{#programs-and-campaigns}

## Plannen, programma’s en campagnes {#about-plans--programs-and-campaigns}

Met Adobe Campaign kunt u marketingcampagnes plannen waarin u verschillende soorten activiteiten kunt maken en beheren: e-mails, sms-berichten, pushmeldingen, workflows en landingspagina’s. Deze campagnes en hun content kunnen in programma’s worden verzameld.

Met de programma’s en campagnes kunt u de verschillende marketingactiviteiten die eraan gekoppeld zijn, opnieuw groeperen en bekijken.

* Een **programma** kan andere programma’s bevatten evenals campagnes, workflows en landingspagina’s. Een programma wordt weergegeven op de tijdlijn en helpt u bij het organiseren van uw marketingactiviteiten: u kunt ze verdelen per land, per merk, per eenheid, enzovoort.
* Met een **campagne** kunt u alle gewenste marketingactiviteiten onder één entiteit verzamelen. Een campagne kan e-mails, sms’en, pushmeldingen, direct mails, workflows en landingspagina’s bevatten.

Adobe raadt de volgende hiërarchie aan om uw marketingplannen beter te organiseren: programma > subprogramma’s > campagnes > workflows > leveringen.

Dankzij rapporten over programma’s en campagnes kunt u de impact ervan analyseren. U kunt bijvoorbeeld rapporten op campagneniveau samenstellen om data over alle leveringen in die campagne samen te voegen.

**Verwante onderwerpen:**

* [Tijdlijn](../../start/using/timeline.md)
* [Informatie over dynamische rapporten](../../reporting/using/about-dynamic-reports.md)

## Een programma maken {#creating-a-program}

Het programma is het eerste niveau van een organisatie. Het kan subprogramma’s, campagnes, workflows of landingspagina’s bevatten.

1. Selecteer de kaart **[!UICONTROL Programs & Campaigns]** op de Adobe Campaign-startpagina.
1. Klik op de knop **[!UICONTROL Create]**.
1. Selecteer een programmatype op het scherm **[!UICONTROL Creation mode]**.

   ![](assets/programs_and_campaigns_2.png)

   De beschikbare programmatypen zijn gebaseerd op sjablonen die zijn gedefinieerd in de sectie **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Program templates]**. Raadpleeg de sectie [Sjablonen beheren](../../start/using/marketing-activity-templates.md) voor meer informatie.

1. Voer op het scherm **[!UICONTROL Properties]** de naam en id van het programma in.

   ![](assets/programs_and_campaigns_3.png)

1. Selecteer een begin- en einddatum voor uw programma. Deze datums gelden alleen voor het programma zelf.

   U kunt uw programma maken in een bovenliggend programma. Selecteer hiervoor het bovenliggende programma in de bestaande programma’s.

1. Klik op **[!UICONTROL Create]** om de aanmaak van het programma te bevestigen.

Het programma wordt gemaakt en weergegeven. Gebruik de knop **[!UICONTROL Create]** om subprogramma’s, campagnes, workflows of landingspagina’s toe te voegen.

>[!NOTE]
>
>U kunt ook een programma maken op basis van de lijst met marketingactiviteiten.

## Een campagne maken {#creating-a-campaign}

U kunt u campagnes toevoegen in programma’s en subprogramma’s. Campagnes kunnen marketingactiviteiten bevatten, zoals e-mails, sms’en, pushmeldingen, workflows en landingspagina’s.

1. Selecteer de kaart **[!UICONTROL Programs & Campaigns]** op de Adobe Campaign-startpagina en open een programma of subprogramma.
1. Klik op de knop **[!UICONTROL Create]** en selecteer **[!UICONTROL Campaign]**.
1. Selecteer een type campagne op het scherm **[!UICONTROL Creation mode]**.

   ![](assets/programs_and_campaigns_7.png)

   De beschikbare campagnetypen zijn gebaseerd op sjablonen die zijn gedefinieerd in **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Campaign templates]**. Raadpleeg de sectie [Sjablonen beheren](../../start/using/marketing-activity-templates.md) voor meer informatie.

1. Voer op het scherm **[!UICONTROL Properties]** de naam en id van de campagne in.
1. Selecteer een begin- en einddatum voor uw campagne. Deze datums gelden alleen voor de campagne zelf.

   ![](assets/programs_and_campaigns_8.png)

1. Klik op **[!UICONTROL Create]** om de aanmaak van de campagne te bevestigen.

De campagne wordt gemaakt en weergegeven. Gebruik de knop **[!UICONTROL Create]** om marketingactiviteiten aan uw campagne toe te voegen.

>[!NOTE]
>
>Afhankelijk van uw licentieovereenkomst hebt u mogelijk slechts toegang tot enkele van deze activiteiten.

U kunt ook een campagne maken op basis van de lijst met marketingactiviteiten. U kunt de marketingactiviteit via het eigenschappenvenster van de campagne koppelen aan een bovenliggend programma of subprogramma.

## Pictogrammen en statussen van programma’s en campagnes {#programs-and-campaigns-icons-and-statuses}

Alle programma’s en campagnes in de lijst hebben een visueel symbool en een pictogram waarvan de kleur de uitvoeringsstatus aangeeft. Deze status hangt af van de geldigheidsperiode van het programma of de campagne.

* Grijs: het programma of de campagne is nog niet begonnen - status **[!UICONTROL Editing]**.
* Blauw: het programma of de campagne is in uitvoering - status **[!UICONTROL In progress]**.
* Groen: het programma of de campagne is voltooid - status **[!UICONTROL Finished]**. Standaard wordt de huidige datum automatisch weergegeven als de begindatum van de geldigheid en de einddatum wordt berekend op basis van de begindatum (**D+186 dagen**). U kunt deze datums wijzigen in de eigenschappen van het programma of de campagne.

![](assets/programs_and_campaigns.png)
