---
title: Sorteren
description: Meer informatie over het uitvoeren van sorteerbewerkingen
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 7db25b8d-a6f1-4151-bf37-c47e9991ae48
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 11%

---

# Sorteren

Sorteren is beschikbaar in oplopende of aflopende volgorde. Hiervoor gebruikt u de parameter **%20desc** of **%20asc** aan uw verzoek.

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
