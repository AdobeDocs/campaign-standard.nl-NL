---
title: Levering in de app
description: Met de leveringsactiviteit in de app kunt u het verzenden van een In-App-bericht binnen een workflow configureren.
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
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Levering in de app{#in-app-delivery}

## Beschrijving {#description}

![](assets/wkf_in_app_1.png)

Met de **leveringsactiviteit** in de app kunt u het verzenden van een In-App-bericht binnen een workflow configureren. Met In-App-berichten kunt u een bericht weergeven wanneer de gebruiker actief is in de toepassing. Raadpleeg deze [sectie](../../channels/using/about-in-app-messaging.md)voor meer informatie over de levering in de app.

## Gebruikscontext {#context-of-use}

De **[!UICONTROL In-App delivery]** activiteit wordt over het algemeen gebruikt om het verzenden van een bericht In-App aan een doelpubliek te automatiseren dat in de zelfde werkschema wordt berekend.

De ontvangers worden vóór de activiteit in de zelfde werkschema gedefinieerd, via het richten van activiteiten zoals vragen, snijpunten, enz.

De voorbereiding van berichten wordt geactiveerd volgens de parameters voor workflowuitvoering. Van het berichtdashboard, kunt u selecteren of om een manuele bevestiging te verzoeken of niet om het bericht te verzenden (die door gebrek wordt vereist). U kunt de workflow handmatig starten of een planneractiviteit in de workflow plaatsen om de uitvoering te automatiseren.

## Configuratie {#configuration}

1. Sleep een **[!UICONTROL Query]** activiteit naar uw werkstroom. Houd er rekening mee dat de **[!UICONTROL Query]** activiteit die gericht is op dimensie op het **[!UICONTROL Properties]** tabblad moet worden bijgewerkt volgens het model dat in stap 4 is gekozen:

   * Targetingdimensie moet worden ingesteld op **[!UICONTROL mobileApp (mobileAppV5)]** voor de sjabloon **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]**.
   * Targetingdimensie moet worden ingesteld op **[!UICONTROL profile (profile)]** voor de sjabloon **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]**.
   * Targetingdimensie moet worden ingesteld op **[!UICONTROL subscriptions to an application (nms:appSubscriptionRcp:appSubscriptionRcpDetail)]** voor de sjabloon **[!UICONTROL Target users based on their Mobile profile (inApp)]**.

1. Sleep een **[!UICONTROL In-App delivery]** activiteit naar uw werkstroom.
1. Selecteer de activiteit, dan open het gebruikend de ![](assets/edit_darkgrey-24px.png) knoop van de snelle acties die verschijnen.

   >[!NOTE]
   >
   >U kunt de algemene eigenschappen en geavanceerde opties van de activiteit (en niet van de levering zelf) via de ![](assets/dlv_activity_params-24px.png) knoop van de snelle acties van de activiteit toegang hebben.

   ![](assets/wkf_in_app_3.png)

1. Selecteer het berichttype in de app. Dit hangt af van de gegevens die in uw **[!UICONTROL Query]** activiteit worden bedoeld.

   * **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]**: Met dit berichttype kunt u zich richten op Adobe Campagne-profielen die zijn geabonneerd op uw mobiele toepassing en kunt u In-App-berichten personaliseren met profielkenmerken die beschikbaar zijn in Campagne.
   * **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]**: Met dit berichttype kunt u een bericht verzenden naar alle gebruikers van uw mobiele toepassing, zelfs als zij geen bestaand profiel in Campagne hebben.
   * **[!UICONTROL Target users based on their Mobile profile (inApp)]**: Met dit berichttype kunt u alle gebruikers van een mobiele app met een mobiel profiel in Campaign als doel instellen, ongeacht of dit bekend is of niet, en kunt u In-App-berichten personaliseren met alle profielkenmerken die zijn verkregen van een mobiel apparaat.
   ![](assets/wkf_in_app_4.png)

1. Voer de berichteigenschappen in de app in en selecteer de mobiele app in het **[!UICONTROL Associate a Mobile App to a delivery]** veld.
1. Sleep op het **[!UICONTROL Triggers]** tabblad de gebeurtenis die het bericht activeert. Er zijn drie categorieën gebeurtenissen beschikbaar:
1. Definieer uw inhoud in de app. Raadpleeg de sectie over [In-App-aanpassing](../../channels/using/customizing-an-in-app-message.md).
1. Standaard bevat de **[!UICONTROL In-App delivery]** activiteit geen uitgaande overgangen. Als u een uitgaande overgang aan uw **[!UICONTROL In-App delivery]** activiteit wilt toevoegen, ga naar het **[!UICONTROL General]** lusje van de geavanceerde activiteitenopties ( ![](assets/dlv_activity_params-24px.png) knoop in de snelle acties van de activiteit) dan controleren één van de volgende opties:

   * **[!UICONTROL Add outbound transition without the population]**: dit laat u een uitgaande overgang produceren die de nauwkeurige zelfde bevolking zoals de binnenkomende overgang bevat.
   * **[!UICONTROL Add outbound transition with the population]**: dit laat u een uitgaande overgang produceren die de bevolking bevat aan wie het bericht werd verzonden. De leden van het doel die tijdens de voorbereiding van de levering zijn uitgesloten, zijn van deze overgang uitgesloten.
   ![](assets/wkf_in_app_5.png)

1. Bevestig de configuratie van uw activiteit en sla uw werkschema op.

Wanneer u de activiteit opnieuw opent, wordt u rechtstreeks genomen aan het dashboard in-App. Alleen de inhoud kan worden bewerkt.

Door gebrek, leidt het beginnen van een leveringswerkschema slechts tot de berichtvoorbereiding. Het verzenden van berichten die op basis van een workflow zijn gemaakt, moet nog worden bevestigd nadat de workflow is gestart. Maar van het berichtdashboard, en slechts als het bericht van een werkschema werd gecreeerd, kunt u de **[!UICONTROL Request confirmation before sending messages]** optie onbruikbaar maken. Als u deze optie uitschakelt, worden berichten zonder verdere kennisgeving verzonden zodra de voorbereiding is voltooid.

## Opmerkingen {#remarks}

De leveringen die in een workflow worden gemaakt, zijn toegankelijk in de lijst met marketingactiviteiten van de toepassing. U kunt de uitvoeringsstatus van de workflow weergeven via het dashboard. Via koppelingen in het overzichtsvenster voor pushmeldingen hebt u rechtstreeks toegang tot gekoppelde elementen (workflow, campagne, enz.).

In de ouderleveringen, die van de marketing activiteitenlijst kunnen worden betreden, kunt u het totale aantal verzenden bekijken die zijn verwerkt (volgens de samenvoegingsperiode die wordt gespecificeerd toen de **[!UICONTROL In-App delivery]** activiteit werd gevormd). U doet dit door de detailweergave van het **[!UICONTROL Deployment]** blok van de bovenliggende levering te openen door ![](assets/wkf_dlv_detail_button.png)te selecteren.
