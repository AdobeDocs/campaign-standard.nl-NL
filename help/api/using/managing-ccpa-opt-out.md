---
title: CCPA-opt-out beheren
description: Leer hoe u de optie CCPA-uitsluiting beheert met API's
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


# CCPA-opt-out beheren {#managing-ccpa-optout}

De optiestatus van een profiel voor CCPA-bestanden kan worden gecontroleerd en beheerd met behulp van het **profiel ccpaOptOut** en de waarden &quot;true&quot; of &quot;false&quot;:

`"ccpaOptOut": <value>`

* **true**:  verbiedt de verkoop van persoonlijke informatie.
* **false**: de verkoop van persoonlijke gegevens toestaat.

>[!CAUTION]
>
>Het kenmerk &quot;Opt-Out CCPA&quot; is alleen beschikbaar vanaf 19.4. Voor 19.3-omgevingen moet u de profielbron uitbreiden en een Booleaans veld toevoegen. Dit veld wordt met het gekozen label toegevoegd aan de API. Wij adviseren u &quot;Opt-Out voor CCPA&quot;gebruikt.
>
>Raadpleeg de documentatie [over](https://helpx.adobe.com/campaign/kb/acs-privacy.html#ccpa)privacybeheer voor meer informatie.

<br/>

***Voorbeeldverzoeken***

* De steekproef krijgt verzoek om van een profiel uit te winnen CCPA opt-out status.

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profilesAndServices/profile/<PKEY> \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>' \
   -H 'Content-Type: application/json;charset=utf-8'
   ```

   Antwoord op het GET verzoek.

   ```
   {
   "PKey": "<PKEY>",
     "ccpaOptOut": false,
     "firstName": "John",
     "lastName": "Doe",
   ...
   }
   ```

* Voorbeeld van POST-verzoek om een profiel voor CCPA-opt-out te markeren.

   ```
   -X POST https://mc.adobe.io/<ORGANIZATION>/campaign/profilesAndServices/profile/ \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>' \
   -H 'Content-Type: application/json;charset=utf-8'
   -i
   -d {
   -d  "firstName": "John",
   -d  "lastName": "Doe",
   -d  "email": "jdoe@mail.com",
   -d  "ccpaOptOut": true
   -d }'
   ```

   Antwoord op het GET verzoek.

   ```
   {
       ...
       "email": "john.doe@mail.com",
       "firstName": "John",
       "lastName": "Doe",
       "ccpaOptOut": true,
       ...
   }
   ```

* Voorbeeld van PATCH-aanvraag om een profiel voor CCPA-opt-out bij te werken.

   ```
   -X PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profilesAndServices/profile/<PKEY> \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>' \
   -H 'Content-Type: application/json;charset=utf-8'
   -i
   -d {
   -d  "ccpaOptOut": true
   -d }'
   ```

   Antwoord op het GET verzoek.

   ```
   {
       ...
       "email": "john.doe@mail.com",
       "firstName": "John",
       "lastName": "Doe",
       "ccpaOptOut": true,
       ...
   }
   ```
