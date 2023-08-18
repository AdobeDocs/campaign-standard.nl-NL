---
title: In-app-levering
description: Met de leveringsactiviteit in de app kunt u het verzenden van een In-App-bericht binnen een workflow configureren.
audience: automating
content-type: reference
topic-tags: channel-activities
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 8d5a35c4-e22b-498e-b71c-c5922cf8c2fd
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '692'
ht-degree: 47%

---

# In-app-levering{#in-app-delivery}

## Beschrijving {#description}

![](assets/wkf_in_app_1.png)

De **Levering in de app** U kunt het verzenden van een In-App-bericht binnen een workflow configureren. Met In-App-berichten kunt u een bericht weergeven wanneer de gebruiker actief is in de toepassing. Voor meer informatie over de levering in de app raadpleegt u deze [sectie](../../channels/using/about-in-app-messaging.md).

## Gebruikscontext {#context-of-use}

De **[!UICONTROL In-App delivery]** activiteit wordt over het algemeen gebruikt om het verzenden van een bericht In-App aan een doelpubliek te automatiseren dat in het zelfde werkschema wordt berekend.

De ontvangers worden vóór de activiteit in de zelfde werkschema gedefinieerd, via het richten van activiteiten zoals vragen, snijpunten, enz.

De voorbereiding van berichten wordt geactiveerd volgens de parameters voor workflowuitvoering. Op het berichtdashboard kunt u kiezen of u al dan niet handmatig wilt bevestigen of u het bericht wilt versturen (standaard vereist). U kunt de workflow handmatig starten of een planneractiviteit in de workflow plaatsen om de uitvoering te automatiseren.

## Configuratie {#configuration}

1. Sleep een **[!UICONTROL Query]** activiteit aan uw werkschema. Houd er rekening mee dat de **[!UICONTROL Query]** activiteiten die gericht zijn op **[!UICONTROL Properties]** moet worden bijgewerkt volgens het in stap 4 gekozen model:

   * Targetingdimensie moet worden ingesteld op **[!UICONTROL mobileApp (mobileAppV5)]** voor de sjabloon **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]**.
   * Targetingdimensie moet worden ingesteld op **[!UICONTROL profile (profile)]** voor de sjabloon **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]**.
   * Targetingdimensie moet worden ingesteld op **[!UICONTROL subscriptions to an application (nms:appSubscriptionRcp:appSubscriptionRcpDetail)]** voor de sjabloon **[!UICONTROL Target users based on their Mobile profile (inApp)]**.

1. Sleep een activiteit **[!UICONTROL In-App delivery]** en zet deze neer in uw workflow.
1. Selecteer de activiteit en open deze met de knop ![](assets/edit_darkgrey-24px.png) vanuit de snelle acties die verschijnen.

   >[!NOTE]
   >
   >U kunt de algemene eigenschappen en geavanceerde opties van de activiteit (niet van de levering zelf) raadplegen via de knop ![](assets/dlv_activity_params-24px.png) van de snelle acties van de activiteit.

   ![](assets/wkf_in_app_3.png)

1. Selecteer het berichttype in de app. Dit is afhankelijk van de gegevens waarop uw **[!UICONTROL Query]** activiteit.

   * **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]**: Met dit berichttype kunt u zich richten op Adobe Campaign-profielen die zijn geabonneerd op uw mobiele toepassing en kunt u In-App-berichten personaliseren met profielkenmerken die beschikbaar zijn in Campagne.
   * **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]**: Met dit berichttype kunt u een bericht verzenden naar alle gebruikers van uw mobiele toepassing, zelfs als zij geen bestaand profiel in Campagne hebben.
   * **[!UICONTROL Target users based on their Mobile profile (inApp)]**: Met dit berichttype kunt u alle gebruikers van een mobiele app met een mobiel profiel in Campaign als doel instellen, ongeacht of dit bekend is of niet, en kunt u In-App-berichten personaliseren met alle profielkenmerken die zijn verkregen van een mobiel apparaat.

   ![](assets/wkf_in_app_4.png)

1. Voer de berichteigenschappen van uw In-app in en selecteer uw mobiele app in het dialoogvenster **[!UICONTROL Associate a Mobile App to a delivery]** veld.
1. Sleep op het tabblad **[!UICONTROL Triggers]** de gebeurtenis die het bericht activeert. Er zijn drie categorieën gebeurtenissen beschikbaar:
1. Definieer uw inhoud in de app. Zie het gedeelte over [Aanpassing in app](../../channels/using/customizing-an-in-app-message.md).
1. Standaard bevat de activiteit **[!UICONTROL In-App delivery]** geen uitgaande overgangen. Als u een uitgaande overgang wilt toevoegen aan uw activiteit **[!UICONTROL In-App delivery]**, ga dan naar het tabblad **[!UICONTROL General]** van de geavanceerde opties voor activiteiten (de knop ![](assets/dlv_activity_params-24px.png) in de snelle acties van de activiteit) en vink een van de volgende opties aan:

   * **[!UICONTROL Add outbound transition without the population]**: Hiermee kunt u een uitgaande overgang genereren die exact dezelfde populatie als de binnenkomende overgang bevat.
   * **[!UICONTROL Add outbound transition with the population]**: hiermee kunt u een uitgaande overgang genereren die de populatie bevat waarnaar het bericht is verstuurd. De leden van het doel die tijdens de voorbereiding van de levering zijn uitgesloten, zijn van deze overgang uitgesloten.

   ![](assets/wkf_in_app_5.png)

1. Bevestig de configuratie van uw activiteit en sla de workflow op.

Wanneer u de activiteit opnieuw opent, wordt u rechtstreeks genomen aan het dashboard in-App. Alleen de content kan worden bewerkt.

Standaard wordt bij het starten van een leveringsworkflow alleen de berichtvoorbereiding geactiveerd. Het verzenden van berichten die op basis van een workflow zijn gemaakt, moet nog worden bevestigd nadat de workflow is gestart. U kunt echter vanaf het berichtdashboard de optie **[!UICONTROL Request confirmation before sending messages]** uitschakelen, maar alleen als het bericht vanuit een workflow is gemaakt. Als u deze optie uitschakelt, worden berichten zonder verdere kennisgeving verzonden zodra de voorbereiding is voltooid.

## Opmerkingen {#remarks}

De leveringen die in een workflow zijn gemaakt, zijn toegankelijk in de lijst met marketingactiviteiten van de applicatie. U kunt de uitvoeringsstatus van de workflow bekijken via het dashboard. Via koppelingen in het overzichtsvenster voor pushmeldingen hebt u rechtstreeks toegang tot gekoppelde elementen (workflow, campagne, enz.).

In de bovenliggende items, die toegankelijk zijn vanuit de lijst met marketingactiviteiten, kunt u het totale aantal verzonden dat is verwerkt, weergeven (volgens de bij het **[!UICONTROL In-App delivery]** activiteit is geconfigureerd). U doet dit door de detailweergave van het blok **[!UICONTROL Deployment]** van de bovenliggende levering te openen door ![](assets/wkf_dlv_detail_button.png) te selecteren.
