---
title: De inhoud voor direct mail definiëren
description: Leer hoe u de inhoud definieert voor het bezorgen van direct mail.
page-status-flag: never-activated
uuid: c1234c06-4d22-46d7-ad1b-3c88660f9b06
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: direct-mail
discoiquuid: 9e73d6b5-41b4-474b-a880-a0cd5999c2d1
context-tags: delivery,directMailContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# De inhoud voor direct mail definiëren{#defining-the-direct-mail-content}

U kunt de inhoud definiëren in het laatste scherm van de wizard Maken of door op het gedeelte **Inhoud** van het dashboard voor de levering te klikken.

![](assets/direct_mail_6.png)

Het **[!UICONTROL Content]** definitiescherm is specifiek voor het direct-mailkanaal. Het bestaat uit vier tabbladen: **[!UICONTROL Extraction]**, **[!UICONTROL File structure]**, **[!UICONTROL Header]** en **[!UICONTROL Footer]**.

![](assets/direct_mail_11.png)

## De extractie definiëren {#defining-the-extraction}

1. Voer eerst de naam van het extractiebestand in. Klik op de knop rechts van het **[!UICONTROL Output file]** veld en voer het gewenste label in. U kunt aanpassingsvelden, inhoudsblokken en dynamische tekst gebruiken (zie Inhoud [](../../designing/using/personalization.md#example-email-personalization)definiëren). U kunt bijvoorbeeld het label invullen met de leverings-id of de extractiedatum.

   ![](assets/direct_mail_12.png)

1. Klik op de **[!UICONTROL +]** knop of de **[!UICONTROL Add an element]** knop om een uitvoerkolom toe te voegen. Hiermee **[!UICONTROL Output columns]** kunt u de profielgegevens (kolommen) definiëren die naar het uitvoerbestand moeten worden geëxporteerd.

   >[!CAUTION]
   >
   >Zorg ervoor dat uw profielen een postadres omvatten aangezien deze informatie voor direct postleverancier essentieel is. Controleer ook of u het **[!UICONTROL Address specified]** selectievakje in de profielgegevens hebt ingeschakeld. Zie [Aanbevelingen](../../channels/using/about-direct-mail.md#recommendations).

   ![](assets/direct_mail_13.png)

1. Maak zoveel kolommen als u nodig hebt. U kunt kolommen bewerken door op de bijbehorende expressies en labels te klikken.

>[!NOTE]
>
>Raadpleeg het gedeelte Activiteit werkstroom [uitpakken voor meer informatie over de definitie van de uitvoerkolom](../../automating/using/extract-file.md) .

## De bestandsstructuur definiëren {#defining-the-file-structure}

Op het tabblad **Bestandsstructuur** kunt u de uitvoer-, datum- en getalnotaties configureren voor het bestand dat wordt geëxporteerd.

![](assets/direct_mail_14.png)

>[!NOTE]
>
>De beschikbare opties worden beschreven in de [sectie Bestandsactiviteiten](../../automating/using/extract-file.md) uitpakken.

## De kop- en voettekst definiëren {#defining-the-header-and-footer}

Soms moet u informatie toevoegen aan het begin of aan het einde van het extractiebestand. Voor dit, gebruik de **[!UICONTROL Header]** en **[!UICONTROL Footer]** lusjes van het **[!UICONTROL Content]** configuratiescherm.

![](assets/direct_mail_7.png)

U kunt bijvoorbeeld de afzendergegevens in de koptekst van het bestand opnemen bij de provider van direct mail. Het is mogelijk om de voettekst en koptekst aan te passen met informatie die beschikbaar is in de context van de levering. Zie [Inhoud](../../designing/using/personalization.md#example-email-personalization)definiëren.

Het afzenderadres wordt bepaald in de **[!UICONTROL Send]** sectie van de direct-maileigenschappen of op het malplaatjeniveau.

![](assets/direct_mail_24.png)

