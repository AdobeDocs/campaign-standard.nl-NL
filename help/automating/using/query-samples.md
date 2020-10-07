---
title: Voorbeelden van query’s
description: Deze sectie stelt gebruiksgeval voor wanneer het gebruiken van een activiteit van de Vraag.
page-status-flag: never-activated
uuid: b3c629fa-370e-481c-b347-fcf9f5a5e847
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 8d46ce28-0101-4f13-865a-2208ed6d6139
context-tags: query,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 90%

---


# Voorbeelden van query&#39;s {#query-samples}

In deze sectie wordt het gebruik van hoofdletters en kleine letters beschreven bij het gebruik van een **[!UICONTROL Query]** activiteit. For more on how to use a **[!UICONTROL Query]** activity, refer to [this section](../../automating/using/query.md).

## Targeting op basis van eenvoudige profielkenmerken {#targeting-on-simple-profile-attributes}

Het volgende voorbeeld toont een queryactiviteit die is gericht op mannen tussen 18 en 30 jaar die in Londen wonen.

![](assets/query_sample_1.png)

## Targeting op basis van e-mailkenmerken {#targeting-on-email-attributes}

In het volgende voorbeeld ziet u een queryactiviteit die is geconfigureerd voor doelprofielen met het e-mailadresdomein &quot;orange.co.uk&quot;.

![](assets/query_sample_emaildomain.png)

In het volgende voorbeeld ziet u een queryactiviteit die is geconfigureerd voor doelprofielen waarvan het e-mailadres is verstrekt.

![](assets/query_sample_emailnotempty.png)

## Targeting van profielen met vandaag als verjaardag {#targeting-profiles-whose-birthday-is-today}

In het volgende voorbeeld ziet u een queryactiviteit die is geconfigureerd voor doelprofielen met vandaag als verjaardag.

1. Sleep het filter **[!UICONTROL Birthday]** en plaats het in uw query.

   ![](assets/query_sample_birthday.png)

1. Stel **[!UICONTROL Filter type]** in op **[!UICONTROL Relative]** en selecteer **[!UICONTROL Today]**.

   ![](assets/query_sample_birthday2.png)

## Targeting van profielen die een specifieke levering hebben geopend {#targeting-profiles-who-opened-a-specific-delivery}

Het volgende voorbeeld toont een queryactiviteit die is geconfigureerd om te filteren op profielen die de levering met het label &quot;Summer Time&quot; hebben geopend.

1. Sleep het filter **[!UICONTROL Opened]** en plaats het in uw query.

   ![](assets/query_sample_opened.png)

1. Selecteer de levering en klik op **[!UICONTROL Confirm]**.

   ![](assets/query_sample_opened2.png)

## Targeting van profielen waarbij de levering om een bepaalde reden is mislukt {#targeting-profiles-for-whom-deliveries-failed-for-a-specific-reason}

Het volgende voorbeeld toont een queryactiviteit die is geconfigureerd om te filteren op profielen waarbij de levering is mislukt omdat hun postvak vol was. Deze query is alleen beschikbaar voor gebruikers met beheerrechten die horen bij de **[!UICONTROL All (all)]** organisatie-eenheden (zie [deze sectie](../../administration/using/organizational-units.md)).

1. Selecteer de bron **[!UICONTROL Delivery logs]** om rechtstreeks te filteren in de tabel met leveringslogboeken (zie [Bronnen gebruiken die niet gelijk zijn aan targetingdimensies](../../automating/using/using-resources-different-from-targeting-dimensions.md)).

   ![](assets/query_sample_failure1.png)

1. Sleep het filter **[!UICONTROL Nature of failure]** en plaats het in uw query.

   ![](assets/query_sample_failure2.png)

1. Selecteer het type fout dat u wilt targetten. In ons geval is dat **[!UICONTROL Mailbox full]**.

   ![](assets/query_sample_failure3.png)

## Targeting van profielen die in de afgelopen 7 dagen niet zijn benaderd {#targeting-profiles-not-contacted-during-the-last-7-days}

Het volgende voorbeeld toont een queryactiviteit die is geconfigureerd om te filteren op profielen die de afgelopen 7 dagen niet zijn benaderd.

1. Sleep het filter **[!UICONTROL Delivery logs (logs)]** en plaats het in uw query.

   ![](assets/query_sample_7days.png)

   Selecteer **[!UICONTROL Does not exist]** in de vervolgkeuzelijst en sleep het filter **[!UICONTROL Delivery]**.

   ![](assets/query_sample_7days1.png)

1. Configureer het filter zoals hieronder aangegeven.

   ![](assets/query_sample_7days2.png)

## Targeting van profielen die op een specifieke koppeling hebben geklikt {#targeting-profiles-who-clicked-a-specific-link-}

1. Sleep het filter **[!UICONTROL Tracking logs (tracking)]** en plaats het in uw query.

   ![](assets/query_sample_trackinglogs.png)

1. Sleep het filter **[!UICONTROL Label (urlLabel)]**.

   ![](assets/query_sample_trackinglogs2.png)

1. In het veld **[!UICONTROL Value]** typt u het label dat is gedefinieerd bij het invoegen van de koppeling in de levering. Bevestig vervolgens de koppeling.

   ![](assets/query_sample_trackinglogs3.png)
