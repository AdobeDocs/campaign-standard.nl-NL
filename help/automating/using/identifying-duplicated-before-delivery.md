---
title: Duplicaten identificeren vóór een levering
description: In het volgende voorbeeld ziet u een deduplicatie waarmee u de duplicaten van een doel kunt uitsluiten voordat u een e-mail verzendt. Hierdoor vermijdt u dat u een communicatie meerdere keren naar hetzelfde profiel verzendt.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: dedup,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: a09b101b-f76f-4377-9854-1fcffaad4f9a
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '287'
ht-degree: 79%

---

# Duplicaten identificeren vóór een levering {#identifying-duplicates-before-a-delivery}

In het volgende voorbeeld ziet u een deduplicatie waarmee u de duplicaten van een doel kunt uitsluiten voordat u een e-mail verzendt. Hierdoor vermijdt u dat u een communicatie meerdere keren naar hetzelfde profiel verzendt.

De workflow bestaat uit:

![](assets/deduplication_example_workflow.png)

* A [Query](../../automating/using/query.md) Hiermee kunt u het doel van de e-mail definiëren. Hier is de workflow gericht op alle profielen tussen 18 en 25 jaar die al langer dan een jaar in de klantendatabase staan.

  ![](assets/deduplication_example_query.png)

* A [Deduplicatie](../../automating/using/deduplication.md) activiteit, die u toestaat om de duplicaten te identificeren die uit de voorafgaande vraag komen. In dit voorbeeld wordt slechts één record opgeslagen voor elk duplicaat. De duplicaten worden geïdentificeerd aan de hand van het e-mailadres. Dit betekent dat de e-maillevering slechts eenmaal kan worden verzonden voor elk e-mailadres dat aanwezig is in de targeting.

  De geselecteerde deduplicatiemethode is **[!UICONTROL Non-empty value]**. Op die manier kunt u ervoor zorgen dat bij duplicaten voorrang wordt gegeven aan de data waarvoor de **voornaam** is opgegeven. Dit zorgt voor meer cohesie als de voornaam wordt gebruikt in de personalisatievelden van de e-mailcontent.

  Bovendien wordt een extra overgang toegevoegd om de duplicaten te behouden en deze weer te geven.

  ![](assets/deduplication_example_dedup.png)

* An [E-maillevering](../../automating/using/email-delivery.md) geplaatst na de belangrijkste uitgaande overgang van deduplicatie.
* A [Adviezen opslaan](../../automating/using/save-audience.md) activiteit die na de extra overgang van deduplicatie wordt geplaatst om de duplicaten op te slaan in een **Duplicaten** publiek. Deze doelgroep kan opnieuw worden gebruikt om de leden ervan direct uit te sluiten van elke e-maillevering.
