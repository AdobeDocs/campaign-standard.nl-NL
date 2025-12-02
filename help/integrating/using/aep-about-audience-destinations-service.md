---
title: Informatie over de service Doelgroepbestemmingen
description: Meer informatie over de service Doelen voor doelgroepen.
audience: audiences
content-type: reference
topic-tags: managing-audiences
context-tags: audience,wizard;audience,overview;delivery,audience,back
feature: Microsoft CRM Integration
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 34235749-d056-4d4c-9939-7dc52f980a76
hide: true
hidefromtoc: true
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '335'
ht-degree: 2%

---

# Informatie over de service Doelgroepbestemmingen {#about-audiences}

>[!IMPORTANT]
>
>De service Doelen van publiek is nu afgekeurd. Verouderde mogelijkheden zijn nog beschikbaar, maar worden niet verder verbeterd en worden niet ondersteund. Leer meer [&#x200B; in deze pagina &#x200B;](../../rn/using/deprecated-features.md)

Verbeter uw ervaringen van de consument door [&#x200B; Adobe Experience Platform &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/landing/home.html?lang=nl-NL) leveraging om hoogst gericht publiek te bouwen dat op grote, complexe datasets wordt gebaseerd. De Adobe Experience Platform consolideert profielen, gedragingen en gegevens van meerdere entiteiten op online en offline bronnen, waaronder Adobe Analytics, om u te helpen een 360-gradenweergave van uw klant te maken, zodat u uw ervaringen met klanten effectief kunt beheren.

Adobe Campaign Standard zal dan de **dienst van de Doelen van het publiek** gebruiken om een inzameling van profielen terug te winnen, die als **publiek** wordt bekend, van Adobe Experience Platform voor multi-step en/of dwars-kanaalcampagneprogramma&#39;s.

**Soorten publiek** wordt gecreeerd door eerst bouwend **segmenten**, die hoofdzakelijk een reeks regels zijn die op vrijwel om het even welke variabele (b.v., profiel, gebeurtenis, multi-entiteitgegevens) binnen een klantenprofiel van Adobe Experience Platform worden gebaseerd om een multidimensionaal doel tot stand te brengen. In de volgende speciale documenten wordt verwezen naar algemene concepten voor Profiel en Segmentatieservices van klanten in realtime:

* [&#x200B; overzicht van het Profiel van de Klant in real time &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=nl-NL)
* [&#x200B; overzicht van de Dienst van de Segmentatie &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=nl-NL)

Zodra een segment is gecreeerd, kunt u het als publiek voor een levering in [&#x200B; werkschema&#39;s van Campaign Standard &#x200B;](../../integrating/using/aep-targeting-audiences.md) dan activeren. Bovendien, kunt u contextafhankelijke gegevens van Adobe Experience Platform gebruiken [&#x200B; personaliseren &#x200B;](../../integrating/using/aep-personalizing-campaigns.md) en dynamische inhoud toevoegen aan uw campagnes.

![](assets/do-not-localize/how-to-video.png) Hoe te video&#39;s zijn ook beschikbaar in [&#x200B; deze sectie &#x200B;](https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.html?lang=nl-NL).

In deze secties gebruikte termen:

* **Profiel**: Het profiel is een Experience Platform standaardgegevensmodel dat wordt gebruikt om attributen van consumenten te bepalen. Een profiel kan ook een aggregaat zijn van gebeurtenisgegevens en -kenmerken die betrekking hebben op een persoon en/of apparaat.

  Voorbeeld: &quot;Jan Doe is een 55-jarige man.&quot;

* **Segment**: Een reeks regels die een ondergroep van profielen van uw gegevensbestand bepaalt, gebruikend zowel attributen als gebeurtenisgegevens.

  Voorbeeld: &quot;Males > 50 jaar oud.&quot;

* **Publiek**: Een inzameling van profielen die segmentregels ontmoeten.

  Voorbeeld: Lijst met profielen voor alle mannen > 50 jaar oud in uw database.
