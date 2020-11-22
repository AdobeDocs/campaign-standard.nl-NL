---
solution: Campaign Standard
product: campaign
title: Levering in de app
description: Met de leveringsactiviteit in de app kunt u het verzenden van een In-App-bericht binnen een workflow configureren.
audience: automating
content-type: reference
topic-tags: channel-activities
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '692'
ht-degree: 47%

---


# Levering in de app{#in-app-delivery}

## Beschrijving {#description}

![](assets/wkf_in_app_1.png)

Met de **leveringsactiviteit** in de app kunt u het verzenden van een In-App-bericht binnen een workflow configureren. Met In-App-berichten kunt u een bericht weergeven wanneer de gebruiker actief is in de toepassing. Raadpleeg deze [sectie](../../channels/using/about-in-app-messaging.md)voor meer informatie over de levering in de app.

## Gebruikscontext {#context-of-use}

The **[!UICONTROL In-App delivery]** activity is generally used to automate sending an In-App message to a target audience calculated in the same workflow.

De ontvangers worden vóór de activiteit in de zelfde werkschema gedefinieerd, via het richten van activiteiten zoals vragen, snijpunten, enz.

De voorbereiding van berichten wordt geactiveerd volgens de parameters voor workflowuitvoering. Op het berichtdashboard kunt u kiezen of u al dan niet handmatig wilt bevestigen of u het bericht wilt versturen (standaard vereist). U kunt de workflow handmatig starten of een planneractiviteit in de workflow plaatsen om de uitvoering te automatiseren.

## Configuratie {#configuration}

1. Drag and drop a **[!UICONTROL Query]** activity to your workflow. Houd er rekening mee dat de **[!UICONTROL Query]** activiteit die gericht is op dimensie op het **[!UICONTROL Properties]** tabblad moet worden bijgewerkt volgens het model dat in stap 4 is gekozen:

   * Targetingdimensie moet worden ingesteld op **[!UICONTROL mobileApp (mobileAppV5)]** voor de sjabloon **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]**.
   * Targetingdimensie moet worden ingesteld op **[!UICONTROL profile (profile)]** voor de sjabloon **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]**.
   * Targetingdimensie moet worden ingesteld op **[!UICONTROL subscriptions to an application (nms:appSubscriptionRcp:appSubscriptionRcpDetail)]** voor de sjabloon **[!UICONTROL Target users based on their Mobile profile (inApp)]**.

1. Sleep een activiteit **[!UICONTROL In-App delivery]** en zet deze neer in uw workflow.
1. Selecteer de activiteit en open deze met de knop ![](assets/edit_darkgrey-24px.png) vanuit de snelle acties die verschijnen.

   >[!NOTE]
   >
   >U kunt de algemene eigenschappen en geavanceerde opties van de activiteit (niet van de levering zelf) raadplegen via de knop ![](assets/dlv_activity_params-24px.png) van de snelle acties van de activiteit.

   ![](assets/wkf_in_app_3.png)

1. Selecteer het berichttype in de app. Dit hangt af van de gegevens die in uw **[!UICONTROL Query]** activiteit worden bedoeld.

   * **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]**: Met dit berichttype kunt u zich richten op Adobe Campaign-profielen die zijn geabonneerd op uw mobiele toepassing en kunt u In-App-berichten personaliseren met profielkenmerken die beschikbaar zijn in Campagne.
   * **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]**: Met dit berichttype kunt u een bericht verzenden naar alle gebruikers van uw mobiele toepassing, zelfs als zij geen bestaand profiel in Campagne hebben.
   * **[!UICONTROL Target users based on their Mobile profile (inApp)]**: Met dit berichttype kunt u alle gebruikers van een mobiele app met een mobiel profiel in Campaign als doel instellen, ongeacht of dit bekend is of niet, en kunt u In-App-berichten personaliseren met alle profielkenmerken die zijn verkregen van een mobiel apparaat.

   ![](assets/wkf_in_app_4.png)

1. Enter your In-App message properties and select your mobile app in the **[!UICONTROL Associate a Mobile App to a delivery]** field.
1. Sleep op het tabblad **[!UICONTROL Triggers]** de gebeurtenis die het bericht activeert. Er zijn drie categorieën gebeurtenissen beschikbaar:
1. Definieer uw inhoud in de app. Raadpleeg de sectie over [In-App-aanpassing](../../channels/using/customizing-an-in-app-message.md).
1. Standaard bevat de activiteit **[!UICONTROL In-App delivery]** geen uitgaande overgangen. Als u een uitgaande overgang wilt toevoegen aan uw activiteit **[!UICONTROL In-App delivery]**, ga dan naar het tabblad **[!UICONTROL General]** van de geavanceerde opties voor activiteiten (de knop ![](assets/dlv_activity_params-24px.png) in de snelle acties van de activiteit) en vink een van de volgende opties aan:

   * **[!UICONTROL Add outbound transition without the population]**: Hiermee kunt u een uitgaande overgang genereren die exact dezelfde populatie als de binnenkomende overgang bevat.
   * **[!UICONTROL Add outbound transition with the population]**: dit laat u een uitgaande overgang produceren die de bevolking bevat aan wie het bericht werd verzonden. De leden van het doel die tijdens de voorbereiding van de levering zijn uitgesloten, zijn van deze overgang uitgesloten.

   ![](assets/wkf_in_app_5.png)

1. Bevestig de configuratie van uw activiteit en sla de workflow op.

Wanneer u de activiteit opnieuw opent, wordt u rechtstreeks genomen aan het dashboard in-App. Alleen de content kan worden bewerkt.

Standaard wordt bij het starten van een leveringsworkflow alleen de berichtvoorbereiding geactiveerd. Het verzenden van berichten die op basis van een workflow zijn gemaakt, moet nog worden bevestigd nadat de workflow is gestart. U kunt echter vanaf het berichtdashboard de optie **[!UICONTROL Request confirmation before sending messages]** uitschakelen, maar alleen als het bericht vanuit een workflow is gemaakt. Als u deze optie uitschakelt, worden berichten zonder verdere kennisgeving verzonden zodra de voorbereiding is voltooid.

## Opmerkingen {#remarks}

De leveringen die in een workflow zijn gemaakt, zijn toegankelijk in de lijst met marketingactiviteiten van de applicatie. U kunt de uitvoeringsstatus van de workflow bekijken via het dashboard. Via koppelingen in het overzichtsvenster voor pushmeldingen hebt u rechtstreeks toegang tot gekoppelde elementen (workflow, campagne, enz.).

In the parent deliveries, which can be accessed from the marketing activity list, you can view the total number of sends that have been processed (according to the aggregation period specified when the **[!UICONTROL In-App delivery]** activity was configured). U doet dit door de detailweergave van het blok **[!UICONTROL Deployment]** van de bovenliggende levering te openen door ![](assets/wkf_dlv_detail_button.png) te selecteren.
