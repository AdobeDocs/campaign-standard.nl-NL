---
solution: Campaign Standard
product: campaign
title: Informatie over doelgroepen
description: Leer hoe u doelgroepen maakt op basis van een query, een lijst of een bestand en hoe u een doelgroep importeert uit Adobe Experience Cloud.
audience: audiences
content-type: reference
topic-tags: managing-audiences
context-tags: audience,wizard;audience,overview;delivery,audience,back
feature: Doelgroepen
role: User
level: Beginner
exl-id: f99987d8-b1bf-4ec7-885c-fb511f4168ac
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 91%

---

# Informatie over doelgroepen{#about-audiences}

Een doelgroep is een lijst met profielen die zijn gebaseerd op regels en kenmerken.

Met Adobe Campaign kunt u handmatig een doelgroep maken via query&#39;s, of automatisch door specifieke workflows te gebruiken. Met Adobe Experience Cloud kunt u ook gedeelde doelgroepen gebruiken. Alle doelgroepen worden opnieuw ingedeeld in een lijst die toegankelijk is via de kaart **[!UICONTROL Audiences]** op de startpagina van Adobe Campaign, of via de koppeling **[!UICONTROL Audiences]**.

![](assets/audience_1.png)

In Adobe Campaign kunt u verschillende soorten doelgroepen bewerken. Het type doelgroep komt overeen met de manier waarop het is gemaakt:

* **[!UICONTROL Query]**: wijst erop dat het publiek gebruikend een  [](../../automating/using/editing-queries.md#about-query-editor) vraaggegevens van het gegevensbestand van Adobe Campaign via de lijst van publiek werd gecreeerd. Doelgroepen die op basis van een query worden gedefinieerd, worden bij elk volgend gebruik opnieuw berekend.
* **[!UICONTROL List]**: geeft aan dat de doelgroep bestaat uit een een vaste lijst met profielen. Deze lijsten worden gemaakt in een [workflow](../../automating/using/get-started-workflows.md) waarbij de datadimensie bekend is bij het opslaan van de doelgroep. Bijvoorbeeld na bepaalde targetingactiviteiten (met name **[!UICONTROL Query]**) of na de afstemming van data die vanuit een bestand zijn geïmporteerd.
* **[!UICONTROL File]**: geeft aan dat de doelgroep rechtstreeks is gebaseerd op een workflow voor [bestandsimport](../../automating/using/load-file.md) en dat de datadimensie onbekend was toen de doelgroep werd opgeslagen.
* **[!UICONTROL Experience Cloud]**: geeft aan dat de doelgroep is geïmporteerd uit Adobe Experience Cloud. Deze optie is alleen beschikbaar als de functionaliteit voor het delen van doelgroepen is geconfigureerd. Zie [Een doelgroep importeren uit Adobe Experience Cloud](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md#importing-an-audience) voor meer informatie.

![](assets/audience_type_selection.png)
