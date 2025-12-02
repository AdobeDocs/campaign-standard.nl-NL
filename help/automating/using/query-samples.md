---
title: Voorbeelden van query’s
description: Deze sectie stelt gebruiksgeval voor wanneer het gebruiken van een activiteit van de Vraag.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: query,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 0a71e3a7-60e6-49ec-af2e-099ad0d69a15
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 76%

---

# Voorbeelden van query’s {#query-samples}

In deze sectie wordt het gebruik van hoofdletters en kleine letters beschreven bij het gebruik van een **[!UICONTROL Query]** -activiteit. Voor meer op hoe te om a **[!UICONTROL Query]** activiteit te gebruiken, verwijs naar [ deze sectie ](../../automating/using/query.md).

## Toewijzen aan eenvoudige profielkenmerken {#targeting-on-simple-profile-attributes}

Het volgende voorbeeld toont een queryactiviteit die is gericht op mannen tussen 18 en 30 jaar die in Londen wonen.

![](assets/query_sample_1.png)

## Gericht op e-mailkenmerken {#targeting-on-email-attributes}

In het volgende voorbeeld ziet u een queryactiviteit die is geconfigureerd voor doelprofielen met het e-mailadresdomein &quot;orange.co.uk&quot;.

![](assets/query_sample_emaildomain.png)

In het volgende voorbeeld ziet u een queryactiviteit die is geconfigureerd voor doelprofielen waarvan het e-mailadres is verstrekt.

![](assets/query_sample_emailnotempty.png)

## Doelprofielen waarvan de verjaardag vandaag is {#targeting-profiles-whose-birthday-is-today}

In het volgende voorbeeld ziet u een queryactiviteit die is geconfigureerd voor doelprofielen met vandaag als verjaardag.

1. Sleep het filter **[!UICONTROL Birthday]** en plaats het in uw query.

   ![](assets/query_sample_birthday.png)

1. Stel **[!UICONTROL Filter type]** in op **[!UICONTROL Relative]** en selecteer **[!UICONTROL Today]**.

   ![](assets/query_sample_birthday2.png)

## Doelprofielen die een specifieke levering hebben geopend {#targeting-profiles-who-opened-a-specific-delivery}

Het volgende voorbeeld toont een queryactiviteit die is geconfigureerd om te filteren op profielen die de levering met het label &quot;Summer Time&quot; hebben geopend.

1. Sleep het filter **[!UICONTROL Opened]** en plaats het in uw query.

   ![](assets/query_sample_opened.png)

1. Selecteer de levering en klik op **[!UICONTROL Confirm]**.

   ![](assets/query_sample_opened2.png)

## Doelprofielen waarvoor leveringen om een bepaalde reden zijn mislukt {#targeting-profiles-for-whom-deliveries-failed-for-a-specific-reason}

Het volgende voorbeeld toont een queryactiviteit die is geconfigureerd om te filteren op profielen waarbij de levering is mislukt omdat hun postvak vol was. Deze query is alleen beschikbaar voor gebruikers met beheerrechten die horen bij de **[!UICONTROL All (all)]** organisatie-eenheden (zie [deze sectie](../../administration/using/organizational-units.md)).

1. Selecteer de bron **[!UICONTROL Delivery logs]** om rechtstreeks te filteren in de tabel met leveringslogboeken (zie [Bronnen gebruiken die niet gelijk zijn aan targetingdimensies](../../automating/using/using-resources-different-from-targeting-dimensions.md)).

   ![](assets/query_sample_failure1.png)

1. Sleep het filter **[!UICONTROL Nature of failure]** en plaats het in uw query.

   ![](assets/query_sample_failure2.png)

1. Selecteer het type fout dat u wilt targetten. In ons geval is dat **[!UICONTROL Mailbox full]**.

   ![](assets/query_sample_failure3.png)

## Doelprofielen waarmee geen contact is opgenomen in de afgelopen 7 dagen {#targeting-profiles-not-contacted-during-the-last-7-days}

Het volgende voorbeeld toont een queryactiviteit die is geconfigureerd om te filteren op profielen die de afgelopen 7 dagen niet zijn benaderd.

1. Sleep het filter **[!UICONTROL Delivery logs (logs)]** en plaats het in uw query.

   ![](assets/query_sample_7days.png)

   Selecteer **[!UICONTROL Does not exist]** in de vervolgkeuzelijst en sleep het filter **[!UICONTROL Delivery]**.

   ![](assets/query_sample_7days1.png)

1. Configureer het filter zoals hieronder aangegeven.

   ![](assets/query_sample_7days2.png)

## Doelprofielen die op een specifieke koppeling hebben geklikt {#targeting-profiles-who-clicked-a-specific-link-}

1. Sleep het filter **[!UICONTROL Tracking logs (tracking)]** en plaats het in uw query.

   ![](assets/query_sample_trackinglogs.png)

1. Sleep het filter **[!UICONTROL Label (urlLabel)]**.

   ![](assets/query_sample_trackinglogs2.png)

1. In het veld **[!UICONTROL Value]** typt u het label dat is gedefinieerd bij het invoegen van de koppeling in de levering. Bevestig vervolgens de koppeling.

   ![](assets/query_sample_trackinglogs3.png)
