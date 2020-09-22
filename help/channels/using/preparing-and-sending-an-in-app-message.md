---
title: Een in-app-bericht voorbereiden en verzenden
description: Maak een in-app-bericht om de abonnees van uw applicatie doelgericht te benaderen met specifieke content.
page-status-flag: never-activated
uuid: a79b0466-8641-46cc-a70f-e4e839587bb2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: in-app-messaging
discoiquuid: 18bf5297-a688-4302-abe4-e2fbcafdb515
context-tags: delivery,triggers,back;deliveryCreation,wizard
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: df70a2165c5d3a4b553565d9a91ec3f8da1b44aa
workflow-type: tm+mt
source-wordcount: '1274'
ht-degree: 98%

---


# Een in-app-bericht voorbereiden en verzenden{#preparing-and-sending-an-in-app-message}

>[!NOTE]
>
>In-app-personalisatie is afhankelijk van een koppelingsveld dat doorgaans een CRM-id en/of een aanmeldings-id voor een mobiele app is. U bent als enige verantwoordelijk voor het beveiligen van dit koppelingsveld wanneer dit wordt gebruikt in combinatie met Adobe Campaign. Als u uw koppelingsveld(en) niet veilig houdt, kan uw persoonlijke bericht kwetsbaar zijn. Adobe is niet aansprakelijk voor schade die voortvloeit uit ongeoorloofde toegang tot of gebruik van profieldata als u de compositie, het beheer en de beveiligingspraktijken voor veilige koppelingsvelden niet opvolgt.

Er zijn drie typen in-app-berichten beschikbaar in Adobe Campaign:

* **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]**: Met dit berichttype kunt u zich richten op Adobe Campaign-profielen (CRM-profielen) die zijn geabonneerd op uw mobiele applicatie. Dit berichttype kan met alle beschikbare profielkenmerken in Adobe Campaign worden gepersonaliseerd maar vereist een veilige handshake tussen Mobile SDK en de in-app-berichtenservice van Adobe Campaign om ervoor te zorgen dat berichten met persoonlijke en gevoelige informatie alleen door geautoriseerde gebruikers worden gebruikt.

   Om dit berichttype op gebruikersapparaten te downloaden, moet Mobile SDK koppelingsgebieden verzenden die worden gebruikt om een mobiel profiel te koppelen aan een CRM-profiel in Adobe Campaign. Raadpleeg deze [pagina](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference)voor meer informatie over SDK API&#39;s die vereist zijn voor ondersteuning van in-app-berichten.

* **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]**: Met dit berichttype kunt u berichten verzenden naar alle (huidige of toekomstige) gebruikers van uw mobiele applicatie, zelfs als ze geen bestaand profiel hebben in Adobe Campaign. Personalisatie is dus niet mogelijk wanneer u de berichten aanpast, omdat het gebruikersprofiel mogelijk niet eens bestaat in Adobe Campaign.
* **[!UICONTROL Target users based on their Mobile profile (inApp)]**: Met dit berichttype kunt u zich richten op alle bekende of anonieme gebruikers van een mobiele app met een mobiel profiel in Adobe Campaign. Dit berichttype kan worden gepersonaliseerd met alleen niet-persoonlijke en niet-gevoelige kenmerken en vereist geen veilige handshake tussen Mobile SDK en de in-app-berichtenservice van Adobe Campaign.

   Zie [Mobiele profielvelden met persoonlijke en vertrouwelijke gegevens verwerken](#handling-mobile-profile-fields-with-personal-and-sensitive-data) voor meer informatie over hoe u met persoonlijke en vertrouwelijke gegevens kunt omgaan.

![](assets/diagram_inapp.png)

## Mobiele profielvelden met persoonlijke en vertrouwelijke gegevens verwerken{#handling-mobile-profile-fields-with-personal-and-sensitive-data}

In Adobe Campaign worden data van mobiele profielkenmerken die vanaf een mobiel apparaat worden verzonden, opgeslagen in de resource **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** waardoor u de data die u van de abonnees van uw applicaties wilt verzamelen, kunt definiëren.

Deze resource moet worden uitgebreid om data te verzamelen die u van het mobiele apparaat naar Adobe Campaign wilt verzenden. Raadpleeg deze [pagina](../../developing/using/extending-the-subscriptions-to-an-application-resource.md) voor de gedetailleerde stappen als u dit wilt doen.

Om personalisatie van uw in-app-berichten veiliger te maken moeten de mobiele profielvelden van deze resource dienovereenkomstig worden geconfigureerd. Wanneer u uw nieuwe mobiele profielvelden maakt, schakelt u in uw **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** de optie **[!UICONTROL Personal and Sensitive]** om deze onbeschikbaar te maken tijdens personalisatie van in-app-berichten.

>[!NOTE]
>
>Als u een bestaande implementatie hebt met een extensie voor aangepaste resources in deze tabel, raden we u aan de velden op de juiste wijze te labelen voordat u ze gebruikt voor de personalisatie van in-app-berichten.

![](assets/in_app_personal_data_2.png)

Zodra uw aangepaste resource voor **[!UICONTROL Subscriptions to an application]** is geconfigureerd en gepubliceerd, kunt u beginnen met de voorbereiding van uw in-app-levering met behulp van de sjabloon **[!UICONTROL Target users based on their Mobile profile (inApp)]**. Alleen niet-persoonlijke en niet-gevoelige velden zijn beschikbaar voor personalisatie vanuit de resource **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]**.

