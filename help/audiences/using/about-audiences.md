---
title: Informatie over doelgroepen
description: Leer hoe u doelgroepen maakt op basis van een query, een lijst of een bestand en hoe u een doelgroep importeert uit Adobe Experience Cloud.
page-status-flag: never-activated
uuid: b3996642-96ec-489e-b146-c8c2cb52aa32
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-audiences
discoiquuid: 750ecd8d-67a5-4180-bfec-2a8e3098c812
context-tags: audience,wizard;audience,overview;delivery,audience,back
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 91%

---


# Informatie over doelgroepen{#about-audiences}

Een doelgroep is een lijst met profielen die zijn gebaseerd op regels en kenmerken.

Met Adobe Campaign kunt u handmatig een doelgroep maken via query&#39;s, of automatisch door specifieke workflows te gebruiken. Met Adobe Experience Cloud kunt u ook gedeelde doelgroepen gebruiken. Alle doelgroepen worden opnieuw ingedeeld in een lijst die toegankelijk is via de kaart **[!UICONTROL Audiences]** op de startpagina van Adobe Campaign, of via de koppeling **[!UICONTROL Audiences]**.

![](assets/audience_1.png)

In Adobe Campaign kunt u verschillende soorten doelgroepen bewerken. Het type doelgroep komt overeen met de manier waarop het is gemaakt:

* **[!UICONTROL Query]**: Hiermee wordt aangegeven dat het publiek is gemaakt met een [query](../../automating/using/editing-queries.md#about-query-editor) op gegevens uit de Adobe Campaign-database via de lijst met doelgroepen. Doelgroepen die op basis van een query worden gedefinieerd, worden bij elk volgend gebruik opnieuw berekend.
* **[!UICONTROL List]**: geeft aan dat de doelgroep bestaat uit een een vaste lijst met profielen. Deze lijsten worden gemaakt in een [workflow](../../automating/using/get-started-workflows.md) waarbij de datadimensie bekend is bij het opslaan van de doelgroep. Bijvoorbeeld na bepaalde targetingactiviteiten (met name **[!UICONTROL Query]**) of na de afstemming van data die vanuit een bestand zijn geïmporteerd.
* **[!UICONTROL File]**: geeft aan dat de doelgroep rechtstreeks is gebaseerd op een workflow voor [bestandsimport](../../automating/using/load-file.md) en dat de datadimensie onbekend was toen de doelgroep werd opgeslagen.
* **[!UICONTROL Experience Cloud]**: geeft aan dat de doelgroep is geïmporteerd uit Adobe Experience Cloud. Deze optie is alleen beschikbaar als de functionaliteit voor het delen van doelgroepen is geconfigureerd. Zie [Een doelgroep importeren uit Adobe Experience Cloud](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md#importing-an-audience) voor meer informatie.

![](assets/audience_type_selection.png)
