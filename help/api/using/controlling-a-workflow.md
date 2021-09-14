---
title: Een workflow beheren
description: Leer hoe u een workflow kunt besturen met API's.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 79eacc31-d5a2-4e13-aa0b-744d7ab7004f
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '94'
ht-degree: 12%

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

Raadpleeg de [Campagne-documentatie](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/executing-a-workflow/about-workflow-execution.html) voor meer informatie over de uitvoeringsopdrachten.

<br/>

***Voorbeeldverzoeken***

* Een workflow starten.

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
