---
title: De integratie van Campaign-Analytics configureren
description: Leer hoe u de integratie met Adobe Analytics configureert om het succes van uw e-mailleveringen te meten.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: a6748b4b-36c5-4961-a599-ace73a8504cc
source-git-commit: 26260b9e633d8be1652eeb46c982864a7477da27
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 9%

---

# De integratie van Campaign-Analytics configureren{#configure-campaign-analytics-integration}

Dankzij deze integratie kunt u uw gegevens in de prestatiekernindicator rechtstreeks van Adobe Campaign naar Adobe Analytics Standard of Premium delen.

Als u de integratie tussen Adobe Campaign Standard en Adobe Analytics wilt starten, moet u eerst de externe account configureren die aan Adobe Analytics is gekoppeld.

Externe accounts en technische workflows kunnen alleen worden beheerd door de functionele beheerder van het platform.

1. Selecteer in het geavanceerde menu via het Adobe Campaign-logo de optie **[!UICONTROL Administration > Application settings > External accounts]**.
1. Selecteer **[!UICONTROL Share KPIs with Adobe Analytics]** externe rekening.

   ![](assets/analytics_2.png)

1. Geef uw **[!UICONTROL Web services user name]** en **[!UICONTROL Web services share secret]** in de **[!UICONTROL Connection]** veld.

   U vindt deze parameters in Analytics door **[!UICONTROL Admin > Company settings > Web services]**.

   ![](assets/analytics_1.png)

1. Klik op de knop **[!UICONTROL Refresh report suites]**.
1. Selecteren in het dialoogvenster **[!UICONTROL Analytics default report suite]** vervolgkeuzelijst met Adobe Analytics-rapporten die u wilt verrijken met Adobe Campaign-gegevens.

   Je externe account is nu klaar en gekoppeld aan Adobe Analytics. U kunt deze op elk gewenst moment uitschakelen door de knop **[!UICONTROL Enabled]** doos.

   ![](assets/analytics.png)

De **[!UICONTROL Share KPIs with Adobe Analytics]** de technische workflow wordt nu automatisch gestart en kan worden weergegeven via het menu Geavanceerd door **[!UICONTROL Administration > Application settings > Workflow]**. Deze technische werkstroom kan tot 6 maanden oude uitzendingen behouden. Deze workflow is incrementeel en wordt gebruikt voor het verzenden van gegevens van de vorige dag.

![](assets/analytics_3.png)

Je gegevens zijn nu beschikbaar in Adobe Analytics.

**Verwante onderwerpen:**

* [Externe accounts](../../administration/using/external-accounts.md)
* [Technische workflows](../../administration/using/technical-workflows.md)
* [KPI&#39;s delen voor geïntegreerde campagnerapportage](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html) video
