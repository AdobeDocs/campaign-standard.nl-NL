---
title: Lijst met functies
description: Met de tool voor het bewerken van query's kunt u geavanceerde functies gebruiken om complexe filters uit te voeren.
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
translation-type: ht
source-git-commit: fa9d2be71b4bbf5eceadbd1835db324618f9529c
workflow-type: ht
source-wordcount: '1912'
ht-degree: 100%

---


# Lijst met functies{#list-of-functions}

## Informatie over functies {#about-functions}

Met de tool voor het bewerken van query&#39;s kunt u geavanceerde functies gebruiken om complexe filters uit te voeren. Daarom bevat het palet met tools het element **[!UICONTROL Expression]** dat u in de werkruimte kunt gebruiken. Nadere informatie over dit element is te vinden in een [specifieke sectie](../../automating/using/advanced-expression-editing.md).

Met dit element kunt u handmatig uw voorwaarden invoeren. U kunt daarbij de functies gebruiken die in de volgende secties worden besproken.

Afhankelijk van de gewenste resultaten en de typen bewerkbare data zijn er verschillende functietypen beschikbaar:

* Datums
* Geomarketing
* Numerieke waarden
* Overige functies
* Aggregaten
* Tekenreeksbewerking
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
   <td> AddDays(&lt;datum&gt;, &lt;nummer&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AddHours</strong><br /> </td> 
   <td> Hiermee voegt u een aantal uren toe aan een datum<br /> </td> 
   <td> AddHours(&lt;datum&gt;, &lt;nummer&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AddMinutes</strong><br /> </td> 
   <td> Hiermee voegt u een aantal minuten toe aan een datum<br /> </td> 
   <td> AddMinutes(&lt;datum&gt;, &lt;nummer&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AddMonths</strong><br /> </td> 
   <td> Hiermee voegt u een aantal maanden toe aan een datum<br /> </td> 
   <td> AddMonths(&lt;datum&gt;, &lt;nummer&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AddSeconds</strong><br /> </td> 
   <td> Hiermee voegt u een aantal seconden toe aan een datum<br /> </td> 
   <td> AddSeconds(&lt;datum&gt;, &lt;nummer&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AddYears</strong><br /> </td> 
   <td> Hiermee voegt u een aantal jaren toe aan een datum<br /> </td> 
   <td> AddYear(&lt;datum&gt;, &lt;nummer&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DateOnly</strong><br /> </td> 
   <td> Retourneert alleen de datum (met de tijd 00:00)<br /> </td> 
   <td> DateOnly(&lt;datum&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Day</strong><br /> </td> 
   <td> Retourneert het getal dat de dag van de datum vertegenwoordigt<br /> </td> 
   <td> Day(&lt;datum&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DayOfYear</strong><br /> </td> 
   <td> Retourneert een getal dat de dag in het jaar van de datum vertegenwoordigt<br /> </td> 
   <td> DayOfYear(&lt;datum&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DaysAgo</strong><br /> </td> 
   <td> Retourneert de huidige datum minus n dagen<br /> </td> 
   <td> DaysAgo(&lt;nummer&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DaysAgoInt</strong><br /> </td> 
   <td> Retourneert de huidige datum minus n dagen (als een geheel getal jjjjmmdd)<br /> </td> 
   <td> DaysAgoInt(&lt;nummer&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DaysDiff</strong><br /> </td> 
   <td> Aantal dagen tussen twee datums<br /> </td> 
   <td> DaysDiff(&lt;einddatum&gt;, &lt;begindatum&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DaysOld</strong><br /> </td> 
   <td> Retourneert de leeftijd in dagen van een datum<br /> </td> 
   <td> DaysOld(&lt;datum&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>GetDate</strong><br /> </td> 
   <td> Hiermee wordt de huidige systeemdatum van de server geretourneerd<br /> </td> 
   <td> GetDate()<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Hour</strong><br /> </td> 
   <td> Retourneert het uur van de datum<br /> </td> 
   <td> Hour(&lt;datum&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>HoursDiff</strong><br /> </td> 
   <td> Retourneert het aantal uren tussen twee datums<br /> </td> 
   <td> HoursDiff(&lt;einddatum&gt;, &lt;begindatum&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>LocalToUTC</strong><br /> </td> 
   <td> Converteert een lokale datum en tijd naar UTC<br /> </td> 
   <td> LocalToUTC(&lt;datum&gt;, &lt;tijdzone&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Minute</strong><br /> </td> 
   <td> Retourneert de minuten van de datum<br /> </td> 
   <td> Minute(&lt;datum&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>MinutesDiff</strong><br /> </td> 
   <td> Retourneert het aantal minuten tussen twee datums<br /> </td> 
   <td> MinutesDiff(&lt;einddatum&gt;, &lt;begindatum&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Month</strong><br /> </td> 
   <td> Retourneert het getal dat de maand van de datum vertegenwoordigt<br /> </td> 
   <td> Month(&lt;datum&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>MonthsAgo</strong><br /> </td> 
   <td> Retourneert de datum die overeenkomt met de huidige datum minus n maanden<br /> </td> 
   <td> MonthsAgo(&lt;nummer&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>MonthsDiff</strong><br /> </td> 
   <td> Retourneert het aantal maanden tussen twee datums<br /> </td> 
   <td> MonthsDiff(&lt;einddatum&gt;, &lt;begindatum&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>MonthsOld</strong><br /> </td> 
   <td> Retourneert de leeftijd in maanden van een datum<br /> </td> 
   <td> MonthsOld(&lt;datum&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Second</strong><br /> </td> 
   <td> Retourneert de seconden van de datum<br /> </td> 
   <td> Second(&lt;datum&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Oldest</strong><br /> </td> 
   <td> Retourneert de oudste datum </td> 
   <td> Oldest(&lt;Datum&gt;, &lt;Datum&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>SecondsDiff</strong><br /> </td> 
   <td> Retourneert het aantal seconden tussen twee datums<br /> </td> 
   <td> SecondsDiff(&lt;einddatum&gt;, &lt;begindatum&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>SubDays</strong><br /> </td> 
   <td> Hiermee trekt u een aantal dagen van een datum af<br /> </td> 
   <td> SubDays(&lt;datum&gt;, &lt;nummer&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>SubHours</strong><br /> </td> 
   <td> Hiermee trekt u een aantal uren van een datum af<br /> </td> 
   <td> SubHours(&lt;datum&gt;, &lt;nummer&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>SubMinutes</strong><br /> </td> 
   <td> Hiermee trekt u een aantal aantal minuten van een datum af<br /> </td> 
   <td> SubMinutes(&lt;datum&gt;, &lt;nummer&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>SubMonths</strong><br /> </td> 
   <td> Hiermee trekt u een aantal maanden van een datum af<br /> </td> 
   <td> SubMonths(&lt;datum&gt;, &lt;nummer&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>SubSeconds</strong><br /> </td> 
   <td> Hiermee trekt u een aantal seconden van een datum af<br /> </td> 
   <td> SubSeconds(&lt;datum&gt;, &lt;nummer&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>SubYears</strong><br /> </td> 
   <td> Hiermee trekt u een aantal jaren van een datum af<br /> </td> 
   <td> SubYears(&lt;datum&gt;, &lt;nummer&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToDate</strong><br /> </td> 
   <td> Converteert een datum + tijd als datum<br /> </td> 
   <td> ToDate(&lt;datum + tijd&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToDateTime</strong><br /> </td> 
   <td> Zet een tekenreeks om in een datum + tijd<br /> </td> 
   <td> ToDateTime(&lt;tekenreeks&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToDateTimeWithTimezone</strong><br /> </td> 
   <td> Zet een tekenreeks om in datum + tijdzone.<br /> Voorbeeld: ToDateTimeWithTimezone ('’2019-02-19 08:09:00'’, '’Azië/Teheran'’)<br /> </td> 
   <td> ToDateTimeWithTimezone(&lt;tekenreeks&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>TruncDate</strong><br /> </td> 
   <td> Rondt een datum+tijd af naar de dichtstbijzijnde seconde<br /> </td> 
   <td> TruncDate(@lastModified, &lt;aantal seconden&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>TruncDateTZ</strong><br /> </td> 
   <td> Rondt een datum + tijd af naar een bepaalde precisie die in seconden wordt uitgedrukt<br /> </td> 
   <td> TruncDateTZ(&lt;datum&gt;, &lt;aantal seconden&gt;, &lt;tijdzone&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>TruncQuarter</strong><br /> </td> 
   <td> Rondt een datum af naar het kwartaal<br /> </td> 
   <td> TruncQuarter(&lt;datum&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>TruncTime</strong><br /> </td> 
   <td> Rondt het tijdsdeel af naar de dichtstbijzijnde seconde<br /> </td> 
   <td> TruncTime(&lt;datum&gt;, &lt;aantal seconden&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>TruncWeek</strong><br /> </td> 
   <td> Rondt een datum af naar de week<br /> </td> 
   <td> TruncWeek(&lt;datum&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>TruncYear</strong><br /> </td> 
   <td> Rondt een datum + tijd naar 1 januari van het jaar<br /> </td> 
   <td> TruncYear(&lt;datum&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>WeekDay</strong><br /> </td> 
   <td> Retourneert het getal dat de dag in de week van de datum vertegenwoordigt<br /> </td> 
   <td> WeekDay(&lt;datum&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Year</strong><br /> </td> 
   <td> Retourneert het getal dat het jaar van de datum vertegenwoordigt<br /> </td> 
   <td> Year(&lt;datum&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>YearAnd Month</strong><br /> </td> 
   <td> Retourneert het getal dat het jaar en de maand van de datum vertegenwoordigt.<br /> </td> 
   <td> YearAndMonth(&lt;datum&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>YearDiff</strong><br /> </td> 
   <td> Retourneert het aantal jaren tussen de twee datums<br /> </td> 
   <td> YearsDiff(&lt;einddatum&gt;, &lt;begindatum&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>YearsOld</strong><br /> </td> 
   <td> Retourneert de leeftijd in jaren van een datum<br /> </td> 
   <td> YearOld(&lt;datum&gt;)<br /> </td> 
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
   <td> <strong>Distance</strong><br /> </td> 
   <td> Hiermee wordt de afstand in km geretourneerd tussen twee punten die worden gedefinieerd door hun lengte- en breedtegraad (uitgedrukt in graden)<br /> </td> 
   <td> Distance(&lt;Lengtegraad A&gt;, &lt;Breedtegraad A&gt;, &lt;Lengtegraad B&gt;, &lt;Breedtegraad B&gt;)<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Numerieke waarden {#numerical}

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
   <td> Abs(&lt;nummer&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Ceil</strong><br /> </td> 
   <td> Retourneert het laagste gehele getal dat groter is dan of gelijk is aan een getal<br /> </td> 
   <td> Ceil(&lt;nummer&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Floor</strong><br /> </td> 
   <td> Retourneert het grootste gehele getal dat kleiner dan of gelijk is aan een getal<br /> </td> 
   <td> Floor(&lt;nummer&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Greatest</strong><br /> </td> 
   <td> Retourneert het hoogste van twee getallen<br /> </td> 
   <td> Greatest(&lt;nummer 1&gt;, &lt;nummer 2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Least</strong><br /> </td> 
   <td> Retourneert het laagste van twee getallen<br /> </td> 
   <td> Least(&lt;nummer 1&gt;, &lt;nummer 2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Mod</strong><br /> </td> 
   <td> Retourneert de rest van de deling van geheel getal n1 door geheel getal n2<br /> </td> 
   <td> Mod(&lt;nummer 1&gt;, &lt;nummer 2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Percent</strong><br /> </td> 
   <td> Retourneert de verhouding van twee getallen uitgedrukt als een percentage<br /> </td> 
   <td> Percent(&lt;nummer 1&gt;, &lt;nummer 2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Random</strong><br /> </td> 
   <td> Hiermee wordt de willekeurige waarde geretourneerd<br /> </td> 
   <td> Random()<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Round</strong><br /> </td> 
   <td> Rondt een getal af naar n decimalen<br /> </td> 
   <td> Round(&lt;nummer&gt;, &lt;aantal decimalen&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sign</strong><br /> </td> 
   <td> Hiermee wordt het teken van het getal geretourneerd<br /> </td> 
   <td> Sign(&lt;nummer&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToDouble</strong><br /> </td> 
   <td> Hiermee wordt een geheel getal omgezet in een zwevende waarde<br /> </td> 
   <td> ToDouble(&lt;nummer&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToInt64</strong><br /> </td> 
   <td> Zet een zwevende waarde om in een 64-bits geheel getal<br /> </td> 
   <td> ToInt64(&lt;nummer&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToInteger</strong><br /> </td> 
   <td> Hiermee wordt een zwevende waarde omgezet in een geheel getal<br /> </td> 
   <td> ToInteger(&lt;nummer&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Trunc</strong><br /> </td> 
   <td> Kapt aantal decimalen af van n1 tot n2<br /> </td> 
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
   <td> Case(When(&lt;voorwaarde&gt;, &lt;waarde 1&gt;), Else(&lt;waarde 2&gt;))<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ClearBit</strong><br /> </td> 
   <td> Hiermee verwijdert u de markering in de waarde<br /> </td> 
   <td> ClearBit(&lt;identificatiecode&gt;, &lt;markering&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Coalesce</strong><br /> </td> 
   <td> Retourneert waarde 2 als waarde 1 null of nihil is, anders wordt waarde 1 geretourneerd<br /> </td> 
   <td> Coalesce(&lt;waarde 1&gt;, &lt;waarde 2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Decode</strong><br /> </td> 
   <td> Retourneert waarde 3 als waarde 1 = waarde 2, anders wordt 4 geretourneerd<br /> </td> 
   <td> Decode(&lt;waarde 1&gt;, &lt;waarde 2&gt;, &lt;waarde 3&gt;, &lt;waarde 4&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Else</strong><br /> </td> 
   <td> Retourneert waarde 1 (mag alleen worden gebruikt als parameter van de case-functie)<br /> </td> 
   <td> Else(&lt;waarde 1&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>GetEmailDomain</strong><br /> </td> 
   <td> Extraheert het domein uit een e-mailadres<br /> </td> 
   <td> GetEmailDomain(&lt;waarde&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>GetMirrorURL</strong><br /> </td> 
   <td> Hiermee wordt de URL van de server van de spiegelpagina opgehaald<br /> </td> 
   <td> GetMirrorURL(&lt;waarde&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Iif</strong><br /> </td> 
   <td> Retourneert waarde 1 als de expressie waar is. Retourneert anders waarde 2<br /> </td> 
   <td> Iif(&lt;voorwaarde&gt;, &lt;waarde 1&gt;, &lt;waarde 2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>IsBitSet</strong><br /> </td> 
   <td> Geeft aan of de markering zich in de waarde bevindt<br /> </td> 
   <td> IsBitSet(&lt;identificatiecode&gt;, &lt;markering&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>IsEmptyString</strong><br /> </td> 
   <td> Retourneert waarde 2 als de tekenreeks leeg is. Retourneert anders waarde 3<br /> </td> 
   <td> IsEmptyString(&lt;tekenreeks&gt;, &lt;waarde 2&gt;, &lt;waarde 3&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>NoNull</strong><br /> </td> 
   <td> Retourneert de lege tekenreeks als het argument NULL is<br /> </td> 
   <td> NoNull(&lt;waarde&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>RowId</strong><br /> </td> 
   <td> Retourneert het regelnummer<br /> </td> 
   <td> RowId<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>SetBit</strong><br /> </td> 
   <td> Hiermee wordt de markering in de waarde geforceerd<br /> </td> 
   <td> SetBit(&lt;identificatiecode&gt;, &lt;markering&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToBoolean</strong><br /> </td> 
   <td> Hiermee wordt een getal omgezet in een Booleaanse waarde<br /> </td> 
   <td> ToBoolean(&lt;nummer&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>When</strong><br /> </td> 
   <td> Retourneert waarde 1 als de expressie wordt geverifieerd. Anders wordt waarde 2 geretourneerd (mag alleen worden gebruikt als parameter van de case-functie)<br /> </td> 
   <td> When(&lt;voorwaarde&gt;, &lt;waarde 1&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>newUUID</strong><br /> </td> 
   <td> Retourneert een nieuwe UUID.<br /> </td> 
   <td> newUUID<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Tekenreeks{#string}

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
   <td> AllNonNull2(&lt;tekenreeks&gt;, &lt;tekenreeks&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AllNonNull3</strong><br /> </td> 
   <td> Geeft aan of alle parameters niet null en niet leeg zijn<br /> </td> 
   <td> AllNonNull3(&lt;tekenreeks&gt;, &lt;tekenreeks&gt;, &lt;tekenreeks&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ASCII</strong><br /> </td> 
   <td> Hiermee wordt de ASCII-waarde van het eerste teken in de tekenreeks geretourneerd<br /> </td> 
   <td> Ascii(&lt;tekenreeks&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Char</strong><br /> </td> 
   <td> Hiermee wordt het teken geretourneerd dat overeenkomt met de ASCII-code ‘n’<br /> </td> 
   <td> Char(&lt;nummer&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Charindex</strong><br /> </td> 
   <td> Retourneert de positie van tekenreeks 2 in tekenreeks 1<br /> </td> 
   <td> Charindex(&lt;tekenreeks&gt;, &lt;tekenreeks&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DataLength</strong><br /> </td> 
   <td> Retourneert het aantal tekens in een tekenreeks<br /> </td> 
   <td> DataLength(&lt;tekenreeks&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>GetLine</strong><br /> </td> 
   <td> Retourneert de n-de (van 1 tot en met n) regel van de tekenreeks<br /> </td> 
   <td> GetLine(&lt;tekenreeks&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>IfEquals</strong><br /> </td> 
   <td> Hiermee wordt de derde parameter geretourneerd als de eerste twee parameters gelijk zijn, anders wordt de laatste parameter geretourneerd<br /> </td> 
   <td> IfEquals(&lt;tekenreeks&gt;, &lt;tekenreeks&gt;, &lt;tekenreeks&gt;, &lt;tekenreeks&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>IsMemoNull</strong><br /> </td> 
   <td> Geeft aan of het als parameter doorgegeven memo null is<br /> </td> 
   <td> IsMemoNull(&lt;Memo&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>JuxtWords</strong><br /> </td> 
   <td> Hiermee worden de twee doorgegeven tekenreeksen als parameters gekoppeld. Tussen elke tekenreeks wordt in de geretourneerde waarde een spatie toegevoegd.<br /> </td> 
   <td> JuxtWords(&lt;tekenreeks&gt;, &lt;tekenreeks&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>JuxtWords3</strong><br /> </td> 
   <td> Hiermee worden de drie doorgegeven tekenreeksen als parameters gekoppeld. Tussen elke tekenreeks wordt in de geretourneerde waarde een spatie toegevoegd.<br /> </td> 
   <td> JuxtWords3(&lt;tekenreeks&gt;, &lt;tekenreeks&gt;, &lt;tekenreeks&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>LPad</strong><br /> </td> 
   <td> Hiermee wordt de voltooide tekenreeks links geretourneerd<br /> </td> 
   <td> LPad(&lt;tekenreeks&gt;, &lt;nummer&gt;, &lt;teken&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Left</strong><br /> </td> 
   <td> Retourneert de eerste n tekens van de tekenreeks<br /> </td> 
   <td> Left(&lt;tekenreeks&gt;, &lt;nummer&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Length</strong><br /> </td> 
   <td> Hiermee wordt de tekenreekslengte geretourneerd<br /> </td> 
   <td> Length(&lt;tekenreeks&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Lower</strong><br /> </td> 
   <td> Hiermee wordt de tekenreeks in kleine letters geretourneerd<br /> </td> 
   <td> Lower(&lt;tekenreeks&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Ltrim</strong><br /> </td> 
   <td> Hiermee worden spaties links van de tekenreeks verwijderd<br /> </td> 
   <td> Ltrim(&lt;tekenreeks&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Md5Digest</strong><br /> </td> 
   <td> Retourneert een hexadecimale representatie van de MD5-toets van een tekenreeks<br /> </td> 
   <td> Md5Digest(&lt;tekenreeks&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>MemoContains</strong><br /> </td> 
   <td> Hiermee wordt opgegeven of het memo de tekenreeks bevat die als parameter is doorgegeven<br /> </td> 
   <td> MemoContains(&lt;memo&gt;, &lt;tekenreeks&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>RPad</strong><br /> </td> 
   <td> Hiermee wordt de voltooide tekenreeks aan de rechterkant geretourneerd<br /> </td> 
   <td> RPad(&lt;tekenreeks&gt;, &lt;nummer&gt;, &lt;teken&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Replace</strong><br /> </td> 
   <td> Vervangt alle instanties van een opgegeven tekenreekswaarde (tweede parameter) door een andere tekenreekswaarde (derde parameter) in een tekenreeks (eerste parameter)<br /> </td> 
   <td> Replace(&lt;tekenreeks&gt;, &lt;tekenreeks&gt;, &lt;tekenreeks&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Right</strong><br /> </td> 
   <td> Retourneert de laatste n tekens van de tekenreeks<br /> </td> 
   <td> Right(&lt;tekenreeks&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Rtrim</strong><br /> </td> 
   <td> Hiermee worden spaties rechts van de tekenreeks verwijderd<br /> </td> 
   <td> Rtrim(&lt;tekenreeks&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sha256Digest</strong><br /> </td> 
   <td> Berekent de standaard <strong>SHA256</strong>-hash voor een bepaalde UTF8-tekenreeks<br /> </td> 
   <td> Sha256Digest(&lt;tekenreeks&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sha384Digest</strong><br /> </td> 
   <td> Berekent de standaard <strong>SHA384</strong>-hash voor een bepaalde UTF8-tekenreeks<br /> </td> 
   <td> Sha384Digest(&lt;tekenreeks&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sha512Digest</strong><br /> </td> 
   <td> Berekent de standaard <strong>SHA512</strong>-hash voor een bepaalde UTF8-tekenreeks<br /> </td> 
   <td> Sha512Digest(&lt;tekenreeks&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Smart</strong><br /> </td> 
   <td> Retourneert de tekenreeks met de eerste letter van elk woord in hoofdletters<br /> </td> 
   <td> Smart(&lt;tekenreeks&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Substring</strong><br /> </td> 
   <td> Extraheert de subtekenreeks die begint bij teken n1 van de tekenreeks en een lengte heeft van n2<br /> </td> 
   <td> Substring(&lt;tekenreeks&gt;, &lt;offset&gt;, &lt;lengte&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToIntlString</strong><br /> </td> 
   <td> Zet het getal om in een tekenreeks<br /> </td> 
   <td> ToIntlString(&lt;nummer&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToString</strong><br /> </td> 
   <td> Zet het getal om in een tekenreeks<br /> </td> 
   <td> ToString(&lt;nummer&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Upper</strong><br /> </td> 
   <td> Hiermee wordt de tekenreeks in hoofdletters geretourneerd<br /> </td> 
   <td> Upper(&lt;tekenreeks&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>VirtualLink</strong><br /> </td> 
   <td> Retourneert de externe sleutel van een koppeling die als een parameter is doorgegeven als de andere twee parameters gelijk zijn<br /> </td> 
   <td> VirtualLink(&lt;nummer&gt;, &lt;nummer&gt;, &lt;nummer&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>VirtualLinkStr</strong><br /> </td> 
   <td> Retourneert de externe sleutel (tekst) van een koppeling die als parameter wordt doorgegeven als de andere twee parameters gelijk zijn<br /> </td> 
   <td> VirtualLinkStr(&lt;tekenreeks&gt;, &lt;nummer&gt;, &lt;nummer&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>encryption_aescbcDecrypt</strong><br /> </td> 
   <td> Decodeert een gecodeerde waarde in HEX-indeling met het voorvoegsel <strong>x</strong> (eerste parameter) met behulp van een sleutel in HEX-indeling (tweede parameter) en een initialisatievector in HEX-indeling (derde parameter)<br /> </td> 
   <td> encryption_aescbcDecrypt(&lt;tekenreeks&gt;, &lt;tekenreeks&gt;, &lt;tekenreeks&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>encryption_aescbcEncrypt</strong><br /> </td> 
   <td> Codeert met AES-algoritme (CBC-blokmodus) een tekenreeks met tekens (eerste parameter) met een sleutel (tweede parameter) en een initialisatievector (derde parameter). De sleutel en de initialisatievector moeten worden opgegeven in een hexadecimale representatie (te beginnen met <strong>\x</strong>). Het resultaat staat in de hexadecimale indeling zonder de <strong>\x</strong>.<br /> Houd er rekening mee dat de sleutellengte 128 bits, 192 bits, 256 bits (16, 24, 32 hexadecimale tekens) kan zijn, maar we raden u aan 256 bits en een gerandomiseerde IV met dezelfde lengte als de sleutel te gebruiken.<br /> </td> 
   <td> encryption_aescbcEncrypt(&lt;Tekenreeks&gt;, &lt;Tekenreeks&gt;, &lt;Tekenreeks&gt;)<br /> Bijvoorbeeld: encryption_aescbcEncrypt(johndoe@example.com, "<strong>\x0123456789ABCDEF0123456789ABCDEF</strong>", "<strong>\x0123456789ABCDEFFEDCBA9876543210</strong>")<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Aggregaten {#aggregates}

De aggregatiefuncties zijn alleen beschikbaar wanneer u [aanvullende data toevoegt](../../automating/using/query.md#enriching-data) uit de activiteit **[!UICONTROL Query]** van een workflow.

De aggregatiefuncties worden gebruikt voor het uitvoeren van berekeningen op een reeks waarden.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Naam</strong><br /> </td> 
   <td> <strong>Beschrijving</strong><br /> </td> 
   <td> <strong>Syntaxis</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Avg</strong>, Average<br /> </td> 
   <td> Retourneert het gemiddelde in een numerieke kolom.<br /> </td> 
   <td> Avg(&lt;waarde&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Count</strong>, Count (except NULL)<br /> </td> 
   <td> Telt de waarden in een kolom die niet null zijn.<br /> </td> 
   <td> Count(&lt;waarde&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>CountAll</strong>, Count all<br /> </td> 
   <td> Telt alle waarden (inclusief null-waarden en duplicaten).<br /> </td> 
   <td> CountAll()<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Countdistinct</strong>, Distinct count<br /> </td> 
   <td> Telt de niet-null-, afzonderlijke waarden in een kolom.<br /> </td> 
   <td> Countdistinct(&lt;waarde&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Max</strong>, max<br /> </td> 
   <td> Retourneert de maximumwaarde in een numerieke kolom en in een tekenreeks- of datumkolom.<br /> </td> 
   <td> Max(&lt;waarde&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Min</strong>, Min<br /> </td> 
   <td> Retourneert de minimumwaarde in een numerieke kolom en in een tekenreeks- of datumkolom.<br /> </td> 
   <td> Min(&lt;waarde&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sum</strong>, Sum<br /> </td> 
   <td> Retourneert de som van de waarden in een numerieke kolom.<br /> </td> 
   <td> Sum(&lt;waarde&gt;)<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Representatie {#representation}

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
   <td> Desc(&lt;waarde 1&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>OrderBy</strong><br /> </td> 
   <td> Hiermee wordt het resultaat binnen de partitie gesorteerd<br /> </td> 
   <td> OrderBy(&lt;waarde 1&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>PartitionBy</strong><br /> </td> 
   <td> Verdeelt het resultaat van een query op een lijst<br /> </td> 
   <td> PartitionBy(&lt;waarde 1&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>RowNum</strong><br /> </td> 
   <td> Hiermee genereert u een regelnummer op basis van de tabelpartitie en een sorteervolgorde. Deze functie wordt niet ondersteund voor MySQL<br /> </td> 
   <td> RowNum(PartitionBy(&lt;waarde 1&gt;), OrderBy(&lt;waarde 1&gt;))<br /> </td> 
  </tr> 
 </tbody> 
</table>

