---
title: Aan de slag met Campaign-integraties
description: Gebruik andere Adobe-oplossingen en combineer hun verschillende mogelijkheden met Campagne.
page-status-flag: never-activated
uuid: 59d7cd99-a6f7-47f1-9b5c-c50e27a2bef8
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: get-started-campaign-integrations
discoiquuid: 9633e9ca-3323-499b-8259-45165d59a4d0
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d425e4b96604133fbdfc66fde38e4ca5c84baccd
workflow-type: tm+mt
source-wordcount: '632'
ht-degree: 7%

---


# Campaign-integraties{#get-started-campaign-integrations}

In deze sectie worden de beschikbare functionele integratie tussen de huidige versie van Adobe Campaign en andere oplossingen en services beschreven.

Met de verschillende hieronder beschreven integraties kunt u de functionaliteit voor levering en geavanceerd campagnebeheer van Adobe Campaign combineren met een reeks oplossingen die u helpen uw gebruikerservaring aan te passen.

>[!NOTE]
>
> Adobe Campaign is standaard al gekoppeld aan een Adobe Experience Cloud-account.

Afhankelijk van uw omgeving kunnen andere oplossingen ook aan Adobe Experience Cloud worden gekoppeld. Ze zijn gekoppeld als organisaties (ook wel huurders genoemd).

Een organisatie is de entiteit die een beheerder toelaat om groepen en gebruikers te vormen, en om enig teken-binnen in de Experience Cloud te controleren. De organisatie functioneert als een login bedrijf dat alle producten en oplossingen van de Experience Cloud overspant. Meestal is een organisatie uw bedrijfsnaam. Een bedrijf kan echter veel organisaties hebben. Het gebruikers- en organisatiebeheer wordt gedetailleerd beschreven in het [Adobe Experience Cloud Help-portaal](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html).

Als u gegevensstromen van andere systemen met Adobe Campaign wilt integreren, bekijk onze [API documentatie](../../api/using/get-started-apis.md).

>[!NOTE]
>
>Adobe Campaign Standard kan ook verbinding maken met Microsoft Dynamics 365 : Dankzij deze integratie kunnen alle beschikbare contactgegevens in het CRM-systeem worden gesynchroniseerd, zodat alle relevante contactgegevens beschikbaar zijn voor campagneactiviteiten. Raadpleeg [Werken met campagne en dynamiek 365 voor meer informatie over deze integratie](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md).


<table> 
 <thead> 
  <tr> 
   <th> Oplossing<br /> </th> 
   <th> Use Case<br /> </th> 
   <th> Zie<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Experience Manager<br /> 6.1, 6.2, 6.3, 6.4, 6.5<br /> </td> 
   <td> Hiermee kunt u rechtstreeks in Adobe Experience Manager e-mailinhoud of formulieren maken die zijn toegewezen aan de Adobe Campaign-database.<br /> </td> 
   <td> 
     <a href="../../integrating/using/integrating-with-experience-manager.md">Werken met campagne en Experience Manager</a>, Experience Manager en Campaign Standard <a href="https://helpx.adobe.com/experience-manager/6-4/sites/administering/using/campaignstandard.html">integreren</a>, een e-mail <a href="https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_AEM.html">maken met Experience Manager en campagne</a> 
    </td> 
  </tr> 
  <tr> 
   <td> Doel<br /> : Klassiek, standaard<br /> </td> 
   <td> Hiermee kunt u afbeeldingen invoegen die dynamisch door Adobe Target worden berekend wanneer een e-mailbericht wordt geopend dat door Adobe Campaign is gemaakt en verzonden.<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-campaign-target-integration.md">Werk met Campagne en Doel</a>, <a href="https://docs.adobe.com/content/help/en/target/using/integrate/campaign-and-target.html">integreer Campagne en Doel</a>, <a href="https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html">Personaliseer E-mailbeelden in Real-Time</a> video (stap 3)
    </td> 
  </tr> 
  <tr> 
   <td> Analytics<br /> Standard, Premium <br /> </td> 
   <td> Hiermee kunt u het succes van uw e-mailleveringen rechtstreeks in Adobe Analytics volgen.<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-campaign-analytics-integration.md">Campagnegegevens delen met Analytics</a>, KPI's <a href="https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html">delen voor geïntegreerde Campagne die video rapporteert</a> (stap 1)
    </td> 
  </tr> 
  <tr> 
   <td> Adobe Audience Manager en People core-service (profielen en soorten publiek)<br /> </td> 
   <td> Sta u toe om publiek met de verschillende toepassingen van Adobe Experience Cloud uit te wisselen die u gebruikt.<br /> </td> 
   <td> <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">People Core-service (profielen en soorten publiek)</a><br /> </td> 
  </tr> 
  <tr> 
   <td> Asset Core-service en bedrijfsmiddelen op aanvraag<br /> </td> 
   <td> Hiermee kunt u elementen uit uw Adobe Experience Cloud-bibliotheek invoegen in e-mails en bestemmingspagina's die in Adobe Campaign zijn gemaakt.<br /> </td> 
   <td> <a href="../../integrating/using/working-with-campaign-and-assets-core-service.md">Assets Core Service</a> of Assets On-demand<br /> </td> 
  </tr> 
  <tr> 
   <td> Interessepunten (Analytics for Mobile)<br /> </td> 
   <td> Hiermee kunt u interessepunten verzamelen van abonnees van uw mobiele toepassing om gepersonaliseerde marketingberichten te verzenden met Adobe Campaign.<br /> </td> 
   <td> <a href="../../integrating/using/about-campaign-points-of-interest-data-integration.md">Op locatie gebaseerde marketingberichten verzenden met Campagne- en interessepunten-gegevens</a> (Analytics for Mobile)<br /> </td> 
  </tr> 
  <tr> 
   <td> Experience Cloud Triggers<br /> </td> 
   <td> Hiermee kunt u persoonlijke e-mails sturen naar uw klanten in Adobe Campaign als reactie op specifieke gedragingen die door Adobe Analytics op uw website worden bijgehouden.<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-adobe-experience-cloud-triggers.md">De Trekkers van de Experience Cloud van het gebruik in Campaign Standard</a>, de <a href="../../integrating/using/abandonment-triggers-use-cases.md">Ontgroting Triggers-Campagne gebruiksgevallen</a>, de Berichten van de <a href="https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html">Trigger die van de Opmerking</a> van de Berichten op de video van de Activiteit van de Plaats worden gebaseerd (stap 2)
    </td> 
  </tr> 
  <tr> 
   <td> Dreamweaver<br /> </td> 
   <td> Hiermee kunt u e-mailinhoud uit Dreamweaver bewerken en synchroniseren met Adobe Campaign.<br /> </td> 
   <td> 
    <a href="https://docs.adobe.com/content/help/nl-NL/campaign-standard-learn/tutorials/designing-content/email-designer/dreamweaver-integration.translate.html">Maak persoonlijke e-mails met Dreamweaver</a> -video, <a href="https://helpx.adobe.com/nl/dreamweaver/using/working-with-dreamweaver-and-campaign.html">gebruik de extensie Campagne voor Dreamweaver</a> 
  </td> 
  </tr> 
  <tr> 
   <td> Experience Platform-SDK's<br /> </td> 
   <td> Hiermee wordt automatisering van het activeringsproces van de eigenschap Mobile App in Adobe Campaign toegestaan met behulp van de Experience Platform-SDK's.<br /> </td> 
   <td> <a href="https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html">Een mobiele toepassing configureren met SDK's van Experience Platforms</a><br /> </td> 
  </tr> 
 </tbody> 
</table>

