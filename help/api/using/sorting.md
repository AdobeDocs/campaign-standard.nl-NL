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
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 11%

---


# Sorteren

Sorteren is beschikbaar in oplopende of aflopende volgorde. Hiervoor gebruikt u de parameter **%20desc** of **%20asc** op uw verzoek.

Als u wilt weten of een veld kan worden gesorteerd, controleert u de parameter &quot;sortable&quot; in de metagegevens van de bron. Raadpleeg [deze sectie](../../api/using/metadata-mechanism.md) voor meer informatie.

<br/>

***Voorbeeldverzoeken***

* Voorbeeld van een GET-aanvraag om e-mailberichten op te halen in de database in alfabetische volgorde.

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

* Voorbeeld van een GET-aanvraag om de e-mail in de database op te halen in aflopende alfavolgorde.

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
