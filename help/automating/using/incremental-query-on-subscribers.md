---
solution: Campaign Standard
product: campaign
title: Incrementele query op abonnees van een service
description: Het volgende voorbeeld stelt voor hoe te om een Incrementele vraagactiviteit te vormen om abonnees aan de dienst te filtreren.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: incremental,main
feature: Workflows
role: Gegevensarchitect
level: Intermediair
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 66%

---


# Incrementele query op abonnees van een service {#example--incremental-query-on-subscribers-to-a-service}

In het volgende voorbeeld wordt de configuratie getoond van een activiteit **[!UICONTROL Incremental query]** die de profielen in de Adobe Campaign-database filtert die zijn geabonneerd op de dienst **Running Newsletter**, om hen een welkomstbericht met een aanbieding te sturen.

De workflow bestaat uit de volgende elementen:

![](assets/incremental_query_example1.png)

* A [Scheduler](../../automating/using/scheduler.md) activiteit, om de werkstroom elke Maandag om 6 uur uit te voeren.

   ![](assets/incremental_query_example2.png)

* Een [Incrementele vraag](../../automating/using/incremental-query.md) activiteit, die alle huidige abonnees tijdens de eerste uitvoering richt, dan slechts de nieuwe abonnees van die week tijdens de volgende uitvoeringen.

   ![](assets/incremental_query_example3.png)

* An [Email delivery](../../automating/using/email-delivery.md) activity. De workflow wordt één keer per week uitgevoerd, maar u kunt de verzonden e-mails en de resultaten per maand samenvoegen, om bijvoorbeeld rapporten te genereren over een periode van een hele maand en niet slechts één week.

   U doet dit door een **[!UICONTROL Recurring email]** **[!UICONTROL By month]** te maken om de e-mails en de resultaten te hergroeperen.

   Definieer de content van uw e-mail en voer de promocode in. Raadpleeg de secties [E-mailinhoud definiëren](../../designing/using/personalization.md) voor meer informatie.

Start vervolgens de workflowuitvoering. Elke week ontvangen nieuwe abonnees het welkomstbericht met de promocode.
