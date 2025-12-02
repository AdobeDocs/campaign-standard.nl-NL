---
title: Aan de slag met bronnen en bestemmingen
description: Meer weten over Adobe Experience Platform-bronnen en -doelen?
audience: integrating
content-type: reference
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: ba6205fa-dbcf-497a-882f-f15c00f12e68
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '292'
ht-degree: 13%

---

# Aan de slag met bronnen en bestemmingen {#rtcdp}

## Informatie over bronnen en doelen

Met Adobe Experience Platform kunt u gegevens delen tussen Campaign Standard en Adobe Real-time Customer Data Platform (RTCDP). Op deze manier kunt u zich richten op Adobe Experience Platform-doelgroepen in uw campagneworkflows en vervolgens gegevens van het klantgegevensplatform van Adobe Real-time terugsturen naar deze doelgroepen, zoals verzenden, openen en klikken.

* Met **Doelen**, neem publiek van Adobe Experience Platform in Campaign Standard op. Hierdoor kunt u uw bekende en onbekende gegevens activeren voor uw marketingcampagnes.
* Met **Bronnen**, de gegevens van de uitvoerCampaign Standard (b.v. verzendt, opent, klikt) in Adobe Experience Platform. Op deze manier kunt u gegevens die u van verschillende bronnen verzamelt, centraliseren in één locatie en de daaruit verkregen inzichten gebruiken om meer te doen.


>[!IMPORTANT]
>
>Houd bij het uitvoeren van deze integratie rekening met de opslaglimieten van SFTP, de opslaglimieten van de database en de limieten van het actieve profiel zoals vastgelegd in uw Adobe Campaign-contract.

Raadpleeg de volgende pagina&#39;s voor een gedetailleerder overzicht van het Adobe Real-time Customer Data Platform, Doelen en Bronnen:

* [Adobe Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html?lang=nl)
* [Documentatie voor bestemmingen](https://experienceleague.adobe.com/docs/experience-platform/destinations/home.html?lang=nl)
* [Documentatie voor bronnen](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=nl)

## Campaign Standard verbinden met Adobe Experience Platform

Om gegevens tussen Adobe Experience Platform en Campaign Standard te kunnen delen, moet u eerst Adobe Campaign als a **Doel** verbinden, en uw AWS S3 of Azure blob opslagplaats als a **Source** in de ervaringsplatform van Adobe verbinden.

Nadat de connectors zijn geconfigureerd, kunt u een gegevensimport of -export naar Campaign Standard instellen met behulp van workflows.

![](assets/rtcdp-schema.png)

Raadpleeg de volgende secties voor meer informatie over het instellen van deze import- en exportprocessen:

* [Adobe Experience Platform-doelgroepen opnemen in Campaign](../../integrating/using/ingest-aep-data.md)
* [Gegevens exporteren van Campaign naar Adobe Experience Platform](../../integrating/using/export-campaign-data.md)
