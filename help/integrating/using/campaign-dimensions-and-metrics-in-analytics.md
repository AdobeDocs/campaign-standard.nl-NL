---
title: Dimensies en metrische gegevens van Campaign in Analytics
description: Leer de verschillende afmetingen die je in Adobe Analytics kunt vinden om je e-mailleveringen van Adobe Campaign bij te houden.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
feature: Triggers
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 6516c71a-efa8-4778-82bb-10615378f985
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 3%

---

# Dimensies en metrische gegevens van Campaign in Analytics{#campaign-dimensions-and-metrics-in-analytics}

Dankzij de integratie met Adobe Campaign en Adobe Analytics kunt u het succes van uw e-mailleveringen direct in Adobe Analytics volgen.

Campagne **[!UICONTROL dimensions]** in Analytics wordt hieronder weergegeven:

<table> 
 <thead> 
  <tr> 
   <th> Dimension<br /> </th> 
   <th> Definition<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Campagne-id <br /> </td> 
   <td> De interne naam van de campagne zoals gezien in Campagne <br /> </td> 
  </tr> 
  <tr> 
   <td> Campagnelabel <br /> </td> 
   <td> Het etiket van de campagne zoals gezien in Campagne <br /> </td> 
  </tr> 
  <tr> 
   <td> Leverings-id <br /> </td> 
   <td> Interne naam van levering zoals weergegeven in Campagne.<br /> DM1 is bijvoorbeeld een terugkerende levering die is gepland om elke week onderliggende leveringen te verzenden. DM2, DM3 en DM4 worden verzonden de eerste drie weken. De dimensie van identiteitskaart van de Levering zal dan de resultaten voor elke levering, namelijk DM1 aan DM4 tonen. <br /> </td> 
  </tr> 
  <tr> 
   <td> Leveringslabel <br /> </td> 
   <td> Het etiket van de levering zoals gezien in Campagne <br /> </td> 
  </tr> 
  <tr> 
   <td> Uitvoerde leverings-id <br /> </td> 
   <td> Interne naam van levering zoals weergegeven in Campagne. Dit heeft alleen betrekking op de uitvoering in Campagne.<br /> DM1 is bijvoorbeeld een terugkerende levering die is gepland om elke week onderliggende leveringen te verzenden. DM2, DM3 en DM4 worden verzonden de eerste drie weken. De uitgevoerde afmeting van leveringsidentiteitskaart zal dan de resultaten voor de uitgevoerde leveringen, namelijk de kindleveringen DM2, DM3 en DM4 tonen. <br /> </td> 
  </tr> 
  <tr> 
   <td> Uitvoerd leveringslabel <br /> </td> 
   <td> Het label van de levering zoals gezien in Campaign. Dit heeft slechts betrekking op levering in uitvoering in Campagne.<br /> </td> 
  </tr> 
 </tbody> 
</table>

Campagne **[!UICONTROL metrics]** in Analytics wordt hieronder weergegeven:

<table> 
 <thead> 
  <tr> 
   <th> Metrisch <br /> </th> 
   <th> Definition<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Klikt <br /> </td> 
   <td> Aantal tijden een inhoud in een levering werd geklikt.<br /> </td> 
  </tr> 
  <tr> 
   <td> Geleverd <br /> </td> 
   <td> Aantal met succes verzonden berichten, met betrekking tot het totale aantal verzonden berichten.<br /> </td> 
  </tr> 
  <tr> 
   <td> Geopend <br /> </td> 
   <td> Aantal tijden een bericht in een levering werd geopend.<br /> </td> 
  </tr> 
  <tr> 
   <td> Verzonden<br /> </td> 
   <td> Het totale aantal verzendt voor de levering.<br /> </td> 
  </tr> 
  <tr> 
   <td> Totaal Bounces <br /> </td> 
   <td> Totaal van fouten die tijdens levering en automatische terugkeerverwerking met betrekking tot het totale aantal verzonden berichten worden gecumuleerd.<br /> </td> 
  </tr> 
  <tr> 
   <td> Unieke open <br /> </td> 
   <td> Aantal ontvangers die de levering opende.<br /> </td> 
  </tr> 
  <tr> 
   <td> Unieke klik <br /> </td> 
   <td> Aantal ontvangers die op een inhoud in een levering klikte.<br /> </td> 
  </tr> 
  <tr> 
   <td> Unsubscribed <br /> </td> 
   <td> Aantal klikken op de unsubscription verbinding.<br /> </td> 
  </tr> 
 </tbody> 
</table>
