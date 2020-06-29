---
title: Bronnen gebruiken die verschillen van doelgerichte dimensies
description: Leer hoe u een bron gebruikt die afwijkt van de doeldimensie.
page-status-flag: never-activated
uuid: b3c629fa-370e-481c-b347-fcf9f5a5e847
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 8d46ce28-0101-4f13-865a-2208ed6d6139
context-tags: query,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f3a668860659e40645ce3e4aab879cae5ad90083
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 0%

---


# Bronnen gebruiken die verschillen van doelgerichte dimensies {#using-resources-different-from-targeting-dimensions}

Dit gebruiksgeval stelt voor hoe te om een middel te gebruiken dat van de het richten dimensie verschillend is, bijvoorbeeld om op een specifiek verslag in een verre lijst te zoeken.

Raadpleeg [deze sectie voor meer informatie over doelgerichtheid en bronnen.](../../automating/using/query.md#targeting-dimensions-and-resources)

**Voorbeeld 1: het identificeren van profielen die door de levering met het etiket worden gericht &quot;Welkom terug!&quot;**.

* In dit geval willen we profielen als doel instellen. We zullen de doelgerichtheid bepalen op **[!UICONTROL Profiles (profile)]**.
* We willen de geselecteerde profielen filteren op basis van het leveringslabel. We zullen de middelen dus op **[!UICONTROL Delivery logs]** zetten. Op deze manier filteren we rechtstreeks in de tabel van het leveringslogboek, wat betere prestaties biedt.

![](assets/targeting_dimension6.png)

![](assets/targeting_dimension7.png)

**Voorbeeld 2: het identificeren van profielen die niet door de levering met het etiket &quot;Welkom terug!&quot;werden gericht**

In het vorige voorbeeld hebben we een andere bron gebruikt dan de doeldimensie. Deze bewerking is alleen mogelijk als u een record wilt zoeken die aanwezig **** is in de verafgelegen tabel (in ons voorbeeld voor leveringslogboeken).

Als wij een verslag willen vinden dat niet aanwezig **in de verre lijst (bijvoorbeeld, profielen die niet door een specifieke levering werden gericht)** is, moet u het zelfde middel en het richten dimensie gebruiken, aangezien het verslag niet in de verre lijst (leveringslogboeken) aanwezig zal zijn.

* In dit geval willen we profielen als doel instellen. We zullen de doelgerichtheid bepalen op **[!UICONTROL Profiles (profile)]**.
* We willen de geselecteerde profielen filteren op basis van het leveringslabel. Het is niet mogelijk om direct op leveringslogboeken te filtreren aangezien wij naar een verslag niet aanwezig in de lijst van leveringslogboeken zoeken. Daarom zullen wij het middel aan plaatsen **[!UICONTROL Profile (profile)]** en onze vraag op de profielenlijst bouwen.

![](assets/targeting_dimension8.png)

![](assets/targeting_dimension9.png)
