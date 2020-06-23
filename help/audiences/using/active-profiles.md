---
title: Actieve profielen
description: U kunt tot een specifiek rapport over klantenmetriek toegang hebben en actieve profielen in uw gegevensbestand van de Campagne visualiseren.
page-status-flag: never-activated
uuid: ee8ac493-c297-49ca-aed4-3976d8a685a4
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-profiles
discoiquuid: e029213f-0b65-41b1-8adf-34fa813b0c70
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 4575c1152f1a33ff18b2200151346cc6e56b45fa
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 0%

---


# Actieve profielen{#active-profiles}

Adobe Campaign geeft een rapport weer waarin het aantal actieve profielen wordt weergegeven. Dit rapport is slechts informatief, het heeft geen directe invloed op het factureren. Alleen beheerders hebben toegang tot dit rapport, onder **[!UICONTROL Administration > Customer metrics]**.

![](assets/audience_active_profiles1.png)

De **[!UICONTROL Billing]** technische workflow genereert elke maand een rapport met het aantal actieve profielen waarop tijdens de laatste 12 maanden durende rolperiode was gericht.

Er wordt geen rekening gehouden met de profielen die tijdens de voorbereiding van de levering zijn uitgesloten (typologische regels, quarantaine). Een profiel dat voor meerdere leveringen is bestemd, wordt slechts eenmaal meegeteld. Onder aan het rapport vindt u de lijst met actieve profielen voor elke doeldimensie.

![](assets/audience_active_profiles2.png)

Als u wordt gehost op AWS en Campaign Standard gebruikt vanuit build 10368, kunt u het aantal actieve profielen dat wordt gebruikt op uw instanties ook rechtstreeks controleren via het Configuratiescherm. Raadpleeg de documentatie bij het [Configuratiescherm voor meer informatie](https://docs.adobe.com/content/help/en/control-panel/using/performance-monitoring/active-profiles-monitoring.html).
