---
title: Afgeschafte en verwijderde functies van Campaign Standard
description: Deze pagina bevat de afgeschafte en verwijderde functies van Adobe Campaign Standard.
feature: Overview
role: User
level: Beginner
exl-id: 03797137-c01c-48dc-b25b-8e72741abb04
source-git-commit: 6b683ccd93e10f78ff643eed9f374a794c085cb1
workflow-type: tm+mt
source-wordcount: '882'
ht-degree: 57%

---

# Verouderde en verwijderde functies {#deprecated-and-removed-features}

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
   <th> <strong>SDK V4 voor mobiele toepassingen</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>De ondersteuning voor de Adobe Experience Platform Mobile-versie 4 SDK's loopt af op 31 augustus 2021. Als u deze oudere versie van de SDK nog steeds gebruikt in Adobe Campaign Standard, moet u uw implementatie bijwerken met de Adobe Experience Platform SDK <strong>vóór eind juni 2024</strong>. </p></br>
   <p>Uitlezen <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/configuring-mobile/sdkv4-migration.html?lang=nl-NL">dit artikel</a> om te leren hoe u uw implementatie kunt aanpassen en naar de nieuwste SDK van het Experience Platform kunt gaan.</p></br>
   <p><strong>Waarschuwing</strong>: De SDK V4 wordt vanaf eind juni 2024 niet meer ondersteund in Campaign Standard.</p>
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
   <td> <p>Vanaf Campaign 19.0 is de verouderde e-maileditor afgeschaft. Gebruiken <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/designing-content-in-adobe-campaign.html?lang=nl-NL">Campagne voor e-mailontwerper</a> om uw e-mailinhoud te maken en aan te passen. </p></br>
   <p>Lees <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/building-email-content/using-existing-content.html?lang=nl-NL">deze sectie</a> om te ontdekken hoe u uw e-mailsjablonen voor de nieuwe editor kunt aanpassen.</p></br>
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
   <td> <p>Vanaf de release Campagne 18.7 zijn geografische eenheden afgekeurd. Organisatie-eenheden en geografische eenheden zijn in Campaign identieke constructies. Gebruikers moeten uitsluitend organisatie-eenheden gebruiken om hun gebruikerstoestemming/gegevenstoegangshiërarchie samen te stellen. <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/users-and-security/organizational-units.html?lang=nl#administrating">Meer informatie</a>. Houd er rekening mee dat vanaf release 18.7 deze functie niet meer kan worden geïmplementeerd voor nieuwe Campaign Standard-instanties of voor bestaande instanties waarin geen geografische eenheden zijn gemaakt.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

## Verwijderde functies {#removed-features}

Deze sectie bevat een lijst met functies en mogelijkheden die uit Campaign Standard zijn verwijderd.

<table> 
 <thead> 
  <tr> 
   <th> <strong>Integratie met de dienst van de Doelen van het Publiek</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p> De aanvang van Campaign Standard 21.3 versie, integratie met de dienst van de Doelen van het Publiek wordt afgekeurd.  Het is nu verwijderd.</p>
   <p>Voor nieuwe implementatie, kunt u de dienst van de Doelen van het Publiek niet meer met Adobe Campaign Standard integreren. U kunt Campagne en Adobe Experience Platform echter integreren via Bronnen en Doelen. <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/aep-sources-destinations/get-started-sources-destinations.html?lang=nl-NL">Meer informatie</a>.</p>
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
   <td> <p> Vanaf de release van Campaign Standard 21.3 is de integratie met de Adobe Experience Platform Data Connector verouderd.  Het is nu verwijderd.</p>
   <p>Voor nieuwe implementatie kunt u de Adobe Experience Platform Data Connector niet meer integreren met Adobe Campaign Standard. U kunt Campagne en Adobe Experience Platform echter integreren via Bronnen en Doelen. <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/aep-sources-destinations/get-started-sources-destinations.html?lang=nl-NL">Meer informatie</a>.</p>
     </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Pushberichten met SDK v4</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p> Vanaf de release van Campagne 20.1 is SDK v4 afgekeurd. Het is nu verwijderd. <a href="https://experienceleague.adobe.com/docs/discontinued/using/mobile-services.htmlhtml?lang=bl">Meer informatie</a>.</p><br/>
   <p>De <a href="https://developer.adobe.com/client-sdks/documentation/">Adobe Experience Platform Mobile SDK</a> (voorheen v5 genoemd) biedt nu exclusief ondersteuning voor toekomstige Adobe Experience Cloud-functies en -functionaliteit.</p>
   <p>Na 31 augustus kunnen 2021 klanten de versie 4 SDK's blijven downloaden en gebruiken, maar er is geen ondersteuning voor de klantenservice of toegang tot forums.</p>
   <p>Leer hoe u van SDK v4 naar Adobe Experience Platform Mobile SDK kunt migreren <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/configuring-mobile/sdkv4-migration.html?lang=nl-NL">op deze pagina</a>.</p></br>
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
   <td> <p>Sinds Campaign 21.2 is het gebruik van de Campaign-API en -interface voor toegangs- en verwijderingsverzoeken afgeschaft. De profielverwijdering in twee stappen is niet meer beschikbaar. Gebruiken <a href="https://developer.adobe.com/experience-platform-apis/references/privacy-service">Adobe Privacy Core-service</a>.</p></br>
   <p>Zie ook <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/getting-started/privacy/privacy-requests.html?lang=nl-NL">Verzoeken om toegang tot persoonsgegevens beheren</a>.</p>
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
   <p>We raden u aan e-mailmogelijkheden van AI te gebruiken om open tarieven, optimale verzendtijden en waarschijnlijke kosten te analyseren en te voorspellen op basis van historische betrokkenheidsmaatstaven. <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/preparing-and-testing-messages/predictive.html?lang=nl-NL">Meer informatie</a></p></br>
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
   <td> <p>De <b>propensiteitscore</b> is uit de Adobe Experience Cloud-triggers verwijderd. Deze optie is daarom ook uit Adobe Campaign Standard verwijderd. Om verouderde waarden van de propensiteitscore in de verrijkingsschema's te vermijden, raden we u aan de schema's bij te werken voor het ophalen van de nieuwste wijzigingen en het opnieuw publiceren van bestaande triggers. Raadpleeg <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/working-with-campaign-and-triggers/using-triggers-in-campaign.html?lang=nl-NL"> Trigger publiceren in Campaign</a> voor meer informatie.
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
   <td> <p>[!DNL Adobe Creative SDK] is ontmanteld. Dientengevolge, beelduitgave aangedreven door [!DNL Creative SDK] in Campaign Standard zijn e-mails niet meer beschikbaar vanaf de release van Campagne 20.2.</p></br>
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
   <td> <p>Adobe Campaign en Adobe Experience Cloud bieden sinds het voorjaar van 2019 en Campaign-versie 19.2 geen ondersteuning meer voor Microsoft Internet Explorer 11. Schakel over naar Microsoft Edge of een andere ondersteunde browser. <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/about-configuration-guidelines.html?lang=nl-NL">Meer informatie</a>.</p>
   </td> 
  </tr> 
 </tbody> 
</table>
