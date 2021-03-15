---
solution: Campaign Standard
product: campaign
title: '"Stap 3: De extensie verifiëren"'
description: Leer hoe u toegang krijgt tot het uitgebreide veld met de rest-API.
audience: developing
content-type: reference
topic-tags: use-case--extending-the-api
feature: Gegevensmodel
role: Ontwikkelaar
level: Ervaren
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '63'
ht-degree: 12%

---


# Stap 3: De extensie verifiëren{#step-verify-the-extension}

1. Voer een bewerking in GET uit op de metagegevens van de API voor profielen en services om te controleren of het veld dat is toegevoegd in de aangepaste bron Profielen nu beschikbaar is.

   ```
   GET profileAndServicesExt/resourceType/profile
   ```

1. Het retourneert:

   ![](assets/extendpandsapiview.png)

   Het veld is nu beschikbaar voor verdere ontwikkelingen en integratie.

