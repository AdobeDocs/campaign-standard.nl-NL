---
title: Aanvullende informatie 2024
description: Deze pagina bevat een overzicht van alle releases van Adobe Campaign Standard in 2024.
feature: Overview
role: User
level: Beginner
exl-id: 26616ecc-a009-485c-b13d-d4e0c23969f2
source-git-commit: 85f3a3d8fe9e41eaa78fac955bc2d0f3f3d2c35e
workflow-type: tm+mt
source-wordcount: '490'
ht-degree: 100%

---

# Aanvullende informatie 2024 {#release-notes-2024}


## Release 24.2 - release zomer 2024 (LA) {#summer-24}

### Verbetering {#summer-24-rn-improvements}

**Migratie naar OAuth-server-naar-server-aanmeldingsgegevens**

Omdat de aanmeldingsgegevens van het serviceaccount (JWT) door Adobe worden beëindigd, zijn vanaf deze versie de uitgaande integraties van Campaign met oplossingen en apps van Adobe nu gebaseerd op de OAuth-server-naar-server-aanmeldingsgegevens. Adobe zal de migratie van JWT naar OAuth voor uw uitgaande integraties uitvoeren, zoals de integratie van Campaign-Analytics en de integratie van Experience Cloud-triggers.

Als u inkomende integraties met Campaign hebt uitgevoerd, en als u [Campaign API&#39;s](../../api/using/get-started-apis.md) gebruikt, moet u uw technische account migreren zoals beschreven in [deze documentatie ](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/){target="_blank"}. Bestaande aanmeldingsgegevens voor het serviceaccount (JWT) zullen niet meer werken vanaf **27 januari, 2025**.

### Oplossingen {#summer-24-rn-fixes}

* Er is een probleem opgelost waarbij de workflowplanner vóór de geplande tijd startte. (CAMP-55412)
* Er is een probleem opgelost dat een fout veroorzaakte bij het dupliceren van aangepaste velden in transactionele pushmeldingen. (CAMP-54459)
* Er zijn problemen opgelost die invloed hadden op de bruikbaarheid van de tijd- en datumplanner voor in-app messaging. (CAMP-54495)
* Er is een probleem opgelost waarbij tracking niet werkte wanneer de functie Aangepaste tracking-alias werd gebruikt en de gehele koppeling dynamisch was. (CAMP-56044)
* Er is een probleem opgelost waarbij een beperkt aantal sjablonen werd weergegeven bij het zoeken naar specifieke sjablonen. (CAMP-55273)
* De volgende talen zijn aan de vervolgkeuzelijst met voorkeurstalen toegevoegd: en_kz (Engels - Kazachstan) en en_ua (Engels - Oekraïne). (CAMP-55336)
* Er is een probleem opgelost waarbij de knoppen voor tijdaanpassing niet werkten in de plannerinstellingen. (CAMP-53602)
* Er zijn diverse gebruikersinterfaceproblemen opgelost met de balk voor tijdaanpassing in plannerinstellingen. (CAMP-55291)


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
