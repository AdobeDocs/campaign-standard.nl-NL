---
solution: Campaign Standard
product: campaign
title: Problemen oplossen
description: Hier vindt u veelgestelde vragen over dynamische rapportage.
audience: reporting
content-type: reference
topic-tags: troubleshooting
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '665'
ht-degree: 5%

---


# Problemen oplossen{#troubleshooting}

In deze sectie vindt u algemene vragen met betrekking tot dynamische rapportage.

## Voor Unieke open en Unieke kliks, komt de telling in de gezamenlijke rij niet degenen in individuele rijen {#unique-open-clicks-no-match} overeen

Dit is een verwacht gedrag.
We kunnen het volgende voorbeeld gebruiken om dit gedrag uit te leggen.

Er wordt een e-mail verzonden naar de profielen P1 en P2.

P1 opent de e-mail tweemaal op de eerste dag en dan drie keer op de tweede dag.

Terwijl P2 de e-mail één keer opent op de eerste dag en het niet in de volgende dagen heropent.
Hier volgt een visuele weergave van de interactie van de profielen met de verzonden e-mail:

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>Day</strong> <br /> </th> 
   <th align="center"> <strong>Geopende items</strong> <br /> </th> 
   <th align="center"> <strong>Unieke openingen</strong> <br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td align="center"> Dag 1<br /> </td> 
   <td align="center"> 2 + 1 = 3<br /> </td> 
   <td align="center"> 1 + 1 = 2<br /> </td> 
  </tr> 
  <tr> 
   <td align="center"> Dag 2<br /> </td> 
   <td align="center"> 3 + 0 = 3<br /> </td> 
   <td align="center"> 1 + 0 = 1<br /> </td> 
  </tr>
 </tbody> 
</table>

Om het algemene aantal unieke opent te begrijpen, moeten wij de rijtellingen van **[!UICONTROL Unique Opens]** samenvatten die ons de waarde 3 geeft. Maar aangezien de e-mail was gericht op slechts 2 profielen, zou het Open tarief 150% moeten tonen.

Om een percentage niet te verkrijgen hoger dan 100, wordt de definitie van **[!UICONTROL Unique Opens]** gehandhaafd om het aantal unieke uitzendingen te zijn die werden geopend. Zelfs als P1 het e-mailbericht op dag 1 en dag 2 heeft geopend, is dit nog steeds 1.

Dit resulteert in de volgende tabel:

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>Dag</strong> <br /> </th> 
   <th align="center"> <strong>Geopende items</strong> <br /> </th> 
   <th align="center"> <strong>Unieke openingen</strong> <br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td align="center"> Dag 1<br /> </td> 
   <td align="center"> 6<br /> </td> 
   <td align="center"> 2<br /> </td>
  </tr> 
  <tr> 
   <td align="center"> Dag 2<br /> </td> 
   <td align="center"> 3<br /> </td> 
   <td align="center"> 2<br /> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>De unieke tellingen zijn gebaseerd op een op HLL-Gebaseerde schets, dit kan kleine onnauwkeurigheden in grote aantallen veroorzaken.

## De open tellingen passen niet de telling van het Gegevensbestand {#open-counts-no-match-database} aan

Dit kan zijn toe te schrijven aan het feit dat, heuristiek in Dynamische rapportering wordt gebruikt om te volgen opent zelfs wanneer wij niet de **[!UICONTROL Open]** actie kunnen volgen.

Als een gebruiker bijvoorbeeld afbeeldingen op zijn client heeft uitgeschakeld en op een koppeling in de e-mail klikt, wordt **[!UICONTROL Open]** mogelijk niet bijgehouden door de database, maar **[!UICONTROL Click]** wel.

Daarom **[!UICONTROL Open]** het volgen logboektellingen kunnen niet de zelfde telling in het gegevensbestand hebben.

Dergelijke voorvallen worden toegevoegd als **&quot;een e-mailklik impliceert een e-mail open&quot;**.

>[!NOTE]
>
>Aangezien de unieke tellingen op een op HLL-Gebaseerde schets gebaseerd zijn, kunnen kleine inconsistenties tussen de tellingen worden ervaren.

