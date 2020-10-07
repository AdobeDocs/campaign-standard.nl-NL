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
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '211'
ht-degree: 67%

---


# Incrementele query op abonnees van een service {#example--incremental-query-on-subscribers-to-a-service}

In het volgende voorbeeld wordt de configuratie getoond van een activiteit **[!UICONTROL Incremental query]** die de profielen in de Adobe Campaign-database filtert die zijn geabonneerd op de dienst **Running Newsletter**, om hen een welkomstbericht met een aanbieding te sturen.

De workflow bestaat uit de volgende elementen:

![](assets/incremental_query_example1.png)

* A [Scheduler](../../automating/using/scheduler.md) activity, to execute the workflow every Monday at 6 am.

   ![](assets/incremental_query_example2.png)

* An [Incremental query](../../automating/using/incremental-query.md) activity, which targets all of the current subscribers during the first execution, then only the new subscribers of that week during the following executions.

   ![](assets/incremental_query_example3.png)

* Een [e-mailleveringsactiviteit](../../automating/using/email-delivery.md) . De workflow wordt één keer per week uitgevoerd, maar u kunt de verzonden e-mails en de resultaten per maand samenvoegen, om bijvoorbeeld rapporten te genereren over een periode van een hele maand en niet slechts één week.

   U doet dit door een **[!UICONTROL Recurring email]** **[!UICONTROL By month]** te maken om de e-mails en de resultaten te hergroeperen.

   Definieer de content van uw e-mail en voer de promocode in. Raadpleeg de secties [E-mailinhoud](../../designing/using/personalization.md) definiëren voor meer informatie.

Start vervolgens de workflowuitvoering. Elke week ontvangen nieuwe abonnees het welkomstbericht met de promocode.
