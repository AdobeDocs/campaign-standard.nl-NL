---
title: De levering en het vormen integratie met de Manager van het Publiek of de kerndienst van Mensen
description: 'Leer hoe u de integratie van Audience Manager/People core-services configureert om publiek of segmenten te delen met de verschillende Adobe Experience Cloud-oplossingen. '
page-status-flag: never-activated
uuid: e7329644-0033-4729-b4a7-61bef137f4b5
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
discoiquuid: eb24f4ea-325f-433a-91a0-c45906320bcb
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7e887fff76660dcb0369d4222e1ab3ac391c3a2d

---


# De levering en het vormen integratie met de Manager van het Publiek of de kerndienst van Mensen{#provisioning-and-configuring-integration-with-audience-manager-or-people-core-service}

De levering en de configuratie van de Kern van de Manager van de Publiek en van Mensen in de Campagne van Adobe nemen twee stappen: Aanvraag [indienen bij Adobe](#submitting-request-to-adobe) en vervolgens de integratie [configureren in Adobe-campagne](#configuring-the-integration-in-adobe-campaign).

## Aanvraag indienen bij Adobe {#submitting-request-to-adobe}

Met de integratie van Audience Manager (AAM) of People core-services kunt u soorten publiek of segmenten in Adobe Campaign importeren en exporteren.

Deze integratie moet eerst worden geconfigureerd. Als u inrichting van deze integratie wilt aanvragen, schrijft u een e-mail naar [Digital-Request@adobe.com](mailto:Digital-Request@adobe.com) met de volgende informatie:

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Type aanvraag:</strong><br /> </td> 
   <td> AAM/de kern van Mensen dienst-Campagne Integratie vormen </td> 
  </tr> 
  <tr> 
   <td> <strong>Naam organisatie:</strong><br /> </td> 
   <td> Uw organisatienaam </td> 
  </tr> 
  <tr> 
   <td> <strong>IMS Org ID</strong><br /> </td> 
   <td> Uw IMS-organisatie-id. <br> U vindt uw IMS-organisatie-id in de Experience Cloud in het menu Beheer. Deze wordt ook geleverd wanneer u voor het eerst verbinding maakt met de Adobe Experience Cloud. </td> 
  </tr> 
  <tr> 
   <td> <strong>Omgeving:</strong><br /> </td> 
   <td> Voorbeeld: Productie </td> 
  </tr> 
  <tr> 
   <td> <strong>AAM of Personenservice</strong><br /> </td> 
   <td> Voorbeeld: Adobe Audience Manager. Vergeet niet om aan het provisioningteam mee te delen of u al dan niet een licentie voor Audience Manager hebt.</td> 
  </tr> 
  <tr> 
   <td> <strong>Opgegeven ID of bezoeker-ID</strong><br /> </td> 
   <td> Voorbeeld: Opgegeven id </td> 
  </tr> 
  <tr> 
   <td> <strong>Aanvullende informatie</strong><br /> </td> 
   <td> Eventuele nuttige informatie of opmerkingen </td> 
  </tr> 
 </tbody> 
</table>

## Integratie in Adobe-campagne configureren {#configuring-the-integration-in-adobe-campaign}

Nadat u dit verzoek hebt verzonden, gaat Adobe door met de levering van de integratie voor u. Neem contact op met u voor meer informatie en informatie die u nodig hebt om de configuratie te voltooien:

* [Stap 1: Externe accounts configureren of controleren in Adobe-campagne](#step-1--configure-or-check-the-external-accounts-in-adobe-campaign)
* [Stap 2: Vorm de Gegevensbronnen](#step-2--configure-the-data-sources)
* [Stap 3: Campagne bijhouden-server configureren](#step-3--configure-campaign-tracking-server)
* [Stap 4: De service voor de bezoekersidentiteitskaart configureren](#step-4--configure-the-visitor-id-service)

### Stap 1: Externe accounts configureren of controleren in Adobe-campagne {#step-1--configure-or-check-the-external-accounts-in-adobe-campaign}

We moeten eerst de externe accounts configureren of controleren in Adobe Campaign. Deze accounts zouden door Adobe moeten zijn geconfigureerd en de benodigde informatie zou aan u moeten zijn doorgegeven.

Daartoe:

1. Kies in het menu Geavanceerd de optie **Beheer > Toepassingsinstellingen > Externe accounts**.

   Selecteer een van de volgende externe accounts die beschikbaar zijn voor deze integratie:

   ![](assets/integration_aam_1.png)

1. Voer **[!UICONTROL Receiver server]** de volgende notatie in
1. Voer de **[!UICONTROL AWS Access Key ID]**, **[!UICONTROL Secret Access Key]** en **[!UICONTROL AWS Region]**.

Uw externe accounts zijn nu geconfigureerd voor deze integratie.

### Stap 2: Vorm de Gegevensbronnen {#step-2--configure-the-data-sources}

De twee volgende gegevensbronnen worden gecreeerd binnen de Manager van het Publiek: Adobe-campagne (MID) en Adobe-campagne (DeclaredId). De volgende twee gegevensbronnen zijn beschikbaar in Adobe Campaign:

* **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**: Dit is een uit-van-de-doos gegevensbron die door gebrek voor identiteitskaart van de Bezoeker wordt gevormd. Segmenten die zijn gemaakt op basis van campagne maken deel uit van deze gegevensbron.
* **Opgegeven ID** -gegevensbron: Deze gegevensbron moet met de **[!UICONTROL DeclaredId]** gegevensbrondefinitie van de Manager van de Publiek worden gecreeerd en in kaart gebracht.

Houd er rekening mee dat in het geval van meerdere websites met verschillende domeinen Adobe Campaign geen ondersteuning biedt voor afstemming op basis van ECID.

De **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]** gegevensbron configureren:

1. In **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Shared Data Sources]**, select **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**.

   ![](assets/integration_aam_2.png)

1. Kies deze optie **[!UICONTROL Adobe Campaign]** in de **[!UICONTROL Data Source/ Alias]** vervolgkeuzelijst.
1. Voer de gegevens in die door Adobe zijn **[!UICONTROL AAM Destination ID]** verstrekt.

   ![](assets/integration_aam_3.png)

1. In de **[!UICONTROL Reconciliation process]** categorie adviseren wij u de verzoeningscriteria niet te wijzigen en altijd de criteria te gebruiken **[!UICONTROL Visitor ID]**.
1. Klik op **[!UICONTROL Save]**.

De **[!UICONTROL Declared ID]** gegevensbron maken:

1. Klik in **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Shared Data Sources]** op de **[!UICONTROL Create]** knop.
1. Bewerk de **[!UICONTROL Label]** gegevensbron.
1. Kies in het **[!UICONTROL Data Source/ Alias]** keuzemenu de gegevensbron die overeenkomt met de **[!UICONTROL DeclaredID]** gegevensbron in Audience Manager.
1. Configureer uw gegevensbron door de gegevens in te voeren **[!UICONTROL Data Source / Alias]** en door Adobe te **[!UICONTROL AAM Destination ID]** leveren.
1. Stel de **[!UICONTROL Reconciliation process]** gewenste waarden in.
1. Klik op **[!UICONTROL Save]**.

>[!NOTE]
>
>Het **[!UICONTROL AAM Destination ID]** veld is niet vereist als u de gedeelde gegevensbron voor de [integratie](../../integrating/using/configuring-triggers-in-experience-cloud.md)Campagne-Triggers configureert. **[!UICONTROL Priority]** is alleen nodig bij het configureren van de integratie Triggers - Campagne. De prioriteit bepaalt welke gegevensbron eerst zal worden gevormd. Prioriteit kan elk nummer zijn, zoals 1 of 100. Hoe hoger de prioriteit, des te hoger de voorkeur tijdens verzoening.

### Stap 3: Campagne bijhouden-server configureren {#step-3--configure-campaign-tracking-server}

Voor de configuratie van de integratie met de dienst van de Kern van Mensen of de manager van het Publiek, moeten wij ook de server van het Volgen van de Campagne vormen.

Hier, moet u ervoor zorgen de het Volgen van de Campagne Server op het domein (CNAME) wordt geregistreerd. Meer informatie over domeinnaamdelegatie vindt u in [dit artikel](https://docs.campaign.adobe.com/doc/AC/en/technicalResources/Technotes/AdobeCampaign_Deliverability_Sub_Domain_Delegation.pdf).

### Stap 4: De service voor de bezoekersidentiteitskaart configureren {#step-4--configure-the-visitor-id-service}

Raadpleeg het volgende [document](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-setup-aam-analytics.html) voor informatie over het configureren van uw service of de volgende [video](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html#step-two)als uw bezoeker-id nog nooit is geconfigureerd op uw webeigenschappen of websites.

Uw configuratie en levering worden voltooid, kan de integratie nu worden gebruikt om publiek of segmenten in te voeren en uit te voeren.
