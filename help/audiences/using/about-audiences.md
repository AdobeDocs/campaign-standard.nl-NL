---
title: Informatie over publiek
description: Leer hoe u een publiek maakt op basis van een query, een lijst of een bestand en hoe u deze importeert uit Adobe Experience Cloud.
page-status-flag: never-activated
uuid: b3996642-96ec-489e-b146-c8c2cb52aa32
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-audiences
discoiquuid: 750ecd8d-67a5-4180-bfec-2a8e3098c812
context-tags: audience,wizard;audience,overview;delivery,audience,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 68e825bc3b6b7f94f61875e7da2bc8f63f06d9cb

---


# Informatie over publiek{#about-audiences}

Een publiek is een lijst van profielen die op regels en attributen worden gebaseerd.

Met Adobe Campaign kunt u handmatig een publiek maken met behulp van query&#39;s of automatisch specifieke workflows gebruiken. U kunt ook een gedeeld publiek gebruiken vanuit de Adobe Experience Cloud. Alle doelgroepen worden opnieuw ingedeeld in een lijst die toegankelijk is via de **[!UICONTROL Audiences]** kaart op de startpagina van Adobe Campagne of via de **[!UICONTROL Audiences]** koppeling.

![](assets/audience_1.png)

U kunt verschillende soorten publiek manipuleren in Adobe Campaign. Het type publiek komt overeen met de manier waarop het is gemaakt:

* **[!UICONTROL Query]**: Hiermee wordt aangegeven dat het publiek is gemaakt op basis van een [query](../../automating/using/editing-queries.md#about-query-editor) op gegevens uit de Adobe Campaign-database in de lijst met doelgroepen. Het publiek dat door een vraag wordt bepaald wordt opnieuw berekend bij elk verder gebruik.
* **[!UICONTROL List]**: Hiermee wordt aangegeven dat het publiek een vaste lijst met profielen is. Deze lijsten worden gecreeerd in een [werkschema](../../automating/using/get-started-workflows.md), waar de gegevensdimensie wanneer het bewaren van het publiek gekend is. Bijvoorbeeld, na het richten van activiteiten (vooral **[!UICONTROL Query]** ) of na de verzoening van gegevens die uit een dossier worden ingevoerd.
* **[!UICONTROL File]**: Hiermee wordt aangegeven dat het publiek rechtstreeks is gemaakt op basis van een workflow voor het importeren van [bestanden](../../automating/using/load-file.md) en dat de gegevensdimensie onbekend was bij het opslaan van het publiek.
* **[!UICONTROL Experience Cloud]**: geeft aan dat het publiek is geïmporteerd uit de Adobe Experience Cloud. Deze optie is alleen beschikbaar als de functionaliteit voor het delen van publiek is geconfigureerd. Zie Een publiek [importeren uit de Adobe Experience Cloud](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md#importing-an-audience)voor meer informatie.

![](assets/audience_type_selection.png)
