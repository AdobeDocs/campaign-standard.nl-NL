---
title: Problemen oplossen
description: Hier vindt u veelgestelde vragen over dynamische rapportage.
page-status-flag: never-activated
uuid: a84a18bd-4e33-466e-a6ce-d7008fe12746
contentOwner: beneat
products: SG_CAMPAIGN/STANDARD
audience: reporting
content-type: reference
topic-tags: troubleshooting
discoiquuid: bbb41c38-12c1-4625-85d5-69627e2f4b39
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a894e72bb02fbecb86d43c6d2a13adf7ab10f73e
workflow-type: tm+mt
source-wordcount: '665'
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
   <th align="center"> <strong>Dag</strong> <br /> </th> 
   <th align="center"> <strong>Openen</strong> <br /> </th> 
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

Om het totale aantal unieke opent te begrijpen, moeten wij de rijtellingen samenvatten waarvan de waarde 3 **[!UICONTROL Unique Opens]** is. Maar aangezien de e-mail was gericht op slechts 2 profielen, zou het Open tarief 150% moeten tonen.

Om geen percentage te verkrijgen hoger dan 100, **[!UICONTROL Unique Opens]** wordt de definitie van gehandhaafd om het aantal unieke uitzendingen te zijn die werden geopend. Zelfs als P1 het e-mailbericht op dag 1 en dag 2 heeft geopend, is dit nog steeds 1.

Dit resulteert in de volgende tabel:

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>Dag</strong> <br /> </th> 
   <th align="center"> <strong>Openen</strong> <br /> </th> 
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

## Open aantallen komen niet overeen met het aantal databases {#open-counts-no-match-database}

Dit kan te wijten zijn aan het feit dat heuristiek wordt gebruikt in Dynamische rapportering om te volgen opent zelfs wanneer wij de **[!UICONTROL Open]** actie niet kunnen volgen.

Als een gebruiker bijvoorbeeld afbeeldingen op zijn client heeft uitgeschakeld en op een koppeling in de e-mail klikt, wordt de afbeelding **[!UICONTROL Open]** mogelijk niet bijgehouden door de database, maar **[!UICONTROL Click]** wel door de database.

Daarom de **[!UICONTROL Open]** volgende logboekaantallen kunnen niet de zelfde telling in het gegevensbestand hebben.

Dergelijke voorvallen worden toegevoegd als **&quot;een e-mailklik impliceert een open e-mail&quot;**.

>[!NOTE]
>
>Aangezien de unieke tellingen op een op HLL-Gebaseerde schets gebaseerd zijn, kunnen kleine inconsistenties tussen de tellingen worden ervaren.

## Hoe worden tellingen voor terugkomende/transactionele leveringen berekend? {#counts-recurring-deliveries}

Wanneer het werken met terugkomende en transactionele leveringen, zullen de tellingen aan zowel de ouder als kindleveringen worden toegeschreven.
Wij kunnen het voorbeeld nemen van een terugkomende levering genoemd **R1** die wordt geplaatst om elke dag op dag 1 (RC1), dag 2 (RC2) en dag 3 (RC3) te lopen.
Laten we aannemen dat slechts één persoon alle onderliggende leveringen meerdere keren heeft geopend. In dit geval, zullen de individuele terugkomende kindleveringen de **[!UICONTROL Open]** telling als 1 voor elk tonen.
Aangezien dezelfde persoon echter op alle leveringen heeft geklikt, heeft de bovenliggende terugkerende levering ook **[!UICONTROL Unique open]** de waarde 1.

Rapporten moeten er als volgt uitzien:

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>Aflevering</strong> <br /> </th> 
   <th align="center"> <strong>Verzonden</strong> <br /> </th> 
   <th align="center"> <strong>Geleverd</strong> <br /> </th>
   <th align="center"> <strong>Openen</strong> <br /> </th> 
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

Als u de kleur wijzigt in Aangepast, wordt de cel groener wanneer de waarde de bovengrens bereikt. **[!UICONTROL Conditional formatting]** Als het de ondergrens bereikt, wordt het rood.

Hier stellen we de waarde bijvoorbeeld in op **[!UICONTROL Upper limit]** 500 en **[!UICONTROL Lower limit]** op 0.

![](assets/troubleshooting_2.png)

## Waarom komt de waarde N.v.t. in mijn rapporten voor?

![](assets/troubleshooting_3.png)

De waarde **N.v.t** kan soms in uw dynamische rapporten verschijnen. Dit kan om twee redenen worden getoond:

* De levering is verwijderd en wordt hier weergegeven als **N.v.t** om geen discrepantie in de resultaten te veroorzaken.
* Wanneer u de **[!UICONTROL Transactional Delivery]** dimensie naar uw rapporten sleept, wordt de waarde **N.v.t** . mogelijk weergegeven. Dit gebeurt omdat het Dynamische rapport elke levering haalt zelfs als zij geen transactie zijn.
Dit kan ook gebeuren wanneer u de **[!UICONTROL Delivery]** dimensie naar uw rapport sleept en neerzet, maar in dit geval, zal de waarde **N/A** transactionele leveringen vertegenwoordigen.
