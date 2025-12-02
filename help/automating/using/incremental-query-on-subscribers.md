---
title: Incrementele query op leden van een service
description: Het volgende voorbeeld stelt voor hoe te om een Incrementele vraagactiviteit te vormen om abonnees aan de dienst te filtreren.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: incremental,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: c80ed1f6-ad8a-4448-a6df-b9881327228a
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 61%

---

# Incrementele query op leden van een service {#example--incremental-query-on-subscribers-to-a-service}

In het volgende voorbeeld wordt de configuratie getoond van een activiteit **[!UICONTROL Incremental query]** die de profielen in de Adobe Campaign-database filtert die zijn geabonneerd op de dienst **Running Newsletter**, om hen een welkomstbericht met een aanbieding te sturen.

De workflow bestaat uit de volgende elementen:

![](assets/incremental_query_example1.png)

* A [ Planner ](../../automating/using/scheduler.md) activiteit, om het werkschema elke Maandag om 6 uur uit te voeren.

  ![](assets/incremental_query_example2.png)

* Een [ Incrementele vraag ](../../automating/using/incremental-query.md) activiteit, die alle huidige abonnees tijdens de eerste uitvoering richt, dan slechts de nieuwe abonnees van die week tijdens de volgende uitvoeringen.

  ![](assets/incremental_query_example3.png)

* Een [ E-maillevering ](../../automating/using/email-delivery.md) activiteit. De workflow wordt één keer per week uitgevoerd, maar u kunt de verzonden e-mails en de resultaten per maand samenvoegen, om bijvoorbeeld rapporten te genereren over een periode van een hele maand en niet slechts één week.

  U doet dit door een **[!UICONTROL Recurring email]** **[!UICONTROL By month]** te maken om de e-mails en de resultaten te hergroeperen.

  Definieer de inhoud van uw e-mail en voeg de code van de welkomstaanbieding in. Voor meer op dit, verwijs naar [ het bepalen van e-mailinhoud ](../../designing/using/personalization.md) secties.

Start vervolgens de workflowuitvoering. Elke week ontvangen nieuwe abonnees het welkomstbericht met de promocode.
