---
title: De integratie met Audience Manager of de People core-service inrichten en configureren
description: Leer hoe te om de de dienstintegratie van de Audience Manager/van de Kern van Mensen te vormen beginnen publiek of segmenten met de verschillende oplossingen van Adobe Experience Cloud te delen.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
feature: People Core Service Integration
role: Data Architect
level: Intermediate
exl-id: 04d0fe26-a8cc-49ae-aaa9-b470169068ee
source-git-commit: 26e37cea37b33924ac634c5e4ab7c60804a738f1
workflow-type: tm+mt
source-wordcount: '769'
ht-degree: 9%

---

# De integratie met Audience Manager of de People core-service inrichten en configureren{#integration-with-audience-manager-or-people-core-service}

De levering en de configuratie van Audience Manager en de kern van Mensen in Adobe Campaign nemen twee stappen: [Verzoek tot Adobe indienen](#submitting-request-to-adobe) dan [Integratie in Adobe Campaign configureren](#configuring-the-integration-in-adobe-campaign).

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
   <td> Uw organisatie-id. <br> Raadpleeg voor meer informatie over uw organisatie-id <a href="https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=nl">deze pagina</a></td> 
  </tr> 
  <tr> 
   <td> <strong>Omgeving:</strong><br /> </td> 
   <td> Voorbeeld: Productie </td> 
  </tr> 
  <tr> 
   <td> <strong>AAM of Persdienst</strong><br /> </td> 
   <td> Voorbeeld: Adobe Audience Manager. Vergeet niet om aan het provisioningteam mee te delen of u al dan niet een Audience Manager-licentie hebt.</td> 
  </tr> 
  <tr> 
   <td> <strong>Opgegeven ID of bezoeker-ID</strong><br /> </td> 
   <td> Voorbeeld: gedeclareerde id </td> 
  </tr> 
  <tr> 
   <td> <strong>Aanvullende informatie</strong><br /> </td> 
   <td> Eventuele nuttige informatie of opmerkingen </td> 
  </tr> 
 </tbody> 
</table>

## Integratie in Adobe Campaign configureren {#configuring-the-integration-in-adobe-campaign}

Na het voorleggen van dit verzoek, zal de Adobe aan de levering van de integratie voor u te werk gaan en u te contacteren om details en informatie te verstrekken die u de configuratie moet voltooien:

* [Stap 1: De externe accounts in Adobe Campaign configureren of controleren](#step-1--configure-or-check-the-external-accounts-in-adobe-campaign)
* [Stap 2: Vorm de Gegevensbronnen](#step-2--configure-the-data-sources)
* [Stap 3: De server voor bijhouden van campagnes configureren](#step-3--configure-campaign-tracking-server)
* [Stap 4: Vorm de Dienst van identiteitskaart van de Bezoeker](#step-4--configure-the-visitor-id-service)

### Stap 1: De externe accounts in Adobe Campaign configureren of controleren {#step-1--configure-or-check-the-external-accounts-in-adobe-campaign}

We moeten eerst de externe accounts in Adobe Campaign configureren of controleren. Deze rekeningen hadden door Adobe moeten worden gevormd en de noodzakelijke informatie zou aan u moeten worden meegedeeld.

Dit doet u als volgt:

1. Selecteer in het menu Geavanceerd de optie **Beheer > Toepassingsinstellingen > Externe accounts**.

   Selecteer een van de volgende externe accounts die beschikbaar zijn voor deze integratie:

   ![](assets/integration_aam_1.png)

1. Enter **[!UICONTROL Receiver server]** in de volgende notatie
1. Voer de **[!UICONTROL AWS Access Key ID]**, **[!UICONTROL Secret Access Key]** en **[!UICONTROL AWS Region]**.

Uw externe accounts zijn nu geconfigureerd voor deze integratie.

### Stap 2: Vorm de Gegevensbronnen {#step-2--configure-the-data-sources}

De volgende twee gegevensbronnen worden gemaakt in Audience Manager: Adobe Campaign (MID) en Adobe Campaign (DeclaredId). Tegelijkertijd zijn deze twee gegevensbronnen beschikbaar in Adobe Campaign:

* **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**: Dit is een gegevensbron buiten de doos die door gebrek voor identiteitskaart van de Bezoeker wordt gevormd. Segmenten die zijn gemaakt op basis van campagne maken deel uit van deze gegevensbron.
* **Opgegeven id** gegevensbron: deze gegevensbron moet worden gemaakt en toegewezen met de **[!UICONTROL DeclaredId]** gegevensbrondefinitie van Audience Manager.

In het geval van meerdere websites met verschillende domeinen ondersteunt Adobe Campaign geen afstemming op basis van ECID.

Om te vormen **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]** gegevensbron:

1. In **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Shared Data Sources]**, selecteert u **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**.

   ![](assets/integration_aam_2.png)

1. Kies **[!UICONTROL Adobe Campaign]** in de **[!UICONTROL Data Source/ Alias]** vervolgkeuzelijst.
1. Voer de **[!UICONTROL AAM Destination ID]** verstrekt door Adobe.

   ![](assets/integration_aam_3.png)

1. In de **[!UICONTROL Reconciliation process]** wij raden u aan de verzoeningscriteria niet te wijzigen en altijd de **[!UICONTROL Visitor ID]**.
1. Klik op **[!UICONTROL Save]**.

Als u de opdracht **[!UICONTROL Declared ID]** gegevensbron:

1. In **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Shared Data Sources]** klikt u op de knop **[!UICONTROL Create]** knop.
1. Bewerk de **[!UICONTROL Label]** van uw gegevensbron.
1. In de **[!UICONTROL Data Source/ Alias]** keuzelijst, kies de Gegevensbron die overeenkomt met de **[!UICONTROL DeclaredID]** gegevensbron uit Audience Manager.
1. Vorm uw gegevensbron door in te gaan **[!UICONTROL Data Source / Alias]** en **[!UICONTROL AAM Destination ID]** verstrekt door Adobe.
1. Stel de **[!UICONTROL Reconciliation process]** indien nodig.
1. Klik op **[!UICONTROL Save]**.

>[!NOTE]
>
>De **[!UICONTROL AAM Destination ID]** veld is niet vereist als u de gedeelde gegevensbron voor de [Integratie van campagne-Triggers](../../integrating/using/configuring-triggers-in-experience-cloud.md). **[!UICONTROL Priority]** is alleen nodig bij het configureren van de integratie Triggers - Campagne. De prioriteit bepaalt welke gegevensbron eerst zal worden gevormd. Prioriteit kan elk nummer zijn, zoals 1 of 100. Hoe hoger de prioriteit, des te hoger de voorkeur tijdens verzoening.

### Stap 3: De server voor bijhouden van campagnes configureren {#step-3--configure-campaign-tracking-server}

Voor de configuratie van de integratie met de dienst van de Kern van Mensen of de manager van het Publiek, moeten wij ook de server van het Volgen van de Campagne vormen.

Als u wilt dat een gedeeld publiek kan functioneren met de bezoeker-id, moet het trackingserverdomein een subdomein zijn van de aangeklikte URL of de hoofdwebsite.

>[!IMPORTANT]
>
> U moet ervoor zorgen de het Volgen van de Campagne Server op het domein (CNAME) wordt geregistreerd. Meer informatie over domeinnaamconfiguratie vindt u in [dit artikel](https://helpx.adobe.com/nl/campaign/kb/domain-name-delegation.html).

### Stap 4: Vorm de Dienst van identiteitskaart van de Bezoeker {#step-4--configure-the-visitor-id-service}

Raadpleeg het volgende als uw bezoekersidentiteitsservice nog nooit is geconfigureerd op uw webeigenschappen of websites [document](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-aam-analytics.html) leren hoe te om uw dienst of het volgende te vormen [video](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html#step-two).

De klant-id&#39;s synchroniseren met de opgegeven id `setCustomerID` functie in de dienst van identiteitskaart van het Experience Cloud met de integratiecode: `AdobeCampaignID`. De `AdobeCampaignID` moet overeenkomen met de waarde van de Reconcilation-sleutel die is ingesteld in de ontvangergegevensbron die is geconfigureerd in [Stap 2: Vorm de Gegevensbronnen](#step-2--configure-the-data-sources).

Uw configuratie en levering worden voltooid, kan de integratie nu worden gebruikt om publiek of segmenten in te voeren en uit te voeren.
