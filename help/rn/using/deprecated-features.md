---
solution: Campaign Standard
product: campaign
title: Afgeschafte en verwijderde functies van Campaign Standard
description: Deze pagina bevat de afgeschafte en verwijderde functies van Adobe Campaign Standard.
audience: rn
content-type: reference
topic-tags: campaign-standard-deprecated-features
translation-type: tm+mt
source-git-commit: ad7322905c69f9575e11efc9d8f68cf909dc425f
workflow-type: tm+mt
source-wordcount: '658'
ht-degree: 90%

---


# Afgeschafte en verwijderde functies {#deprecated-and-removed-features}

Adobe evalueert voortdurend de productmogelijkheden om oudere functies te identificeren die door modernere alternatieven zouden moeten worden vervangen om de algehele klantwaarde te verbeteren. Hierbij wordt altijd zorgvuldig rekening gehouden met achterwaartse compatibiliteit.

Voor het meedelen van de aanstaande verwijdering/vervanging van mogelijkheden van Campaign Standard gelden de volgende regels:

* De aankondiging van de afschaffing komt eerst. Hoewel afgeschafte mogelijkheden nog steeds beschikbaar kunnen zijn voor bestaande gebruikers, worden ze niet verder uitgebreid of gedocumenteerd.
* Verouderde functies worden op zijn vroegst uit de volgende release verwijderd. De werkelijke doeldatum voor verwijdering wordt op deze pagina aangekondigd.

Dit proces biedt klanten minstens één releasecyclus om hun implementatie aan een nieuwe versie of opvolger van een vervangen mogelijkheid aan te passen vóór de daadwerkelijke verwijdering.

>[!NOTE]
>Adobe Campaign-releases en nieuwe mogelijkheden worden vermeld in de [release-opmerkingen](../../rn/using/release-notes.md).


## Afgeschafte functies {#deprecated-features}

Deze sectie bevat een lijst met functies en mogelijkheden die zijn gemarkeerd als afgeschaft in de nieuwste Campaign Standard-releases.

In het algemeen worden functies die in een toekomstige versie moeten worden verwijderd, eerst ingesteld op afgeschaft, waarbij een alternatief wordt aangeboden. Deze functies en mogelijkheden zijn niet meer beschikbaar voor nieuwe Campaign Standard-klanten, of ze mogen niet worden gebruikt voor nieuwe implementaties. Ze worden ook verwijderd uit de productdocumentatie.

Klanten wordt aangeraden na te gaan of ze in hun huidige implementatie gebruikmaken van de functie of mogelijkheid en om plannen te maken voor een wijziging in hun implementatie zodat het alternatief wordt gebruikt. Bekijk in welke versie de verwijdering plaatsvindt om uw omgeving en projectupdates dienovereenkomstig te plannen.

<table> 
 <thead> 
  <tr> 
   <th> <strong>Pushberichten met SDK v4</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p> Vanaf release 20.1 is SDK v4 afgeschaft. <a href="https://aep-sdks.gitbook.io/docs/version-4-sdk-end-of-support-faq">Meer informatie</a>.</p><br/>
   <p>De <a href="https://aep-sdks.gitbook.io/docs/">Adobe Experience Platform Mobile SDK</a> (vroeger v5 genoemd) ondersteunt uitsluitend nieuwe Adobe Experience Cloud-functies.</p></br>
     <p>
     <em>Doeldatum verwijdering: 31 augustus 2021</em></p>
     </td> 
  </tr> 
 </tbody> 
</table>
<table> 
 <thead> 
  <tr> 
   <th> <strong>Privacyverzoeken - Campaign-API en -interface</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Sinds Campaign 19.4 is het gebruik van de Campaign-API en -interface voor toegangs- en verwijderingsverzoeken afgeschaft. De profielverwijdering in twee stappen is niet beschikbaar. Gebruik de <a href="https://www.adobe.io/apis/experiencecloud/gdpr.html">Adobe Privacy-kernservice</a>.</p></br>
   <p>Zie ook <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/getting-started/privacy/privacy-requests.html?lang=en">Verzoeken om toegang tot persoonsgegevens beheren</a>.</p>
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
   <td> <p>Vanaf Campaign 19.0 is de verouderde e-maileditor afgeschaft. Met <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/designing-content-in-adobe-campaign.html">Campagne voor e-mailontwerpen</a> kunt u uw e-mailinhoud maken en aanpassen. </p></br>
   <p>Lees <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/building-email-content/using-existing-content.html">deze sectie</a> om te ontdekken hoe u uw e-mailsjablonen voor de nieuwe editor kunt aanpassen.</p></br>
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
   <td> <p>Vanaf release 18.7 zijn geografische eenheden afgeschaft. Organisatie-eenheden en geografische eenheden zijn in Campaign identieke constructies. Gebruikers moeten uitsluitend organisatie-eenheden gebruiken om hun gebruikerstoestemming/gegevenstoegangshiërarchie samen te stellen. <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/users-and-security/organizational-units.html?lang=nl#administrating">Meer informatie</a>. Houd er rekening mee dat vanaf release 18.7 deze functie niet meer kan worden geïmplementeerd voor nieuwe Campaign Standard-instanties of voor bestaande instanties waarin geen geografische eenheden zijn gemaakt.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

## Verwijderde functies {#removed-features}

Deze sectie bevat een lijst met functies en mogelijkheden die uit Campaign Standard zijn verwijderd.

<table> 
 <thead> 
  <tr> 
   <th> <strong>Propensiteitscore bij Experience Cloud-triggers</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>De <b>propensiteitscore</b> is uit de Adobe Experience Cloud-triggers verwijderd. Deze optie is daarom ook uit Adobe Campaign Standard verwijderd. Om verouderde waarden van de propensiteitscore in de verrijkingsschema's te vermijden, raden we u aan de schema's bij te werken voor het ophalen van de nieuwste wijzigingen en het opnieuw publiceren van bestaande triggers. Raadpleeg <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/working-with-campaign-and-triggers/using-triggers-in-campaign.html"> Trigger publiceren in Campaign</a> voor meer informatie.
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
   <td> <p>[!DNL Adobe Creative SDK] is uit bedrijf genomen. Daardoor is de afbeeldingseditie die werd aangestuurd door [!DNL Creative SDK] in Campaign Standard-e-mails niet meer beschikbaar vanaf Campaign-versie 20.2.</p></br>
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
   <td> <p>Adobe Campaign en Adobe Experience Cloud bieden sinds het voorjaar van 2019 en Campaign-versie 19.2 geen ondersteuning meer voor Microsoft Internet Explorer 11. Schakel over naar Microsoft Edge of een andere ondersteunde browser. <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/about-configuration-guidelines.html">Meer informatie</a>.</p>
   </td> 
  </tr> 
 </tbody> 
</table>
