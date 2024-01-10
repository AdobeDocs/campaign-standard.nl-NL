---
title: Vroege aanvullende informatie
description: Vroege aanvullende informatie
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: ac4a52263482557a6d5c370af6df5d54a42671b4
workflow-type: ht
source-wordcount: '159'
ht-degree: 100%

---


# Vroege aanvullende informatie {#e-new-release}

Op deze pagina worden nieuwe verbeteringen en oplossingen beschreven die in de volgende release van Campaign Standard zijn opgenomen.

>[!CAUTION]
>
> Deze content kan zonder voorafgaande kennisgeving worden gewijzigd tot de upgradedatum van de werkgebiedomgevingen. Meer informatie vindt u op de [releaseplanningspagina](../../rn/using/release-planning.md).

## Versie 24.1: winterversie 2024 {#winter-24}

>[!AVAILABILITY]
>
>Deze release is maar voor een aantal organisaties beschikbaar (beperkte beschikbaarheid). Neem voor meer informatie contact op met uw Adobe-vertegenwoordiger.

### Verbeteringen {#e-rn-improvements}

Adobe Campaign Standard 24.1 gebruikt de HTTP v1-API&#39;s om pushmeldingen van Android te verzenden, zodat deze compatibel zijn met aanstaande FCM-wijzigingen. Meer informatie vindt u [in deze technische opmerking](../../administration/using/push-technote.md).

Adobe Campaign Standard 24.1 ondersteunt nu p8-verificatiecertificaten voor iOS-pushmeldingen. Uw implementatie moet worden aangepast om deze wijzigingen te activeren. Meer informatie vindt u [in deze technische opmerking](../../administration/using/push-technote.md).


### Oplossingen {#e-rn-fixes}

* Probleem verholpen waarbij werd verhinderd dat de teruggestuurde e-mailadressen na 30 dagen uit quarantaine werden verwijderd. (CAMP-52977)
* Probleem verholpen waarbij de workflow voor leveringswaarschuwingen werd gestopt met de volgende fout: `division by zero`. (CAMP-49786)
