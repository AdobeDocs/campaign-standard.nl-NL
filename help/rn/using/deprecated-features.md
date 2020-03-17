---
title: Verouderde en verwijderde functies voor de campagne
description: Deze pagina bevat een lijst met vervangen en verwijderde functies van Adobe Campagne Standard.
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
source-git-commit: 490908e5fe0810c0a07c73fef5040ddb42983019

---


# Verouderde en verwijderde functies {#deprecated-and-removed-features}

Adobe evalueert voortdurend de productmogelijkheden om oudere eigenschappen te identificeren die met modernere alternatieven zouden moeten worden vervangen om algemene klantenwaarde te verbeteren, altijd onder zorgvuldig onderzoek van achterwaartse verenigbaarheid.

Om de aanstaande verwijdering/vervanging van de Standaardmogelijkheden van de Campagne mee te delen, zijn de volgende regels van toepassing:

* Aankondiging van afkeuring komt voorop. Hoewel verouderde mogelijkheden nog steeds beschikbaar kunnen zijn voor bestaande gebruikers, worden deze niet verder uitgebreid of gedocumenteerd.
* Afgekeurde functies worden ten vroegste uit de volgende release verwijderd. De werkelijke doeldatum voor verwijdering wordt op deze pagina aangekondigd.

Dit proces biedt klanten minstens één releasecyclus om hun implementatie aan een nieuwe versie of opvolger van een vervangen capaciteit aan te passen, alvorens daadwerkelijke verwijdering.

>[!NOTE]
>De Adobe Campaign Standard-releases en nieuwe mogelijkheden worden vermeld in de [Opmerkingen bij de release](../../rn/using/release-notes.md).


## Verouderde functies {#deprecated-features}

Deze sectie maakt een lijst van eigenschappen en mogelijkheden die als verouderd met de recentste versies van de Standaard van de Campagne zijn gemerkt.

In het algemeen worden functies die in een toekomstige release verwijderd moeten worden, eerst vervangen, met een alternatief dat beschikbaar is. Deze functies en mogelijkheden zijn niet meer beschikbaar voor nieuwe standaardklanten van de campagne of moeten niet worden gebruikt voor nieuwe implementatie. Ze worden ook verwijderd uit de productdocumentatie.

Klanten wordt aangeraden na te gaan of zij in hun huidige implementatie gebruik maken van de functie/mogelijkheid en plannen te maken om hun implementatie te wijzigen en het geboden alternatief te gebruiken. Raadpleeg de verwijderingsdatum van het doel om uw omgeving en projectupdates dienovereenkomstig te plannen.

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
     <p>Doeldatum verwijdering: 30 september 2020</p>
     </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Creative SDK voor campagnestandaard</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Adobe Creative SDK is uit bedrijf genomen. Daarom is de versie van de afbeelding, die vanaf 20.1 wordt geactiveerd door Creative SDK in e-mailberichten van de Campagnestandaard, verouderd.</p></br>
  <p> Doeldatum verwijdering: Maart 2020 - release Campagne 20.2</p>
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
   <td> <p>Vanaf de release van Campagne 19.4 is het gebruik van de campagne-API en de interface voor toegangs- en verwijderingsverzoeken afgekeurd. Gebruik <a href="https://www.adobe.io/apis/experiencecloud/gdpr.html">Adobe Privacy Core Service</a>.</p></br>
   <p>Zie ook <a href="https://helpx.adobe.com/campaign/kb/acs-privacy.html">Privacybeheer in de Standaard</a>van de Campagne.</p>
  <p> Doeldatum verwijdering: Juli 2020 - Versie van Campagne 20.5</p>
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
  <p> Doeldatum verwijdering: Oktober 2020 - de release van de Campagne 20.6</p>
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
   <td> <p>Vanaf release 18.7 zijn geografische eenheden afgekeurd. Organisatorische en geografische eenheden zijn identieke constructies in Campaign. Gebruikers moeten alleen Organizationele eenheden gebruiken om hun gebruikerstoestemming/gegevenstoegangshiërarchie samen te stellen. <a href="https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html">Meer</a>informatie. Houd er rekening mee dat deze functie niet kan worden geïmplementeerd vanaf de release 18.7 van nieuwe campagnestandaard en bestaande exemplaren zonder gemaakte geografische eenheden.</p>
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
   <td> <p>Adobe Campaign and Adobe Experience Cloud heeft vanaf het voorjaar van 2019 de ondersteuning voor Microsoft Internet Explorer 11 en Campagne 19.2 verwijderd. Schakel over naar Microsoft Edge of een andere ondersteunde browser. <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/getting-started/discovering-the-interface/compatible-browsers.html">Meer</a>informatie.</p>
   </td> 
  </tr> 
 </tbody> 
</table>
