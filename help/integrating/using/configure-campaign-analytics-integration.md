---
title: De integratie van Campaign-Analytics configureren
description: Leer hoe u de integratie met Adobe Analytics configureert om het succes van uw e-mailleveringen te meten.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
feature: Triggers
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: a6748b4b-36c5-4961-a599-ace73a8504cc
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 7%

---

# De integratie van Campaign-Analytics configureren{#configure-campaign-analytics-integration}

Dankzij deze integratie kunt u uw gegevens in de prestatiekernindicator rechtstreeks van Adobe Campaign naar Adobe Analytics Standard of Premium delen.

Als u de integratie tussen Adobe Campaign Standard en Adobe Analytics wilt starten, moet u eerst de externe account configureren die aan Adobe Analytics is gekoppeld.

Externe accounts en technische workflows kunnen alleen worden beheerd door de functionele beheerder van het platform.

1. Selecteer **[!UICONTROL Administration > Application settings > External accounts]** in het geavanceerde menu via het Adobe Campaign-logo.
1. Selecteer de **[!UICONTROL Share KPIs with Adobe Analytics]** externe account.

   ![](assets/analytics_2.png)

1. Geef de **[!UICONTROL Web services user name]** en **[!UICONTROL Web services share secret]** op in het veld **[!UICONTROL Connection]** .

   U vindt deze parameters in Analytics door **[!UICONTROL Admin > Company settings > Web services]** te selecteren.

   ![](assets/analytics_1.png)

1. Klik op de knop **[!UICONTROL Refresh report suites]**.
1. Selecteer in de vervolgkeuzelijst **[!UICONTROL Analytics default report suite]** de Adobe Analytics-rapportsuite die u wilt verrijken met Adobe Campaign-gegevens.

   Je externe account is nu klaar en gekoppeld aan Adobe Analytics. U kunt deze functie op elk gewenst moment uitschakelen door het selectievakje **[!UICONTROL Enabled]** in te schakelen.

   ![](assets/analytics.png)

De technische workflow van **[!UICONTROL Share KPIs with Adobe Analytics]** wordt nu automatisch gestart en kan worden weergegeven vanuit het geavanceerde menu door **[!UICONTROL Administration > Application settings > Workflow]** te selecteren. Deze technische werkstroom kan tot 6 maanden oude uitzendingen behouden. Deze workflow is incrementeel en wordt gebruikt voor het verzenden van gegevens van de vorige dag.

![](assets/analytics_3.png)

Je gegevens zijn nu beschikbaar in Adobe Analytics.

**Verwante onderwerpen:**

* [Externe accounts](../../administration/using/external-accounts.md)
* [Technische workflows](../../administration/using/technical-workflows.md)
* [ KPIs van het Aandeel voor geïntegreerde Campagne die ](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html) video meldt
