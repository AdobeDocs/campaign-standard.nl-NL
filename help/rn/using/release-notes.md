---
title: Nieuwste aanvullende informatie
description: Op deze pagina vindt u content over de nieuwste release van Campaign Standard
feature: Overview
role: User
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: 44c436a74a0a4aa688427bfb36d506566d57ac3a
workflow-type: ht
source-wordcount: '387'
ht-degree: 100%

---


# Nieuwste aanvullende informatie {#latest-release}

<!--
![Control Panel](assets/do-not-localize/cp-icon.png) **New Control Panel release**. [Learn more](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html){target="_blank"}.-->


## Vroege aanvullende informatie {#e-new-release}

In deze sectie worden nieuwe verbeteringen en wijzigingen vermeld die in de volgende release van Campaign Standard zijn opgenomen.

>[!CAUTION]
>
>Deze content kan zonder voorafgaande kennisgeving worden gewijzigd tot de upgradedatum van de werkgebiedomgevingen. Meer informatie vindt u op de pagina [Releaseplanning](../../rn/using/release-planning.md).

**Release 24.2 - zomerrelease 2024**

* **Releasedatum**: augustus 2024 (beperkte beschikbaarheid) - [Meer informatie](../../rn/using/release-planning.md).

* **Migratie naar OAuth-server-naar-server-aanmeldingsgegevens**

  Omdat de aanmeldingsgegevens van het serviceaccount (JWT) door Adobe worden beëindigd, zijn vanaf deze versie de uitgaande integraties van Campaign met oplossingen en apps van Adobe nu gebaseerd op de OAuth-server-naar-server-aanmeldingsgegevens. Adobe zal de migratie van JWT naar OAuth voor uw uitgaande integraties uitvoeren, zoals de integratie van Campaign-Analytics en de integratie van Experience Cloud-triggers.

  Als u inkomende integraties met Campaign hebt uitgevoerd, en als u [Campaign API&#39;s](../../api/using/get-started-apis.md) gebruikt, moet u uw technische account migreren zoals beschreven in [deze documentatie ](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/){target="_blank"}. Bestaande aanmeldingsgegevens voor het serviceaccount (JWT) zullen niet meer werken vanaf **27 januari, 2025**.


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

