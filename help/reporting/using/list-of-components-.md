---
solution: Campaign Standard
product: campaign
title: 'Lijst met componenten '
description: Hier vindt u de lijst met alle componenten die beschikbaar zijn in     Dynamische rapporten en hun definities.
audience: reporting
content-type: reference
topic-tags: about-reporting
translation-type: tm+mt
source-git-commit: 6fffc6a3574c71c01f1e07ff4e6e6aa194479079
workflow-type: tm+mt
source-wordcount: '1285'
ht-degree: 1%

---


# Lijst met componenten {#list-of-components}

Meer over verenigbaarheid tussen dimensies en metriek leren, verwijs naar dit [lijst](/help/reporting/using/assets/dynamic_report_compatibility.pdf). Als twee componenten niet compatibel zijn, zal de cel de waarde **None** tonen.

[![image](assets/dynamic_report_compatibility.png)](https://experienceleague.adobe.com/docs/campaign-standard/assets/dynamic_report_compatibility.pdf?lang=en)

## Dimension {#dimensions}

In de onderstaande tabel vindt u een overzicht van de afmetingen die in rapporten en de definities daarvan worden gebruikt.

<table> 
 <thead> 
  <tr> 
   <th> Dimension<br /> </th> 
   <th> Definition<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Browser<br /> </td> 
   <td> Browser waarvan het bericht werd geopend of aangeklikt.<br /> </td> 
  </tr> 
  <tr> 
   <td> Campaign<br /> </td> 
   <td> Label en id van uw campagne.<br /> </td> 
  </tr> 
  <tr> 
   <td> Stad<br /> </td> 
   <td> Plaats geregistreerd in het profiel van de ontvanger.<br /> </td> 
  </tr> 
  <tr> 
   <td> Land/regio<br /> </td> 
   <td> Land geregistreerd in profiel van ontvanger.<br /> </td> 
  </tr> 
  <tr> 
   <td> Levering<br /> </td> 
   <td> Label en id van de levering.<br /> </td> 
  </tr> 
  <tr> 
   <td> Device<br /> </td> 
   <td> Apparaat van waaruit de e-mail/SMS/push-melding is geopend/weergegeven/waarop is geklikt.<br /> </td> 
  </tr> 
  <tr> 
   <td> Reddingsreden<br /> </td> 
   <td> Typen fouten die stuitingen hebben veroorzaakt voor elke levering, bijvoorbeeld onbekend gebruiker, ongeldig domein of postbus vol.<br /> </td> 
  </tr> 
  <tr> 
   <td> Geslacht<br /> </td> 
   <td> geslacht van de ontvanger, zoals man of vrouw. Als het genderveld leeg is in het profiel van de ontvanger, is de waarde Geen.<br /> </td> 
  </tr> 
  <tr> 
   <td> Berichtacties in de app<br /> </td> 
   <td> Handelingen in het geleverde bericht in de app, bijvoorbeeld acties op knop 1 of 2 of ontslagen.<br /> </td> 
  </tr> 
  <tr> 
   <td> Berichttype<br /> </td> 
   <td> Kanaal dat voor de levering wordt gebruikt, zoals e-mail, SMS, pushmelding of In-App.<br /> </td> 
  </tr> 
  <tr> 
   <td> Mobiele toepassingsnaam<br /> </td> 
   <td> Naam van de mobiele toepassing<br /> </td> 
  </tr> 
  <tr> 
   <td> Platform<br /> </td> 
   <td> Platform van het apparaat waarvan het bericht is geopend/bekeken/aangeklikt.<br /> </td> 
  </tr> 
  <tr> 
   <td> Profiel<br /> </td> 
   <td> Hiermee groepeert u velden buiten de box en aangepaste profielvelden die zijn gemaakt tijdens de uitbreiding van de profielbron. Meer informatie hierover verwijst naar deze <a href="../../developing/using/key-steps-to-add-a-resource.md">pagina</a> of dit <a href="../../reporting/using/creating-a-custom-profile-dimension.md">voorbeeld</a>.<br /> De gegevens voor deze dimensie worden opgehaald zodra de aangepaste bron die is gekoppeld aan het profielveld is gepubliceerd.<br /> </td> 
  </tr> 
  <tr> 
   <td> Push platform<br /> </td> 
   <td> Platform van het apparaat waarvan de pushmelding is geopend, zoals iOS of Android.<br /> </td> 
  </tr> 
  <tr> 
   <td> Ontvangerdomein<br /> </td> 
   <td> Domein dat wordt gebruikt om e-mail te openen.<br /> </td> 
  </tr> 
  <tr> 
   <td> Terugkerende levering<br /> </td> 
   <td> Label en id van de terugkerende levering.<br /> </td> 
  </tr> 
  <tr> 
   <td> Afzender domein<br /> </td> 
   <td> Domein dat wordt gebruikt om e-mail te verzenden.<br /> </td> 
  </tr> 
  <tr> 
   <td> IP<br /> van afzender </td> 
   <td> IP wordt gebruikt om e-mail te verzenden.<br /> </td> 
  </tr> 
  <tr> 
   <td> Status<br /> </td> 
   <td> Staat die is geregistreerd in het profiel van de ontvanger.<br /> </td> 
  </tr> 
  <tr> 
   <td> URL bijhouden<br /> </td> 
   <td> URL die door de gebruiker van het bericht werd aangeklikt.<br /> </td> 
  </tr> 
  <tr> 
   <td> URL-categorie bijhouden<br /> </td> 
   <td> Categorie toegewezen aan volgende URL.<br /> </td> 
  </tr> 
  <tr> 
   <td> URL-label bijhouden<br /> </td> 
   <td> Label dat aan de URL wordt gegeven, zoals de spiegel, contacteert ons of opent.<br /> </td> 
  </tr> 
  <tr> 
   <td> Transactielevering<br /> </td> 
   <td> Label en id van de levering van de transactie.<br /> </td> 
  </tr> 
  <tr> 
   <td> Variant<br /> </td> 
   <td> Variant van het e-mailbericht in geval van A/B-tests.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Metrisch {#metrics}

De lijsten hieronder geven u de lijst van metriek die in rapporten en hun definities afhankelijk van het leveringstype wordt gebruikt.

### Metrische gegevens voor e-mail en SMS {#email-and-sms-metrics}

<table> 
 <thead> 
  <tr> 
   <th> Metrisch<br /> </th> 
   <th> Definition<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Op lijst van afgewezen personen<br /> </td> 
   <td> Aantal ontvangers die een e-mail als spam of junk hebben verklaard.<br /> </td> 
  </tr> 
  <tr> 
   <td> Lijst van afgewezen personen snelheid<br /> </td> 
   <td> Percentage leveringen gemarkeerd op lijst van afgewezen personen.<br /> </td> 
  </tr> 
  <tr> 
   <td> Stuiterwaarden + fouten<br /> </td> 
   <td> Totaal van fouten gecumuleerd tijdens levering en automatische terugkeerverwerking met betrekking tot het totale aantal verzonden berichten.<br /> </td> 
  </tr> 
  <tr> 
   <td> Bounce + foutenfrequentie<br /> </td> 
   <td> Percentage verzonden e-mailberichten dat is teruggestuurd in vergelijking met verzonden e-mail.<br /> </td> 
  </tr> 
  <tr> 
   <td> Klik op<br /> </td> 
   <td> Aantal keren dat op een inhoud is geklikt in een levering.<br /> </td> 
  </tr> 
  <tr> 
   <td> Klikken door frequentie<br /> </td> 
   <td> Percentage van klikken in een levering.<br /> </td> 
  </tr> 
  <tr> 
   <td> Afgeleverd<br /> </td> 
   <td> Aantal berichten dat is verzonden, in verhouding tot het totale aantal verzonden berichten.<br /> </td> 
  </tr> 
  <tr> 
   <td> Afgeleverde snelheid<br /> </td> 
   <td> Percentage van de verzonden berichten.<br /> </td> 
  </tr> 
  <tr> 
   <td> Hard stuit<br /> </td> 
   <td> Het totale aantal permanente fouten, zoals een onjuist e-mailadres.<br /> </td> 
  </tr> 
  <tr> 
   <td> Harde stuitersnelheid<br /> </td> 
   <td> Percentage leveringen dat is mislukt als gevolg van permanente fouten.<br /> </td> 
  </tr> 
  <tr> 
   <td> Pagina spiegelen<br /> </td> 
   <td> Aantal ontvangers die op de verbinding van de spiegelpagina klikte.<br /> </td> 
  </tr> 
  <tr> 
   <td> Bezig met spiegelen van paginasnelheid<br /> </td> 
   <td> Percentage van klikken op de verbinding van de spiegelpagina vergeleken met de totale leveringsberichten.<br /> </td> 
  </tr> 
  <tr> 
   <td> Aanbieding klikt<br /> </td> 
   <td> Aantal tijd een aanbieding werd geklikt op in een levering.<br /> </td> 
  </tr> 
  <tr> 
   <td> Aanbiedingskliktarief<br /> </td> 
   <td> Percentage van klikken op een aanbieding.<br /> </td> 
  </tr> 
  <tr> 
   <td> Open<br /> </td> 
   <td> Aantal tijden een bericht in een levering werd geopend.<br /> </td> 
  </tr> 
  <tr> 
   <td> Open rate<br /> </td> 
   <td> Percentage van geopende berichten.<br /> </td> 
  </tr> 
  <tr> 
   <td> Verwerkt/verzonden<br /> </td> 
   <td> Het totale aantal verzendt voor de levering.<br /> </td> 
  </tr> 
  <tr> 
   <td> Quarantine<br /> </td> 
   <td> Aantal berichten die in quarantaine van het adres stuitten en resulteerden.<br /> </td> 
  </tr> 
  <tr> 
   <td> Quarantaine rate<br /> </td> 
   <td> Percentage quarantines in vergelijking met verzonden berichten.<br /> </td> 
  </tr> 
  <tr> 
   <td> Afgewezen<br /> </td> 
   <td> Aantal berichten die als spam door de servers SMTP worden geclassificeerd.<br /> </td> 
  </tr> 
  <tr> 
   <td> Afgewezen snelheid<br /> </td> 
   <td> Percentage berichten gemarkeerd als afgewezen.<br /> </td> 
  </tr> 
  <tr> 
   <td> Zachte stuit<br /> </td> 
   <td> Het totale aantal tijdelijke fouten, zoals een volledig inbox.<br /> </td> 
  </tr> 
  <tr> 
   <td> Zachte stuitsnelheid<br /> </td> 
   <td> Percentage leveringen dat vanwege een tijdelijke reden is mislukt.<br /> </td> 
  </tr> 
  <tr> 
   <td> Unieke klikken<br /> </td> 
   <td> Aantal ontvangers die op een inhoud in een levering klikte.<br /> </td> 
  </tr> 
  <tr> 
   <td> Uniek wordt geopend<br /> </td> 
   <td> Aantal ontvangers die de levering hebben geopend.<br /> </td> 
  </tr> 
  <tr> 
   <td> Abonnement opzeggen<br /> </td> 
   <td> Percentage afboekingen door ontvanger in vergelijking met de geleverde berichten.<br /> </td> 
  </tr> 
  <tr> 
   <td> Afgemeld<br /> </td> 
   <td> Aantal klikken op de unsubscription verbinding.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Metrische gegevens voor pushmeldingen {#push-notification-metrics}

<table> 
 <thead> 
  <tr> 
   <th> Metrisch<br /> </th> 
   <th> Definition<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Stuiterwaarden + fouten<br /> </td> 
   <td> Totaal aantal fouten tijdens de levering in verhouding tot het totale aantal verzonden berichten, bv. fouten van MCPNS of provider.<br /> </td> 
  </tr> 
  <tr> 
   <td> Bounce + foutenfrequentie<br /> </td> 
   <td> Percentage pushmeldingen dat is teruggestuurd in vergelijking met verzonden pushberichten.<br /> </td> 
  </tr> 
  <tr> 
   <td> Klik op<br /> </td> 
   <td> Het aantal keren dat een pushmelding aan het apparaat is afgeleverd en door de gebruiker is aangeklikt. De gebruiker wilde of het bericht bekijken, dat dan zal worden bewogen om Open het volgen te duwen, of het ontslaan.<br /> </td> 
  </tr> 
  <tr> 
   <td> Klikken door frequentie<br /> </td> 
   <td> Percentage gebruikers dat interactie heeft gehad met de pushmelding.<br /> </td> 
  </tr> 
  <tr> 
   <td> Afgeleverd<br /> </td> 
   <td> Aantal verzonden pushberichten is geslaagd, in verhouding tot het totale aantal verzonden pushmeldingen.<br /> </td> 
  </tr> 
  <tr> 
   <td> Afgeleverde snelheid<br /> </td> 
   <td> Percentage verzonden pushmeldingen.<br /> </td> 
  </tr> 
  <tr> 
   <td> Impressies<br /> </td> 
   <td> Het aantal keren dat een pushmelding aan het apparaat is afgeleverd en ongewijzigd is gelaten in het meldingscentrum. In de meeste gevallen zou het aantal afdrukken gelijk moeten zijn aan het geleverde getal. Dit zorgt ervoor dat het apparaat het bericht kreeg en die informatie terug naar de server.<br /> </td> 
  </tr> 
  <tr> 
   <td> Verwerkt/verzonden<br /> </td> 
   <td> Totaal aantal verzonden pushmeldingen.<br /> </td> 
  </tr> 
  <tr> 
   <td> Open<br /> </td> 
   <td> Het totale aantal pushberichten dat aan het apparaat is geleverd en waarop gebruikers hebben geklikt om de app te openen. Dit is gelijkaardig aan de Duw klikt behalve zal een Duw Open niet teweeggebracht worden als het bericht werd verworpen.<br /> </td> 
  </tr> 
  <tr> 
   <td> Open rate<br /> </td> 
   <td> Percentage geopende pushmeldingen.<br /> </td> 
  </tr> 
  <tr> 
   <td> Unieke klikken<br /> </td> 
   <td> Aantal keren dat een unieke gebruiker communiceert met de pushmelding, bijvoorbeeld wanneer hij op de melding of knop klikt.<br /> </td> 
  </tr> 
  <tr> 
   <td> Unieke afbeeldingen<br /> </td> 
   <td> Aantal afbeeldingen door ontvanger.<br /> </td> 
  </tr> 
  <tr> 
   <td> Unieke open<br /> </td> 
   <td> Aantal ontvangers die de levering hebben geopend.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Metrische waarden {#in-app-metrics} in de app

<table> 
 <thead> 
  <tr> 
   <th> Metrisch<br /> </th> 
   <th> Definition<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Afgeleverd<br /> </td> 
   <td> Het totale aantal berichten in de app dat door de serviceprovider aan het apparaat is geleverd.<br /> </td> 
  </tr> 
  <tr> 
   <td> Impressies<br /> </td> 
   <td> Totaal aantal berichten in de app die door ontvangers worden gezien, afhankelijk van het feit of aan het triggercriterium is voldaan.<br /> </td> 
  </tr> 
  <tr> 
   <td> In-app klikt <br /> </td> 
   <td> Het totale aantal ontvangers dat op Knoop 1 of Knoop 2 klikte.<br /> </td> 
  </tr> 
  <tr> 
   <td> In-app klik door tarief<br /> </td> 
   <td> Percentage gebruikers die op Knoop 1 of Knoop 2 klikte vergeleken met gebruikers die het bericht zagen.<br /> </td> 
  </tr> 
  <tr> 
   <td> In-app ontslag<br /> </td> 
   <td> Het totale aantal berichten dat de ontvangers of door de dichte knoop te klikken of auto-dismiss verwierpen.<br /> </td> 
  </tr> 
  <tr> 
   <td> Ontslagfrequentie in de app<br /> </td> 
   <td> Percentage in-app-berichten dat ontvangers hebben verwijderd.<br /> </td> 
  </tr> 
  <tr> 
   <td> Verwerkt/verzonden<br /> </td> 
   <td> Het totale aantal berichten in de app dat door Adobe Campaign is verzonden als onderdeel van het verzonden leveringsproces.<br /> </td> 
  </tr> 
  <tr> 
   <td> Unieke afbeeldingen<br /> </td> 
   <td> Aantal afbeeldingen door een unieke ontvanger.<br /> </td> 
  </tr> 
  <tr> 
   <td> Unieke klik in de app<br /> </td> 
   <td> Aantal tijden de ontvangers klikten op Knoop 1 of Knoop 2.<br /> </td> 
  </tr> 
  <tr> 
   <td> Unieke ontslagen in de app<br /> </td> 
   <td> Aantal tijdontvangers hebben een bericht in de app genegeerd.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Segmenten {#segments}

>[!NOTE]
>
>Standaard is het segment **[!UICONTROL Exclude proof]** al geselecteerd om uw rapporten te filteren, maar kan het desgewenst worden gewijzigd.

In de onderstaande tabel vindt u een lijst met segmenten die in rapporten en de bijbehorende definities worden gebruikt.

<table> 
 <thead> 
  <tr> 
   <th> Segment<br /> </th> 
   <th> Definition<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Leeftijd: Boomsoorten 1<br /> </td> 
   <td> Ontvangers geboren van 1946 tot 1954.<br /> </td> 
  </tr> 
  <tr> 
   <td> Leeftijd: Boomers 2<br /> </td> 
   <td> Ontvangers geboren van 1955 tot 1965.<br /> </td> 
  </tr> 
  <tr> 
   <td> Leeftijd: Van 18 tot 25<br /> </td> 
   <td> Ontvangers van 18 tot 25 jaar oud.<br /> </td> 
  </tr> 
  <tr> 
   <td> Leeftijd: Van 26 tot 30<br /> </td> 
   <td> Ontvangers van 26 tot 30 jaar oud.<br /> </td> 
  </tr> 
  <tr> 
   <td> Leeftijd: Van 31 tot 40<br /> </td> 
   <td> Ontvangers van 31 tot 40 jaar oud.<br /> </td> 
  </tr> 
  <tr> 
   <td> Leeftijd: Van 41 tot 50<br /> </td> 
   <td> Ontvangers van 41 tot 50 jaar oud.<br /> </td> 
  </tr> 
  <tr> 
   <td> Leeftijd: Generatie X<br /> </td> 
   <td> Ontvangers geboren van 1966 tot 1976.<br /> </td> 
  </tr> 
  <tr> 
   <td> Leeftijd: Generatie Y (Millenniumwaarden)<br /> </td> 
   <td> Ontvangers geboren van 1977 tot 1994.<br /> </td> 
  </tr> 
  <tr> 
   <td> Leeftijd: Generatie Z<br /> </td> 
   <td> Ontvangers geboren van 1995 tot vandaag.<br /> </td> 
  </tr> 
  <tr> 
   <td> Leeftijd: Groter dan 50<br /> </td> 
   <td> Ontvangers die ouder zijn dan 50.<br /> </td> 
  </tr> 
  <tr> 
   <td> Leeftijd: Minder dan 25<br /> </td> 
   <td> Ontvangers die jonger zijn dan 25 jaar.<br /> </td> 
  </tr> 
  <tr> 
   <td> Leeftijd: Minder dan 30<br /> </td> 
   <td> Ontvangers die jonger zijn dan 30 jaar.<br /> </td> 
  </tr> 
  <tr> 
   <td> Leeftijd: Minder dan 40<br /> </td> 
   <td> Ontvangers met een leeftijd van minder dan 40 jaar.<br /> </td> 
  </tr> 
  <tr> 
   <td> Leeftijd: Minder dan 50<br /> </td> 
   <td> Ontvangers met een leeftijd van minder dan 50 jaar.<br /> </td> 
  </tr> 
  <tr> 
   <td> Leeftijd: Stille generatie<br /> </td> 
   <td> Ontvangers geboren in 1945 of eerder.<br /> </td> 
  </tr> 
  <tr> 
   <td> Alle bezoeken<br /> </td> 
   <td> Elke ontvanger<br /> </td> 
  </tr> 
    <tr> 
   <td> Proef<br /> uitsluiten </td> 
   <td> Proefdrukken uitsluiten van uw rapporten<br /> </td> 
  </tr> 
 </tbody> 
</table>

