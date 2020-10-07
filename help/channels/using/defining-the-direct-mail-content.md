---
title: De content voor direct mail definiëren
description: Ontdek hoe u de content definieert voor uw direct-maillevering.
page-status-flag: never-activated
uuid: c1234c06-4d22-46d7-ad1b-3c88660f9b06
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: direct-mail
discoiquuid: 9e73d6b5-41b4-474b-a880-a0cd5999c2d1
context-tags: delivery,directMailContent,back
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 100%

---


# De content voor direct mail definiëren{#defining-the-direct-mail-content}

U kunt de content definiëren in het laatste scherm van de wizard Maken of door op de sectie **Content** van het leveringsdashboard te klikken.

![](assets/direct_mail_6.png)

Het scherm voor de definitie van **[!UICONTROL Content]** is specifiek voor het direct-mailkanaal. Het bestaat uit vier tabbladen: **[!UICONTROL Extraction]**, **[!UICONTROL File structure]**, **[!UICONTROL Header]** en **[!UICONTROL Footer]**.

![](assets/direct_mail_11.png)

## De extractie definiëren {#defining-the-extraction}

1. Definieer eerst de naam van het extractiebestand. Klik op de knop rechts van het veld **[!UICONTROL Output file]** en voer het gewenste label in. U kunt personalisatievelden, contentblokken en dynamische tekst gebruiken (zie [Content definiëren](../../designing/using/personalization.md#example-email-personalization)). U kunt bijvoorbeeld het label invullen met de leverings-id of de extractiedatum.

   ![](assets/direct_mail_12.png)

1. Klik op de knop **[!UICONTROL +]** of de knop **[!UICONTROL Add an element]** om een uitvoerkolom toe te voegen. Met de **[!UICONTROL Output columns]** kunt u de profielinformatie (kolommen) definiëren die naar het uitvoerbestand moeten worden geëxporteerd.

   >[!CAUTION]
   >
   >Zorg ervoor dat uw profielen een postadres bevatten aangezien deze informatie essentieel is voor direct-mailproviders. Controleer ook of u het selectievakje **[!UICONTROL Address specified]** in de profieldata hebt ingeschakeld. Zie [Aanbevelingen](../../channels/using/about-direct-mail.md#recommendations).

   ![](assets/direct_mail_13.png)

1. Maak zoveel kolommen als u nodig hebt. U kunt kolommen bewerken door op de bijbehorende expressies en labels te klikken.

>[!NOTE]
>
>Raadpleeg de sectie over activiteit van de workflow voor [Bestand extraheren](../../automating/using/extract-file.md) voor meer informatie over het definiëren van de uitvoerkolom.

## De bestandsstructuur definiëren {#defining-the-file-structure}

Op het tabblad **File structure** kunt u de uitvoer-, datum- en getalnotaties configureren voor het bestand dat wordt geëxporteerd.

![](assets/direct_mail_14.png)

>[!NOTE]
>
>De beschikbare opties worden beschreven in de secties over activiteit van de workflow voor [Bestand extraheren](../../automating/using/extract-file.md).

## De kop- en voettekst definiëren {#defining-the-header-and-footer}

Soms moet u informatie toevoegen aan het begin of aan het einde van het extractiebestand. Hiervoor gebruikt u de tabbladen **[!UICONTROL Header]** en **[!UICONTROL Footer]** van het configuratiescherm voor **[!UICONTROL Content]**.

![](assets/direct_mail_7.png)

U kunt bijvoorbeeld de afzenderdata in de koptekst van het bestand opnemen voor de direct-mailprovider. U kunt de voettekst en koptekst personaliseren met informatie die beschikbaar is in de context van de levering. Zie [Content definiëren](../../designing/using/personalization.md#example-email-personalization).

Het afzenderadres wordt gedefinieerd in de sectie **[!UICONTROL Send]** van de direct-maileigenschappen of op het niveau van de sjabloon.

![](assets/direct_mail_24.png)
