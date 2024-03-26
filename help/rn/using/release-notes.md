---
title: Laatste release
description: Op deze pagina vindt u content van de nieuwste release van Campaign Standard
feature: Overview
role: User
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: 26a1c36003645446fb8b827d76afba749d64e9f2
workflow-type: tm+mt
source-wordcount: '136'
ht-degree: 100%

---


# Laatste release{#latest-release}

<!--
![Control Panel](assets/do-not-localize/cp-icon.png) **New Control Panel release**. [Learn more](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html){target="_blank"}.-->

## Versie 24.1: winterversie 2024 {#winter-24}

### Verbeteringen {#e-rn-improvements}

Adobe Campaign Standard 24.1 gebruikt de HTTP v1-API&#39;s om pushmeldingen van Android te verzenden, zodat deze compatibel zijn met aanstaande FCM-wijzigingen. Meer informatie vindt u [in deze technische opmerking](../../administration/using/push-technote.md).

Adobe Campaign Standard 24.1 ondersteunt nu p8-verificatiecertificaten voor iOS-pushmeldingen. Uw implementatie moet worden aangepast om deze wijzigingen te activeren. Meer informatie vindt u [in deze technische opmerking](../../administration/using/push-technote.md).

Vanaf 1 juni 2024 moeten afzenders bij Google en Yahoo! voldoen aan uitschrijven met één klik voor lijsten. Campaign ondersteunt deze mogelijkheid nu standaard. Lees meer in [deze sectie](../../administration/using/configuring-email-channel.md#email-channel-parameters).

### Oplossingen {#e-rn-fixes}

* Probleem verholpen waarbij werd verhinderd dat de teruggestuurde e-mailadressen na 30 dagen uit quarantaine werden verwijderd. (CAMP-52977)
* Probleem verholpen waarbij de workflow voor leveringswaarschuwingen werd gestopt met de volgende fout: `division by zero`. (CAMP-49786)

