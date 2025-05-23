---
title: Informatie over de service Doelgroepbestemmingen
description: Meer informatie over de service Doelen voor doelgroepen.
audience: audiences
content-type: reference
topic-tags: managing-audiences
context-tags: audience,wizard;audience,overview;delivery,audience,back
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: 34235749-d056-4d4c-9939-7dc52f980a76
hide: true
hidefromtoc: true
source-git-commit: 376f00576ca1d0dfb536b29dbf25d88f7c93b9a8
workflow-type: tm+mt
source-wordcount: '335'
ht-degree: 2%

---

# Informatie over de service Doelgroepbestemmingen {#about-audiences}

>[!IMPORTANT]
>
>De service Doelen van publiek is nu afgekeurd. Verouderde mogelijkheden zijn nog beschikbaar, maar worden niet verder verbeterd en worden niet ondersteund. Meer informatie [op deze pagina](../../rn/using/deprecated-features.md)

Verbeter uw ervaringen met de consument door de [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/landing/home.html?lang=nl-NL) het opbouwen van een doelgericht publiek op basis van grote, complexe gegevensbestanden. De Adobe Experience Platform consolideert profielen, gedragingen en gegevens van meerdere entiteiten op online en offline bronnen, waaronder Adobe Analytics, om u te helpen een 360-gradenweergave van uw klant te maken, zodat u uw ervaringen met klanten effectief kunt beheren.

Adobe Campaign Standard gebruikt vervolgens de **Bestemmingen publiek** service voor het ophalen van een verzameling profielen, ook wel bekend als **Soorten publiek**, van Adobe Experience Platform voor meerstapse en/of kanaalse campagneprogramma&#39;s.

**Soorten publiek** worden gemaakt door het eerste gebouw **segmenten**, die in wezen een set regels zijn die zijn gebaseerd op vrijwel elke variabele (bijvoorbeeld profiel, gebeurtenis, gegevens van meerdere entiteiten) binnen een klantprofiel van Adobe Experience Platform om een multidimensionaal doel te maken. In de volgende speciale documenten wordt verwezen naar algemene concepten voor Profiel en Segmentatieservices van klanten in realtime:

* [Overzicht van het realtime klantprofiel](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=nl-NL)
* [Overzicht van segmentatieservice](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=nl-NL)

Nadat u een segment hebt gemaakt, kunt u het als publiek activeren voor levering in [Workflows voor Campaigns Standard](../../integrating/using/aep-targeting-audiences.md). Daarnaast kunt u contextafhankelijke gegevens van de Adobe Experience Platform naar [personaliseren](../../integrating/using/aep-personalizing-campaigns.md) en voeg dynamische inhoud toe aan uw campagnes.

![](assets/do-not-localize/how-to-video.png) Hoe kan ik-video&#39;s zijn ook beschikbaar in [deze sectie](https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.html?lang=nl-NL).

In deze secties gebruikte termen:

* **Profiel**: Profiel is een standaardgegevensmodel voor Experience Platforms dat wordt gebruikt om de kenmerken van de consument te definiëren. Een profiel kan ook een aggregaat zijn van gebeurtenisgegevens en -kenmerken die betrekking hebben op een persoon en/of apparaat.

  Voorbeeld: &quot;Jan Doe is een 55-jarige man.&quot;

* **Segment**: Een set regels die een subset van profielen definieert vanuit uw database, waarbij zowel kenmerken als gebeurtenisgegevens worden gebruikt.

  Voorbeeld: &quot;Males > 50 jaar oud.&quot;

* **Publiek**: Een verzameling profielen die voldoen aan segmentregels.

  Voorbeeld: Lijst met profielen voor alle mannen > 50 jaar oud in uw database.
