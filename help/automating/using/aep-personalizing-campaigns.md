---
title: Campagnes aanpassen met de kenmerken van het Adobe Experience Platform
description: Leer hoe u uw campagnes kunt personaliseren met de kenmerken van het Adobe-ervaringsplatform.
page-status-flag: never-activated
uuid: 528d9472-e447-47af-a6b2-3181aa5fb5ad
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: channel-activities
discoiquuid: 19796aca-6e9e-4d3a-8917-ba660ec7993c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 68e825bc3b6b7f94f61875e7da2bc8f63f06d9cb

---


# Campagnes aanpassen met de kenmerken van het Adobe Experience Platform {#personalizing-campaigns-using-aep-attributes}

>[!IMPORTANT]
>
>De dienst van de Doelen van het publiek is momenteel in bèta, die aan regelmatige updates zonder bericht kan worden onderworpen. Klanten moeten op Azure (momenteel alleen in bèta voor Noord-Amerika) worden gehost om toegang te krijgen tot deze mogelijkheden. Neem contact op met de klantenservice van Adobe als u toegang wilt.
>
>**Push** - en **in-app** -kanalen zijn nog niet beschikbaar voor personalisatie met gebruik van contextuele gegevens van het Adobe Experience Platform.

Zodra uw werkschema met een publiek [van het Platform van de Ervaring van](../../audiences/using/aep-about-audience-destinations-service.md)Adobe wordt gevormd, kunt u berichten met profielattributen personaliseren die uitsluitend in het Model van de Gegevens van de Ervaring (XDM) bestaan.

Hiervoor moet u de volgende kenmerken aan de **[!UICONTROL Read audience]** activiteit toevoegen:

1. Open de **[!UICONTROL Read audience]** activiteit. Klik op het **[!UICONTROL Additional data]** tabblad op de **[!UICONTROL Create element]** knop.

   Het **[!UICONTROL Additional data]** tabblad is alleen beschikbaar nadat een publiek van het Adobe Experience Platform is geselecteerd.

   ![](assets/aep_wkf_readaudience_attributes.png)

   >[!NOTE]
   >
   >De gegevenstypen Array en Map worden niet ondersteund in deze functie. Ook, slechts zullen de gegevens van het unieschema in de plukker worden getoond.

1. Selecteer het gewenste XDM-veld in de lijst en klik op **[!UICONTROL Confirm]**.

   ![](assets/aep_wkf_readaudience_perso1.png)

1. Klik op de **[!UICONTROL Add]** knop om deze toe te voegen aan de lijst met aanvullende gegevens.

   ![](assets/aep_wkf_readaudience_perso3.png)

1. Herhaal deze stappen voor elk XDM gebied dat u in uw werkschema wilt toevoegen.

   >[!NOTE]
   >
   >U kunt maximaal 20 XDM-velden toevoegen aan een **[!UICONTROL Read audience]** activiteit.

1. Nadat alle velden zijn toegevoegd, klikt u op de **[!UICONTROL Confirm]** knop om de wijzigingen op te slaan. Ze zijn nu beschikbaar om uw leveringen aan te passen.

Raadpleeg de documentatie bij Campagnestandaard voor meer informatie over het maken en personaliseren van leveringen:

* [Communicatiekanalen detecteren](../../channels/using/get-started-communication-channels.md)
* [Kanaalactiviteiten](../../automating/using/about-channel-activities.md)
* [Leveringen aanpassen](../../designing/using/personalization.md)
