---
solution: Campaign Standard
product: campaign
title: De integratie van Campaign en Analytics configureren
description: Leer hoe u de integratie met Adobe Analytics configureert om het succes van uw e-mailleveringen te meten.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 9%

---


# De integratie van Campaign en Analytics configureren{#configure-campaign-analytics-integration}

Dankzij deze integratie kunt u uw gegevens in de prestatiekernindicator rechtstreeks van Adobe Campaign naar Adobe Analytics Standard of Premium delen.

Als u de integratie tussen Adobe Campaign Standard en Adobe Analytics wilt starten, moet u eerst de externe account configureren die aan Adobe Analytics is gekoppeld.

Externe accounts en technische workflows kunnen alleen worden beheerd door de functionele beheerder van het platform.

1. From the advanced menu, via the Adobe Campaign logo, select **[!UICONTROL Administration > Application settings > External accounts]**.
1. Select the **[!UICONTROL Share KPIs with Adobe Analytics]** external account.

   ![](assets/analytics_2.png)

1. Geef uw **[!UICONTROL Web services user name]** en **[!UICONTROL Web services share secret]** in het **[!UICONTROL Connection]** veld op.

   U vindt deze parameters in Analytics door deze te selecteren **[!UICONTROL Admin > Company settings > Web services]**.

   ![](assets/analytics_1.png)

1. Klik op de knop **[!UICONTROL Refresh report suites]**.
1. Selecteer in de **[!UICONTROL Analytics default report suite]** vervolgkeuzelijst de Adobe Analytics-rapportsuite die u wilt verrijken met Adobe Campaign-gegevens.

   Je externe account is nu klaar en gekoppeld aan Adobe Analytics. U kunt deze functie op elk gewenst moment uitschakelen door het **[!UICONTROL Enabled]** selectievakje in te schakelen.

   ![](assets/analytics.png)

De **[!UICONTROL Share KPIs with Adobe Analytics]** technische workflow wordt nu automatisch gestart en kan worden weergegeven in het menu Geavanceerd door **[!UICONTROL Administration > Application settings > Workflow]** te selecteren. Deze technische workflow wordt automatisch elke 15 minuten uitgevoerd en er worden maximaal 6 maanden oude gegevens in Adobe Analytics opgestuwd.

![](assets/analytics_3.png)

Je gegevens zijn nu beschikbaar in Adobe Analytics.

**Verwante onderwerpen:**

* [Externe accounts](../../administration/using/external-accounts.md)
* [Technische workflows](../../administration/using/technical-workflows.md)
* [KPI&#39;s delen voor geïntegreerde Campagne die video rapporteert](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html)

