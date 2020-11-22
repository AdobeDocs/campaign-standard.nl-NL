---
solution: Campaign Standard
product: campaign
title: Campaign-berichten personaliseren met Point of Interest-data
description: Leer hoe te om een gepersonaliseerd bericht tot stand te brengen dat op de plaats van uw abonnees met de de gegevensintegratie van het Punt van Interesse wordt gebaseerd.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics-for-mobile
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 10%

---


# Campaign-berichten personaliseren met Point of Interest-data{#personalizing-campaign-messages-with-point-of-interest-data}

In Adobe Campaign kunt u de interessepunten die zijn verzameld bij de abonnees van uw mobiele toepassing gebruiken om persoonlijke marketingberichten, zoals een e-mail, te verzenden.

U kunt alleen reageren op Point of Interest-gegevens met standaardleveringen. [Transactieberichten](../../channels/using/getting-started-with-transactional-msg.md) kunnen geen locatiegegevens gebruiken.

De vroegste reactie is ongeveer 10 minuten.

In dit geval besluit u een e-mail te sturen naar alle abonnees die uw winkel in Boston in de afgelopen twee weken hebben bezocht.

1. Maak een e-mailmarketingactiviteit.
1. Wanneer u het publiek van de levering definieert, sleept u het **[!UICONTROL Subscriptions to an application]** element naar de werkruimte.

   ![](assets/poi_subscriptions_app.png)

   Het beheren van het publiek wordt gedetailleerd beschreven in de sectie [Het publiek](../../audiences/using/creating-audiences.md) definiëren.

1. In the **[!UICONTROL Add a rule - Profile/Subscriptions to an application]** window, drag and drop the **[!UICONTROL POI Location Subscription]** element into the workspace.

   ![](assets/poi_add_rule_profile_subscription.png)

1. Voer in het **[!UICONTROL Add a rule - POI Location Subscription]** venster het label in van het Point of Interest dat u wilt gebruiken.

   ![](assets/poi_location_subscription.png)

1. Selecteer in het veld **[!UICONTROL Filter type]** de optie **[!UICONTROL Relative]**.
1. Schakel de **[!UICONTROL Preceding days]** optie in en typ **[!UICONTROL 15]** het desbetreffende veld.
1. Bepaal het aantal tijden de gebruiker het Punt van Interesse moet hebben bezocht.
1. Click **[!UICONTROL Confirm]** to save your audience.

   ![](assets/poi_subscriptions_app_audience_defined.png)

1. Voeg inhoud toe aan uw e-mail.

   ![](assets/poi_email_content.png)

1. Bevestig dat u de activiteit maakt om het dashboard van de e-mail weer te geven.
1. Verzend uw bericht.

De e-mail met de korting van 10% wordt verzonden naar abonnees die:

* In de afgelopen twee weken heeft u minstens één keer een bezoek gebracht aan uw winkel in Boston.
* Houd uw mobiele toepassing tijdens het bezoek minstens één keer op de voorgrond.

**Verwante onderwerpen:**

* [Een e-mail maken](../../channels/using/creating-an-email.md)
* [Inhoud definiëren](../../designing/using/personalization.md#example-email-personalization)
* [Berichten verzenden](../../sending/using/confirming-the-send.md)

