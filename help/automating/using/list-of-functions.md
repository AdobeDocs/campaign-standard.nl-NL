---
title: Lijst met functies
description: Met het gereedschap voor het bewerken van query's kunt u geavanceerde functies gebruiken om complexe filters uit te voeren.
page-status-flag: never-activated
uuid: fd50fc99-1e7a-479b-beb7-1f246b419d46
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: filtering-data
discoiquuid: 3cdbe962-1c59-4cd8-b29e-36aa2562fac6
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: fa9d2be71b4bbf5eceadbd1835db324618f9529c

---


# Lijst met functies{#list-of-functions}

## Informatie over functies {#about-functions}

Met het gereedschap voor het bewerken van query&#39;s kunt u geavanceerde functies gebruiken om complexe filters uit te voeren. Hiertoe bevat het gereedschapspalet het **[!UICONTROL Expression]** element dat u in de werkruimte kunt gebruiken. Nadere informatie over dit element is te vinden in een [specifieke sectie](../../automating/using/advanced-expression-editing.md).

Met dit element kunt u handmatig uw voorwaarden invoeren. Hier kunt u de functies gebruiken die in de volgende secties worden bepaald.

Afhankelijk van de gewenste resultaten en de typen gemanipuleerde gegevens zijn er verschillende functietypen beschikbaar:

* Datums
* Geomarketing
* Numerieke waarden
* Overige functies
* Aggregaten
* Bewerking van tekenreeks
* Sorteren

## Datums {#dates}

