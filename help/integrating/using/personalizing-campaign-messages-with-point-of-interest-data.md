---
title: Campaign-berichten personaliseren met gegevens van Point of Interest
description: Leer hoe te om een gepersonaliseerd bericht tot stand te brengen dat op de plaats van uw abonnees met de de gegevensintegratie van het Punt van Interesse wordt gebaseerd.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics-for-mobile
feature: Audiences
role: Data Architect
level: Intermediate
exl-id: fcc79829-902d-4547-87c5-8a213e1257b7
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 9%

---

# Campaign-berichten personaliseren met gegevens van Point of Interest{#personalizing-campaign-messages-with-point-of-interest-data}

In Adobe Campaign kunt u de interessepunten die zijn verzameld bij de abonnees van uw mobiele toepassing gebruiken om persoonlijke marketingberichten, zoals een e-mail, te verzenden.

U kunt alleen reageren op Point of Interest-gegevens met standaardleveringen. [Transactieberichten](../../channels/using/getting-started-with-transactional-msg.md) kan geen locatiegegevens gebruiken.

De vroegste reactie is ongeveer 10 minuten.

In dit geval besluit u een e-mail te sturen naar alle abonnees die uw winkel in Boston in de afgelopen twee weken hebben bezocht.

1. Maak een e-mailmarketingactiviteit.
1. Wanneer het bepalen van het publiek van de levering, sleep en laat vallen **[!UICONTROL Subscriptions to an application]** in de werkruimte.

   ![](assets/poi_subscriptions_app.png)

   Het beheren van het publiek wordt beschreven in het dialoogvenster [Soorten publiek definiëren](../../audiences/using/creating-audiences.md) sectie.

1. In de **[!UICONTROL Add a rule - Profile/Subscriptions to an application]** venster, slepen en neerzetten **[!UICONTROL POI Location Subscription]** in de werkruimte.

   ![](assets/poi_add_rule_profile_subscription.png)

1. In de **[!UICONTROL Add a rule - POI Location Subscription]** voert u het label in van het Point of Interest dat u wilt gebruiken.

   ![](assets/poi_location_subscription.png)

1. Selecteer in het veld **[!UICONTROL Filter type]** de optie **[!UICONTROL Relative]**.
1. Controleer de **[!UICONTROL Preceding days]** en voert u **[!UICONTROL 15]** in het desbetreffende veld.
1. Bepaal het aantal tijden de gebruiker het Punt van Interesse moet hebben bezocht.
1. Klikken **[!UICONTROL Confirm]** om uw publiek op te slaan.

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
