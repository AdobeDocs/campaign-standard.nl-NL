---
solution: Campaign Standard
product: campaign
title: De doelgroep voor direct mail definiëren
description: Ontdek hoe u het doel voor uw direct-maillevering definieert.
audience: channels
content-type: reference
topic-tags: direct-mail
context-tags: delivery,directMailContent,back
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 100%

---


# De doelgroep voor direct mail definiëren{#defining-the-direct-mail-audience}

U kunt de doelgroep definiëren in de wizard Creation of door op de sectie **Audience** van het leveringsdashboard te klikken.

![](assets/direct_mail_15.png)

## Het hoofddoel definiëren {#defining-the-main-target}

Voor direct mail zijn de doelprofielen die profielen die worden opgenomen in het extractiebestand dat u naar uw direct-mailprovider verzendt.

Voor elk doelprofiel wordt een nieuwe regel toegevoegd aan het extractiebestand. De hoeveelheid profielinformatie die voor elke ontvanger wordt opgenomen, wordt gedefinieerd op het scherm [Defining the extraction](../../channels/using/defining-the-direct-mail-content.md#defining-the-extraction).

>[!CAUTION]
>
>Zorg ervoor dat uw profielen een postadres bevatten aangezien deze informatie essentieel is voor direct-mailproviders. Controleer ook of u het selectievakje **[!UICONTROL Address specified]** in de profieldata hebt ingeschakeld. Zie [Aanbevelingen](../../channels/using/about-direct-mail.md#recommendations).

## Test- en trapprofielen toevoegen {#adding-test-and-trap-profiles}

Voeg testprofielen toe zodat u het bestand met een klein aantal profielen kunt testen. Zo kunt u snel een bestandsvoorbeeld maken om de structuur te testen en te valideren voordat u het eigenlijke bestand voorbereidt. Zie [Testprofielen beheren](../../audiences/using/managing-test-profiles.md).

Het gebruik van traps is essentieel voor direct-mailleveringen. Zij staan u toe om te verifiëren dat uw direct-mailprovider de communicatie echt verzendt en dat deze uw klantenlijst niet naar een andere provider verzendt. Zie [Traps gebruiken](../../sending/using/using-traps.md).

Voor direct-mailleveringen worden traps tijdens de extractie toegevoegd en in het uitvoerdocument geplaatst. Standaard worden ze in de sorteervolgorde van het uitvoerbestand ingevoegd, maar u kunt ervoor kiezen deze aan het einde of het begin van het bestand in te voegen. Selecteer bij het definiëren van de doelgroep de gewenste optie op het tabblad **[!UICONTROL Trap insertion mode]**.

![](assets/direct_mail_trap_insertion_mode.png)