De datumfuncties worden gebruikt om datum- of tijdwaarden te manipuleren.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Naam</strong><br /> </td> 
   <td> <strong>Beschrijving</strong><br /> </td> 
   <td> <strong>Syntaxis</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AddDays</strong><br /> </td> 
   <td> Hiermee voegt u een aantal dagen toe aan een datum<br /> </td> 
   <td> AddDays(&lt;date&gt;, &lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AddHours</strong><br /> </td> 
   <td> Hiermee voegt u een aantal uren toe aan een datum<br /> </td> 
   <td> AddHours(&lt;date&gt;, &lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AddMinutes</strong><br /> </td> 
   <td> Hiermee wordt een aantal minuten toegevoegd aan een datum<br /> </td> 
   <td> AddMinutes(&lt;date&gt;, &lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AddMonths</strong><br /> </td> 
   <td> Hiermee voegt u een aantal maanden toe aan een datum<br /> </td> 
   <td> AddMonths(&lt;date&gt;, &lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AddSeconds</strong><br /> </td> 
   <td> Hiermee wordt een aantal seconden toegevoegd aan een datum<br /> </td> 
   <td> AddSeconds(&lt;date&gt;, &lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AddYaren</strong><br /> </td> 
   <td> Hiermee wordt een aantal jaren toegevoegd aan een datum<br /> </td> 
   <td> AddYear(&lt;date&gt;, &lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DateOnly</strong><br /> </td> 
   <td> Retourneert alleen de datum (met tijd om 00:00)<br /> </td> 
   <td> DateOnly(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Dag</strong><br /> </td> 
   <td> Retourneert het getal dat de dag van de datum vertegenwoordigt<br /> </td> 
   <td> Dag (&lt;datum&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DayOfYear</strong><br /> </td> 
   <td> Retourneert een getal dat de dag in het jaar van de datum vertegenwoordigt<br /> </td> 
   <td> DayOfYear(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DaysAgo</strong><br /> </td> 
   <td> Retourneert de huidige datum min n dagen<br /> </td> 
   <td> DaysAgo(&lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DaysAgoInt</strong><br /> </td> 
   <td> Retourneert de huidige datum min n dagen (als een geheel getal jjjjmmdd)<br /> </td> 
   <td> DaysAgoInt(&lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DaysDiff</strong><br /> </td> 
   <td> Aantal dagen tussen twee datums<br /> </td> 
   <td> DaysDiff(&lt;einddatum&gt;, &lt;begindatum&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DaysOld</strong><br /> </td> 
   <td> Retourneert de leeftijd in dagen van een datum<br /> </td> 
   <td> DaysOld(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>GetDate</strong><br /> </td> 
   <td> Hiermee wordt de huidige systeemdatum van de server geretourneerd<br /> </td> 
   <td> GetDate()<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Uur</strong><br /> </td> 
   <td> Retourneert het uur van de datum<br /> </td> 
   <td> Uur(&lt;datum&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>HoursDiff</strong><br /> </td> 
   <td> Retourneert het aantal uren tussen twee datums<br /> </td> 
   <td> HoursDiff(&lt;einddatum&gt;, &lt;begindatum&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>LocalToUTC</strong><br /> </td> 
   <td> Converteert een lokale datum en tijd naar UTC<br /> </td> 
   <td> LocalToUTC(&lt;date&gt;, &lt;Time Zone&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Minuut</strong><br /> </td> 
   <td> Retourneert de minuten van de datum<br /> </td> 
   <td> Minuut(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>MinutesDiff</strong><br /> </td> 
   <td> Retourneert het aantal minuten tussen twee datums<br /> </td> 
   <td> MinutesDiff(&lt;end date&gt;, &lt;start date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Maand</strong><br /> </td> 
   <td> Retourneert het getal dat de maand van de datum vertegenwoordigt<br /> </td> 
   <td> Maand (&lt;datum&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>MonthsAgo</strong><br /> </td> 
   <td> Retourneert de datum die overeenkomt met de huidige datum min n maanden<br /> </td> 
   <td> MonthsAgo(&lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>MonthsDiff</strong><br /> </td> 
   <td> Retourneert het aantal maanden tussen twee datums<br /> </td> 
   <td> MonthsDiff(&lt;end date&gt;, &lt;start date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>MonthsOld</strong><br /> </td> 
   <td> Retourneert de leeftijd in maanden van een datum<br /> </td> 
   <td> MonthsOld(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Seconde</strong><br /> </td> 
   <td> Hiermee worden de seconden van de datum geretourneerd<br /> </td> 
   <td> Second(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Oudst</strong><br /> </td> 
   <td> Retourneert de oudste datum </td> 
   <td> Oudst(&lt;Date&gt;, &lt;Date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>SecondsDiff</strong><br /> </td> 
   <td> Retourneert het aantal seconden tussen twee datums<br /> </td> 
   <td> SecondsDiff(&lt;einddatum&gt;, &lt;begindatum&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Subdagen</strong><br /> </td> 
   <td> Hiermee trekt u een aantal dagen van een datum af<br /> </td> 
   <td> SubDays(&lt;date&gt;, &lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>SubHours</strong><br /> </td> 
   <td> Hiermee wordt een aantal uren van een datum afgetrokken<br /> </td> 
   <td> SubHours(&lt;date&gt;, &lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>SubMinutes</strong><br /> </td> 
   <td> Hiermee wordt een aantal minuten van een datum afgetrokken<br /> </td> 
   <td> SubMinutes(&lt;date&gt;, &lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Submaanden</strong><br /> </td> 
   <td> Hiermee trekt u een aantal maanden van een datum af<br /> </td> 
   <td> SubMonths(&lt;date&gt;, &lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>SubSeconds</strong><br /> </td> 
   <td> Trekt een aantal seconden van een datum af<br /> </td> 
   <td> SubSeconds(&lt;date&gt;, &lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Subjaren</strong><br /> </td> 
   <td> Hiermee trekt u een aantal jaren van een datum af<br /> </td> 
   <td> Subjaren(&lt;date&gt;, &lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToDate</strong><br /> </td> 
   <td> Converteert een datum + tijd als datum<br /> </td> 
   <td> TotDatum (&lt;datum + tijd&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToDateTime</strong><br /> </td> 
   <td> Zet een tekenreeks om in een datum + tijd<br /> </td> 
   <td> ToDateTime(&lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToDateTimeWithTimezone</strong><br /> </td> 
   <td> Zet een tekenreeks om in datum en tijdzone.<br /> Voorbeeld: ToDateTimeWithTimezone ("2019-02-19 08:09:00", "Asia/Teheran")<br /> </td> 
   <td> ToDateTimeWithTimezone(&lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>TruncDate</strong><br /> </td> 
   <td> Rondt een datum+tijd aan het dichtstbijzijnde tweede<br /> </td> 
   <td> TruncDate(@lastModified, &lt;aantal seconden&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>TruncDateTZ</strong><br /> </td> 
   <td> Rondt een datum + tijd aan een bepaalde precisie die in seconden wordt uitgedrukt<br /> </td> 
   <td> TruncDateTZ(&lt;date&gt;, &lt;number of seconds&gt;, &lt;time zone&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>TruncQuarter</strong><br /> </td> 
   <td> Rondt een datum af op het kwartaal<br /> </td> 
   <td> TruncQuarter(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>TruncTime</strong><br /> </td> 
   <td> Rondt het tijdsdeel af tot de dichtstbijzijnde seconde<br /> </td> 
   <td> TruncTime(&lt;date&gt;, &lt;number of seconds&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>TruncWeek</strong><br /> </td> 
   <td> Rondt een datum af naar de week<br /> </td> 
   <td> TruncWeek(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>TruncYear</strong><br /> </td> 
   <td> Rondt een datum + tijd tot 1 januari van het jaar<br /> </td> 
   <td> TruncYear(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>WeekDay</strong><br /> </td> 
   <td> Retourneert het getal dat de dag in de week van de datum vertegenwoordigt<br /> </td> 
   <td> WeekDay(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Jaar</strong><br /> </td> 
   <td> Retourneert het getal dat het jaar van de datum vertegenwoordigt<br /> </td> 
   <td> Jaar (&lt;datum&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Jaar en maand</strong><br /> </td> 
   <td> Retourneert het getal dat het jaar en de maand van de datum vertegenwoordigt.<br /> </td> 
   <td> YearAndMonth(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>YearDiff</strong><br /> </td> 
   <td> Retourneert het aantal jaren tussen de twee datums<br /> </td> 
   <td> YarenDiff(&lt;einddatum&gt;, &lt;begindatum&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>JarenOud</strong><br /> </td> 
   <td> Retourneert de leeftijd in jaren van een datum<br /> </td> 
   <td> YearOld(&lt;date&gt;)<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Geomarketing {#geomarketing}

De geomarketing-functies worden gebruikt om geografische waarden te manipuleren.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Naam</strong><br /> </td> 
   <td> <strong>Beschrijving</strong><br /> </td> 
   <td> <strong>Syntaxis</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Afstand</strong><br /> </td> 
   <td> Hiermee wordt de afstand in km geretourneerd tussen twee punten die worden gedefinieerd door hun lengte en breedte (uitgedrukt in graden)<br /> </td> 
   <td> Afstand (&lt;Lengtegraad A&gt;, &lt;Latitude A&gt;, &lt;Lengtegraad B&gt;, &lt;Latitude B&gt;)<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Numeriek {#numerical}

De functies voor numerieke waarden worden gebruikt om tekst om te zetten in getallen.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Naam</strong><br /> </td> 
   <td> <strong>Beschrijving</strong><br /> </td> 
   <td> <strong>Syntaxis</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Abs</strong><br /> </td> 
   <td> Retourneert de absolute waarde van een getal<br /> </td> 
   <td> Abs(&lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Ceil</strong><br /> </td> 
   <td> Retourneert het laagste gehele getal dat groter is dan of gelijk is aan een getal<br /> </td> 
   <td> Ceil(&lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Floor</strong><br /> </td> 
   <td> Retourneert het grootste gehele getal dat kleiner dan of gelijk is aan een getal<br /> </td> 
   <td> Floor(&lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Groter</strong><br /> </td> 
   <td> Retourneert de grootste van twee getallen<br /> </td> 
   <td> Greatest(&lt;number 1&gt;, &lt;number 2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Minste</strong><br /> </td> 
   <td> Retourneert het laagste van twee getallen<br /> </td> 
   <td> Least(&lt;number 1&gt;, &lt;number 2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Mod</strong><br /> </td> 
   <td> Retourneert de rest van de integer-deling van n1 door n2<br /> </td> 
   <td> Mod(&lt;number 1&gt;, &lt;number 2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Percentage</strong><br /> </td> 
   <td> Retourneert de verhouding van twee getallen uitgedrukt als een percentage<br /> </td> 
   <td> Percentage (&lt;number 1&gt;, &lt;number 2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Willekeurig</strong><br /> </td> 
   <td> Hiermee wordt de willekeurige waarde geretourneerd<br /> </td> 
   <td> Random()<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Rond</strong><br /> </td> 
   <td> Rondt een getal af naar n decimalen<br /> </td> 
   <td> Round(&lt;number&gt;, &lt;number of decimal&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Ondertekenen</strong><br /> </td> 
   <td> Hiermee wordt het teken van het getal geretourneerd<br /> </td> 
   <td> Sign(&lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToDouble</strong><br /> </td> 
   <td> Hiermee wordt een geheel getal omgezet in een zwevende waarde<br /> </td> 
   <td> ToDouble(&lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToInt64</strong><br /> </td> 
   <td> Zet een float om in een 64-bits geheel getal<br /> </td> 
   <td> ToInt64(&lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToInteger</strong><br /> </td> 
   <td> Hiermee wordt een zwevende waarde omgezet in een geheel getal<br /> </td> 
   <td> ToInteger(&lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Trunc</strong><br /> </td> 
   <td> Aantal decimalen n1 tot n2<br /> </td> 
   <td> Trunc(&lt;n1&gt;, &lt;n2&gt;)<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Overige {#others}

Deze tabel bevat de resterende beschikbare functies.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Naam</strong><br /> </td> 
   <td> <strong>Beschrijving</strong><br /> </td> 
   <td> <strong>Syntaxis</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Case</strong><br /> </td> 
   <td> Retourneert waarde 1 als de voorwaarde is geverifieerd. Anders wordt waarde 2 geretourneerd<br /> </td> 
   <td> Case(When(&lt;condition&gt;, &lt;value 1&gt;), else(&lt;value 2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ClearBit</strong><br /> </td> 
   <td> Hiermee verwijdert u de markering in de waarde<br /> </td> 
   <td> ClearBit(&lt;identifier&gt;, &lt;flag&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Coalesce</strong><br /> </td> 
   <td> Retourneert waarde 2 als waarde 1 nul of null is, anders wordt waarde 1 geretourneerd<br /> </td> 
   <td> Coalesce(&lt;value 1&gt;, &lt;value 2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Decode</strong><br /> </td> 
   <td> Retourneert waarde 3 is waarde 1 = waarde 2, anders retourneert 4<br /> </td> 
   <td> Decode(&lt;value 1&gt;, &lt;value 2&gt;, &lt;value 3&gt;, &lt;value 4&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Else</strong><br /> </td> 
   <td> Retourneert waarde 1 (mag alleen worden gebruikt als parameter van de case-functie)<br /> </td> 
   <td> else(&lt;value 1&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>GetEmailDomain</strong><br /> </td> 
   <td> Extraheert het domein uit een e-mailadres<br /> </td> 
   <td> GetEmailDomain(&lt;value&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>GetMirrorURL</strong><br /> </td> 
   <td> Hiermee wordt de URL van de server van de spiegel opgehaald<br /> </td> 
   <td> GetMirrorURL(&lt;value&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Iif</strong><br /> </td> 
   <td> Retourneert waarde 1 als de expressie true is. Retourneert anders waarde 2<br /> </td> 
   <td> Iif(&lt;condition&gt;, &lt;value 1&gt;, &lt;value 2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>IsBitSet</strong><br /> </td> 
   <td> Geeft aan of de markering zich in de waarde bevindt<br /> </td> 
   <td> IsBitSet(&lt;identifier&gt;, &lt;flag&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>IsEmptyString</strong><br /> </td> 
   <td> Retourneert waarde 2 als de tekenreeks leeg is. Retourneert anders waarde 3<br /> </td> 
   <td> IsEmptyString(&lt;string&gt;, &lt;value 2&gt;, &lt;value 3&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>NoNull</strong><br /> </td> 
   <td> Retourneert de lege tekenreeks als het argument NULL is<br /> </td> 
   <td> NoNull(&lt;value&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>RowId</strong><br /> </td> 
   <td> Retourneert het regelnummer<br /> </td> 
   <td> RowId<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>SetBit</strong><br /> </td> 
   <td> Hiermee wordt de vlag in de waarde geforceerd<br /> </td> 
   <td> SetBit(&lt;identifier&gt;, &lt;flag&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToBoolean</strong><br /> </td> 
   <td> Hiermee wordt een getal omgezet in een Booleaanse waarde<br /> </td> 
   <td> ToBoolean(&lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Wanneer</strong><br /> </td> 
   <td> Retourneert waarde 1 als de expressie wordt geverifieerd. Anders wordt waarde 2 geretourneerd (mag alleen worden gebruikt als parameter van de case-functie)<br /> </td> 
   <td> When(&lt;condition&gt;, &lt;value 1&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>newUID</strong><br /> </td> 
   <td> Retourneert een nieuwe UUID.<br /> </td> 
   <td> newUID<br /> </td> 
  </tr> 
 </tbody> 
</table>

## String {#string}

De tekenreeksfuncties worden gebruikt om een set tekenreeksen te manipuleren.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Naam</strong><br /> </td> 
   <td> <strong>Beschrijving</strong><br /> </td> 
   <td> <strong>Syntaxis</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AllNonNull2</strong><br /> </td> 
   <td> Geeft aan of alle parameters niet null en niet leeg zijn<br /> </td> 
   <td> AllNonNull2(&lt;string&gt;, &lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AllNonNull3</strong><br /> </td> 
   <td> Geeft aan of alle parameters niet null en niet leeg zijn<br /> </td> 
   <td> AllNonNull3(&lt;string&gt;, &lt;string&gt;, &lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ASCII</strong><br /> </td> 
   <td> Hiermee wordt de ASCII-waarde van het eerste teken in de tekenreeks geretourneerd<br /> </td> 
   <td> Ascii(&lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Char</strong><br /> </td> 
   <td> Hiermee wordt het teken geretourneerd dat overeenkomt met de ASCII-code 'n'<br /> </td> 
   <td> Char(&lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Charindex</strong><br /> </td> 
   <td> Retourneert de positie van tekenreeks 2 in tekenreeks 1<br /> </td> 
   <td> Charindex(&lt;string&gt;, &lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DataLength</strong><br /> </td> 
   <td> Retourneert het aantal tekens in een tekenreeks<br /> </td> 
   <td> DataLength(&lt;String&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>GetLine</strong><br /> </td> 
   <td> Retourneert de nde (van 1 tot en met n) regel van de tekenreeks<br /> </td> 
   <td> GetLine(&lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>IfEquals</strong><br /> </td> 
   <td> Hiermee wordt de derde parameter geretourneerd als de eerste twee parameters gelijk zijn, anders wordt de laatste parameter geretourneerd<br /> </td> 
   <td> IfEquals(&lt;string&gt;, &lt;string&gt;, &lt;string&gt;, &lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>IsMemoNull</strong><br /> </td> 
   <td> Geeft aan of het als parameter doorgegeven memo null is<br /> </td> 
   <td> IsMemoNull(&lt;Memo&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>JuxtWords</strong><br /> </td> 
   <td> Hiermee worden de twee doorgegeven tekenreeksen als parameters gekoppeld. Tussen elke tekenreeks wordt in de geretourneerde waarde een spatie toegevoegd.<br /> </td> 
   <td> JuxtWords(&lt;string&gt;, &lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>JuxtWords3</strong><br /> </td> 
   <td> Hiermee worden de drie doorgegeven tekenreeksen als parameters gekoppeld. Tussen elke tekenreeks wordt in de geretourneerde waarde een spatie toegevoegd.<br /> </td> 
   <td> JuxtWords3(&lt;string&gt;, &lt;string&gt;, &lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>LPad</strong><br /> </td> 
   <td> Hiermee wordt de voltooide tekenreeks links geretourneerd<br /> </td> 
   <td> LPad(&lt;string&gt;, &lt;number&gt;, &lt;caractère&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Links</strong><br /> </td> 
   <td> Retourneert de eerste n tekens van de tekenreeks<br /> </td> 
   <td> Left(&lt;string&gt;, &lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Lengte</strong><br /> </td> 
   <td> Hiermee wordt de tekenreekslengte geretourneerd<br /> </td> 
   <td> Lengte (&lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Onder</strong><br /> </td> 
   <td> Hiermee wordt de tekenreeks in kleine letters geretourneerd<br /> </td> 
   <td> Lower(&lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Ltrim</strong><br /> </td> 
   <td> Hiermee worden spaties links van de tekenreeks verwijderd<br /> </td> 
   <td> Ltrim(&lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Md5Digest</strong><br /> </td> 
   <td> Retourneert een hexadecimale representatie van de toets MD5 van een tekenreeks<br /> </td> 
   <td> Md5Digest(&lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>MemoContains</strong><br /> </td> 
   <td> Hiermee wordt opgegeven of het memo de tekenreeks bevat die als parameter is doorgegeven<br /> </td> 
   <td> MemoContains(&lt;memo&gt;, &lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>RPad</strong><br /> </td> 
   <td> Hiermee wordt de voltooide tekenreeks aan de rechterkant geretourneerd<br /> </td> 
   <td> RPad(&lt;string&gt;, &lt;number&gt;, &lt;character&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Vervangen</strong><br /> </td> 
   <td> Vervangt alle instanties van een opgegeven tekenreekswaarde (tweede parameter) door een andere tekenreekswaarde (derde parameter) in een tekenreeks (eerste parameter)<br /> </td> 
   <td> Replace(&lt;String&gt;, &lt;String&gt;, &lt;String&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Rechts</strong><br /> </td> 
   <td> Retourneert de laatste n tekens van de tekenreeks<br /> </td> 
   <td> Right(&lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Rtrim</strong><br /> </td> 
   <td> Hiermee worden spaties rechts van de tekenreeks verwijderd<br /> </td> 
   <td> Rtrim(&lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sha256Digest</strong><br /> </td> 
   <td> Berekent de standaard <strong>SHA256</strong> -hash voor een bepaalde UTF8-tekenreeks<br /> </td> 
   <td> Sha256Digest(&lt;String&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sha384Digest</strong><br /> </td> 
   <td> Berekent de standaard <strong>SHA384</strong> -hash voor een bepaalde UTF8-tekenreeks<br /> </td> 
   <td> Sha384Digest(&lt;String&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sha512Digest</strong><br /> </td> 
   <td> Berekent de standaard <strong>SHA512</strong> -hash voor een bepaalde UTF8-tekenreeks<br /> </td> 
   <td> Sha512Digest(&lt;String&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Slim</strong><br /> </td> 
   <td> Retourneert de tekenreeks met de eerste letter van elk woord in hoofdletters<br /> </td> 
   <td> Smart(&lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Subtekenreeks</strong><br /> </td> 
   <td> Extraheert de subtekenreeks die begint op teken n1 van de tekenreeks en met een lengte van n2<br /> </td> 
   <td> Substring(&lt;string&gt;, &lt;offset&gt;, &lt;length&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToIntlString</strong><br /> </td> 
   <td> Zet het getal om in een tekenreeks<br /> </td> 
   <td> ToIntlString(&lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToString</strong><br /> </td> 
   <td> Zet het getal om in een tekenreeks<br /> </td> 
   <td> ToString(&lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Bovenkant</strong><br /> </td> 
   <td> Hiermee wordt de tekenreeks in hoofdletters geretourneerd<br /> </td> 
   <td> Upper(&lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>VirtualLink</strong><br /> </td> 
   <td> Retourneert de externe sleutel van een koppeling die als een parameter is doorgegeven als de andere twee parameters gelijk zijn<br /> </td> 
   <td> VirtualLink(&lt;number&gt;, &lt;number&gt;, &lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>VirtualLinkStr</strong><br /> </td> 
   <td> Retourneert de externe (tekst) sleutel van een koppeling die als parameter wordt doorgegeven als de andere twee parameters gelijk zijn<br /> </td> 
   <td> VirtualLinkStr(&lt;string&gt;, &lt;number&gt;, &lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>encryption_aescbcDecrypt</strong><br /> </td> 
   <td> Decodeert een gecodeerde waarde in HEX-indeling met het voorvoegsel "<strong>x</strong>" (eerste parameter) met behulp van een sleutel in HEX-indeling (tweede parameter) en een initialisatievector in HEX-indeling (derde parameter)<br /> </td> 
   <td> encryption_aescbcDecrypt(&lt;String&gt;, &lt;String&gt;, &lt;String&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>encryption_aescbcEncrypt</strong><br /> </td> 
   <td> Codeert met AES-algoritme (CBC-blokmodus) een tekenreeks met tekens (eerste parameter) met een sleutel (tweede parameter) en een initialisatievector (derde parameter). De sleutel en de initialisatievector moeten worden opgegeven in een hexadecimale representatie (te beginnen met <strong>\x</strong>). Het resultaat wordt hexadecimaal zonder de <strong>\x</strong>.<br /> Houd er rekening mee dat de sleutellengte 128 bits, 192 bits, 256 bits (16, 24, 32 hexadecimale tekens) kan zijn, maar we raden u aan 256 bits en een gerandomiseerde IV met dezelfde lengte als de sleutel te gebruiken.<br /> </td> 
   <td> encryption_aescbcEncrypt(&lt;String&gt;, &lt;String&gt;, &lt;String&gt;)<br /> Bijvoorbeeld: encryption_aescbcEncrypt(johndoe@example.com, "<strong>\x0123456789ABCDEF0123456789ABCDEF</strong>", "<strong>\x0123456789ABCDEFFEDA 9876543210</strong>")<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Aggregaten {#aggregates}

De samenvoegingsfuncties zijn alleen beschikbaar wanneer u aanvullende gegevens [](../../automating/using/query.md#enriching-data) toevoegt uit de **[!UICONTROL Query]** activiteit van een workflow.

De statistische functies worden gebruikt voor het uitvoeren van berekeningen op een reeks waarden.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Naam</strong><br /> </td> 
   <td> <strong>Beschrijving</strong><br /> </td> 
   <td> <strong>Syntaxis</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Gemiddeld</strong>, gemiddeld<br /> </td> 
   <td> Retourneert het gemiddelde in een numerieke kolom.<br /> </td> 
   <td> Avg(&lt;value&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Aantal</strong>, Aantal (behalve ONGELDIG)<br /> </td> 
   <td> Telt de waarden in een kolom die niet 'null' zijn.<br /> </td> 
   <td> Count(&lt;value&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Alles</strong>tellen, alles tellen<br /> </td> 
   <td> Telt alle waarden (inclusief null-waarden en duplicaten).<br /> </td> 
   <td> CountAll()<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Aftelbaar</strong>, Afzonderlijk aantal<br /> </td> 
   <td> Telt de niet-null, verschillende waarden in een kolom.<br /> </td> 
   <td> Countdifferent(&lt;value&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Max</strong>, max<br /> </td> 
   <td> Retourneert de maximumwaarde in een numerieke, tekenreeks- of datumkolom.<br /> </td> 
   <td> Max(&lt;value&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Min</strong>, min<br /> </td> 
   <td> Retourneert de minimumwaarde in een numerieke, tekenreeks- of datumkolom.<br /> </td> 
   <td> Min(&lt;value&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Som</strong>, Som<br /> </td> 
   <td> Retourneert de som van de waarden in een numerieke kolom.<br /> </td> 
   <td> Sum(&lt;value&gt;)<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Vertegenwoordiging {#representation}

De representatiefuncties worden gebruikt om waarden te bestellen.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Naam</strong><br /> </td> 
   <td> <strong>Beschrijving</strong><br /> </td> 
   <td> <strong>Syntaxis</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Desc</strong><br /> </td> 
   <td> Hiermee wordt een aflopende sortering toegepast<br /> </td> 
   <td> Desc(&lt;value 1&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>OrderBy</strong><br /> </td> 
   <td> Hiermee wordt het resultaat binnen de partitie gesorteerd<br /> </td> 
   <td> OrderBy(&lt;value 1&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>PartitionBy</strong><br /> </td> 
   <td> Verdeelt het resultaat van een vraag op een lijst<br /> </td> 
   <td> PartitionBy(&lt;value 1&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>RowNum</strong><br /> </td> 
   <td> Hiermee genereert u een regelnummer op basis van de tabelpartitie en een sorteervolgorde. Deze functie wordt niet ondersteund voor MySQL<br /> </td> 
   <td> RowNum(PartitionBy(&lt;value 1&gt;), OrderBy(&lt;value 1&gt;))<br /> </td> 
  </tr> 
 </tbody> 
</table>

