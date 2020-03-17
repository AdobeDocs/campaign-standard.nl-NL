---
title: Campagnedimensies en meetgegevens in Analytics
description: Leer de verschillende afmetingen die u in Adobe Analytics kunt vinden beginnen uw e-mailleveringen van de Campagne van Adobe te volgen.
page-status-flag: never-activated
uuid: effa1028-66b2-4bef-b5e4-7319dbb23d5d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
discoiquuid: eb3639f5-7246-46c4-8ddb-da9413b40c32
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Campagnedimensies en meetgegevens in Analytics{#campaign-dimensions-and-metrics-in-analytics}

Met de integratie van Adobe Campaign en Adobe Analytics kunt u het succes van uw e-mailleveringen rechtstreeks bijhouden in Adobe Analytics.

Campagne **[!UICONTROL dimensions]** gevonden in Analytics wordt hieronder vermeld:

<table> 
 <thead> 
  <tr> 
   <th> Dimensie<br /> </th> 
   <th> Definitie<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Campagne-id<br /> </td> 
   <td> Interne naam van campagne zoals weergegeven in campagne<br /> </td> 
  </tr> 
  <tr> 
   <td> Campagnelabel<br /> </td> 
   <td> Campagnelabel zoals weergegeven in Campagne<br /> </td> 
  </tr> 
  <tr> 
   <td> Leverings-id<br /> </td> 
   <td> Interne naam van levering zoals weergegeven in Campagne.<br /> Bijvoorbeeld, is DM1 een terugkomende levering die wordt gepland om kindleveringen elke week te verzenden. DM2, DM3 en DM4 worden verzonden de eerste drie weken. De dimensie van identiteitskaart van de Levering zal dan de resultaten voor elke levering, namelijk DM1 aan DM4 tonen. <br /> </td> 
  </tr> 
  <tr> 
   <td> Afleveringslabel<br /> </td> 
   <td> Label van levering zoals weergegeven in campagne<br /> </td> 
  </tr> 
  <tr> 
   <td> Uitgevoerde leverings-id<br /> </td> 
   <td> Interne naam van levering zoals weergegeven in Campagne. Dit heeft alleen betrekking op de uitvoering in Campagne.<br /> Bijvoorbeeld, is DM1 een terugkomende levering die wordt gepland om kindleveringen elke week te verzenden. DM2, DM3 en DM4 worden verzonden de eerste drie weken. De uitgevoerde afmeting van leveringsidentiteitskaart zal dan de resultaten voor de uitgevoerde leveringen, namelijk de kindleveringen DM2, DM3 en DM4 tonen. <br /> </td> 
  </tr> 
  <tr> 
   <td> Uitvoerd leveringslabel<br /> </td> 
   <td> Het label van de levering zoals gezien in Campaign. Dit heeft alleen betrekking op de uitvoering in Campagne.<br /> </td> 
  </tr> 
 </tbody> 
</table>

Campagne **[!UICONTROL metrics]** gevonden in Analytics wordt hieronder vermeld:

<table> 
 <thead> 
  <tr> 
   <th> Metrisch<br /> </th> 
   <th> Definitie<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Geklikt<br /> </td> 
   <td> Het aantal keren dat op een inhoud is geklikt in een levering.<br /> </td> 
  </tr> 
  <tr> 
   <td> Geleverd<br /> </td> 
   <td> Het aantal berichten dat is verzonden in verhouding tot het totale aantal verzonden berichten.<br /> </td> 
  </tr> 
  <tr> 
   <td> Geopend<br /> </td> 
   <td> Aantal keren dat een bericht in een levering werd geopend.<br /> </td> 
  </tr> 
  <tr> 
   <td> Verzonden<br /> </td> 
   <td> Het totale aantal verzendt voor de levering.<br /> </td> 
  </tr> 
  <tr> 
   <td> Totaal Bounces<br /> </td> 
   <td> Totaal van fouten die tijdens levering en automatische terugkeerverwerking met betrekking tot het totale aantal verzonden berichten worden gecumuleerd.<br /> </td> 
  </tr> 
  <tr> 
   <td> Unieke open<br /> </td> 
   <td> Aantal ontvangers dat de levering heeft geopend.<br /> </td> 
  </tr> 
  <tr> 
   <td> Unieke klik<br /> </td> 
   <td> Aantal ontvangers die op een inhoud in een levering hebben geklikt.<br /> </td> 
  </tr> 
  <tr> 
   <td> Abonnement opgezegd<br /> </td> 
   <td> Aantal klikken op de verbinding van het unsubscription.<br /> </td> 
  </tr> 
 </tbody> 
</table>

