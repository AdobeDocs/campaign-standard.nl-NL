---
solution: Campaign Standard
product: campaign
title: '"Stap 3: De extensie verifiëren"'
description: Leer hoe u toegang krijgt tot het uitgebreide veld met de rest-API.
audience: developing
content-type: reference
topic-tags: use-case--extending-the-api
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '59'
ht-degree: 13%

---


# Stap 3: De extensie verifiëren{#step-verify-the-extension}

1. Voer een bewerking in GET uit op de metagegevens van de API voor profielen en services om te controleren of het veld dat is toegevoegd in de aangepaste bron Profielen nu beschikbaar is.

   ```
   GET profileAndServicesExt/resourceType/profile
   ```

1. Het retourneert:

   ![](assets/extendpandsapiview.png)

   Het veld is nu beschikbaar voor verdere ontwikkelingen en integratie.

