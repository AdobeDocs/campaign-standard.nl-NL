---
title: Wijzigingen in een gegevensmodel controleren
description: Leer hoe u het Adobe Campaign-gegevensmodel kunt diagnosticeren.
audience: developing
content-type: reference
topic-tags: about-custom-resources
feature: Data Model
role: Developer
level: Experienced
exl-id: ced9a897-47e9-4128-84fb-35660c553cd4
source-git-commit: 5fef74296a4790102c75e609c270e52d5ead1d58
workflow-type: tm+mt
source-wordcount: '194'
ht-degree: 5%

---

# Wijzigingen in een gegevensmodel controleren{#monitoring-data-model-changes}

Van de **[!UICONTROL Diagnosis]** kunt u de technische objecten weergeven die door de toepassing worden gegenereerd, zodat u deze kunt analyseren.

>[!NOTE]
>
>De schermen in dit menu zijn alleen-lezen.

![](assets/diagnostic.png)

U kunt de volgende typen objecten weergeven:

* Gegevensschema’s
* Webpagina&#39;s
* Filters
* Navigatie
* Componenten
* Batchtaken

U kunt de lijstconfiguratie veranderen:

* U kunt kolommen toevoegen en verwijderen.
* U kunt kolomnamen definiëren.
* U kunt de weergavevolgorde van kolommen in de lijst definiëren.
* U kunt de sorteervolgorde van waarden in de lijst kiezen.

U kunt de lijst filteren:

* U kunt eigen gegevensschema&#39;s, webpagina&#39;s, filters en navigatieobjecten opnemen of uitsluiten.
* U kunt objecten zoeken op hun naam.
* U kunt batchtaken filteren op hun status, begindatum en einddatum.

U kunt de weergegeven lijst downloaden in een bestand in TXT-indeling met door komma&#39;s gescheiden waarden.

U kunt de details van het geselecteerde object weergeven.

U kunt deze functie bijvoorbeeld gebruiken om de filtercriteria van out-of-the-box filters weer te geven. Dit voorbeeld toont de code die voor de het filtreren criteria van een uit-van-de-doosfilter wordt getoond:

```xml
<where displayFilter="Has clicked an offer">
  <condition boolOperator="AND" enabledIf="$(offer) != ''" expr="trackingLog" internalId="1" setOperator="EXISTS">
    <condition boolOperator="AND" expr="[url/offer] = $RestKey(offer)" internalId="2"/>
    <condition boolOperator="AND" expr="[@url-id] != 1" internalId="3"/>
  </condition>
</where>
```

![](assets/diagnosis_filter_criteria.png)