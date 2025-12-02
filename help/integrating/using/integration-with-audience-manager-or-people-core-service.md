---
title: De integratie met Audience Manager of de People core-service inrichten en configureren
description: Leer hoe u de integratie van de Audience Manager/People-kernservice configureert om publiek of segmenten te delen met de verschillende Adobe Experience Cloud-oplossingen.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
feature: People Core Service Integration
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 04d0fe26-a8cc-49ae-aaa9-b470169068ee
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '757'
ht-degree: 4%

---

# De integratie met Audience Manager of de People core-service inrichten en configureren{#integration-with-audience-manager-or-people-core-service}

De levering en het vormen van de kern van Audience Manager en van Mensen in Adobe Campaign nemen twee stappen: [&#x200B; Voorgaand verzoek aan Adobe &#x200B;](#submitting-request-to-adobe) toen [&#x200B; Vormend de integratie in Adobe Campaign &#x200B;](#configuring-the-integration-in-adobe-campaign).

## Aanvraag indienen bij Adobe {#submitting-request-to-adobe}

Met de integratie van Audience Manager (AAM) of People core kunt u soorten publiek of segmenten in Adobe Campaign importeren en exporteren.

Deze integratie moet eerst worden geconfigureerd. Neem contact op met Adobe Support voor de volgende informatie als u een aanvraag wilt indienen voor de levering van deze integratie:

<table> 
 <tbody> 
  <tr> 
   <td> <strong> Type van Verzoek:</strong><br /> </td> 
   <td> AAM/People core service-Campagne integratie configureren </td> 
  </tr> 
  <tr> 
   <td> <strong> Naam van de Organisatie:</strong><br /> </td> 
   <td> Uw organisatienaam </td> 
  </tr> 
  <tr> 
   <td> <strong> IMS Org ID </strong><br /> </td> 
   <td> Uw organisatie-id. <br> om uw organisatieidentiteitskaart te vinden, verwijs naar <a href="https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=nl"> deze pagina </a></td> 
  </tr> 
  <tr> 
   <td> <strong> Milieu:</strong><br /> </td> 
   <td> Voorbeeld: Productie </td> 
  </tr> 
  <tr> 
   <td> <strong> AAM of de Dienst van Mensen </strong><br /> </td> 
   <td> Voorbeeld: Adobe Audience Manager. Vergeet niet het provisioningteam mee te delen of u al dan niet een Audience Manager-licentie hebt.</td> 
  </tr> 
  <tr> 
   <td> <strong> Verklaarde identiteitskaart of identiteitskaart van de Bezoeker </strong><br /> </td> 
   <td> Voorbeeld: gedeclareerde id </td> 
  </tr> 
  <tr> 
   <td> <strong> Aanvullende Informatie </strong><br /> </td> 
   <td> Eventuele nuttige informatie of opmerkingen </td> 
  </tr> 
 </tbody> 
</table>

## Integratie in Adobe Campaign configureren {#configuring-the-integration-in-adobe-campaign}

Na het indienen van dit verzoek, zal Adobe aan de levering van de integratie voor u te werk gaan en u contacteren om details en informatie te verstrekken die u de configuratie moet voltooien:

* [Stap 1: De externe accounts in Adobe Campaign configureren of controleren](#step-1--configure-or-check-the-external-accounts-in-adobe-campaign)
* [Stap 2: Vorm de Gegevensbronnen](#step-2--configure-the-data-sources)
* [Stap 3: De server voor bijhouden van campagnes configureren](#step-3--configure-campaign-tracking-server)
* [Stap 4: Vorm de Dienst van identiteitskaart van de Bezoeker](#step-4--configure-the-visitor-id-service)

### Stap 1: De externe accounts in Adobe Campaign configureren of controleren {#step-1--configure-or-check-the-external-accounts-in-adobe-campaign}

We moeten eerst de externe accounts in Adobe Campaign configureren of controleren. Deze rekeningen hadden door Adobe moeten worden gevormd en de noodzakelijke informatie zou aan u moeten worden meegedeeld.

Dit doet u als volgt:

1. Van het geavanceerde menu, uitgezochte **Beleid > de montages van de Toepassing > Externe rekeningen**.

   Selecteer een van de volgende externe accounts die beschikbaar zijn voor deze integratie:

   ![](assets/integration_aam_1.png)

1. Voer **[!UICONTROL Receiver server]** in de volgende notatie in
1. Voer de waarden **[!UICONTROL AWS Access Key ID]** , **[!UICONTROL Secret Access Key]** en **[!UICONTROL AWS Region]** in.

Uw externe accounts zijn nu geconfigureerd voor deze integratie.

### Stap 2: Vorm de Gegevensbronnen {#step-2--configure-the-data-sources}

De volgende twee gegevensbronnen worden gemaakt in Audience Manager: Adobe Campaign (MID) en Adobe Campaign (DeclaredId). Tegelijkertijd zijn deze twee gegevensbronnen beschikbaar in Adobe Campaign:

* **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**: dit is een gegevensbron die buiten de doos door gebrek voor identiteitskaart van de Bezoeker wordt gevormd. Segmenten die zijn gemaakt op basis van campagne maken deel uit van deze gegevensbron.
* **Verklaarde identiteitskaart** gegevensbron: Deze gegevensbron moet met de **[!UICONTROL DeclaredId]** gegevensbrondefinitie van Audience Manager worden gecreeerd en in kaart gebracht.

In het geval van meerdere websites met verschillende domeinen ondersteunt Adobe Campaign geen afstemming op basis van ECID.

U configureert de gegevensbron **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]** als volgt:

1. Selecteer **[!UICONTROL Administration]** in **[!UICONTROL Application settings]** > **[!UICONTROL Shared Data Sources]** > **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]** .

   ![](assets/integration_aam_2.png)

1. Kies **[!UICONTROL Adobe Campaign]** in de vervolgkeuzelijst **[!UICONTROL Data Source/ Alias]** .
1. Voer de **[!UICONTROL AAM Destination ID]** in die door Adobe is opgegeven.

   ![](assets/integration_aam_3.png)

1. In de categorie **[!UICONTROL Reconciliation process]** raden we u aan de verzoeningscriteria niet te wijzigen en altijd de categorie **[!UICONTROL Visitor ID]** te gebruiken.
1. Klik op **[!UICONTROL Save]**.

U kunt als volgt de gegevensbron **[!UICONTROL Declared ID]** maken:

1. Klik in **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Shared Data Sources]** op de knop **[!UICONTROL Create]** .
1. Bewerk de **[!UICONTROL Label]** van de gegevensbron.
1. Kies in de vervolgkeuzelijst **[!UICONTROL Data Source/ Alias]** de Data Source die overeenkomt met de **[!UICONTROL DeclaredID]** -gegevensbron uit Audience Manager.
1. Configureer uw gegevensbron door de **[!UICONTROL Data Source / Alias]** en **[!UICONTROL AAM Destination ID]** in te voeren die door Adobe worden geleverd.
1. Stel de **[!UICONTROL Reconciliation process]** naar wens in.
1. Klik op **[!UICONTROL Save]**.

>[!NOTE]
>
>Het **[!UICONTROL AAM Destination ID]** gebied wordt niet vereist als u de gedeelde gegevensbron voor de [&#x200B; campagne-Triggers integratie &#x200B;](../../integrating/using/configuring-triggers-in-experience-cloud.md) vormt. **[!UICONTROL Priority]** is alleen nodig bij het configureren van de integratie Triggers - Campagne. De prioriteit bepaalt welke gegevens-Source het eerst wordt geconfigureerd. Prioriteit kan elk nummer zijn, zoals 1 of 100. Hoe hoger de prioriteit, des te hoger de voorkeur tijdens verzoening.

### Stap 3: De server voor bijhouden van campagnes configureren {#step-3--configure-campaign-tracking-server}

Voor de configuratie van de integratie met de dienst van de Kern van Mensen of de manager van het Publiek, moeten wij ook de server van het Volgen van de Campagne vormen.

Als u wilt dat een gedeeld publiek kan functioneren met de bezoeker-id, moet het trackingserverdomein een subdomein zijn van de aangeklikte URL of de hoofdwebsite.

>[!IMPORTANT]
>
> U moet ervoor zorgen de het Volgen van de Campagne Server op het domein (CNAME) wordt geregistreerd. U kunt meer informatie over de configuratie van de domeinnaam in [&#x200B; dit artikel &#x200B;](https://helpx.adobe.com/nl/campaign/kb/domain-name-delegation.html) vinden.

### Stap 4: Vorm de Dienst van identiteitskaart van de Bezoeker {#step-4--configure-the-visitor-id-service}

In het geval dat uw dienst van identiteitskaart van de Bezoeker nooit op uw Webeigenschappen of websites is gevormd, verwijs naar het volgende [&#x200B; document &#x200B;](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-aam-analytics.html) om te leren hoe te om uw dienst of de volgende [&#x200B; video &#x200B;](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html#step-two) te vormen.

Synchroniseer de id&#39;s van de klant met de functie `setCustomerID` in de Experience Cloud-id-service met de integratiecode: `AdobeCampaignID` . `AdobeCampaignID` zou de waarde van de sleutel van de Wederopbouw moeten aanpassen die in de Ontvankelijke Gegevens Source in [&#x200B; wordt gevormd Stap 2: Vorm de Gegevensbronnen &#x200B;](#step-2--configure-the-data-sources).

Uw configuratie en levering worden voltooid, kan de integratie nu worden gebruikt om publiek of segmenten in te voeren en uit te voeren.
