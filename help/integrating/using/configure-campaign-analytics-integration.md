---
title: Integratie van Campagne-Analytics configureren
description: Leer hoe u de integratie met Adobe Analytics configureert om te bepalen of uw e-mailberichten succesvol zijn.
page-status-flag: never-activated
uuid: bdaa00b0-7445-469c-8268-9d06c53ce2b0
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
discoiquuid: 92b9004c-cba0-41fd-a035-32bee1d6a42c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Integratie van Campagne-Analytics configureren{#configure-campaign-analytics-integration}

Dankzij deze integratie kunt u uw gegevens in de prestatiekernindicator rechtstreeks delen, van Adobe Campagne tot Adobe Analytics Standard of Premium.

Als u de integratie tussen Adobe Campaign Standard en Adobe Analytics wilt starten, moet u eerst het externe account configureren dat is gekoppeld aan Adobe Analytics.

Externe accounts en technische workflows kunnen alleen worden beheerd door de functionele beheerder van het platform.

1. Selecteer in het menu Geavanceerd via het Adobe Campagne-logo **[!UICONTROL Administration > Application settings > External accounts]**.
1. Selecteer de **[!UICONTROL Share KPIs with Adobe Analytics]** externe account.

   ![](assets/analytics_2.png)

1. Geef uw **[!UICONTROL Web services user name]** en **[!UICONTROL Web services share secret]** in het **[!UICONTROL Connection]** veld op.

   U vindt deze parameters in Analytics door deze te selecteren **[!UICONTROL Admin > Company settings > Web services]**.

   ![](assets/analytics_1.png)

1. Klik op de **[!UICONTROL Refresh report suites]** knop.
1. Selecteer in de **[!UICONTROL Analytics default report suite]** vervolgkeuzelijst de rapportsuite van Adobe Analytics die u wilt verrijken met Adobe Campagne-gegevens.

   Uw externe account is nu klaar en gekoppeld aan Adobe Analytics. U kunt deze functie op elk gewenst moment uitschakelen door het **[!UICONTROL Enabled]** selectievakje in te schakelen.

   ![](assets/analytics.png)

De **[!UICONTROL Share KPIs with Adobe Analytics]** technische workflow wordt nu automatisch gestart en kan worden weergegeven in het menu Geavanceerd door **[!UICONTROL Administration > Application settings > Workflow]** te selecteren. Deze technische workflow wordt automatisch elke 15 minuten uitgevoerd en er worden maximaal 6 maanden oude gegevens in Adobe Analytics opgehaald.

![](assets/analytics_3.png)

Uw gegevens zijn nu beschikbaar in Adobe Analytics.

**Verwante onderwerpen:**

* [Externe rekeningen](../../administration/using/external-accounts.md)
* [Technische workflows](../../administration/using/technical-workflows.md)
* [KPI&#39;s delen voor geïntegreerde Campagne die video rapporteert](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html)

