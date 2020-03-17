---
title: Het directe-mailpubliek definiëren
description: Leer hoe u het doel voor direct-maillevering definieert.
page-status-flag: never-activated
uuid: f843e368-5c07-4b53-8943-46f7bf45b62b
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: direct-mail
discoiquuid: f993d1b6-4b9a-4f95-81fc-60c126211bd2
context-tags: delivery,directMailContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 07d68b5bf8d800ebd95919f491e98f1b7a015705

---


# Het directe-mailpubliek definiëren{#defining-the-direct-mail-audience}

U kunt het publiek definiëren in de wizard Maken of door te klikken op de sectie **Publiek** van het dashboard voor de levering.

![](assets/direct_mail_15.png)

## Het hoofddoel definiëren {#defining-the-main-target}

Voor direct mail, zijn de doelprofielen die in het extractiedossier zullen worden omvat dat u naar uw directe postleverancier zult verzenden.

Voor elk doelprofiel wordt een nieuwe regel toegevoegd aan het extractiebestand. De hoeveelheid profielinformatie die voor elke ontvanger zal worden omvat wordt bepaald in het [Bepalen van het extractiescherm](../../channels/using/defining-the-direct-mail-content.md#defining-the-extraction) .

>[!CAUTION]
>
>Zorg ervoor dat uw profielen een postadres omvatten aangezien deze informatie voor direct postleverancier essentieel is. Controleer ook of u het **[!UICONTROL Address specified]** selectievakje in de profielgegevens hebt ingeschakeld. Zie [Aanbevelingen](../../channels/using/about-direct-mail.md#recommendations).

## Testen- en overvulprofielen toevoegen {#adding-test-and-trap-profiles}

Voeg testprofielen toe zodat u het bestand met een klein aantal profielen kunt testen. Zo kunt u snel een bestandsvoorbeeld maken om de structuur te testen en te valideren voordat u het eigenlijke bestand voorbereidt. Zie [Testprofielen](../../audiences/using/managing-test-profiles.md)beheren.

Het gebruik van vallen is van essentieel belang voor directe postzendingen. Zij staan u toe om te verifiëren dat uw direct-mailleverancier werkelijk de mededeling verzendt en dat zij uw cliëntlijst niet naar een andere leverancier verzenden. Zie [Overvullen](../../sending/using/using-traps.md)gebruiken.

Voor direct-mailleveringen worden overvullingen tijdens de extractie toegevoegd en in het uitvoerdocument gemengd. Deze worden standaard ingevoegd in de sorteervolgorde van het uitvoerbestand, maar u kunt ze aan het einde of het begin van het bestand invoegen. Selecteer bij het definiëren van het publiek de gewenste optie op het **[!UICONTROL Trap insertion mode]** tabblad.

![](assets/direct_mail_trap_insertion_mode.png)
