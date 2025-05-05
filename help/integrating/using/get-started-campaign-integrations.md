---
title: Aan de slag met Campaign-integraties
description: Gebruik andere Adobe-oplossingen en combineer hun verschillende mogelijkheden met Campaign.
audience: integrating
content-type: reference
topic-tags: get-started-campaign-integrations
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: ecf88c7d-6729-4b3a-85c4-60427bb57442
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '657'
ht-degree: 77%

---

# Campaign-integraties{#get-started-campaign-integrations}

In deze sectie worden de beschikbare functionele integraties tussen de huidige versie van Adobe Campaign en andere oplossingen en services beschreven.

Met de verschillende hieronder vermelde integraties kunt u de functies voor levering en geavanceerd campagnebeheer van Adobe Campaign combineren met een reeks oplossingen die u helpen uw gebruikerservaring aan te passen.

>[!NOTE]
>
> Adobe Campaign is standaard al gekoppeld aan een Adobe Experience Cloud-account.

Afhankelijk van uw omgeving kunnen andere oplossingen ook aan Adobe Experience Cloud worden gekoppeld. Ze zijn gekoppeld als organisaties (ook wel tenants genoemd).

Een organisatie is de entiteit waarmee een beheerder groepen en gebruikers kan configureren en eenmalig aanmelden in de Experience Cloud kan beheren. De organisatie functioneert als een aanmeldingsbedrijf dat alle producten en oplossingen van Experience Cloud omvat. Meestal is een organisatie uw bedrijfsnaam. Een bedrijf kan echter vele organisaties hebben. Het gebruikers- en organisatiebeheer wordt gedetailleerd beschreven in de [Adobe Experience Cloud Help-portal](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html?lang=nl-NL).

Als u gegevensstromen van andere systemen wilt integreren met Adobe Campaign, lees dan onze [API-documentatie](../../api/using/get-started-apis.md).

>[!NOTE]
>
>Adobe Campaign Standard kan ook verbinding maken met Microsoft Dynamics 365: dankzij deze integratie kunnen alle beschikbare contactgegevens in het CRM-systeem worden gesynchroniseerd, zodat alle relevante contactgegevens beschikbaar zijn voor campagneactiviteiten. Zie [Werken met Campaign en Dynamics 365](../../integrating/using/d365-acs-get-started.md) voor meer informatie over deze integratie.


