---
title: Duplicaten identificeren vóór levering
description: In het volgende voorbeeld ziet u een deduplicatie waarmee u de duplicaten van een doel kunt uitsluiten voordat u een e-mail verzendt. Dit betekent dat u een communicatie niet meerdere keren naar hetzelfde profiel verzendt.
page-status-flag: never-activated
uuid: 11a22a9c-3bfe-4953-8a52-2f4e93c128fb
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: e7a5e1e7-4680-46c7-98b8-0a47bb7be2b8
context-tags: dedup,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7ffa48365875883a98904d6b344ac005afe26e18
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 0%

---


# Duplicaten identificeren vóór levering {#identifying-duplicates-before-a-delivery}

In het volgende voorbeeld ziet u een deduplicatie waarmee u de duplicaten van een doel kunt uitsluiten voordat u een e-mail verzendt. Dit betekent dat u een communicatie niet meerdere keren naar hetzelfde profiel verzendt.

De workflow bestaat uit:

![](assets/deduplication_example_workflow.png)

* Een [query](../../automating/using/query.md) waarmee u het doel van de e-mail kunt definiëren. Hier, richt het werkschema zich alle profielen tussen 18 en 25 die in het cliëntgegevensbestand meer dan een jaar zijn geweest.

   ![](assets/deduplication_example_query.png)

* Een activiteit van de [Deduplicatie](../../automating/using/deduplication.md) , die u toestaat om de duplicaten te identificeren die uit de voorafgaande vraag komen. In dit voorbeeld wordt slechts één record opgeslagen voor elk duplicaat. De duplicaten worden geïdentificeerd aan de hand van het e-mailadres. Dit betekent dat de e-maillevering slechts eenmaal kan worden verzonden voor elk e-mailadres dat aanwezig is bij de doelversie.

   De geselecteerde deduplicatiemethode is **[!UICONTROL Non-empty value]**. Op die manier kunt u ervoor zorgen dat bij dubbele gegevens voorrang wordt gegeven aan de gegevens waarvoor de **voornaam** is opgegeven. Hierdoor wordt het coherenter als de voornaam wordt gebruikt in de personalisatievelden van de e-mailinhoud.

   Bovendien wordt een extra overgang toegevoegd om de duplicaten te behouden en deze weer te geven.

   ![](assets/deduplication_example_dedup.png)

* Een [E-maillevering](../../automating/using/email-delivery.md) geplaatst na de belangrijkste uitgaande overgang van deduplicatie.
* Een publieksactiviteit [van het](../../automating/using/save-audience.md) sparen die na de extra overgang van deduplicatie wordt geplaatst om de duplicaten in een **Duplicaten** publiek te bewaren. Dit publiek kan worden hergebruikt om zijn leden van elke e-maillevering direct uit te sluiten.
