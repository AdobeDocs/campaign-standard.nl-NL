---
solution: Campaign Standard
product: campaign
title: CCPA-opt-out beheren
description: Leer hoe u de optie CCPA-uitsluiting beheert met API's
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 4%

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
>Raadpleeg voor meer informatie de documentatie bij [het](../../start/using/privacy-requests.md#sale-of-personal-information-ccpa)beheren van privacyverzoeken.

<br/>

***Voorbeeldverzoeken***

* De vraag van de GET van de steekproef om de optiestatus van CCPA van een profiel terug te winnen.

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profilesAndServices/profile/<PKEY> \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>' \
   -H 'Content-Type: application/json;charset=utf-8'
   ```

   Antwoord op het verzoek van de GET.

   ```
   {
   "PKey": "<PKEY>",
     "ccpaOptOut": false,
     "firstName": "John",
     "lastName": "Doe",
   ...
   }
   ```

* De vraag van de POST van de steekproef om een profiel voor opt-out CCPA te merken.

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

   Antwoord op het verzoek van de GET.

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

* Voorbeeld van PATCH-verzoek om een profiel voor CCPA-opt-out bij te werken.

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

   Antwoord op het verzoek van de GET.

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
