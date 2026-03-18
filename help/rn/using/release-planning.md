---
title: Campaign Standard Release Planning
description: Deze pagina bevat een overzicht van komende releases van Adobe Campaign Standard.
audience: rn
content-type: reference
topic-tags: campaign-standard-release-planning
feature: Overview
role: User
level: Beginner
exl-id: 1f48d4da-5622-4fab-af87-fcce0e40ade1
source-git-commit: 035fa1ab4703d5511bdd1bbdbf2585f893b9d787
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 0%

---

# Release-planning {#release-planning}

Adobe verbetert zijn oplossingen voortdurend door nieuwe mogelijkheden, verbeteringen en oplossingen toe te voegen.

Alle Adobe Campaign Standard-instanties worden geüpgraded met elke nieuwe release. Er is geen actie vereist om een upgrade uit te voeren.

Upgrades worden in twee fasen geïmplementeerd. Eerst worden Stage-instanties bijgewerkt, zodat u nieuwe mogelijkheden kunt testen en zo nodig uw configuratie kunt aanpassen. Productie-instanties worden vervolgens bijgewerkt.

Alle releasedatums kunnen worden gewijzigd: ga regelmatig naar deze pagina om te controleren op updates. De updates van het milieu gebeuren in golven, tijdens de vermelde hieronder termijnen. Exacte datums worden per e-mail naar elke klant verzonden.

## Release 26.3 {#release-26-3-release}

De gedetailleerde informatie over deze versie is beschikbaar in de [&#x200B; Nota&#39;s van de Versie &#x200B;](release-notes.md) wanneer het milieu van het Stadium begint.

<table>
 <thead>
  <tr>
   <th> Omgevingen </th>
   <th> Datums</th>
   <!--th> General Availability </th-->
  </tr>
 </thead>
 <tbody>
  <tr>
   <td>Werkgebied </td>
   <td>augustus </td>
   <!--td>2025 - Dates to be confirmed</td-->
  </tr>
  <tr>
   <td>Productie </td>
   <td>september </td>
   <!--td>2025 - Dates to be confirmed</td-->
  </tr>
 </tbody>
</table>

## Vragen en antwoorden {#questions-and-answers}

**Q: Wat is het effect?**

A: De veranderingen zijn vermeld in de [&#x200B; Nota&#39;s van de Versie &#x200B;](../../rn/using/release-notes.md), met inbegrip van verbindingen aan verwante documentatie. Adobe adviseert ook om [&#x200B; Vervangen en Verwijderde pagina van Eigenschappen &#x200B;](../../rn/using/deprecated-features.md) te raadplegen. Deze pagina&#39;s zijn beschikbaar voor de nieuwe versie op de de milieuverbeteringsdatum van het Stadium.

**Q: Wat is het bevestigingsproces?**

A: Aangezien uw het opvoeren instantie wordt bevorderd, adviseert Adobe om uw processen te bevestigen en gebruiksgevallen behoorlijk met deze nieuwe versie werken, en om het even welk probleem aan [&#x200B; de Zorg van de Cliënt van Adobe te melden &#x200B;](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html).

**Q: Zal er toegang tot de instantie tijdens het verbeteringsproces zijn?**

A: Nee. Tijdens de upgrade van de instantie is de database mogelijk niet gedurende een paar minuten toegankelijk. Alle processen worden automatisch opnieuw gestart.

**Q: Zal de berichten blijven worden verzonden?**

A: Nee. Berichten worden over een paar minuten niet verzonden. Wanneer de upgrade is voltooid, worden de processen automatisch opnieuw gestart.

**Q: Zal de werkschema&#39;s blijven in werking stellen en de leveringen verzenden?**

A: Nee. Tijdens bouwstijlverbetering, werkschemaserver en MTA allebei tegengehouden. Dit heeft tot gevolg dat workflows niet worden uitgevoerd en dat leveringen niet gedurende een paar minuten worden verzonden. Er is geen actie vereist: de workflows worden opnieuw gestart zodra de upgrade van de instantie wordt uitgevoerd.

**Q: Zal het volgen van verbindingen in berichten nog tijdens de verbetering werken?**

A: Ja, ze zullen werken. Er kunnen geen nieuwe e-mailberichten worden verzonden tijdens de upgrade, maar de trackingkoppelingen in al verzonden e-mails zijn actief.

**Q: Hoe weet ik dat de verbetering wordt voltooid?**

A: Wanneer het programma openen aan Campaign, zal popup van het versiebericht, met de recentste versie worden getoond.

Voor andere vragen, contacteer [&#x200B; de Zorg van de Cliënt van Adobe &#x200B;](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html).
