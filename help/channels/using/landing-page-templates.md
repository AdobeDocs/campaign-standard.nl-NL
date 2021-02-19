---
solution: Campaign Standard
product: campaign
title: Sjablonen voor landingspagina's
description: Leer meer over sjablonen voor landingspagina's.
audience: channels
content-type: reference
topic-tags: landing-pages
context-tags: landingPage,wizard;landingPage,overview;landingPage,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 94%

---


# Informatie over sjablonen voor landingspagina&#39;s {#landing-page-templates}

Campaign wordt geleverd met een aantal kant-en-klare sjablonen voor landingspagina&#39;s:

* **[!UICONTROL Acquisition]**: dit is de standaardsjabloon voor landingspagina&#39;s waarmee u data in de Campaign-database kunt vastleggen en bijwerken.
* **[!UICONTROL Subscription]**: deze sjabloon moet worden gebruikt om abonnementen op een service aan te bieden.
* **[!UICONTROL Unsubscription]**: deze sjabloon kan worden gekoppeld via een e-mail die naar abonnees van een service wordt verzonden, zodat zij hun abonnement op deze service kunnen opzeggen.
* **[!UICONTROL Denylist]**: deze sjabloon moet worden gebruikt wanneer een profiel niet langer wenst te worden gecontacteerd via Campaign. Raadpleeg [Informatie over opt-in en opt-out in Campagne](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md) voor meer informatie over het beheer van lijst van gewezen personen.

Deze sjablonen worden standaard voorgesteld bij het maken van een nieuwe landingspagina.

![](assets/lp_creation_1.png)

Als u de sjablonen voor landingspagina&#39;s wilt openen, klikt u op het logo van Adobe Campaign in de linkerbovenhoek en selecteert u **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Landing page templates]**.

>[!NOTE]
>
>Het wordt aanbevolen uw eigen sjablonen te maken door een ingebouwde sjabloon te dupliceren. Sommige parameters kunnen alleen worden ingesteld in sjablonen voor landingspagina&#39;s en kunnen niet rechtstreeks worden gewijzigd in landingspagina&#39;s.

Bij het samenstellen van een sjabloon wordt aangeraden een **&#39;type’**-attribuut toe te voegen aan tags. Deze informatie wordt door de editor verwerkt en helpt de gebruiker bij het configureren van de webapplicatie een databaseveld te koppelen aan het formulierveld.

Voorbeeld van HTML-code in de sjabloon:

```
<input id="email" type="email" name="email"/>
```

De officiële lijst van &#39;type&#39;-attributen is beschikbaar op het volgende adres: [https://www.w3schools.com/tags/att_input_type.asp](https://www.w3schools.com/tags/att_input_type.asp)