Als u personalisatie met **persoonlijke en gevoelige** velden nodig hebt, raden wij u aan de sjabloon **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]** te gebruiken die over een extra veiligheidsmechanisme beschikt om ervoor te zorgen dat de PII-data van uw gebruikers veilig blijven.

## Uw in-app-bericht voorbereiden {#preparing-your-in-app-message}

De stappen voor het maken van een zelfstandig in-app-bericht met Adobe Campaign zijn de volgende:

1. Klik op de kaart **[!UICONTROL In-App messaging]** op de startpagina van Adobe Campaign.

   U kunt ook een in-app-bericht maken via het tabblad **Marketing activities** door op de knop **[!UICONTROL Create]** te klikken.

   Merk op dat een in-app-bericht ook kan worden gemaakt op basis van een campagne of vanaf de startpagina van Adobe Campaign of in een workflow.

1. Selecteer **In-App message**.

   ![](assets/inapp_creating.png)

1. Selecteer een geschikte sjabloon op basis van de behoeften van uw doelgroep.

   ![](assets/inapp_creating_2.png)

   Standaard kunt u een van de volgende drie kant-en-klare sjablonen selecteren:

   * **[!UICONTROL Target users based on their Campaign CRM profile (inAppProfile)]**
   * **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]**
   * **[!UICONTROL Target users based on their Mobile profile (inApp)]**

