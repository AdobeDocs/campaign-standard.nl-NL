---
title: Nieuwste aanvullende informatie
description: Op deze pagina vindt u content over de nieuwste release van Campaign Standard
feature: Overview
role: User
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: c2d2f3843801d108f007fea52a76e41abe16d76c
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 76%

---


# Nieuwste aanvullende informatie {#latest-release}

<!--
![Control Panel](assets/do-not-localize/cp-icon.png) **New Control Panel release**. [Learn more](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html){target="_blank"}.-->


## Vroege aanvullende informatie {#e-new-release}

In deze sectie worden nieuwe verbeteringen en wijzigingen vermeld die in de volgende release van Campaign Standard zijn opgenomen.

>[!CAUTION]
>
>Deze content kan zonder voorafgaande kennisgeving worden gewijzigd tot de upgradedatum van de werkgebiedomgevingen. Meer informatie vindt u op de pagina [Releaseplanning](../../rn/using/release-planning.md).

### Versie 25.1: winterversie 2025 {#winter-25}

#### Beveiligingsoplossingen {#winter-25-security}

* Deze release biedt beveiligingsoplossingen.
* Deze release wordt geleverd met de volgende beveiligingsupgrade: Apache Tomcat is bijgewerkt naar versie 10.1.33.

#### Andere oplossingen {#winter-25-fixes}

* Een dubbel probleem in sjablonen opgelost (CAMP-56340)
* Probleem verholpen waarbij een regressie bij het bijhouden van wijzigingen werd gecorrigeerd toen dynamische URL&#39;s werden gebruikt in Adobe Experience Manager-sjablonen (CAMP-51932)
* Oplossing voor een prestatieprobleem met het factureringsproces (CAMP-56796)
* Probleem met HTML-codering verholpen met het teken `>` op JSSP-webpagina&#39;s (CAMP-56497)
* Vaste een kwestie in Dynamische rapportering wanneer het gebruiken van **Vertoning op geselecteerde rijen** optie (CAMP-55895)


## Release 24.2 - 2024 Summer Release (LA) {#summer-24}

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
