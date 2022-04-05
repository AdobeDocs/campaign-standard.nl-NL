---
title: Afgeschafte en verwijderde functies van Campaign Standard
description: Deze pagina bevat de afgeschafte en verwijderde functies van Adobe Campaign Standard.
audience: rn
content-type: reference
topic-tags: campaign-standard-deprecated-features
feature: Overview
role: User
level: Beginner
exl-id: 03797137-c01c-48dc-b25b-8e72741abb04
source-git-commit: 4b0c4fb13cc11c06e2487e531ca96574e49b6beb
workflow-type: tm+mt
source-wordcount: '864'
ht-degree: 64%

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
   <th> <strong>Integratie met de dienst van de Doelen van het Publiek</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p> De aanvang van Campaign Standard 21.3 versie, integratie met de dienst van de Doelen van het Publiek wordt afgekeurd. </p>
   <p>Voor nieuwe implementatie, kunt u de dienst van de Doelen van het Publiek niet meer met Adobe Campaign Standard integreren. U kunt Campagne en Adobe Experience Platform echter integreren via Bronnen en Doelen. <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/aep-sources-destinations/get-started-sources-destinations.html?lang=en">Meer informatie</a>.</p>
     <em>Streefdatum voor verwijdering: 2022</em></p>
     </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Integratie met Adobe Experience Platform Data Connector</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p> Vanaf de Campaign Standard 21.3-release is de integratie met de Adobe Experience Platform Data Connector verouderd. </p>
   <p>Voor nieuwe implementatie kunt u de Adobe Experience Platform Data Connector niet meer integreren met Adobe Campaign Standard. U kunt Campagne en Adobe Experience Platform echter integreren via Bronnen en Doelen. <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/aep-sources-destinations/get-started-sources-destinations.html?lang=en">Meer informatie</a>.</p>
     <em>Streefdatum voor verwijdering: 2022</em></p>
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
   <td> <p>Vanaf Campaign 19.0 is de verouderde e-maileditor afgeschaft. Gebruiken <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/designing-content-in-adobe-campaign.html">Campagne voor e-mailontwerper</a> om uw e-mailinhoud te maken en aan te passen. </p></br>
   <p>Lees <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/building-email-content/using-existing-content.html">deze sectie</a> om te ontdekken hoe u uw e-mailsjablonen voor de nieuwe editor kunt aanpassen.</p></br>
  <p> 
  <em>Streefdatum voor verwijdering: 2022</em></p>
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
   <td> <p>Vanaf de startversie van Campagne 18.7 zijn geografische eenheden afgekeurd. Organisatie-eenheden en geografische eenheden zijn in Campaign identieke constructies. Gebruikers moeten uitsluitend organisatie-eenheden gebruiken om hun gebruikerstoestemming/gegevenstoegangshiërarchie samen te stellen. <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/users-and-security/organizational-units.html?lang=nl#administrating">Meer informatie</a>. Houd er rekening mee dat vanaf release 18.7 deze functie niet meer kan worden geïmplementeerd voor nieuwe Campaign Standard-instanties of voor bestaande instanties waarin geen geografische eenheden zijn gemaakt.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

## Verwijderde functies {#removed-features}

Deze sectie bevat een lijst met functies en mogelijkheden die uit Campaign Standard zijn verwijderd.



<table> 
 <thead> 
  <tr> 
   <th> <strong>Pushberichten met SDK v4</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p> Vanaf de release van Campagne 20.1 is SDK v4 afgekeurd. <a href="https://aep-sdks.gitbook.io/docs/version-4-sdk-end-of-support-faq">Meer informatie</a>.</p><br/>
   <p>De <a href="https://aep-sdks.gitbook.io/docs/">Adobe Experience Platform Mobile SDK</a> (voorheen v5 genoemd) biedt nu exclusief ondersteuning voor toekomstige Adobe Experience Cloud-functies en -functionaliteit.</p>
   <p>Na 31 augustus kunnen 2021 klanten de versie 4 SDK's blijven downloaden en gebruiken, maar er is geen ondersteuning voor de klantenservice of toegang tot forums.</p>
   <p>Leer hoe u van SDK v4 naar Adobe Experience Platform Mobile SDK kunt migreren <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/configuring-mobile/sdkv4-migration.html">op deze pagina</a>.</p></br>
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
   <td> <p>Sinds Campaign 21.2 is het gebruik van de Campaign-API en -interface voor toegangs- en verwijderingsverzoeken afgeschaft. De profielverwijdering in twee stappen is niet beschikbaar. Gebruik de <a href="https://developer.adobe.com/experience-platform-apis/references/privacy-service">Adobe Privacy-kernservice</a>.</p></br>
   <p>Zie ook <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/getting-started/privacy/privacy-requests.html?lang=nl">Verzoeken om toegang tot persoonsgegevens beheren</a>.</p>
  </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
 <tr> 
   <th> <strong>Voorspelende onderwerpregel</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p> Vanaf april 2021 wordt de voorspellende onderwerpregel uit bedrijf genomen.</p><br/>
   <p>We raden u aan e-mailmogelijkheden van AI te gebruiken om open tarieven, optimale verzendtijden en waarschijnlijke kosten te analyseren en te voorspellen op basis van historische betrokkenheidsmaatstaven. <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/preparing-and-testing-messages/predictive.html">Meer informatie</a></p></br>
     </td> 
  </tr> 
  </tbody> 
</table>

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
   <td> <p>[!DNL Adobe Creative SDK] is buiten gebruik gesteld. Dientengevolge, beelduitgave aangedreven door [!DNL Creative SDK] in Campaign Standard e-mailberichten zijn niet meer beschikbaar vanaf de release van Campagne 20.2.</p></br>
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
