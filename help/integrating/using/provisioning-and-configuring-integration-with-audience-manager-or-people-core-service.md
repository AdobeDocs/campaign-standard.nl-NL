---
solution: Campaign Standard
product: campaign
title: De integratie met Audience Manager of de People-kernservice inrichten en configureren
description: 'Leer hoe te om de de dienstintegratie van de Audience Manager/van de Kern van Mensen te vormen beginnen publiek of segmenten met de verschillende oplossingen van Adobe Experience Cloud te delen. '
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
translation-type: tm+mt
source-git-commit: ad7322905c69f9575e11efc9d8f68cf909dc425f
workflow-type: tm+mt
source-wordcount: '719'
ht-degree: 9%

---


# De integratie met Audience Manager of de People-kernservice inrichten en configureren{#provisioning-and-configuring-integration-with-audience-manager-or-people-core-service}

De levering en de configuratie van Audience Manager en de kern van Mensen in Adobe Campaign nemen twee stappen: [Aanvraag indienen bij Adobe](#submitting-request-to-adobe) dan [De integratie configureren in Adobe Campaign](#configuring-the-integration-in-adobe-campaign).

## Aanvraag indienen bij Adobe {#submitting-request-to-adobe}

De de dienstintegratie van de Audience Manager (AAM) of van de Kern van Mensen laat u publiek of segmenten in Adobe Campaign invoeren en uitvoeren.

Deze integratie moet eerst worden geconfigureerd. Als u inrichting van deze integratie wilt aanvragen, schrijft u een e-mail naar [Digital-Request@adobe.com](mailto:Digital-Request@adobe.com) met de volgende informatie:

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Type aanvraag:</strong><br /> </td> 
   <td> AAM/de kern van de Mensen dienst-Campagne Integratie vormen </td> 
  </tr> 
  <tr> 
   <td> <strong>Naam organisatie:</strong><br /> </td> 
   <td> Uw organisatienaam </td> 
  </tr> 
  <tr> 
   <td> <strong>IMS-organisatie-id</strong><br /> </td> 
   <td> Uw IMS-organisatie-id. <br> U kunt uw IMS Organisatie-id op de Experience Cloud, in het menu van het Beleid vinden. Deze wordt ook geleverd wanneer u voor het eerst verbinding maakt met de Adobe Experience Cloud. </td> 
  </tr> 
  <tr> 
   <td> <strong>Omgeving:</strong><br /> </td> 
   <td> Voorbeeld: Productie </td> 
  </tr> 
  <tr> 
   <td> <strong>AAM of Persdienst</strong><br /> </td> 
   <td> Voorbeeld: Adobe Audience Manager. Vergeet niet om aan het inrichtingsteam te vermelden of u al dan niet een Audience Manager-licentie hebt.</td> 
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

## Integratie in Adobe Campaign {#configuring-the-integration-in-adobe-campaign} configureren

Na het voorleggen van dit verzoek, zal Adobe aan de levering van de integratie voor u te werk gaan en u contacteren om details en informatie te verstrekken die u de configuratie moet voltooien:

* [Stap 1: Externe accounts in Adobe Campaign configureren of controleren](#step-1--configure-or-check-the-external-accounts-in-adobe-campaign)
* [Stap 2: Vorm de Gegevensbronnen](#step-2--configure-the-data-sources)
* [Stap 3: Campagne bijhouden-server configureren](#step-3--configure-campaign-tracking-server)
* [Stap 4: De service voor de bezoekersidentiteitskaart configureren](#step-4--configure-the-visitor-id-service)

### Stap 1: Externe accounts in Adobe Campaign configureren of controleren{#step-1--configure-or-check-the-external-accounts-in-adobe-campaign}

We moeten eerst de externe accounts in Adobe Campaign configureren of controleren. Deze rekeningen hadden door Adobe moeten worden gevormd en de noodzakelijke informatie zou aan u moeten worden meegedeeld.

Dit doet u als volgt:

1. Selecteer **Beheer > Toepassingsinstellingen > Externe accounts** in het geavanceerde menu.

   Selecteer een van de volgende externe accounts die beschikbaar zijn voor deze integratie:

   ![](assets/integration_aam_1.png)

1. **[!UICONTROL Receiver server]** invoeren in de volgende notatie
1. Voer **[!UICONTROL AWS Access Key ID]**, **[!UICONTROL Secret Access Key]** en **[!UICONTROL AWS Region]** in.

Uw externe accounts zijn nu geconfigureerd voor deze integratie.

### Stap 2: Gegevensbronnen configureren {#step-2--configure-the-data-sources}

De twee volgende gegevensbronnen worden gecreeerd binnen de Manager van het Publiek: Adobe Campaign (MID) en Adobe Campaign (DeclaredId). Tegelijkertijd zijn deze twee gegevensbronnen beschikbaar in Adobe Campaign:

* **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**: Dit is een uit-van-de-doos gegevensbron die door gebrek voor identiteitskaart van de Bezoeker wordt gevormd. Segmenten die zijn gemaakt op basis van campagne maken deel uit van deze gegevensbron.
* **Gedeclareerde** IDdata-bron: Deze gegevensbron moet met de  **[!UICONTROL DeclaredId]** gegevensbrondefinitie van Audience Manager worden gecreeerd en in kaart gebracht.

In het geval van meerdere websites met verschillende domeinen ondersteunt Adobe Campaign geen afstemming op basis van ECID.

De **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**-gegevensbron configureren:

1. In **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Shared Data Sources]**, select **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**.

   ![](assets/integration_aam_2.png)

1. Kies **[!UICONTROL Adobe Campaign]** in **[!UICONTROL Data Source/ Alias]** drop-down.
1. Voer de **[!UICONTROL AAM Destination ID]** in die door Adobe wordt opgegeven.

   ![](assets/integration_aam_3.png)

1. In de **[!UICONTROL Reconciliation process]** categorie adviseren wij u om de verzoeningscriteria niet te veranderen en altijd **[!UICONTROL Visitor ID]** te gebruiken.
1. Klik op **[!UICONTROL Save]**.

De **[!UICONTROL Declared ID]**-gegevensbron maken:

1. Klik in **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Shared Data Sources]** op de knop **[!UICONTROL Create]**.
1. Bewerk de **[!UICONTROL Label]** van de gegevensbron.
1. Kies in de vervolgkeuzelijst **[!UICONTROL Data Source/ Alias]** de gegevensbron die overeenkomt met de **[!UICONTROL DeclaredID]** gegevensbron uit Audience Manager.
1. Vorm uw gegevensbron door **[!UICONTROL Data Source / Alias]** en **[!UICONTROL AAM Destination ID]** in te gaan die door Adobe wordt verstrekt.
1. Stel de **[!UICONTROL Reconciliation process]** naar wens in.
1. Klik op **[!UICONTROL Save]**.

>[!NOTE]
>
>Het **[!UICONTROL AAM Destination ID]** gebied wordt niet vereist als u de gedeelde gegevensbron voor [Campagne-Triggers integratie](../../integrating/using/configuring-triggers-in-experience-cloud.md) vormt. **[!UICONTROL Priority]** is alleen nodig bij het configureren van de integratie Triggers - Campagne. De prioriteit bepaalt welke gegevensbron eerst zal worden gevormd. Prioriteit kan elk nummer zijn, zoals 1 of 100. Hoe hoger de prioriteit, des te hoger de voorkeur tijdens verzoening.

### Stap 3: Campagne bijhouden-server {#step-3--configure-campaign-tracking-server} configureren

Voor de configuratie van de integratie met de dienst van de Kern van Mensen of de manager van het Publiek, moeten wij ook de server van het Volgen van de Campagne vormen.

Hier, moet u ervoor zorgen de het Volgen van de Campagne Server op het domein (CNAME) wordt geregistreerd. U kunt meer informatie over de configuratie van de domeinnaam in [dit artikel](https://helpx.adobe.com/nl/campaign/kb/domain-name-delegation.html) vinden.

### Stap 4: De Bezoeker-id-service {#step-4--configure-the-visitor-id-service} configureren

Als uw bezoeker-id-service nooit is geconfigureerd op uw wegeigenschappen of websites, raadpleegt u het volgende [document](https://docs.adobe.com/content/help/en/id-service/using/implementation/setup-aam-analytics.html) om te leren hoe u uw service of de volgende [video](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html#step-two) kunt configureren.

Uw configuratie en levering worden voltooid, kan de integratie nu worden gebruikt om publiek of segmenten in te voeren en uit te voeren.
