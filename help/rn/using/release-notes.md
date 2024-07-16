---
title: Opmerkingen bij de nieuwste release
description: Op deze pagina vindt u content van de nieuwste release van Campaign Standard
feature: Overview
role: User
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: 44c436a74a0a4aa688427bfb36d506566d57ac3a
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 66%

---


# Opmerkingen bij de nieuwste release {#latest-release}

<!--
![Control Panel](assets/do-not-localize/cp-icon.png) **New Control Panel release**. [Learn more](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html){target="_blank"}.-->


## Vroege aanvullende informatie {#e-new-release}

Deze sectie maakt een lijst van verbeteringen en veranderingen inbegrepen in de volgende versie van het Campaign Standard.

>[!CAUTION]
>
>Deze content kan zonder voorafgaande kennisgeving worden gewijzigd tot de upgradedatum van de werkgebiedomgevingen. Leer meer in de [ Versie plannende pagina ](../../rn/using/release-planning.md).

**Versie 24.2 - 2024 Versie van de Zomer**

* **de datum van de Versie**: Augustus 2024 (Beperkte Beschikbaarheid) - [ Leer meer ](../../rn/using/release-planning.md).

* **Migratie aan Server-aan-Server referentie OAuth**

  Beginnend deze versie, met de referentie van de Rekening van de Dienst (JWT) die door Adobe wordt verouderd, steunen de uitgaande integraties van de Campagne met de oplossingen en apps van de Adobe nu op server-aan-server referentie OAuth. De Adobe zal JWT aan migratie OAuth voor uw uitgaande integratie, zoals de integratie van Campaign-Analytics of de integratie van Triggers van het Experience Cloud uitvoeren.

  Als u binnenkomende integratie met Campagne hebt uitgevoerd, en als u [ Campagne APIs ](../../api/using/get-started-apis.md) gebruikt, moet u uw Technische Rekening zoals die in [ wordt gedetailleerd deze documentatie ](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/) migreren {target="_blank"}. De bestaande geloofsbrieven van de Rekening van de Dienst (JWT) zullen ophouden werkend op **27 Januari, 2025**.


## Versie 24.1: winterversie 2024 {#winter-24}

### Verbeteringen {#e-rn-improvements}

* **Android-pushmeldingen**: Adobe Campaign Standard 24.1 gebruikt de HTTP v1 API&#39;s om Android-pushmeldingen te verzenden, om compatibiliteit met komende FCM-wijzigingen te garanderen. Meer informatie vindt u in [deze technische opmerking](../../administration/using/push-technote.md).

* **iOS-pushmeldingen**: Adobe Campaign Standard 24.1 ondersteunt nu p8-verificatiecertificaten voor iOS-pushmeldingen. Uw implementatie moet worden aangepast om deze wijzigingen te activeren. Meer informatie vindt u [in deze technische opmerking](../../administration/using/push-technote.md).

* **Uitschrijven met één klik voor lijsten**: vanaf 1 juni 2024, Google en Yahoo! voldoen aan uitschrijven met één klik voor lijsten. Campaign ondersteunt deze mogelijkheid nu standaard. Lees meer in [deze sectie](../../administration/using/configuring-email-channel.md#list-of-email-smtp-parameters).

* **Infrastructuur**: de Postgres-database is bijgewerkt van versie 11.22 naar versie 12.17.

* **CTA-tracking**: wanneer de gebruikers een gepersonaliseerde URL openen en erop klikken, wordt nu de opgeloste gepersonaliseerde URL gevolgd in plaats van de gecodeerde gepersonaliseerde URL. Deze wijziging is standaard niet ingeschakeld. Neem contact op met uw Adobe-vertegenwoordiger als u de functie wilt inschakelen voor uw Campaign-instantie.

* **Vervolgkeuzelijst personalisatievelden**: wanneer u transactionele e-mailberichtsjablonen maakt in Adobe Experience Manager, kunt u nu personalisatievelden selecteren in een vervolgkeuzelijst. Deze wijziging is standaard niet ingeschakeld. Neem contact op met uw Adobe-vertegenwoordiger als u de functie wilt inschakelen voor uw Campaign-instantie.

### Oplossingen {#e-rn-fixes}

* Probleem verholpen waarbij werd verhinderd dat de teruggestuurde e-mailadressen na 30 dagen uit quarantaine werden verwijderd. (CAMP-52977)
* Probleem verholpen waarbij de workflow voor leveringswaarschuwingen werd gestopt met de volgende fout: `division by zero`. (CAMP-49786)

