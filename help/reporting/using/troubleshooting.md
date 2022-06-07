---
title: Problemen met dynamische rapportage oplossen
description: Hier vindt u veelgestelde vragen over dynamische rapportage.
audience: reporting
content-type: reference
topic-tags: troubleshooting
feature: Reporting
role: Leader
level: Intermediate
exl-id: 0f99a109-2923-4e64-8131-80fcacf79c82
source-git-commit: 7767b39a48502f97e2b3af9d21a3f49b9283ab2e
workflow-type: tm+mt
source-wordcount: '790'
ht-degree: 4%

---

# Problemen oplossen{#troubleshooting}

In deze sectie vindt u algemene vragen met betrekking tot dynamische rapportage.

## Voor Unieke open en Unieke kliks, komt de telling in de gezamenlijke rij niet degenen in individuele rijen overeen {#unique-open-clicks-no-match}

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

Om het totale aantal unieke opent te begrijpen, moeten wij de rijtellingen van samenvatten **[!UICONTROL Unique Opens]** Dat geeft ons de waarde 3. Maar aangezien de e-mail was gericht op slechts 2 profielen, zou het Open tarief 150% moeten tonen.

Om een percentage van meer dan 100 te verkrijgen, wordt de definitie van **[!UICONTROL Unique Opens]** wordt gehandhaafd om het aantal unieke uitzendingen te zijn dat is geopend. Zelfs als P1 het e-mailbericht op dag 1 en dag 2 heeft geopend, is de unieke opening nog steeds 1.

Dit resulteert in de volgende tabel:

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong></strong> <br /> </th> 
   <th align="center"> <strong>Geopende items</strong> <br /> </th> 
   <th align="center"> <strong>Unieke openingen</strong> <br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td align="center"> <strong> Day </strong><br /> </td> 
   <td align="center"> <strong> 6 </strong><br /> </td> 
   <td align="center"> <strong> 2</strong><br /> </td>
  </tr> 
  <tr> 
   <td align="center"> Dag 1<br /> </td> 
   <td align="center"> 3<br /> </td> 
   <td align="center"> 2<br /> </td>
  </tr> 
  <tr> 
   <td align="center"> Dag 2<br /> </td> 
   <td align="center"> 3<br /> </td> 
   <td align="center"> 1<br /> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>De unieke tellingen zijn gebaseerd op een op HLL-Gebaseerde schets, dit kan kleine onnauwkeurigheden in grote aantallen veroorzaken.

## Open aantallen komen niet overeen met het aantal databases {#open-counts-no-match-database}

Dit kan te wijten zijn aan het feit dat heuristiek wordt gebruikt in Dynamische rapportering om te volgen opent zelfs wanneer wij niet kunnen volgen **[!UICONTROL Open]** handeling.

Als een gebruiker bijvoorbeeld afbeeldingen op zijn client heeft uitgeschakeld en op een koppeling in de e-mail klikt, **[!UICONTROL Open]** mag niet door de database worden bijgehouden, maar **[!UICONTROL Click]** zal.

Daarom **[!UICONTROL Open]** het volgen logboektellingen kunnen niet de zelfde telling in het gegevensbestand hebben.

Dergelijke voorvallen worden toegevoegd als **&quot;Een e-mailklik betekent dat er een e-mailbericht is geopend&quot;**.

>[!NOTE]
>
>Aangezien de unieke tellingen op een op HLL-Gebaseerde schets gebaseerd zijn, kunnen kleine inconsistenties tussen de tellingen worden ervaren.

## Hoe worden tellingen voor terugkomende/transactionele leveringen berekend? {#counts-recurring-deliveries}

Wanneer het werken met terugkomende en transactionele leveringen, zullen de tellingen aan zowel de ouder als kindleveringen worden toegeschreven.
We kunnen het voorbeeld nemen van een terugkerende levering met de naam **R1** die elke dag moet worden uitgevoerd op dag 1 (RC1), dag 2 (RC2) en dag 3 (RC3).
Laten we aannemen dat slechts één persoon alle onderliggende leveringen meerdere keren heeft geopend. In dit geval worden op de individuele terugkerende onderliggende leveringen de volgende gegevens vermeld: **[!UICONTROL Open]** tel als 1 voor elk.
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
   <td align="center"> <strong>R1</strong><br/> </td> 
   <td align="center"> <strong>100</strong><br/> </td> 
   <td align="center"> <strong>90</strong><br/> </td> 
   <td align="center"> <strong>10</strong><br/> </td> 
   <td align="center"> <strong>3</strong><br/> </td> 
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

Als u de **[!UICONTROL Conditional formatting]** aan douane, wanneer de waarde de hogere grens bereikt zal de cel groener worden. Als het de ondergrens bereikt, wordt het rood.

Hier stellen we bijvoorbeeld de **[!UICONTROL Upper limit]** tot en met 500 en **[!UICONTROL Lower limit]** tot 0.

![](assets/troubleshooting_2.png)

## Waarom komt de waarde N.v.t. in mijn rapporten voor?

![](assets/troubleshooting_3.png)

De waarde **N.v.t.** kan soms in uw dynamische rapporten verschijnen. Dit kan om drie redenen worden getoond:

* De levering is verwijderd en wordt hier weergegeven als **N.v.t.** geen discrepantie in de resultaten veroorzaken.
* Wanneer u het gereedschap **[!UICONTROL Transactional Delivery]** dimensie aan uw rapporten, de waarde **N.v.t.** kan hierdoor ontstaan. Dit gebeurt omdat het Dynamische rapport elke levering haalt zelfs als zij geen transactie zijn. Dit kan ook gebeuren wanneer u het gereedschap **[!UICONTROL Delivery]** de dimensie van uw verslag, maar in dit geval **N.v.t.** value zal transactionele leveringen vertegenwoordigen.
* Wanneer een afmeting met metrisch wordt gebruikt die niet met de afmeting verwant is. In het onderstaande voorbeeld wordt een uitsplitsing toegevoegd met de **[!UICONTROL Tracking URL]** hoewel de **[!UICONTROL Click]** count is ingesteld op 0 in this delivery.

   ![](assets/troubleshooting_4.png)

## De rapporten van leveringen tonen onvolledige gegevens wanneer het gebruiken van de afbeelding van het douaneDoel

Als u de ingevoerde afbeeldingen van het douaneDoel in leveringen gebruikt en geen gegevens in de verschillende rapporten worden getoond, zou dit kunnen betekenen dat de verbeteringen van de Rapportering niet voor die afbeeldingen van het Doel werden gecreeerd.

U lost dit als volgt op:

* Na het invoeren van uw afbeelding van het Doel van XML, zult u ook de Verrijking van de Rapportering moeten invoeren.

* In plaats van uw afbeelding van het Doel in te voeren, kunt u het direct in Adobe Campaign Standard tot stand brengen die automatisch tot de Verrijking van de Rapportering zal leiden.
