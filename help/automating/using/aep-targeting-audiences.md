---
title: Adobe Experience Platform-doelgroepen doelgericht benaderen
description: Leer hoe u doelgroepen voor Adobe Experience Platform aanwijst in workflows.
page-status-flag: never-activated
uuid: 528d9472-e447-47af-a6b2-3181aa5fb5ad
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: channel-activities
discoiquuid: 19796aca-6e9e-4d3a-8917-ba660ec7993c
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 5%

---


# Adobe Experience Platform-doelgroepen doelgericht benaderen {#targeting-aep-audiences}

>[!IMPORTANT]
>
>De dienst van de Doelen van het publiek is momenteel in bèta, die aan regelmatige updates zonder bericht kan worden onderworpen. Klanten moeten op Azure (momenteel alleen in bèta voor Noord-Amerika) worden gehost om toegang te krijgen tot deze mogelijkheden. Neem contact op met de klantenservice van Adobe als u toegang wilt.

Zodra u een publiek [van](../../audiences/using/aep-about-audience-destinations-service.md) Adobe Experience Platform gebruikend de Bouwer van het Segment hebt gecreeerd, kunt u het op de zelfde manier gebruiken zoals u voor een publiek van de Campagne binnen werkschema&#39;s om berichten te personaliseren en te verzenden.

Voer de volgende stappen uit om een Adobe Experience Platform-publiek te activeren in uw workflows:

1. Voeg een **[!UICONTROL Read audience]** activiteit in het werkschema toe, dan open het.

1. Selecteer de **[!UICONTROL Adobe Experience Platform]** optie onder **[!UICONTROL Type of audience]** en voeg vervolgens het gewenste publiek toe.

   ![](assets/aep_wkf_readaudience.png)

1. (Optioneel) Als het publiek is geselecteerd, kunt u op de oogknop klikken om de segmentdefinitie te bekijken en/of bewerken (vergeet niet om de wijzigingen opnieuw op te slaan).

   Als u op de oogknop klikt, gaat u naar de Segment Builder (op een ander tabblad) die is gekoppeld aan het geselecteerde publiek in Campagne.

1. Selecteer een **[!UICONTROL Platform data mapping]** element om de gewenste doeldimensie voor het geselecteerde Adobe Experience Platform-publiek op te geven.

   Standaard is de primaire sleutel (bijvoorbeeld iRecipientID voor de tabel Profile, iAppSubscriptionID voor de tabel AppSubscription) die voor de afstemming wordt gebruikt, automatisch beschikbaar in de vervolgkeuzelijst. Als u een object buiten de primaire sleutel wilt plaatsen, moet u een aangepaste **naamruimte** maken.

   >[!NOTE]
   >
   >Voor doelen buiten de primaire sleutel moet u ook een aangepaste doeltoewijzing maken die overeenkomt met de aangepaste naamruimte. For more information on Target Mapping, refer to [this section](../../administration/using/target-mappings-in-campaign.md).

   ![](assets/aep_wkf_readaudience_namespace.png)

   Deze lijst bevat alle afbeeldingen van het Gegevensmodel van de Ervaring (XDM) die op uw instantie zijn gevormd. Raadpleeg [dit speciale document](../../developing/using/aep-about-data-connector.md)voor meer informatie over de Adobe Experience Platform Data Connector.

   ![](assets/aep_wkf_readaudience_namespace2.png)

1. Zodra het publiek en het richten dimensies behoorlijk worden gevormd, klik de **[!UICONTROL Confirm]** knoop om uw veranderingen te bewaren.

U kunt nu uw workflow configureren met andere activiteiten. U kunt bijvoorbeeld een **[!UICONTROL Email delivery]** activiteit koppelen om een e-mail te verzenden naar het geselecteerde publiek.

![](assets/aep_wkf_email.png)

>[!NOTE]
>
>Met Campaign Standard kunt u Adobe Experience Platform-doelgroepen binnen alle leveringskanalen kiezen: E-mails, SMS-berichten, Direct-mailberichten, pushberichten en In-App-berichten.
>
>*Opmerking: Voor alle push- en In-App-berichten ondersteunt Campaign Standard alleen leveringen voor bekende profielen.

Raadpleeg de volgende secties voor meer informatie over het gebruik van workflows en leveringen:

* [Workflows detecteren](../../automating/using/get-started-workflows.md)
* [Een workflow maken](../../automating/using/building-a-workflow.md)
* [Communicatiekanalen detecteren](../../channels/using/get-started-communication-channels.md)
* [Informatie over kanaalactiviteiten](../../automating/using/about-channel-activities.md)
