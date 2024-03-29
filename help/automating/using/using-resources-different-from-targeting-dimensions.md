---
title: Bronnen gebruiken die niet gelijk zijn aan targetingdimensies
description: Leer hoe u een bron gebruikt die afwijkt van de doeldimensie.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: query,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 5805bdfa-fb33-4a46-ba1e-7a10b067349b
source-git-commit: 9c14fc3de60d8e0304f8a7ebd46e7be34d2e0499
workflow-type: tm+mt
source-wordcount: '295'
ht-degree: 76%

---

# Bronnen gebruiken die niet gelijk zijn aan targetingdimensies {#using-resources-different-from-targeting-dimensions}

Dit gebruiksgeval stelt voor hoe te om een middel te gebruiken dat van de het richten dimensie verschillend is, bijvoorbeeld om op een specifiek verslag in een verre lijst te zoeken.

Raadpleeg voor meer informatie over doelgerichtheid en bronnen [deze sectie](../../automating/using/query.md#targeting-dimensions-and-resources)

**Voorbeeld 1: profielen identificeren die door de levering worden getarget met het label &quot;Welkom terug!&quot;**.

* In dit geval willen we profielen als doel instellen. We stellen de targetingdimensie in op **[!UICONTROL Profiles (profile)]**.
* We willen de geselecteerde profielen filteren op basis van het leveringslabel. We stellen de bron daarom in op **[!UICONTROL Delivery logs]**. Op deze manier, filtreren wij direct in de lijst van het leveringslogboek, die betere prestaties zal aanbieden.

![](assets/targeting_dimension6.png)

![](assets/targeting_dimension7.png)

**Voorbeeld 2: profielen identificeren die niet door de levering zijn getarget met het label &quot;Welkom terug!&quot;**.

In het vorige voorbeeld hebben we een andere bron gebruikt dan de doeldimensie. Deze bewerking is alleen mogelijk als u een record wilt zoeken dat **aanwezig is** in de verafgelegen tabel (in ons voorbeeld gaat het om leveringslogboeken).

Als we een record willen vinden dat **niet aanwezig is** in de verre tabel (bijvoorbeeld, profielen die niet door een specifieke levering zijn getarget), moet u dezelfde bron en targetingdimensie gebruiken, aangezien de record niet aanwezig is in de verafgelegen tabel (leveringslogboeken).

* In dit geval willen we profielen als doel instellen. We stellen de targetingdimensie in op **[!UICONTROL Profiles (profile)]**.
* We willen de geselecteerde profielen filteren op basis van het leveringslabel. Het is niet mogelijk om een filter rechtstreeks toe te passen op de leveringslogboeken, omdat we zoeken naar een record die niet aanwezig in de tabel met leveringslogboeken. Daarom moeten we de bron instellen op **[!UICONTROL Profile (profile)]** en onze query bouwen op de profielentabel.

![](assets/targeting_dimension8.png)

![](assets/targeting_dimension9.png)
