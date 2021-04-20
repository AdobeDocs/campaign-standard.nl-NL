---
solution: Campaign Standard
product: campaign
title: Campagnes aanpassen met behulp van Adobe Experience Platform-kenmerken
description: Leer hoe u uw campagnes kunt personaliseren met de kenmerken van het Adobe-Platform.
audience: automating
content-type: reference
topic-tags: channel-activities
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 7%

---


# Campagnes aanpassen met behulp van Adobe Experience Platform-kenmerken {#personalizing-campaigns-using-aep-attributes}

>[!IMPORTANT]
>
>De dienst van de Doelen van het publiek is momenteel in bèta, die aan regelmatige updates zonder bericht kan worden onderworpen. Klanten moeten op Azure (momenteel alleen in bèta voor Noord-Amerika) worden gehost om toegang te krijgen tot deze mogelijkheden. Neem contact op met de klantenservice van Adobe als u toegang wilt.
>
>**** Pushand  **in-** apps zijn nog niet beschikbaar voor personalisatie met gebruik van contextuele gegevens van Adobe Experience Platform.

Zodra uw werkschema met [Adobe Experience Platform publiek](../../integrating/using/aep-about-audience-destinations-service.md) wordt gevormd, kunt u berichten met profielattributen personaliseren die uitsluitend in het Model van de Gegevens van de Ervaring (XDM) bestaan.

Hiervoor moet u deze kenmerken toevoegen aan de **[!UICONTROL Read audience]**-activiteit:

1. Open de **[!UICONTROL Read audience]** activiteit. Klik op het tabblad **[!UICONTROL Additional data]** op de knop **[!UICONTROL Create element]**.

   Het tabblad **[!UICONTROL Additional data]** is alleen beschikbaar nadat een Adobe Experience Platform-publiek is geselecteerd.

   ![](assets/aep_wkf_readaudience_attributes.png)

   >[!NOTE]
   >
   >De gegevenstypen Array en Map worden niet ondersteund in deze functie. Ook, slechts zullen de gegevens van het unieschema in de plukker worden getoond.

1. Selecteer het gewenste XDM-veld in de lijst en klik op **[!UICONTROL Confirm]**.

   ![](assets/aep_wkf_readaudience_perso1.png)

1. Klik op de knop **[!UICONTROL Add]** om deze toe te voegen aan de lijst met aanvullende gegevens.

   ![](assets/aep_wkf_readaudience_perso3.png)

1. Herhaal deze stappen voor elk XDM gebied dat u in uw werkschema wilt toevoegen.

   >[!NOTE]
   >
   >U kunt maximaal 20 XDM gebieden in een **[!UICONTROL Read audience]** activiteit toevoegen.

1. Nadat alle velden zijn toegevoegd, klikt u op de knop **[!UICONTROL Confirm]** om de wijzigingen op te slaan. Ze zijn nu beschikbaar om uw leveringen aan te passen.

Raadpleeg de documentatie bij Campaign Standard voor meer informatie over het maken en personaliseren van leveringen:

* [Communicatiekanalen detecteren](../../channels/using/get-started-communication-channels.md)
* [Informatie over kanaalactiviteiten](../../automating/using/about-channel-activities.md)
* [Leveringen personaliseren](../../designing/using/personalization.md)
