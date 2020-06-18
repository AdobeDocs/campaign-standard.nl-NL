---
title: Sjablonen voor bestemmingspagina
description: Meer informatie over sjablonen voor bestemmingspagina's.
page-status-flag: never-activated
uuid: b316bf47-7d98-46fa-ab4f-67ff50de8095
contentOwner: lemaitre
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: landing-pages
discoiquuid: ca8d1698-6e8a-4f5a-b017-74a152e14286
context-tags: landingPage,wizard;landingPage,overview;landingPage,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 012546e109b085b7ed968bcefa8f76482656ae0d
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 0%

---


# Informatie over sjablonen voor openingspagina&#39;s {#landing-page-templates}

Campagne wordt geleverd met een set ingebouwde sjablonen voor bestemmingspagina&#39;s:

* **[!UICONTROL Acquisition]**: Dit is het standaardmalplaatje voor het landen van pagina&#39;s, dat u toelaat om gegevens in het gegevensbestand van de Campagne te vangen en bij te werken.
* **[!UICONTROL Subscription]**: deze template moet worden gebruikt om abonnementen op een service aan te bieden.
* **[!UICONTROL Unsubscription]**: deze sjabloon kan worden gekoppeld via een e-mail die naar abonnees van een service wordt verzonden, zodat zij hun abonnement op deze service kunnen opzeggen.
* **[!UICONTROL Block list]**: deze sjabloon moet worden gebruikt wanneer een profiel niet langer via Campagne in contact wil komen. Raadpleeg [Informatie over opt-in en opt-out in Campagne voor meer informatie over beheer van](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)bloklijsten.

Deze sjablonen worden standaard voorgesteld bij het maken van een nieuwe bestemmingspagina.

![](assets/lp_creation_1.png)

Klik op het Adobe Campaign-logo in de linkerbovenhoek van de landingspagina en selecteer **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Landing page templates]**.

>[!NOTE]
>
>Adobe raadt u aan uw eigen sjablonen te maken door een ingebouwde sjabloon te dupliceren. Sommige parameters kunnen alleen worden ingesteld in sjablonen voor bestemmingspagina&#39;s en kunnen niet rechtstreeks worden gewijzigd in bestemmingspagina&#39;s.

Wanneer het bouwen van een malplaatje, adviseren wij toevoegend een **&#39;type&#39;** attribuut aan markeringen. Deze informatie wordt door de editor verwerkt en helpt de gebruiker bij het configureren van de webtoepassing een databaseveld te koppelen aan het formulierveld.

Voorbeeld van HTML-code in de sjabloon:

```
<input id="email" type="email" name="email"/>
```

De officiële lijst van &#39;type&#39;-kenmerken is beschikbaar op het volgende adres: [https://www.w3schools.com/tags/att_input_type.asp](https://www.w3schools.com/tags/att_input_type.asp)