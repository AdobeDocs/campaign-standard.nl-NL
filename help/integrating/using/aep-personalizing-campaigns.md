---
title: Campagnes aanpassen met Adobe Experience Platform-kenmerken
description: Leer hoe u uw campagnes kunt personaliseren met de kenmerken van het Adobe EExperience Platform.
audience: automating
content-type: reference
topic-tags: channel-activities
feature: Microsoft CRM Integration
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 4d4e7e58-e161-4e5a-898a-b5c29ffb20e0
hide: true
hidefromtoc: true
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 6%

---

# Campagnes aanpassen met Adobe Experience Platform-kenmerken {#personalizing-campaigns-using-aep-attributes}

>[!IMPORTANT]
>
>De dienst van de Doelen van het publiek is momenteel in bèta, die aan regelmatige updates zonder bericht kan worden onderworpen. Klanten moeten op Azure (momenteel alleen in bèta voor Noord-Amerika) worden gehost om toegang te krijgen tot deze mogelijkheden. Neem contact op met de klantenservice van Adobe als u toegang wilt.
>
>**duw** en **in-app** kanalen zijn nog niet beschikbaar voor verpersoonlijking gebruikend contextafhankelijke gegevens van Adobe Experience Platform.

Zodra uw werkschema met een [&#x200B; publiek van Adobe Experience Platform &#x200B;](../../integrating/using/aep-about-audience-destinations-service.md) wordt gevormd, kunt u berichten met profielattributen personaliseren die uitsluitend in het Model van de Gegevens van de Ervaring (XDM) bestaan.

Hiervoor moet u deze kenmerken toevoegen aan de **[!UICONTROL Read audience]** -activiteit:

1. Open de **[!UICONTROL Read audience]** -activiteit. Klik op de knop **[!UICONTROL Additional data]** op het tabblad **[!UICONTROL Create element]** .

   Het tabblad **[!UICONTROL Additional data]** is alleen beschikbaar nadat een Adobe Experience Platform-publiek is geselecteerd.

   ![](assets/aep_wkf_readaudience_attributes.png)

   >[!NOTE]
   >
   >De gegevenstypen Array en Map worden niet ondersteund in deze functie. Ook, slechts zullen de gegevens van het unieschema in de plukker worden getoond.

1. Selecteer het gewenste XDM-veld in de lijst en klik op **[!UICONTROL Confirm]** .

   ![](assets/aep_wkf_readaudience_perso1.png)

1. Klik op de knop **[!UICONTROL Add]** om deze toe te voegen aan de lijst met aanvullende gegevens.

   ![](assets/aep_wkf_readaudience_perso3.png)

1. Herhaal deze stappen voor elk XDM gebied dat u in uw werkschema wilt toevoegen.

   >[!NOTE]
   >
   >U kunt maximaal 20 XDM-velden toevoegen aan een **[!UICONTROL Read audience]** -activiteit.

1. Nadat alle velden zijn toegevoegd, klikt u op de knop **[!UICONTROL Confirm]** om de wijzigingen op te slaan. Ze zijn nu beschikbaar om uw leveringen aan te passen.

Raadpleeg de documentatie bij Campaign Standard voor meer informatie over het maken en personaliseren van leveringen:

* [Communicatiekanalen detecteren](../../channels/using/get-started-communication-channels.md)
* [Informatie over kanaalactiviteiten](../../automating/using/about-channel-activities.md)
* [Leveringen aanpassen](../../designing/using/personalization.md)
