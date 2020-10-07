---
title: 'Lijst met componenten '
description: Hier vindt u de lijst met alle componenten die beschikbaar zijn in dynamische rapporten en de bijbehorende definities.
page-status-flag: never-activated
uuid: a2403806-8df4-4bb1-bac2-2689dc584ae0
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: reporting
content-type: reference
topic-tags: about-reporting
discoiquuid: 17cf126a-7ce1-4e11-bb5e-2bdce01cfded
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '1274'
ht-degree: 1%

---


# Lijst met componenten {#list-of-components}

Raadpleeg deze [tabel](/help/reporting/using/assets/dynamic_report_compatibility.pdf)voor meer informatie over compatibiliteit tussen afmetingen en metriek. Als twee componenten niet compatibel zijn, geeft de cel de waarde **Geen** weer.

![](assets/dynamic_report_compatibility.png)

## Dimension {#dimensions}

In de onderstaande tabel vindt u een overzicht van de afmetingen die in rapporten en de definities daarvan worden gebruikt.

<table> 
 <thead> 
  <tr> 
   <th> Dimension<br /> </th> 
   <th> Definitie<br /> </th> 
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
   <td> Plaats<br /> </td> 
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
   <td> Apparaat<br /> </td> 
   <td> Apparaat van waaruit de e-mail/SMS/push-melding is geopend/weergegeven/waarop is geklikt.<br /> </td> 
  </tr> 
  <tr> 
   <td> Mislukt<br /> </td> 
   <td> Typen fouten die stuitingen veroorzaakten voor elke levering, bijvoorbeeld onbekend gebruiker, ongeldig domein of postbus vol.<br /> </td> 
  </tr> 
  <tr> 
   <td> Geslacht<br /> </td> 
   <td> geslacht van de ontvanger, zoals man of vrouw. Als het genderveld leeg is in het profiel van de ontvanger, is de waarde Geen.<br /> </td> 
  </tr> 
  <tr> 
   <td> Berichtacties in de app<br /> </td> 
   <td> Handelingen in het geleverde bericht in de app, bijvoorbeeld acties op knop 1 of 2 of ontslag.<br /> </td> 
  </tr> 
  <tr> 
   <td> Berichttype<br /> </td> 
   <td> Kanaal dat voor de levering wordt gebruikt, zoals e-mail, SMS, pushmelding of In-App.<br /> </td> 
  </tr> 
  <tr> 
   <td> Naam van mobiele toepassing<br /> </td> 
   <td> Naam van de mobiele toepassing<br /> </td> 
  </tr> 
  <tr> 
   <td> Platform<br /> </td> 
   <td> Platform van het apparaat waarvan het bericht werd geopend/bekeken/aangeklikt.<br /> </td> 
  </tr> 
  <tr> 
   <td> Profiel<br /> </td> 
   <td> Hiermee groepeert u de velden voor een out-of-the-box- en aangepast profiel die zijn gemaakt tijdens de uitbreiding van de profielbron. Meer informatie hierover verwijst naar deze <a href="../../developing/using/key-steps-to-add-a-resource.md">pagina</a> of dit <a href="../../reporting/using/creating-a-custom-profile-dimension.md">voorbeeld</a>.<br /> De gegevens voor deze dimensie worden opgehaald zodra de aangepaste bron die is gekoppeld aan het profielveld is gepubliceerd.<br /> </td> 
  </tr> 
  <tr> 
   <td> Push-platform<br /> </td> 
   <td> Platform van het apparaat waarvan de pushmelding is geopend, zoals iOS of Android.<br /> </td> 
  </tr> 
  <tr> 
   <td> Ontvangerdomein<br /> </td> 
   <td> Domein dat wordt gebruikt om de e-mail te openen.<br /> </td> 
  </tr> 
  <tr> 
   <td> Terugkerende levering<br /> </td> 
   <td> Label en id van de terugkerende levering.<br /> </td> 
  </tr> 
  <tr> 
   <td> Domein afzender<br /> </td> 
   <td> Domein dat wordt gebruikt om de e-mail te verzenden.<br /> </td> 
  </tr> 
  <tr> 
   <td> IP van afzender<br /> </td> 
   <td> IP gebruikt om e-mail te verzenden.<br /> </td> 
  </tr> 
  <tr> 
   <td> Staat<br /> </td> 
   <td> Staat die is geregistreerd in het profiel van de ontvanger.<br /> </td> 
  </tr> 
  <tr> 
   <td> URL bijhouden<br /> </td> 
   <td> URL waarop de gebruiker via het bericht heeft geklikt.<br /> </td> 
  </tr> 
  <tr> 
   <td> Categorie URL bijhouden<br /> </td> 
   <td> Categorie die is toegewezen aan de URL voor bijhouden.<br /> </td> 
  </tr> 
  <tr> 
   <td> URL-label bijhouden<br /> </td> 
   <td> Label dat aan de URL wordt gegeven, zoals de spiegelpagina, neemt u contact met ons op of opent u.<br /> </td> 
  </tr> 
  <tr> 
   <td> Transactionele levering<br /> </td> 
   <td> Label en id van de levering voor de transactie.<br /> </td> 
  </tr> 
  <tr> 
   <td> Variant<br /> </td> 
   <td> Variant van het e-mailbericht in het geval van A/B-tests.<br /> </td> 
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
   <th> Definitie<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Op lijst van afgewezen personen<br /> </td> 
   <td> Aantal ontvangers die een e-mailbericht hebben gedeclareerd als spam of junk.<br /> </td> 
  </tr> 
  <tr> 
   <td> Lijst van afgewezen personen<br /> </td> 
   <td> Percentage van de op de lijst van afgewezen personen aangegeven leveringen.<br /> </td> 
  </tr> 
  <tr> 
   <td> Bounces + fouten<br /> </td> 
   <td> Totaal van fouten die tijdens levering en automatische terugkeerverwerking met betrekking tot het totale aantal verzonden berichten worden gecumuleerd.<br /> </td> 
  </tr> 
  <tr> 
   <td> Stuiteren + foutenfrequentie<br /> </td> 
   <td> Percentage van e-mailberichten dat is teruggestuurd in vergelijking met verzonden e-mail.<br /> </td> 
  </tr> 
  <tr> 
   <td> Klik op<br /> </td> 
   <td> Het aantal keren dat op een inhoud is geklikt in een levering.<br /> </td> 
  </tr> 
  <tr> 
   <td> Klikken tot snelheid<br /> </td> 
   <td> Percentage van klikken in een levering.<br /> </td> 
  </tr> 
  <tr> 
   <td> Geleverd<br /> </td> 
   <td> Het aantal berichten dat is verzonden in verhouding tot het totale aantal verzonden berichten.<br /> </td> 
  </tr> 
  <tr> 
   <td> Afgeleverde rente<br /> </td> 
   <td> Percentage berichten verzonden.<br /> </td> 
  </tr> 
  <tr> 
   <td> Hard stuiteren<br /> </td> 
   <td> Het totale aantal permanente fouten, zoals een onjuist e-mailadres.<br /> </td> 
  </tr> 
  <tr> 
   <td> Harde stuitsnelheid<br /> </td> 
   <td> Percentage leveringen dat is mislukt als gevolg van permanente fouten.<br /> </td> 
  </tr> 
  <tr> 
   <td> Pagina spiegelen<br /> </td> 
   <td> Aantal ontvangers die op de verbinding van de spiegelpagina klikte.<br /> </td> 
  </tr> 
  <tr> 
   <td> Paginasnelheid spiegelen<br /> </td> 
   <td> Percentage van klikken op de verbinding van de spiegelpagina vergeleken met de totale leveringsberichten.<br /> </td> 
  </tr> 
  <tr> 
   <td> Aanbiedingen klikken<br /> </td> 
   <td> Aantal tijd waarop op een voorstel is geklikt in een levering.<br /> </td> 
  </tr> 
  <tr> 
   <td> Aanbiedingskliktarief<br /> </td> 
   <td> Percentage van klikken op een aanbieding.<br /> </td> 
  </tr> 
  <tr> 
   <td> Open<br /> </td> 
   <td> Aantal keren dat een bericht in een levering werd geopend.<br /> </td> 
  </tr> 
  <tr> 
   <td> Open rate<br /> </td> 
   <td> Percentage geopende berichten.<br /> </td> 
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
   <td> Quarantaine<br /> </td> 
   <td> Percentage quarantines vergeleken met verzonden berichten.<br /> </td> 
  </tr> 
  <tr> 
   <td> Geweigerd<br /> </td> 
   <td> Aantal berichten die als spam door de servers SMTP worden geclassificeerd.<br /> </td> 
  </tr> 
  <tr> 
   <td> Geweigerde snelheid<br /> </td> 
   <td> Percentage berichten gemarkeerd als afgewezen.<br /> </td> 
  </tr> 
  <tr> 
   <td> Zachte stuit<br /> </td> 
   <td> Het totale aantal tijdelijke fouten, zoals een volledig postvak.<br /> </td> 
  </tr> 
  <tr> 
   <td> Zachte stuitsnelheid<br /> </td> 
   <td> Percentage leveringen dat om tijdelijke redenen is mislukt.<br /> </td> 
  </tr> 
  <tr> 
   <td> Unieke klikken<br /> </td> 
   <td> Aantal ontvangers die op een inhoud in een levering hebben geklikt.<br /> </td> 
  </tr> 
  <tr> 
   <td> Unieke openingen<br /> </td> 
   <td> Aantal ontvangers dat de levering heeft geopend.<br /> </td> 
  </tr> 
  <tr> 
   <td> Abonnement opzeggen<br /> </td> 
   <td> Percentage afboekingen door ontvanger in vergelijking met de geleverde berichten.<br /> </td> 
  </tr> 
  <tr> 
   <td> Abonnement opgezegd<br /> </td> 
   <td> Aantal klikken op de verbinding van het unsubscription.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Metrische gegevens voor pushmeldingen {#push-notification-metrics}

<table> 
 <thead> 
  <tr> 
   <th> Metrisch<br /> </th> 
   <th> Definitie<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Bounces + fouten<br /> </td> 
   <td> Totaal van fouten die tijdens de levering zijn gecumuleerd ten opzichte van het totale aantal verzonden berichten, bv. fouten van MCPNS of provider.<br /> </td> 
  </tr> 
  <tr> 
   <td> Stuiteren + foutenfrequentie<br /> </td> 
   <td> Percentage pushmeldingen dat is teruggestuurd in vergelijking met verzonden pushberichten.<br /> </td> 
  </tr> 
  <tr> 
   <td> Klik op<br /> </td> 
   <td> Het aantal keren dat een pushmelding aan het apparaat is afgeleverd en door de gebruiker is aangeklikt. De gebruiker wilde het bericht bekijken, dat dan zal worden bewogen om Open het volgen te duwen, of het sluiten.<br /> </td> 
  </tr> 
  <tr> 
   <td> Klikken tot snelheid<br /> </td> 
   <td> Percentage gebruikers die interactie hadden met de pushmelding.<br /> </td> 
  </tr> 
  <tr> 
   <td> Geleverd<br /> </td> 
   <td> Aantal verzonden pushmeldingen in verhouding tot het totale aantal verzonden pushmeldingen.<br /> </td> 
  </tr> 
  <tr> 
   <td> Afgeleverde rente<br /> </td> 
   <td> Percentage pushberichten verzonden.<br /> </td> 
  </tr> 
  <tr> 
   <td> Impressies<br /> </td> 
   <td> Het aantal keren dat een pushmelding aan het apparaat is afgeleverd en ongewijzigd is gelaten in het meldingscentrum. In de meeste gevallen zou het aantal afdrukken gelijk moeten zijn aan het geleverde getal. Dit zorgt ervoor dat het apparaat het bericht kreeg en die informatie terug naar de server terugbracht.<br /> </td> 
  </tr> 
  <tr> 
   <td> Verwerkt/verzonden<br /> </td> 
   <td> Het totale aantal verzonden pushberichten.<br /> </td> 
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
   <td> Aantal indrukken door ontvanger.<br /> </td> 
  </tr> 
  <tr> 
   <td> Unieke open<br /> </td> 
   <td> Aantal ontvangers dat de levering heeft geopend.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Metrische gegevens in de app {#in-app-metrics}

<table> 
 <thead> 
  <tr> 
   <th> Metrisch<br /> </th> 
   <th> Definitie<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Geleverd<br /> </td> 
   <td> Het totale aantal berichten in de app die door de serviceprovider aan het apparaat worden geleverd.<br /> </td> 
  </tr> 
  <tr> 
   <td> Impressies<br /> </td> 
   <td> Totaal aantal berichten in de app die door ontvangers worden gezien, afhankelijk van of aan het triggercriterium is voldaan.<br /> </td> 
  </tr> 
  <tr> 
   <td> In-app klikken <br /> </td> 
   <td> Het totale aantal ontvangers dat op Knoop 1 of Knoop 2 klikte.<br /> </td> 
  </tr> 
  <tr> 
   <td> In-app klikfrequentie<br /> </td> 
   <td> Percentage gebruikers die op Knoop 1 of Knoop 2 klikte vergeleken met gebruikers die het bericht zagen.<br /> </td> 
  </tr> 
  <tr> 
   <td> Ontslag in de app<br /> </td> 
   <td> Het totale aantal berichten dat de ontvangers of door de dichte knoop of auto-dismiss ontvingen te klikken ontvingen.<br /> </td> 
  </tr> 
  <tr> 
   <td> Ontslagfrequentie in de app<br /> </td> 
   <td> Percentage in-app-berichten dat ontvangers hebben afgewezen.<br /> </td> 
  </tr> 
  <tr> 
   <td> Verwerkt/verzonden<br /> </td> 
   <td> Het totale aantal berichten in de app dat door Adobe Campaign is verzonden als onderdeel van het verzendproces voor de levering.<br /> </td> 
  </tr> 
  <tr> 
   <td> Unieke afbeeldingen<br /> </td> 
   <td> Aantal indrukken door een unieke ontvanger.<br /> </td> 
  </tr> 
  <tr> 
   <td> Unieke muisklikken in de app<br /> </td> 
   <td> Aantal keren dat ontvangers op Knoop 1 of Knoop 2 klikten.<br /> </td> 
  </tr> 
  <tr> 
   <td> Unieke ontslagen in de app<br /> </td> 
   <td> Aantal tijdontvangers hebben een bericht in de app afgewezen.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Segmenten {#segments}

>[!NOTE]
>
>Standaard is het **[!UICONTROL Exclude proof]** segment al geselecteerd om uw rapporten te filteren, maar u kunt deze desgewenst wijzigen.

In de onderstaande tabel vindt u een lijst met segmenten die in rapporten en de bijbehorende definities worden gebruikt.

<table> 
 <thead> 
  <tr> 
   <th> Segment<br /> </th> 
   <th> Definitie<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Leeftijd: Boomklasse 1<br /> </td> 
   <td> Ontvangers, geboren van 1946 tot en met 1954.<br /> </td> 
  </tr> 
  <tr> 
   <td> Leeftijd: Boomklasse 2<br /> </td> 
   <td> Ontvangers geboren van 1955 tot 1965.<br /> </td> 
  </tr> 
  <tr> 
   <td> Leeftijd: 18 t/m 25<br /> </td> 
   <td> Ontvangers van 18 tot 25 jaar oud.<br /> </td> 
  </tr> 
  <tr> 
   <td> Leeftijd: Van 26 t/m 30<br /> </td> 
   <td> Ontvangers van 26 tot 30 jaar oud.<br /> </td> 
  </tr> 
  <tr> 
   <td> Leeftijd: Van 31 t/m 40<br /> </td> 
   <td> Ontvangers van 31 tot 40 jaar oud.<br /> </td> 
  </tr> 
  <tr> 
   <td> Leeftijd: 41 t/m 50<br /> </td> 
   <td> Ontvangers van 41 tot 50 jaar oud.<br /> </td> 
  </tr> 
  <tr> 
   <td> Leeftijd: Generatie X<br /> </td> 
   <td> Ontvangers geboren van 1966 tot 1976.<br /> </td> 
  </tr> 
  <tr> 
   <td> Leeftijd: Generation Y (Millenniumjaar)<br /> </td> 
   <td> Ontvangers, geboren van 1977 tot 1994.<br /> </td> 
  </tr> 
  <tr> 
   <td> Leeftijd: Generatie Z<br /> </td> 
   <td> Ontvangers geboren van 1995 tot vandaag.<br /> </td> 
  </tr> 
  <tr> 
   <td> Leeftijd: Groter dan 50<br /> </td> 
   <td> Ontvangers die ouder zijn dan 50 jaar.<br /> </td> 
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
   <td> Ontvangers die jonger zijn dan 40 jaar.<br /> </td> 
  </tr> 
  <tr> 
   <td> Leeftijd: Minder dan 50<br /> </td> 
   <td> Ontvangers die jonger zijn dan 50 jaar.<br /> </td> 
  </tr> 
  <tr> 
   <td> Leeftijd: Stil genereren<br /> </td> 
   <td> Ontvangers geboren in 1945 of eerder.<br /> </td> 
  </tr> 
  <tr> 
   <td> Alle bezoeken<br /> </td> 
   <td> Elke ontvanger<br /> </td> 
  </tr> 
    <tr> 
   <td> Bewijs uitsluiten<br /> </td> 
   <td> Proefdrukken uit uw rapporten uitsluiten<br /> </td> 
  </tr> 
 </tbody> 
</table>

