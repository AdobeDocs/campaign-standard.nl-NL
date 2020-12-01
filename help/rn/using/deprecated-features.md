---
solution: Campaign Standard
product: campaign
title: Campaign Standard Verouderde en verwijderde functies
description: Deze pagina bevat een lijst met vervangen en verwijderde functies van Adobe Campaign Standard.
audience: rn
content-type: reference
topic-tags: campaign-standard-deprecated-features
translation-type: tm+mt
source-git-commit: ad7322905c69f9575e11efc9d8f68cf909dc425f
workflow-type: tm+mt
source-wordcount: '658'
ht-degree: 16%

---


# Vervangen en verwijderde functies {#deprecated-and-removed-features}

Adobe evalueert voortdurend de productmogelijkheden om oudere functies te identificeren die door modernere alternatieven zouden moeten worden vervangen om de algehele klantwaarde te verbeteren. Hierbij wordt altijd zorgvuldig rekening gehouden met achterwaartse compatibiliteit.

Om de dreigende verwijdering/vervanging van de mogelijkheden van Campaign Standard mee te delen, zijn de volgende regels van toepassing:

* De aankondiging van de afschaffing komt eerst. Hoewel verouderde mogelijkheden nog steeds beschikbaar kunnen zijn voor bestaande gebruikers, worden ze niet verder uitgebreid of gedocumenteerd.
* Verouderde functies worden op zijn vroegst uit de volgende release verwijderd. De werkelijke doeldatum voor verwijdering wordt op deze pagina aangekondigd.

Dit proces biedt klanten minstens één releasecyclus om hun implementatie aan een nieuwe versie of opvolger van een vervangen mogelijkheid aan te passen vóór de daadwerkelijke verwijdering.

>[!NOTE]
>Adobe Campaign Standard-releases en nieuwe mogelijkheden worden vermeld in de [Opmerkingen bij de release](../../rn/using/release-notes.md).


## Verouderde functies {#deprecated-features}

Deze sectie maakt een lijst van eigenschappen en mogelijkheden die als verouderd met recentste versies van Campaign Standard zijn gemerkt.

In het algemeen worden functies die in een toekomstige versie moeten worden verwijderd, eerst vervangen door een alternatief. Deze eigenschappen en mogelijkheden zijn of niet meer beschikbaar voor nieuwe klanten van Campaign Standard, of zouden niet voor om het even welke nieuwe implementatie moeten worden gebruikt. Ze worden ook verwijderd uit de productdocumentatie.

Klanten wordt aangeraden na te gaan of zij in hun huidige implementatie gebruik maken van de functie/mogelijkheid en plannen te maken om hun implementatie te wijzigen en het geboden alternatief te gebruiken. Raadpleeg de versie voor doelverwijdering om uw omgeving en projectupdates dienovereenkomstig te plannen.

<table> 
 <thead> 
  <tr> 
   <th> <strong>Pushberichten met SDK v4</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p> Vanaf release 20.1 is SDK v4 afgekeurd. <a href="https://aep-sdks.gitbook.io/docs/version-4-sdk-end-of-support-faq">Meer informatie</a>.</p><br/>
   <p>De <a href="https://aep-sdks.gitbook.io/docs/">Adobe Experience Platform Mobile SDK</a> (voorheen v5 genoemd) biedt uitsluitend ondersteuning voor de komende Adobe Experience Cloud-functies en -functionaliteit.</p></br>
     <p>
     <em>Doeldatum verwijdering: 31 augustus 2021</em></p>
     </td> 
  </tr> 
 </tbody> 
</table>
<table> 
 <thead> 
  <tr> 
   <th> <strong>Privacy-aanvragen - Campagne-API en -interface</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Vanaf de release van Campagne 19.4 is het gebruik van de campagne-API en de interface voor toegangs- en verwijderingsverzoeken afgekeurd. De profielverwijdering in twee stappen is niet beschikbaar. Gebruik <a href="https://www.adobe.io/apis/experiencecloud/gdpr.html">Adobe Privacy Core Service</a>.</p></br>
   <p>Zie ook <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/getting-started/privacy/privacy-requests.html?lang=en">Privacy-aanvragen beheren</a>.</p>
  <p> 
  <em>Doeldatum voor verwijdering: 2021</em></p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>E-mailontwerp - Verouderde e-maileditor</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Vanaf de release Campagne 19.0 is de oude e-maileditor afgekeurd. Met <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/designing-content-in-adobe-campaign.html">Campagne voor e-mailontwerpen</a> kunt u uw e-mailinhoud maken en aanpassen. </p></br>
   <p>Lees <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/building-email-content/using-existing-content.html">deze sectie</a> om te leren hoe te om uw e-mailmalplaatjes voor de nieuwe redacteur aan te passen.</p></br>
  <p> 
  <em>Doeldatum verwijdering: eind 2021</em></p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Gebruikers en beveiliging - Geografische eenheden</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Vanaf release 18.7 zijn geografische eenheden afgekeurd. Organisatorische en geografische eenheden zijn identieke constructies in Campaign. Gebruikers moeten alleen Organizationele eenheden gebruiken om hun gebruikerstoestemming/gegevenstoegangshiërarchie samen te stellen. <a href="https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html">Meer informatie</a>. Houd er rekening mee dat deze functie niet kan worden geïmplementeerd vanaf de release 18.7 voor nieuwe Campaign Standard-exemplaren en bestaande exemplaren zonder gemaakte geografische eenheden.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

## Verwijderde functies {#removed-features}

Deze sectie bevat een lijst met functies en mogelijkheden die uit Campaign Standard zijn verwijderd.

<table> 
 <thead> 
  <tr> 
   <th> <strong>Propensatiescore met Experience Cloud-triggers</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>De <b>Propensiteitsscore</b> is gedeactiveerd uit Adobe Experience Cloud-triggers. Deze optie is daarom uit Adobe Campaign Standard verwijderd. Om om het even welke verouderde waarden van de score van de Volheid in de schema's van de Verrijking te vermijden, adviseren wij het bijwerken van schema's om de recentste veranderingen terug te winnen en bestaande Trekkers opnieuw te publiceren. Raadpleeg <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/working-with-campaign-and-triggers/using-triggers-in-campaign.html"> Een trigger publiceren in Campagne </a> voor meer informatie.
</p></br>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Creative SDK voor Campaign Standard</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>[!DNL Adobe Creative SDK] is uit bedrijf genomen. Als gevolg hiervan is de afbeeldingseditie met de functie [!DNL Creative SDK] in e-mails met Campaign Standard niet meer beschikbaar vanaf de release van Campagne 20.2.</p></br>
   </td> 
  </tr> 
 </tbody> 
</table>

## Einde van compatibiliteit {#end-of-compatibility}

<table> 
 <thead> 
  <tr> 
   <th> <strong>Microsoft Internet Explorer 11</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Adobe Campaign en Adobe Experience Cloud hebben de ondersteuning voor Microsoft Internet Explorer 11 vanaf het voorjaar van 2019 en de release Campagne 19.2 ingetrokken. Schakel over naar Microsoft Edge of een andere ondersteunde browser. <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/about-configuration-guidelines.html">Meer informatie</a>.</p>
   </td> 
  </tr> 
 </tbody> 
</table>
