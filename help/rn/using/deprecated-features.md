---
title: Campaign Standard Verouderde en verwijderde functies
description: Deze pagina bevat een lijst met vervangen en verwijderde functies van Adobe Campaign Standard.
page-status-flag: never-activated
uuid: null
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: campaign-standard-deprecated-features
discoiquuid: null
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7622018bff9c8b8573dae139372bea697815849f
workflow-type: tm+mt
source-wordcount: '589'
ht-degree: 0%

---


# Verouderde en verwijderde functies {#deprecated-and-removed-features}

Adobe evalueert voortdurend de productmogelijkheden om oudere eigenschappen te identificeren die met modernere alternatieven zouden moeten worden vervangen om algemene klantenwaarde te verbeteren, altijd onder zorgvuldig onderzoek van achterwaartse verenigbaarheid.

Om de aanstaande verwijdering/vervanging van de mogelijkheden van Campaign Standard mee te delen, zijn de volgende regels van toepassing:

* Aankondiging van afkeuring komt voorop. Hoewel verouderde mogelijkheden nog steeds beschikbaar kunnen zijn voor bestaande gebruikers, worden ze niet verder uitgebreid of gedocumenteerd.
* Afgekeurde functies worden ten vroegste uit de volgende release verwijderd. De werkelijke doeldatum voor verwijdering wordt op deze pagina aangekondigd.

Dit proces biedt klanten minstens één releasecyclus om hun implementatie aan een nieuwe versie of opvolger van een vervangen capaciteit aan te passen, alvorens daadwerkelijke verwijdering.

>[!NOTE]
>Adobe Campaign Standard-releases en nieuwe mogelijkheden worden vermeld in de [releaseopmerkingen](../../rn/using/release-notes.md).


## Verouderde functies {#deprecated-features}

Deze sectie bevat een lijst met functies en mogelijkheden die zijn gemarkeerd als verouderd in de nieuwste Campaign Standard-releases.

In het algemeen worden functies die in een toekomstige release verwijderd moeten worden, eerst vervangen, met een alternatief dat beschikbaar is. Deze functies en mogelijkheden zijn niet meer beschikbaar voor nieuwe Campaign Standard-klanten of moeten niet worden gebruikt voor nieuwe implementaties. Ze worden ook verwijderd uit de productdocumentatie.

Klanten wordt aangeraden na te gaan of zij in hun huidige implementatie gebruik maken van de functie/mogelijkheid en plannen te maken om hun implementatie te wijzigen en het geboden alternatief te gebruiken. Raadpleeg de versie voor doelverwijdering om uw omgeving en projectupdates dienovereenkomstig te plannen.

<table> 
 <thead> 
  <tr> 
   <th> <strong>Pushberichten met SDK v4</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p> Vanaf release 20.1 is SDK v4 afgekeurd. <a href="https://aep-sdks.gitbook.io/docs/version-4-sdk-end-of-support-faq">Meer</a>informatie.</p><br/>
   <p>De <a href="https://aep-sdks.gitbook.io/docs/">Adobe Experience Platform Mobile SDK</a> (voorheen v5 genoemd) biedt uitsluitend ondersteuning voor toekomstige functies en functies van Adobe Experience Cloud.</p></br>
     <p>
     <em>Verwijderingsdatum Target: 30 september 2020</em></p>
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
   <p>Zie ook <a href="https://helpx.adobe.com/campaign/kb/acs-privacy.html">Privacy Management in Campaign Standard</a>.</p>
  <p> 
  <em>Target-verwijderingsversie: Release van campagne 20.4</em></p>
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
   <td> <p>Vanaf de release Campagne 19.0 is de oude e-maileditor afgekeurd. Met <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/designing-content/designing-content-in-adobe-campaign.html">de nieuwe e-mailontwerper</a> kunt u uw e-mailinhoud maken en aanpassen. </p></br>
   <p>Lees <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/designing-content/building-email-content/using-existing-content.html">deze sectie</a> om te leren hoe u uw e-mailsjablonen voor de nieuwe editor kunt aanpassen.</p></br>
  <p> 
  <em>Target-verwijderingsversie: 2021</em></p>
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
   <td> <p>Vanaf release 18.7 zijn geografische eenheden afgekeurd. Organisatorische en geografische eenheden zijn identieke constructies in Campaign. Gebruikers moeten alleen Organizationele eenheden gebruiken om hun gebruikerstoestemming/gegevenstoegangshiërarchie samen te stellen. <a href="https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html">Meer</a>informatie. Houd er rekening mee dat deze functie niet kan worden geïmplementeerd vanaf de release 18.7 voor nieuwe Campaign Standard-exemplaren en bestaande exemplaren zonder gemaakte geografische eenheden.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

## Verwijderde functies {#removed-features}

Deze sectie bevat een lijst met functies en mogelijkheden die uit Campaign Standard zijn verwijderd.

<table> 
 <thead> 
  <tr> 
   <th> <strong>Creative SDK voor Campaign Standard</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Adobe Creative SDK is uit bedrijf genomen. Als gevolg hiervan is de afbeeldingseditie, aangedreven door Creative SDK, in e-mailberichten van Campaign Standard niet meer beschikbaar vanaf de release Campagne 20.2.</p></br>
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
   <td> <p>Adobe Campaign en Adobe Experience Cloud hebben vanaf het voorjaar van 2019 de ondersteuning voor Microsoft Internet Explorer 11 en de release van Campagne 19.2 stopgezet. Schakel over naar Microsoft Edge of een andere ondersteunde browser. <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/administrating/about-configuration-guidelines.html#compatible-browsers">Meer</a>informatie.</p>
   </td> 
  </tr> 
 </tbody> 
</table>