<table> 
 <thead> 
  <tr> 
   <th> Oplossing<br /> </th> 
   <th> Gebruiksscenario<br /> </th> 
   <th> Zie<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Adobe Experience Manager<br /> </td> 
   <td> Hiermee kunt u rechtstreeks in Adobe Experience Manager e-mailcontent of formulieren maken die worden toegewezen aan de Adobe Campaign-database.<br /> </td> 
   <td> 
     <a href="../../integrating/using/integrating-with-experience-manager.md">Werken met campagne en Experience Manager</a>, <a href="https://helpx.adobe.com/nl/experience-manager/6-4/sites/administering/using/campaignstandard.html">Experience Manager en Campaign Standard integreren</a>, <a href="https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignstandard.html?lang=nl-NL">Een e-mail maken met Experience Manager en campagne</a> 
    </td> 
  </tr> 
  <tr> 
   <td> Adobe Target<br /> </td> 
   <td> Hiermee kunt u afbeeldingen invoegen die door Adobe Target dynamisch worden berekend wanneer een e-mailbericht wordt geopend dat door Adobe Campaign is gemaakt en verzonden.<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-campaign-target-integration.md">Werken met campagne en doel</a>, <a href="https://experienceleague.adobe.com/docs/target/using/integrate/campaign-and-target.html?lang=nl-NL">Campagne en doel integreren</a>, <a href="https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html">E-mailafbeeldingen in realtime aanpassen</a> video (stap 3)
    </td> 
  </tr> 
  <tr> 
   <td> Adobe Analytics<br /> </td> 
   <td> Hiermee kunt u het succes van uw e-mailleveringen rechtstreeks in Adobe Analytics volgen.<br /> </td> 
   <td> 
    Video <a href="../../integrating/using/about-campaign-analytics-integration.md">Campaign-data delen met Analytics</a>, <a href="https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html">KPI’s delen voor geïntegreerde Campaign-rapportage</a> (stap 1)
    </td> 
  </tr> 
  <tr> 
   <td> Adobe Audience Manager en People-kernservice (profielen en doelgroepen)<br /> </td> 
   <td> Hiermee kunt u doelgroepen uitwisselen met de verschillende applicaties van Adobe Experience Cloud die u gebruikt.<br /> </td> 
   <td> <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">People-kernservice (profielen en doelgroepen)</a><br /> </td> 
  </tr> 
   <tr> 
   <td> Adobe Real-time Customer Data Platform (RTCDP)<br /> </td> 
   <td> Dankzij de integratie tussen Adobe Campaign en Adobe Real-time Customer Data Platform (RTCDP) kunt u segmentgegevens delen en doelgroepen importeren naar Adobe Campaign.</td>
   <td><a href="../../integrating/using/get-started-sources-destinations.md">Aan de slag met bronnen en bestemmingen</a></td>
  </tr> 
  <tr> 
   <td> Adobe Asset Core-service en Activa op aanvraag<br /> </td> 
   <td> Hiermee kunt u assets uit uw Adobe Experience Cloud-bibliotheek invoegen in e-mails en landingspagina’s die in Adobe Campaign zijn gemaakt.<br /> </td> 
   <td> <a href="../../integrating/using/working-with-campaign-and-assets-core-service.md">Assets-kernservice</a> of Assets on demand<br /> </td> 
  </tr> 
  <tr> 
   <td> Points of Interest (Analytics for Mobile)<br /> </td> 
   <td> Hiermee kunt u Points of Interest-data verzamelen van abonnees van uw mobiele applicatie om gepersonaliseerde marketingberichten te verzenden met Adobe Campaign.<br /> </td> 
   <td> <a href="../../integrating/using/about-campaign-points-of-interest-data-integration.md">Op locatie gebaseerde marketingberichten verzenden met data van Campaign en Points of Interest</a> (Analytics for Mobile)<br /> </td> 
  </tr> 
  <tr> 
   <td> Adobe Experience Cloud Triggers<br /> </td> 
   <td> Hiermee kunt u persoonlijke e-mails verzenden naar uw klanten in Adobe Campaign als reactie op specifieke gedragingen die door Adobe Analytics op uw website worden bijgehouden.<br /> </td> 
   <td> 
    Video <a href="../../integrating/using/about-adobe-experience-cloud-triggers.md">Experience Cloud Triggers gebruiken in Campaign Standard</a>, <a href="../../integrating/using/abandonment-triggers-use-cases.md">Gebruiksscenario’s voor afbreking in Triggers en Campaign</a>, <a href="https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html">Remarketingberichten activeren op basis van siteactiviteit</a> (stap 2)
    </td> 
  </tr> 
    <tr> 
   <td> Journey Orchestration Adobe<br /> </td> 
   <td> Hiermee kunt u e-mails, pushberichten en SMS verzenden via de mogelijkheden voor Transactioneel Overseinen van Adobe Campaign Standard in het kader van het Journey Orchestration van de Adobe, via een actie 'uit de doos'.<br /> </td> 
   <td> <a href="https://experienceleague.adobe.com/docs/journeys/using/action-journeys/working-with-adobe-campaign.html?lang=nl-NL">Werken met Adobe Journey Orchestration en Adobe Campaign Standard</a><br /> </td> 
  </tr> 
  <tr> 
   <td> Adobe Dreamweaver<br /> </td> 
   <td> Hiermee kunt u e-mailcontent uit Dreamweaver bewerken en met Adobe Campaign synchroniseren.<br /> </td> 
   <td> 
    <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html?lang=nl">Persoonlijke e-mails maken met Dreamweaver</a> video, <a href="https://helpx.adobe.com/nl/dreamweaver/using/working-with-dreamweaver-and-campaign.html">Campagneextensie gebruiken voor Dreamweaver</a> 
  </td> 
  </tr> 
  <tr> 
   <td> Adobe Experience Platform SDK's<br /> </td> 
   <td> Hiermee is automatisering mogelijk van het activeringsproces van de eigenschap Mobile App in Adobe Campaign met de Experience Platform-SDK’s.<br /> </td> 
   <td> <a href="https://helpx.adobe.com/nl/campaign/kb/configuring-app-sdk.html">Een mobiele applicatie configureren met Experience Platform SDK’s</a><br /> </td> 
  </tr> 
 </tbody> 
</table>
