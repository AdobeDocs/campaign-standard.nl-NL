---
title: Workflows beheren
description: Leer hoe u een workflow kunt besturen met API's.
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: aee0e0437cbfe578cb2f715a2433099c79dd1748

---


# Workflows beheren {#controlling-a-workflow}

U kunt een workflow rechtstreeks vanuit de REST API beheren via een POST-aanvraag met de workflow-id en de vereiste uitvoeringsopdracht:

`POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands`

>[!CAUTION]
>
>Als de werklow-id wordt gewijzigd in Adobe Campaign, werkt de API-aanvraag niet meer.

Er zijn vier uitvoeringsopdrachten beschikbaar om een workflow te besturen:

* Start
* Pauzeren
* Hervatten
* Stoppen

Raadpleeg de documentatie bij [Campagne voor meer informatie over de uitvoeringsopdrachten](https://helpx.adobe.com/campaign/standard/automating/using/executing-a-workflow.html).

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
