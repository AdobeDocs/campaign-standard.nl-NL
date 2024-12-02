---
title: 'Stap 3: de extensie verifiëren'
description: Leer hoe u toegang krijgt tot het uitgebreide veld met de rest-API.
audience: developing
content-type: reference
topic-tags: use-case-extending-the-api
feature: Data Model
role: Developer
level: Experienced
exl-id: 34cb416c-ee3d-4b7c-a75b-640432db320d
source-git-commit: dcfd4e2610cbf9d250359cab6ed43e8c97dd4536
workflow-type: tm+mt
source-wordcount: '61'
ht-degree: 16%

---

# Stap 3: de extensie verifiëren{#step-verify-the-extension}

1. Voer een bewerking in GET uit op de metagegevens van de API voor profielen en services om te controleren of het veld dat is toegevoegd in de aangepaste bron Profielen nu beschikbaar is.

   ```
   GET profileAndServicesExt/resourceType/profile
   ```

1. Het retourneert:

   ![](assets/extendpandsapiview.png)

   Het veld is nu beschikbaar voor verdere ontwikkelingen en integratie.
