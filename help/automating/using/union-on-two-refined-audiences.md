---
title: Unie op twee verfijnde doelgroepen
description: Dit gebruiksgeval toont de samenvoeging van twee Lees publieksactiviteiten.
page-status-flag: never-activated
uuid: 58c54e71-f4a7-4ae9-80a3-33c379ab1db9
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 674684e5-8830-4d2f-ba97-59ed4ba7422f
context-tags: readAudience,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7ffa48365875883a98904d6b344ac005afe26e18
workflow-type: tm+mt
source-wordcount: '150'
ht-degree: 0%

---


# Unie op twee verfijnde doelgroepen {#example--union-on-two-refined-audiences}

De workflow die in dit voorbeeld wordt gedefinieerd, toont de samenvoeging van twee **[!UICONTROL Read audience]** activiteiten. Het doel van deze workflow is om een e-mail te sturen naar Gold- of Silver-leden van 18 tot 30 jaar oud. Er zijn al specifieke doelgroepen in het systeem gecreëerd om de Gold- en Silver-leden bij te houden.

De workflow is als volgt ontworpen:

![](assets/readaudience_activity_example1.png)

* Een eerste [activiteit van het publiek](../../automating/using/read-audience.md) Read die het Gold ledenpubliek terugwint en het door slechts profielen te selecteren die tussen 18 en 30 jaar oud zijn verfijnt.
* Een tweede **[!UICONTROL Read audience]** activiteit die het Silver ledenpubliek terugwint en het verfijnt door slechts profielen te selecteren die tussen 18 en 30 jaar oud zijn.
* Een activiteit van de [Unie](../../automating/using/union.md) die populaties van beide **[!UICONTROL Read audiences]** activiteiten verenigt in één eindpopulatie.
* Een [e-mailbezorgingsactiviteit](../../automating/using/email-delivery.md) die de e-mail verzendt naar de populatie die uit de **[!UICONTROL Union]** activiteit komt.
