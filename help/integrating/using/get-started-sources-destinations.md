---
solution: Campaign Standard
product: campaign
title: Ga aan de slag met Bronnen en Doelen
description: Meer weten over Adobe Experience Platform-bronnen en -doelen?
audience: integrating
content-type: reference
feature: Sources and Destinations
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: ebbdea387a547cd95c96681faed0a20b37edaf0f
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 0%

---


# Aan de slag met bronnen en doelen {#rtcdp}

## Bronnen en doelen

Met Adobe Experience Platform kunt u gegevens delen tussen Campaign Standard en Adobe Real-Time Customer Data Platform (RTCDP). Dit staat u toe om het publiek van Adobe Experience Platform in uw werkschema&#39;s van de Campagne te richten, dan terug naar de gegevens van het Platform van de Gegevens van de Klant van de Adobe in real time met betrekking tot deze doelgroepen zoals verzendt, opent, en klikt.

* Met **Doelen**, neemt publiek van Adobe Experience Platform in Campaign Standard in. Hierdoor kunt u uw bekende en onbekende gegevens activeren voor uw marketingcampagnes.
* Met **Bronnen**, voer Campaign Standard gegevens (b.v. verzendt, opent, klikt) in Adobe Experience Platform uit. Op deze manier kunt u gegevens die u van verschillende bronnen verzamelt, centraliseren in één locatie en de daaruit verkregen inzichten gebruiken om meer te doen.


>[!IMPORTANT]
>
>Houd bij het uitvoeren van deze integratie rekening met de opslaglimieten van SFTP, de opslaglimieten van de database en de limieten van het actieve profiel zoals vastgelegd in uw Adobe Campaign-contract.

Voor een meer gedetailleerd overzicht van het Platform van de Gegevens van de Klant in real time van Adobe, Doelen en Bronnen, verwijs naar deze pagina&#39;s:

* [Adobe Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html)
* [Doelen](https://experienceleague.adobe.com/docs/experience-platform/destinations/home.html)
* [Brondocumentatie](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html)

## Connect Campaign Standard met Adobe Experience Platform

Om gegevens tussen Adobe Experience Platform en Campaign Standard te kunnen delen, moet u eerst Adobe Campaign als **Doel** verbinden, en uw AWS S3 of Azure opslagplaats van de blob als **Bron** in Adobe ervaren Platform aansluiten.

Zodra de schakelaars zijn gevormd, kunt u opstelling een gegevensinvoer of uitvoer naar Campaign Standard gebruikend werkschema&#39;s.

![](assets/rtcdp-schema.png)

Raadpleeg de volgende secties voor meer informatie over het instellen van deze import- en exportprocessen:

* [Adobe Experience Platform-publiek verfraaien in campagne](../../integrating/using/ingest-aep-data.md)
* [Gegevens exporteren van campagne naar Adobe Experience Platform](../../integrating/using/export-campaign-data.md)
