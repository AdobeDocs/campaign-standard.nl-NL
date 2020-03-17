---
title: Sorteren
description: Meer informatie over het uitvoeren van sorteerbewerkingen
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
source-git-commit: c0c0be79613f99a15676343d8ce10d335baf968a

---


# Sorteren

Sorteren is beschikbaar in oplopende of aflopende volgorde. Hiervoor gebruikt u de parameter **%20desc** of **%20asc** op uw verzoek.

Als u wilt weten of een veld kan worden gesorteerd, controleert u de parameter &quot;sortable&quot; in de metagegevens van de bron. For more on this, refer to [this section](../../api/using/metadata-mechanism.md).

<br/>

***Voorbeeldverzoeken***

* De steekproef krijgt verzoek om e-mails in het gegevensbestand terug te winnen alfabetisch bevolen.

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email/email?_order=email \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

   Antwoord op het verzoek.

   ```
   {
   "content": [
       "adam@email.com",
       "allison.durance@example.com",
       "amy.dakota@mail.com",
       "andrea.johnson@mail.com",
       ...
   ]
   ...
   }
   ```

* Steekproef krijgt verzoek om e-mail in het gegevensbestand in een dalende alpha- orde terug te winnen.

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_order=email%20desc \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

   Antwoord op het verzoek.

   ```
   {
   "content": [
       "tombinder@example.com",
       "tombinder@example.com",
       "timross@example.com",
       "john.smith@example.com",
       ...
   ]
   }
   ```
