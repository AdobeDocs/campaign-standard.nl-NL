---
title: Duplicaten identificeren vóór een levering
description: In het volgende voorbeeld ziet u een deduplicatie waarmee u de duplicaten van een doel kunt uitsluiten voordat u een e-mail verzendt. Hierdoor vermijdt u dat u een communicatie meerdere keren naar hetzelfde profiel verzendt.
page-status-flag: never-activated
uuid: 11a22a9c-3bfe-4953-8a52-2f4e93c128fb
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: e7a5e1e7-4680-46c7-98b8-0a47bb7be2b8
context-tags: dedup,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 78%

---


# Duplicaten identificeren vóór een levering {#identifying-duplicates-before-a-delivery}

In het volgende voorbeeld ziet u een deduplicatie waarmee u de duplicaten van een doel kunt uitsluiten voordat u een e-mail verzendt. Hierdoor vermijdt u dat u een communicatie meerdere keren naar hetzelfde profiel verzendt.

De workflow bestaat uit:

![](assets/deduplication_example_workflow.png)

* A [Query](../../automating/using/query.md) which allows you to define the target of the email. Hier is de workflow gericht op alle profielen tussen 18 en 25 jaar die al langer dan een jaar in de klantendatabase staan.

   ![](assets/deduplication_example_query.png)

* A [Deduplication](../../automating/using/deduplication.md) activity, which allows you to identify the duplicates that come from the preceding query. In dit voorbeeld wordt slechts één record opgeslagen voor elk duplicaat. De duplicaten worden geïdentificeerd aan de hand van het e-mailadres. Dit betekent dat de e-maillevering slechts eenmaal kan worden verzonden voor elk e-mailadres dat aanwezig is in de targeting.

   De geselecteerde deduplicatiemethode is **[!UICONTROL Non-empty value]**. Op die manier kunt u ervoor zorgen dat bij duplicaten voorrang wordt gegeven aan de data waarvoor de **voornaam** is opgegeven. Dit zorgt voor meer cohesie als de voornaam wordt gebruikt in de personalisatievelden van de e-mailcontent.

   Bovendien wordt een extra overgang toegevoegd om de duplicaten te behouden en deze weer te geven.

   ![](assets/deduplication_example_dedup.png)

* An [Email delivery](../../automating/using/email-delivery.md) placed after the main outbound transition of the deduplication.
* A [Save audience](../../automating/using/save-audience.md) activity placed after the additional transition of the deduplication to save the duplicates in a **Duplicates** audience. Deze doelgroep kan opnieuw worden gebruikt om de leden ervan direct uit te sluiten van elke e-maillevering.
