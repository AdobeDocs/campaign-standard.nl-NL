---
title: Planning van Campaign Standard-releases
description: Deze pagina bevat een overzicht van de komende versies van Adobe Campaign Standard.
audience: rn
content-type: reference
topic-tags: campaign-standard-release-planning
feature: Overview
role: User
level: Beginner
exl-id: 1f48d4da-5622-4fab-af87-fcce0e40ade1
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 100%

---

# Releaseplanning {#release-planning}

Adobe-oplossingen worden voortdurend verbeterd door het toevoegen van nieuwe functies, verbeteringen en correcties.

Alle Adobe Campaign Standard-instanties worden geüpgraded met elke nieuwe release. Er is geen actie vereist om een upgrade uit te voeren.

Upgrades worden in twee fasen geïmplementeerd. Eerst worden Stage-instanties bijgewerkt zodat onze klanten nieuwe mogelijkheden kunnen testen en zo nodig hun configuratie kunnen aanpassen. Vervolgens worden productie-instanties bijgewerkt.

Alle releasedatums kunnen worden gewijzigd. We raden u aan deze pagina regelmatig te bezoeken om te kijken of er updates zijn.

## Release 21.3 - release van september 2021 {#release-21-3-release}

Omgevingsupdates vinden in golven plaats, tijdens de hieronder vermelde tijdschema&#39;s. De exacte datums worden per e-mail naar elke klant verzonden.

Gedetailleerde informatie over deze release is te vinden in de [Aanvullende informatie](../../rn/using/release-notes.md).

<table>
 <thead>
  <tr>
   <th> Omgeving<br /> </th>
   <th> Datums<br /> </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td>Stage<br /> </td>
   <td>7-8 september 2021<br /> </td>
  </tr>
  <tr>
   <td>Productie<br /> </td>
   <td>14-21 september 2021<br /> </td>
  </tr>
 </tbody>
</table>

Neem contact op met [Adobe Client Care](https://helpx.adobe.com/nl/enterprise/using/support-for-experience-cloud.html) als u nog vragen hebt.

## Vragen en antwoorden {#questions-and-answers}

**V: Wat is de impact?**

A: Wijzigingen worden vermeld in de [Release-opmerkingen](../../rn/using/release-notes.md), waaronder koppelingen naar gerelateerde documentatie. Adobe raadt ook aan de pagina [Verouderde en verwijderde functies](../../rn/using/deprecated-features.md) te raadplegen. Deze pagina&#39;s zijn op de upgradedatum van de Stage-omgeving beschikbaar voor de nieuwe release.

**V: Wat is het validatieproces?**

A: Als de upgrade van uw stage-instantie is uitgevoerd, raadt Adobe u aan te valideren of uw processen en gebruiksscenario&#39;s correct werken met deze nieuwe versie en om eventuele problemen aan [Adobe Client Care](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) te melden.

**V: Heb ik tijdens het upgradeproces toegang tot de instantie?**

A: Nee. Tijdens een upgrade van de database kan het zijn dat deze gedurende enkele minuten niet toegankelijk is. Alle processen worden automatisch opnieuw gestart.

**V: Worden de berichten nog steeds verstuurd?**

A: Nee. Berichten worden gedurende een paar minuten niet verzonden. Zodra de upgrade is voltooid, worden de processen automatisch opnieuw gestart.

**V: Blijven de workflows lopen en worden de leveringen verzonden?**

A: Nee. Tijdens de upgrade worden de workflowserver en MTA allebei onderbroken. Dit betekent dat workflows niet worden uitgevoerd en dat de leveringen gedurende een paar minuten niet worden verzonden. U hoeft niets te doen, de workflows worden opnieuw gestart zodra de instantie is bijgewerkt.

**V: Werkt de tracking van koppelingen in berichten nog tijdens de upgrade?**

A: Ja, deze blijven werken. Er kunnen geen nieuwe e-mailberichten worden verzonden tijdens de upgrade, maar het bijhouden van koppelingen in reeds verzonden e-mails blijft werken

**V: Hoe weet ik dat de upgrade is voltooid?**

A: Bij het inloggen bij Campaign wordt een pop-upmelding met de laatste versie weergegeven.

Neem voor alle andere vragen contact op met [Adobe Client Care](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html).