## Hoe worden tellingen voor terugkomende/transactionele leveringen berekend? {#counts-recurring-deliveries}

Wanneer het werken met terugkomende en transactionele leveringen, zullen de tellingen aan zowel de ouder als kindleveringen worden toegeschreven.
Wij kunnen het voorbeeld nemen van terugkomende levering genoemd **R1** die wordt geplaatst om elke dag op dag 1 (RC1), dag 2 (RC2) en dag 3 (RC3) te lopen.
Laten we aannemen dat slechts één persoon alle onderliggende leveringen meerdere keren heeft geopend. In dit geval, zullen de individuele terugkomende kindleveringen **[!UICONTROL Open]** tellen als 1 voor elk tonen.
Aangezien dezelfde persoon echter op alle leveringen heeft geklikt, heeft de bovenliggende terugkerende levering ook **[!UICONTROL Unique open]** als 1.

Rapporten moeten er als volgt uitzien:

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>Levering</strong> <br /> </th> 
   <th align="center"> <strong>Verzonden</strong> <br /> </th> 
   <th align="center"> <strong>Geleverd</strong> <br /> </th>
   <th align="center"> <strong>Geopende items</strong> <br /> </th> 
   <th align="center"> <strong>Unieke openingen</strong> <br /> </th>
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td align="center"> <strong>R1<br/> </td> 
   <td align="center"> <strong>100<br/> </td> 
   <td align="center"> <strong>90<br/> </td> 
   <td align="center"> <strong>10<br/> </td> 
   <td align="center"> <strong>3<br/> </td> 
  </tr> 
  <tr> 
   <td align="center"> RC1<br/> </td> 
   <td align="center"> 20<br /> </td> 
   <td align="center"> 20<br /> </td> 
   <td align="center"> 6<br /> </td> 
   <td align="center"> 1<br /> </td> 
  </tr>
    <tr> 
   <td align="center"> RC2<br /> </td> 
   <td align="center"> 40<br /> </td> 
   <td align="center"> 30<br /> </td> 
   <td align="center"> 2<br /> </td> 
   <td align="center"> 1<br /> </td> 
  </tr> 
    <tr> 
   <td align="center"> RC3<br /> </td> 
   <td align="center"> 40<br /> </td> 
   <td align="center"> 40<br /> </td> 
   <td align="center"> 2<br /> </td> 
   <td align="center"> 1<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Wat is de aanduiding van de kleuren in de tabel van mijn verslagen? {#reports-color-signification}

De kleuren die in uw rapporten worden getoond zijn willekeurig en kunnen niet worden gepersonaliseerd. Ze vertegenwoordigen een voortgangsbalk en worden weergegeven om u te helpen de maximale waarde die in uw rapporten wordt bereikt, beter te benadrukken.

In het onderstaande voorbeeld heeft de cel dezelfde kleur omdat de waarde 100% is.

![](assets/troubleshooting_1.png)

Als u **[!UICONTROL Conditional formatting]** in douane verandert, wanneer de waarde de hogere grens bereikt zal de cel groener worden. Als het de ondergrens bereikt, wordt het rood.

Hier stellen we bijvoorbeeld **[!UICONTROL Upper limit]** in op 500 en **[!UICONTROL Lower limit]** op 0.

![](assets/troubleshooting_2.png)

## Waarom komt de waarde N.v.t. in mijn rapporten voor?

![](assets/troubleshooting_3.png)

De waarde **N/A** kan soms in uw dynamische rapporten verschijnen. Dit kan om twee redenen worden getoond:

* De levering is verwijderd en wordt hier weergegeven als **N/A** om geen discrepantie in de resultaten te veroorzaken.
* Wanneer u de **[!UICONTROL Transactional Delivery]**-dimensie naar uw rapporten sleept, wordt mogelijk de waarde **N/A** weergegeven. Dit gebeurt omdat het Dynamische rapport elke levering haalt zelfs als zij geen transactie zijn.
Dit kan ook gebeuren wanneer u de **[!UICONTROL Delivery]**-dimensie naar uw rapport sleept en neerzet, maar in dit geval zal de waarde **N/A** transactionele leveringen vertegenwoordigen.
