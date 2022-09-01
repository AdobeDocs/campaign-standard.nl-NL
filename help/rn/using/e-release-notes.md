---
title: Vroege aanvullende informatie
description: Vroege aanvullende informatie
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: e74ce4aea097e5078aabf83f424e855db72b04a1
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 21%

---


# Vroege aanvullende informatie {#e-new-release}

Op deze pagina vindt u een beschrijving van de verbeteringen en correcties die zijn opgenomen in de volgende release van Campaign Standard.

>[!CAUTION]
>
> Deze content kan zonder voorafgaande kennisgeving worden gewijzigd tot de upgradedatum van de werkgebiedomgevingen. Meer informatie vindt u op de [releaseplanningspagina](../../rn/using/release-planning.md).

## Release 22.3 - september 2022 {#e-rn-2022}

**Verbeteringen**

**Toegankelijkheid**

Campaign Standard 2.2.3 wordt geleverd met toegankelijkheidsoplossingen en -verbeteringen die gebruikers helpen om te navigeren en optimaal te profiteren van Adobe Campaign.

Deze mogelijkheden worden vrijgegeven in Beperkte Beschikbaarheid en slechts uitgevoerd aan een reeks klanten. Neem contact op met uw Adobe als u deze verbeteringen wilt inschakelen in uw Campagneomgeving(en).

<!--
* **Data retention**

    Data retention periods have been reduced to avoid overloading Campaign server. However, you can still modify these values and define a custom period of time based on your needs and data retention policies. To change retention periods, contact Adobe.
-->

**Beveiligingsupdate**

Deze release wordt geleverd met de volgende beveiligingsupgrade: Apache Tomcat is geüpgraded van v7.0 naar v8.0.

**Oplossingen**

* Probleem verholpen met geplande rapporten, die een uur voor de geplande timing werden geactiveerd. (CAMP-51502)
* Probleem verholpen met betrekking tot de leveringsindicatoren in het leveringsdashboard die niet overeenkwamen met het verzenden van logboeken (nms:wideLogRcp). (CAMP-51127)
* Probleem verholpen waarbij uitbreiding van aangepaste bronnen met ACS-connector (prime-aanbieding) werd voorkomen. (CAMP-51033)
* Verbeterde publicatieprocedure voor reacties op privacyverzoeken om vertraging te voorkomen. (CAMP-50613)