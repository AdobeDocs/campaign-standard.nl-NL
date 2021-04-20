---
solution: Campaign Standard
product: campaign
title: Dimensies en metrische data van Campaign in Analytics
description: Leer de verschillende afmetingen die je in Adobe Analytics kunt vinden om je e-mailleveringen van Adobe Campaign bij te houden.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
feature: Triggers
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 3%

---


# Dimensies en metrische data van Campaign in Analytics{#campaign-dimensions-and-metrics-in-analytics}

Dankzij de integratie met Adobe Campaign en Adobe Analytics kunt u het succes van uw e-mailleveringen direct in Adobe Analytics volgen.

Campagne **[!UICONTROL dimensions]** gevonden in Analytics wordt hieronder vermeld:

<table> 
 <thead> 
  <tr> 
   <th> Dimension<br /> </th> 
   <th> Definition<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Campagne-id<br /> </td> 
   <td> Interne naam van campagne zoals gezien in Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> Campagnelabel<br /> </td> 
   <td> Label van campagne zoals weergegeven in campagne<br /> </td> 
  </tr> 
  <tr> 
   <td> Leverings-id<br /> </td> 
   <td> Interne naam van levering zoals weergegeven in Campagne.<br /> Bijvoorbeeld, is DM1 een terugkomende levering die wordt gepland om kindleveringen elke week te verzenden. DM2, DM3 en DM4 worden verzonden de eerste drie weken. De dimensie van identiteitskaart van de Levering zal dan de resultaten voor elke levering, namelijk DM1 aan DM4 tonen. <br /> </td> 
  </tr> 
  <tr> 
   <td> Leveringslabel<br /> </td> 
   <td> Label van levering zoals weergegeven in campagne<br /> </td> 
  </tr> 
  <tr> 
   <td> Uitvoerde leverings-id<br /> </td> 
   <td> Interne naam van levering zoals weergegeven in Campagne. Dit heeft alleen betrekking op de uitvoering in Campagne.<br /> Bijvoorbeeld, is DM1 een terugkomende levering die wordt gepland om kindleveringen elke week te verzenden. DM2, DM3 en DM4 worden verzonden de eerste drie weken. De uitgevoerde afmeting van leveringsidentiteitskaart zal dan de resultaten voor de uitgevoerde leveringen, namelijk de kindleveringen DM2, DM3 en DM4 tonen. <br /> </td> 
  </tr> 
  <tr> 
   <td> Uitvoerd leveringslabel<br /> </td> 
   <td> Het label van de levering zoals gezien in Campaign. Dit heeft alleen betrekking op levering in uitvoering in campagne.<br /> </td> 
  </tr> 
 </tbody> 
</table>

Campagne **[!UICONTROL metrics]** gevonden in Analytics wordt hieronder vermeld:

<table> 
 <thead> 
  <tr> 
   <th> Metrisch<br /> </th> 
   <th> Definition<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Klikken<br /> </td> 
   <td> Aantal keren dat op een inhoud is geklikt in een levering.<br /> </td> 
  </tr> 
  <tr> 
   <td> Afgeleverd<br /> </td> 
   <td> Aantal berichten dat is verzonden, in verhouding tot het totale aantal verzonden berichten.<br /> </td> 
  </tr> 
  <tr> 
   <td> Geopend<br /> </td> 
   <td> Aantal tijden een bericht in een levering werd geopend.<br /> </td> 
  </tr> 
  <tr> 
   <td> Verzonden<br /> </td> 
   <td> Het totale aantal verzendt voor de levering.<br /> </td> 
  </tr> 
  <tr> 
   <td> Totaal Bounces<br /> </td> 
   <td> Totaal van fouten gecumuleerd tijdens levering en automatische terugkeerverwerking met betrekking tot het totale aantal verzonden berichten.<br /> </td> 
  </tr> 
  <tr> 
   <td> Unieke open<br /> </td> 
   <td> Aantal ontvangers die de levering hebben geopend.<br /> </td> 
  </tr> 
  <tr> 
   <td> Unieke klik<br /> </td> 
   <td> Aantal ontvangers die op een inhoud in een levering klikte.<br /> </td> 
  </tr> 
  <tr> 
   <td> Afgemeld<br /> </td> 
   <td> Aantal klikken op de unsubscription verbinding.<br /> </td> 
  </tr> 
 </tbody> 
</table>

