---
title: Laatste release
description: Op deze pagina vindt u content van de nieuwste release van Campaign Standard
feature: Overview
role: User
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: 9291eb06c35b1d06c0a992fa64a460215477f57e
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 38%

---


# Laatste release{#latest-release}

<!--
![Control Panel](assets/do-not-localize/cp-icon.png) **New Control Panel release**. [Learn more](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html){target="_blank"}.-->

## Versie 24.1: winterversie 2024 {#winter-24}

### Verbeteringen {#e-rn-improvements}

* **Android-pushmeldingen** - Adobe Campaign Standard 24.1 gebruikt de v1-API&#39;s van HTTP om Android Push Notification Messages te verzenden, om ervoor te zorgen dat deze compatibel zijn met aanstaande FCM-wijzigingen. Meer informatie vindt u [in deze technische opmerking](../../administration/using/push-technote.md).

* **iOS Push Notifications** - Adobe Campaign Standard 24.1 ondersteunt nu p8-verificatiecertificaten voor iOS-pushberichten. Uw implementatie moet worden aangepast om deze wijzigingen te activeren. Meer informatie vindt u [in deze technische opmerking](../../administration/using/push-technote.md).

**Een-klik List-Unsubscribe** - Vanaf 1 juni 2024, Google en Yahoo! voldoen aan uitschrijven met één klik voor lijsten. Campaign ondersteunt deze mogelijkheid nu standaard. Lees meer in [deze sectie](../../administration/using/configuring-email-channel.md#list-of-email-smtp-parameters).

* **Infrastructuur** - De Postgres-database is bijgewerkt van versie 11.22 naar versie 12.17.

* **CTA-tracking** - Wanneer de gebruikers openen en op een gepersonaliseerde URL klikken, wordt de opgeloste gepersonaliseerde URL nu gevolgd in plaats van de gecodeerde gepersonaliseerde URL. Deze wijziging is niet standaard ingeschakeld. Neem contact op met uw Adobe als u de functie wilt inschakelen voor uw Campagne-instantie.

* **Vervolgkeuzelijst Persoonlijke velden** - Wanneer u transactionele e-mailberichtsjablonen maakt in Adobe Experience Manager, kunt u nu aanpassingsvelden selecteren in een vervolgkeuzelijst. Deze wijziging is niet standaard ingeschakeld. Neem contact op met uw Adobe als u de functie wilt inschakelen voor uw Campagne-instantie.

### Oplossingen {#e-rn-fixes}

* Probleem verholpen waarbij werd verhinderd dat de teruggestuurde e-mailadressen na 30 dagen uit quarantaine werden verwijderd. (CAMP-52977)
* Probleem verholpen waarbij de workflow voor leveringswaarschuwingen werd gestopt met de volgende fout: `division by zero`. (CAMP-49786)