1. Voer de eigenschappen voor het in-app-bericht in en selecteer de mobiele app in het veld **[!UICONTROL Associate a Mobile App to a delivery]**. Houd er rekening mee dat als u uw mobiele app niet hebt geconfigureerd met Adobe Campaign Standard, deze niet in de lijst wordt weergegeven. Raadpleeg deze [pagina](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#ChannelspecificapplicationconfigurationinAdobeCampaign) voor meer informatie over de configuratie van mobiele applicaties.

   ![](assets/inapp_creating_3.png)

1. Selecteer de doelgroep die u als doel voor uw in-app-bericht wilt instellen. Uw doelgroep wordt vooraf gefilterd afhankelijk van de mobiele applicatie die aan deze levering is gekoppeld.

   Houd er rekening mee dat deze stap niet nodig is voor het **[!UICONTROL Broadcast an In-App message (inAppBroadcast)]** omdat dit gericht is op alle gebruikers van een mobiele applicatie.

   ![](assets/inapp_creating_8.png)

1. Sleep op het tabblad **[!UICONTROL Triggers]** de gebeurtenis die het bericht activeert. Door een trigger te kiezen, kiest u een actie die door gebruikers wordt uitgevoerd en die ertoe leidt dat het in-app-bericht wordt weergegeven.

   Er zijn vier categorieën gebeurtenissen beschikbaar:

   * **[!UICONTROL Mobile Application events]**: Aangepaste gebeurtenissen die in uw mobiele applicatie zijn geïmplementeerd.

      Raadpleeg deze [pagina](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html)voor meer informatie over het maken van gebeurtenissen.

   * **[!UICONTROL Life Cycle events]**: Kant-en-klare levenscyclusgebeurtenissen die worden ondersteund door Adobe Mobile SDK.

      Raadpleeg deze [pagina](https://docs.adobe.com/content/help/en/mobile-services/android/metrics.html)voor meer informatie over levenscyclusgebeurtenissen.

   * **[!UICONTROL Analytics Events]**: De volgende drie categorieën worden ondersteund, afhankelijk van wat er is opgebouwd in uw mobiele app: Adobe Analytics, Context data of View state.

      Deze gebeurtenissen zijn alleen beschikbaar als u een Adobe Analytics-licentie hebt.

   * **[!UICONTROL Places]**: De volgende drie categorieën maken gebruik van realtime locatiedata om contextueel relevante mobiele ervaringen te bieden: Places context data, Places custom metadata of Places event type.

      Raadpleeg de [documentatie bij Places](https://placesdocs.com/) voor meer informatie over Adobe Places.
   ![](assets/inapp_creating_4.png)

1. Als u een **[!UICONTROL Analytics Events]** gebruikt, worden Adobe Analytics- en View state-gebeurtenissen automatisch ingevuld op basis van de rapportsuites die zijn geconfigureerd in de Analytics-extensie in Adobe Experience Platform Launch, terwijl Context data-gebeurtenissen handmatig moeten worden toegevoegd.

   Deze gebeurtenissen zijn alleen beschikbaar als u een Adobe Analytics-licentie hebt.

   ![](assets/inapp_creating_7.png)

1. Als u een trigger **[!UICONTROL Places]** gebruikt, worden Places context data, Places custom metadata of Places event type automatisch ingevuld op basis van alle Libraries en hun Points of Interest die zijn gemaakt in Adobe Places.

   Deze trigger wordt alleen op het apparaat toegepast voor de Points of Interest uit de Libraries die in de extensie Places in Experience Platform Launch zijn geselecteerd. Raadpleeg deze [documentatie](https://docs.adobe.com/content/help/en/places/using/places-ext-aep-sdks/places-extension/places-extension.html) voor meer informatie over de extensie Places en over het installeren ervan.

1. Kies op het tabblad **[!UICONTROL Frequency & duration]** de frequentie voor de trigger, de begin- en einddatum, de dag van de week en het tijdstip van de dag waarop het in-app-bericht actief wordt.

   ![](assets/inapp_creating_5.png)

1. Bewerk de content van uw bericht en definieer de geavanceerde opties. Zie [Een in-app-bericht aanpassen](https://helpx.adobe.com/campaign/standard/channels/using/customizing-an-in-app-message.html).

   ![](assets/inapp_creating_6.png)

1. Klik op **[!UICONTROL Create]**.

Uw in-app-bericht is nu klaar om naar de beoogde doelgroep te worden verzonden.

**Verwante onderwerpen:**

* [Een in-app-bericht aanpassen](../../channels/using/customizing-an-in-app-message.md)
* [In-app-rapport](../../reporting/using/in-app-report.md)
* [Een in-app-bericht verzenden binnen een workflow](../../automating/using/in-app-delivery.md)

## Uw in-app-bericht verzenden {#sending-your-in-app-message}

Nadat u de levering hebt voorbereid en de goedkeuringsstappen zijn uitgevoerd, kunt u uw bericht verzenden.

1. Klik op **[!UICONTROL Prepare]** om het doel te berekenen en de berichten te genereren.

   ![](assets/inapp_sending_4.png)

1. Zodra de voorbereiding is voltooid, geeft het venster **Deployment** de volgende KPI&#39;s weer: **Target** en **To deliver**.

   U kunt het venster Deployment controleren door op de knop ![](assets/lp_link_properties.png) voor potentiële uitsluitingen of fouten in uw levering te klikken.

   ![](assets/inapp_sending_5.png)

1. Klik op **[!UICONTROL Confirm]** om uw in-app-bericht te verzenden.

   ![](assets/inapp_sending_6.png)

1. Controleer de status van uw levering via het berichtdashboard en de logboeken. Raadpleeg deze [sectie](../../sending/using/monitoring-a-delivery.md) voor meer informatie.

   De aantallen **[!UICONTROL Delivered]** en **[!UICONTROL Sent]** KPI&#39;s zijn gebaseerd op succesvolle verzendingen van Campaign naar de leveringsservice voor berichten. Merk op dat deze KPI&#39;s geen aanwijzing zijn van het aantal mobiele apparaten dat het bericht heeft ontvangen of gedownload van de leveringsservice voor berichten.

   ![](assets/inapp_sending_7.png)

1. Meet het effect van uw in-app-berichten met leveringsrapporten. Raadpleeg [deze sectie](../../reporting/using/in-app-report.md) voor meer informatie over rapporten.

**Verwante onderwerpen:**

* [In-app-rapport](../../reporting/using/in-app-report.md)
* [Een in-app-bericht verzenden binnen een workflow](../../automating/using/in-app-delivery.md)

