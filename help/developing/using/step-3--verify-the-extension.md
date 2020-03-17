---
title: '"Stap 3: De extensie controleren"'
description: Leer hoe u toegang krijgt tot het uitgebreide veld met de rest-API.
page-status-flag: never-activated
uuid: 35ba89a5-a354-466f-91a0-50de111a2e00
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: use-case--extending-the-api
discoiquuid: 21bad242-5921-445c-8df9-3d57dbe35197
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Stap 3: De extensie verifiëren{#step-verify-the-extension}

1. Voer een GET-bewerking uit op de metagegevens van de API voor profielen en services om te controleren of het veld dat is toegevoegd in de aangepaste bron Profielen nu beschikbaar is.

   ```
   GET profileAndServicesExt/resourceType/profile
   ```

1. Het retourneert:

   ![](assets/extendpandsapiview.png)

   Het veld is nu beschikbaar voor verdere ontwikkelingen en integratie.

