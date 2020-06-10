---
title: Planning van standaardrelease
description: Deze pagina bevat een overzicht van de komende versies van Adobe Campagne Standard.
page-status-flag: never-activated
uuid: null
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: campaign-standard-release-planning
discoiquuid: null
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c7ed307e982e3fe41b2e3a7d0de7de356338bc08
workflow-type: tm+mt
source-wordcount: '458'
ht-degree: 0%

---


# Release-planning {#release-planning}

Adobe verbetert zijn oplossingen voortdurend door nieuwe mogelijkheden, verbeteringen en oplossingen toe te voegen.

Alle instanties van de Standaard van de Campagne van Adobe worden bevorderd met elke nieuwe versie. Er is geen actie vereist om een upgrade uit te voeren.

Upgrades worden in twee fasen geïmplementeerd. Eerst worden Stage-instanties bijgewerkt zodat onze klanten nieuwe mogelijkheden kunnen testen en zo nodig hun configuratie kunnen aanpassen. Productie-instanties worden vervolgens bijgewerkt.

Alle releasedatums kunnen worden gewijzigd: We raden u aan deze pagina regelmatig te bezoeken om te controleren op updates.

**NIEUW!** Meld u aan bij [de releasemeldingen](http://amc-mkt-prod1-t.adobe-campaign.com/lp/LP25?service=%40rZ5cqp2DgNzrgz0alKPInakNbPSTeJYozZYnS7Wbs802u4GlISkHZX4omtK00nAU6xzZ6luEWQzr7kQ9pkCwJYumWkU) voor Campagne Standard voor meer informatie over komende releases in uw Postvak IN.

## Release 20.4 - Release oktober {#release-20-4-oct-release}

De updates van het milieu gebeuren in golven, tijdens de vermelde hieronder termijnen. Gedetailleerde informatie over deze versie vindt u in de [releaseopmerkingen](../../rn/using/release-notes.md). Neem contact op met de [Adobe Client Care](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)als u nog vragen hebt.

<table>
 <thead>
  <tr>
   <th> Omgeving<br /> </th>
   <th> Datums<br /> </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td>Werkgebied<br /> </td>
   <td>21 sep. 22, 2020<br /> </td>
  </tr>
  <tr>
   <td> Productie<br /> </td>
   <td>28 sep. - 5 okt. 2020<br /> </td>
  </tr>
 </tbody>
</table>



## Vragen en antwoorden {#questions-and-answers}

**V: Wat is de impact?**

A: Wijzigingen worden vermeld in de [releaseopmerkingen](../../rn/using/release-notes.md), waaronder koppelingen naar gerelateerde documentatie. Adobe raadt ook aan de pagina [Afgekeurde en](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html)Verwijderde functies te raadplegen. Deze pagina&#39;s zijn beschikbaar voor de nieuwe versie op de de milieuverbeteringsdatum van het Stadium.

**V: Wat is het validatieproces?**

A: Naarmate de upgrade van uw testexemplaar wordt uitgevoerd, raadt Adobe u aan uw processen te valideren en de gebruiksgevallen correct met deze nieuwe versie werken en eventuele problemen aan de [Adobe Client Care](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)te melden.

**V: Zal er toegang tot de instantie tijdens het verbeteringsproces zijn?**

A: Nee. Tijdens de upgrade van de instantie is de database mogelijk niet gedurende een paar minuten toegankelijk. Alle processen worden automatisch opnieuw gestart.

**V: Zullen de berichten blijven worden verzonden?**

A: Nee. Berichten worden over een paar minuten niet verzonden. Zodra de upgrade is voltooid, worden de processen automatisch opnieuw gestart.

**V: Zullen de workflows blijven uitvoeren en de leveringen verzenden?**

A: Nee. Tijdens de bouwstijlverbetering, worden de werkschemaserver en MTA allebei tegengehouden. Dit betekent dat werkstromen niet worden uitgevoerd en dat de leveringen niet gedurende een paar minuten worden verzonden. Geen actie vereist: workflows worden opnieuw gestart zodra de instantie is bijgewerkt.

**V: Werkt het bijhouden van koppelingen in berichten nog tijdens de upgrade?**

A: Ja, ze zullen werken. Er kunnen geen nieuwe e-mailberichten worden verzonden tijdens de upgrade, maar de trackingkoppelingen in al verzonden e-mails zijn actief.

**V: Hoe weet ik dat de upgrade is voltooid?**

A: Wanneer het programma openen aan Campaign, zal popup van het versiebericht, met de recentste versie worden getoond.

Neem voor alle andere vragen contact op met de [klantenservice](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)van Adobe.
