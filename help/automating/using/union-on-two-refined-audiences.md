---
solution: Campaign Standard
product: campaign
title: Samenvoeging op twee verfijnde doelgroepen
description: Dit gebruiksgeval toont de samenvoeging van twee Lees publieksactiviteiten.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: readAudience,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '150'
ht-degree: 58%

---


# Samenvoeging op twee verfijnde doelgroepen {#example--union-on-two-refined-audiences}

De workflow die in dit voorbeeld wordt gedefinieerd, toont de samenvoeging van twee activiteiten voor **[!UICONTROL Read audience]**. Het doel van deze workflow is om een e-mail te sturen naar Gold- of Silver-leden tussen 18 en 30 jaar oud. Er zijn al specifieke doelgroepen in het systeem gemaakt om de Gold- en Silver-leden bij te houden.

De workflow is als volgt ontworpen:

![](assets/readaudience_activity_example1.png)

* A first [Read audience](../../automating/using/read-audience.md) activity that retrieves the Gold members audience and refines it by selecting only profiles that are between 18 and 30 years old.
* Een tweede activiteit **[!UICONTROL Read audience]** die de doelgroep met Silver-leden ophaalt en deze verfijnt door slechts profielen te selecteren die tussen 18 en 30 jaar oud zijn.
* A [Union](../../automating/using/union.md) activity that unites populations from both **[!UICONTROL Read audiences]** activities into one final population.
* An [Email delivery](../../automating/using/email-delivery.md) activity that sends the email to the population coming from the **[!UICONTROL Union]** activity.
