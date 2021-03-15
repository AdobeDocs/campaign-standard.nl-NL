---
solution: Campaign Standard
product: campaign
title: De integratie van Campaign en Analytics configureren
description: Leer hoe u de integratie met Adobe Analytics configureert om het succes van uw e-mailleveringen te meten.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
feature: Triggers
role: Gegevensarchitect
level: Intermediair
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 9%

---


# De integratie van Campaign en Analytics configureren{#configure-campaign-analytics-integration}

Dankzij deze integratie kunt u uw gegevens in de prestatiekernindicator rechtstreeks van Adobe Campaign naar Adobe Analytics Standard of Premium delen.

Als u de integratie tussen Adobe Campaign Standard en Adobe Analytics wilt starten, moet u eerst de externe account configureren die aan Adobe Analytics is gekoppeld.

Externe accounts en technische workflows kunnen alleen worden beheerd door de functionele beheerder van het platform.

1. Selecteer **[!UICONTROL Administration > Application settings > External accounts]** in het geavanceerde menu via het Adobe Campaign-logo.
1. Selecteer de externe account **[!UICONTROL Share KPIs with Adobe Analytics]**.

   ![](assets/analytics_2.png)

1. Geef uw **[!UICONTROL Web services user name]** en **[!UICONTROL Web services share secret]** op in het veld **[!UICONTROL Connection]**.

   Deze parameters vindt u in Analytics door **[!UICONTROL Admin > Company settings > Web services]** te selecteren.

   ![](assets/analytics_1.png)

1. Klik op de knop **[!UICONTROL Refresh report suites]**.
1. Selecteer in de vervolgkeuzelijst **[!UICONTROL Analytics default report suite]** de Adobe Analytics-rapportsuite die u wilt verrijken met Adobe Campaign-gegevens.

   Je externe account is nu klaar en gekoppeld aan Adobe Analytics. U kunt het op elk ogenblik onbruikbaar maken door **[!UICONTROL Enabled]** doos te controleren.

   ![](assets/analytics.png)

De technische workflow **[!UICONTROL Share KPIs with Adobe Analytics]** wordt nu automatisch gestart en kan worden weergegeven vanuit het geavanceerde menu door **[!UICONTROL Administration > Application settings > Workflow]** te selecteren. Deze technische workflow wordt automatisch elke 15 minuten uitgevoerd en er worden maximaal 6 maanden oude gegevens in Adobe Analytics opgestuwd.

![](assets/analytics_3.png)

Je gegevens zijn nu beschikbaar in Adobe Analytics.

**Verwante onderwerpen:**

* [Externe accounts](../../administration/using/external-accounts.md)
* [Technische workflows](../../administration/using/technical-workflows.md)
* [KPI&#39;s delen voor geïntegreerde ](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html) rapportage van campagnes

