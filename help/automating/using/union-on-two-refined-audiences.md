---
title: Samenvoeging op twee verfijnde doelgroepen
description: Dit gebruiksgeval toont de samenvoeging van twee Lees publieksactiviteiten.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: readAudience,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 6261f800-11bd-4b02-a587-49ddb0da240f
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '156'
ht-degree: 43%

---

# Samenvoeging op twee verfijnde doelgroepen {#example--union-on-two-refined-audiences}

De workflow die in dit voorbeeld wordt gedefinieerd, toont de samenvoeging van twee activiteiten voor **[!UICONTROL Read audience]**. Het doel van deze workflow is om een e-mail te sturen naar Gold- of Silver-leden van 18 tot 30 jaar oud. Er zijn al specifieke doelgroepen in het systeem gemaakt om de Gold- en Silver-leden bij te houden.

De workflow is als volgt ontworpen:

![](assets/readaudience_activity_example1.png)

* Een eerste [&#x200B; leest publiek &#x200B;](../../automating/using/read-audience.md) activiteit die het Gouden ledenpubliek terugwint en het raffineert door slechts profielen te selecteren die tussen 18 en 30 jaar oud zijn.
* Een tweede activiteit **[!UICONTROL Read audience]** die de doelgroep met Silver-leden ophaalt en deze verfijnt door slechts profielen te selecteren die tussen 18 en 30 jaar oud zijn.
* A [&#x200B; activiteit 0&rbrace; Unie die populaties van beide &#x200B;](../../automating/using/union.md) activiteiten in één definitieve bevolking verenigt.**[!UICONTROL Read audiences]**
* Een [&#x200B; e-maillevering &#x200B;](../../automating/using/email-delivery.md) activiteit die e-mail naar de bevolking verzendt die uit de **[!UICONTROL Union]** activiteit komt.
