---
title: Zoekvoorbeelden
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
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2d994d85f126951215f1227301599c554c1f12c8
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 0%

---


# Zoekvoorbeelden {#query-samples}

In deze sectie wordt het gebruik van hoofdletters en kleine letters beschreven bij het gebruik van een **[!UICONTROL Query]** activiteit. Raadpleeg **[!UICONTROL Query]** deze sectie [voor meer informatie over het gebruik van een](../../automating/using/query.md)activiteit.

## Toewijzen aan eenvoudige profielkenmerken {#targeting-on-simple-profile-attributes}

Het volgende voorbeeld toont een vraagactiviteit die wordt gevormd om mannen tussen 18 en 30 jaar te richten, woonend in Londen.

![](assets/query_sample_1.png)

## Gericht op e-mailkenmerken {#targeting-on-email-attributes}

In het volgende voorbeeld ziet u een queryactiviteit die is geconfigureerd voor doelprofielen met het e-mailadresdomein &quot;orange.co.uk&quot;.

![](assets/query_sample_emaildomain.png)

In het volgende voorbeeld ziet u een queryactiviteit die is geconfigureerd voor doelprofielen waarvan het e-mailadres is opgegeven.

![](assets/query_sample_emailnotempty.png)

## Doelprofielen waarvan de verjaardag vandaag is {#targeting-profiles-whose-birthday-is-today}

Het volgende voorbeeld toont een vraagactiviteit die aan doelprofielen wordt gevormd de waarvan verjaardag vandaag is.

1. Sleep het **[!UICONTROL Birthday]** filter in uw vraag.

   ![](assets/query_sample_birthday.png)

1. Stel de **[!UICONTROL Filter type]** optie in op **[!UICONTROL Relative]** en selecteer **[!UICONTROL Today]**.

   ![](assets/query_sample_birthday2.png)

## Doelprofielen die een specifieke levering hebben geopend {#targeting-profiles-who-opened-a-specific-delivery}

In het volgende voorbeeld ziet u een query-activiteit die is geconfigureerd voor filterprofielen die de levering hebben geopend met het label &#39;Zomertijd&#39;.

1. Sleep het **[!UICONTROL Opened]** filter in uw vraag.

   ![](assets/query_sample_opened.png)

1. Selecteer de levering en klik op **[!UICONTROL Confirm]**.

   ![](assets/query_sample_opened2.png)

## Doelprofielen waarvoor leveringen om een bepaalde reden zijn mislukt {#targeting-profiles-for-whom-deliveries-failed-for-a-specific-reason}

Het volgende voorbeeld toont een vraagactiviteit die aan filterprofielen wordt gevormd voor wie de leveringen ontbraken omdat hun brievenbus volledig was. Deze query is alleen beschikbaar voor gebruikers met beheerrechten die tot de **[!UICONTROL All (all)]** organisatie-eenheden behoren (zie [deze sectie](../../administration/using/organizational-units.md)).

1. Selecteer het **[!UICONTROL Delivery logs]** middel om direct in de lijst van het leveringslogboek te filtreren (zie het [Gebruiken van middelen verschillend van het richten van dimensies](../../automating/using/using-resources-different-from-targeting-dimensions.md)).

   ![](assets/query_sample_failure1.png)

1. Sleep het **[!UICONTROL Nature of failure]** filter in uw vraag.

   ![](assets/query_sample_failure2.png)

1. Selecteer het type fout dat u als doel wilt instellen. In ons geval **[!UICONTROL Mailbox full]**.

   ![](assets/query_sample_failure3.png)

## Doelprofielen waarmee geen contact is opgenomen in de afgelopen 7 dagen {#targeting-profiles-not-contacted-during-the-last-7-days}

In het volgende voorbeeld ziet u een queryactiviteit die is geconfigureerd voor filterprofielen die tijdens de laatste 7 dagen niet zijn benaderd.

1. Sleep het **[!UICONTROL Delivery logs (logs)]** filter in uw vraag.

   ![](assets/query_sample_7days.png)

   Selecteer **[!UICONTROL Does not exist]** in de vervolgkeuzelijst en sleep het **[!UICONTROL Delivery]** filter.

   ![](assets/query_sample_7days1.png)

1. Configureer het filter zoals hieronder.

   ![](assets/query_sample_7days2.png)

## Doelprofielen die op een specifieke koppeling hebben geklikt {#targeting-profiles-who-clicked-a-specific-link-}

1. Sleep het **[!UICONTROL Tracking logs (tracking)]** filter in uw vraag.

   ![](assets/query_sample_trackinglogs.png)

1. Sleep het **[!UICONTROL Label (urlLabel)]** filter.

   ![](assets/query_sample_trackinglogs2.png)

1. Typ in het **[!UICONTROL Value]** veld het label dat is gedefinieerd bij het invoegen van de koppeling in de levering en bevestig vervolgens de koppeling.

   ![](assets/query_sample_trackinglogs3.png)
