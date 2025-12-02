---
title: CCPA-opt-out beheren
description: Leer hoe u de optie CCPA-uitsluiting beheert met API's
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
old-role: Data Architect
role: Developer
level: Experienced
exl-id: bfc52511-f66f-4948-a939-d0d77e8ef03c
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 6%

---

# CCPA-opt-out beheren {#managing-ccpa-optout}

De opt-outstatus van CCPA van een profiel kan worden gecontroleerd en worden geleid gebruikend **ccpaOptOut** profielattributen en de &quot;waar&quot;of &quot;vals&quot;waarden:

`"ccpaOptOut": <value>`

* **waar**: verbiedt de verkoop van persoonlijke informatie.
* **vals**: keurt de verkoop van persoonlijke informatie goed.

<!--The “CCPA Opt-Out” attribute is only available starting 19.4. For 19.3 environments, you need to extend the Profiles resource and add a boolean field. This field will be added to the API with the chosen label. We suggest you use “Opt-Out for CCPA”.
>
>For more on this, refer to the [Managing Privacy requests documentation](../../start/using/privacy-requests.md#sale-of-personal-information-ccpa).-->

<br/>

***verzoeken van de Steekproef***

* Voorbeeld van een GET-aanvraag om de status voor een CCPA-uitschakelstatus van een profiel op te halen.

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profilesAndServices/profile/<PKEY> \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>' \
  -H 'Content-Type: application/json;charset=utf-8'
  ```

  Antwoord op het GET-verzoek.

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

  Antwoord op het GET-verzoek.

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

* Voorbeeld van een PATCH-verzoek om een profiel voor CCPA-opt-out bij te werken.

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

  Antwoord op het GET-verzoek.

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
