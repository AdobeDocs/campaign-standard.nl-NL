---
solution: Campaign Standard
product: campaign
title: Een workflow beheren
description: Leer hoe u een workflow kunt besturen met API's.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Gegevensengineer
level: Ervaren
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '100'
ht-degree: 10%

---


# Een workflow beheren {#controlling-a-workflow}

U kunt een werkstroom rechtstreeks vanuit de REST API besturen via een verzoek van een POST met de werkstroom-id en de vereiste uitvoeringsopdracht:

`POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands`

>[!CAUTION]
>
>Als de workflow-id in Adobe Campaign wordt gewijzigd, werkt de API-aanvraag niet meer.

Er zijn vier uitvoeringsopdrachten beschikbaar om een workflow te besturen:

* Starten
* Pauzeren
* Hervatten
* Stoppen

Raadpleeg de [Campagne-documentatie](https://docs.adobe.com/content/help/en/campaign-standard/using/managing-processes-and-data/executing-a-workflow/about-workflow-execution.html) voor meer informatie over de uitvoeringsopdrachten.

<br/>

***Voorbeeldverzoeken***

* Start een workflow.

   ```
   -X POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>' \
   -i
   -d '{"method":"start"}'
   ```

   <!-- + réponse -->

* Stop een workflow.

   ```
   -X POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>' \
   -i
   -d '{"method":"stop"}'
   ```

   <!-- + réponse -->
