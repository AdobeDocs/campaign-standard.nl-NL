---
title: Incrementele query op abonnees van een service
description: Het volgende voorbeeld stelt voor hoe te om een Incrementele vraagactiviteit te vormen om abonnees aan de dienst te filtreren.
page-status-flag: never-activated
uuid: 73b42422-e815-43ef-84c0-97c4433ccc98
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 80961e73-42ec-463a-8496-cff69fab0475
context-tags: incremental,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7ffa48365875883a98904d6b344ac005afe26e18
workflow-type: tm+mt
source-wordcount: '211'
ht-degree: 0%

---


# Incrementele query op abonnees van een service {#example--incremental-query-on-subscribers-to-a-service}

In het volgende voorbeeld wordt de configuratie getoond van een **[!UICONTROL Incremental query]** activiteit die de profielen in de Adobe Campaign-database filtert die zijn geabonneerd op de service **Running Newsletter** , om hen een welkomstbericht met een promo-code te sturen.

De workflow bestaat uit de volgende elementen:

![](assets/incremental_query_example1.png)

* Een [Planneractiviteit](../../automating/using/scheduler.md) , om de werkschema uit te voeren elke Maandag om 6.00 uur.

   ![](assets/incremental_query_example2.png)

* Een [Incrementele vraagactiviteit](../../automating/using/incremental-query.md) , die alle huidige abonnees tijdens de eerste uitvoering richt, toen slechts de nieuwe abonnees van die week tijdens de volgende uitvoeringen.

   ![](assets/incremental_query_example3.png)

* Een [e-mailleveringsactiviteit](../../automating/using/email-delivery.md) . De workflow wordt één keer per week uitgevoerd, maar u kunt de verzonden e-mails en de resultaten per maand samenvoegen, bijvoorbeeld om rapporten te genereren over een periode van een hele maand en niet slechts één week.

   U doet dit door een nieuwe e-mail en de resultaten te hergroeperen **[!UICONTROL Recurring email]** **[!UICONTROL By month]**.

   Definieer de inhoud van uw e-mail en voeg de code van de welkomstaanbieding in. Raadpleeg de secties [E-mailinhoud](../../designing/using/personalization.md) definiëren voor meer informatie.

Start vervolgens de workflowuitvoering. Elke week ontvangen de nieuwe abonnees het welkomstbericht met de promotiecode.
