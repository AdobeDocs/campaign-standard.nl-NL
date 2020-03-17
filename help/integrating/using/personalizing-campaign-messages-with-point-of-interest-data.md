---
title: Campagneberichten aanpassen met gegevens van het Punt
description: Leer hoe te om een gepersonaliseerd bericht tot stand te brengen dat op de plaats van uw abonnees met de de gegevensintegratie van het Punt van Interesse wordt gebaseerd.
page-status-flag: never-activated
uuid: d74c3e55-f130-441b-bc2a-06ddcd5d9784
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics-for-mobile
discoiquuid: a1736ba3-5121-4d01-bf04-ebb7e701e2e0
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Campagneberichten aanpassen met gegevens van het Punt{#personalizing-campaign-messages-with-point-of-interest-data}

In Adobe Campagne kunt u de gegevens van de Punten van Interesse gebruiken die van de abonnees van uw mobiele toepassing worden verzameld om hen gepersonaliseerde marketing berichten, zoals een e-mail te verzenden.

U kunt alleen reageren op Point of Interest-gegevens met standaardleveringen. [Transactieberichten](../../channels/using/about-transactional-messaging.md) kunnen geen locatiegegevens gebruiken.

De vroegste reactie is ongeveer 10 minuten.

In dit geval besluit u een e-mail te sturen naar alle abonnees die uw winkel in Boston in de afgelopen twee weken hebben bezocht.

1. Maak een e-mailmarketingactiviteit.
1. Wanneer u het publiek van de levering definieert, sleept u het **[!UICONTROL Subscriptions to an application]** element naar de werkruimte.

   ![](assets/poi_subscriptions_app.png)

   Het beheren van het publiek wordt gedetailleerd beschreven in de sectie [Het publiek](../../audiences/using/creating-audiences.md) definiëren.

1. Sleep het **[!UICONTROL Add a rule - Profile/Subscriptions to an application]** element in het **[!UICONTROL POI Location Subscription]** venster naar de werkruimte.

   ![](assets/poi_add_rule_profile_subscription.png)

1. Voer in het **[!UICONTROL Add a rule - POI Location Subscription]** venster het label in van het Point of Interest dat u wilt gebruiken.

   ![](assets/poi_location_subscription.png)

1. Selecteer in het **[!UICONTROL Filter type]** veld **[!UICONTROL Relative]**.
1. Schakel de **[!UICONTROL Preceding days]** optie in en typ **[!UICONTROL 15]** het desbetreffende veld.
1. Bepaal het aantal tijden de gebruiker het Punt van Interesse moet hebben bezocht.
1. Klik **[!UICONTROL Confirm]** om uw publiek op te slaan.

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

