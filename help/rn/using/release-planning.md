---
title: Planning van Campaign Standard-releases
description: Deze pagina bevat een overzicht van de komende versies van Adobe Campaign Standard.
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
translation-type: ht
source-git-commit: b0c98e54893f1de5f378c74cec5182b1132ca995
workflow-type: ht
source-wordcount: '458'
ht-degree: 100%

---


# Releaseplanning {#release-planning}

Adobe-oplossingen worden voortdurend verbeterd door het toevoegen van nieuwe functies, verbeteringen en correcties.

Alle Adobe Campaign Standard-instanties worden geüpgraded met elke nieuwe release. Er is geen actie vereist om een upgrade uit te voeren.

Upgrades worden in twee fasen geïmplementeerd. Eerst worden Stage-instanties bijgewerkt zodat onze klanten nieuwe mogelijkheden kunnen testen en zo nodig hun configuratie kunnen aanpassen. Vervolgens worden productie-instanties bijgewerkt.

Alle releasedatums kunnen worden gewijzigd. We raden u aan deze pagina regelmatig te bezoeken om te kijken of er updates zijn.

**NIEUW!** Abonneer u op [Campaign Standard-releasemeldingen](http://amc-mkt-prod1-t.adobe-campaign.com/lp/LP25?service=%40rZ5cqp2DgNzrgz0alKPInakNbPSTeJYozZYnS7Wbs802u4GlISkHZX4omtK00nAU6xzZ6luEWQzr7kQ9pkCwJYumWkU) om details over aankomende releases rechtstreeks in uw inbox te krijgen.

## Release 20.4 - Release van oktober {#release-20-4-oct-release}

Updates vinden in golven plaats, tijdens de hieronder vermelde tijdschema&#39;s. Gedetailleerde informatie over deze release is te vinden in de [Release-opmerkingen](../../rn/using/release-notes.md). Neem contact op met [Adobe Client Care](https://helpx.adobe.com/nl/enterprise/using/support-for-experience-cloud.html) als u nog vragen hebt.

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
   <td>21-23 september 2020<br /> </td>
  </tr>
  <tr>
   <td> Productie<br /> </td>
   <td>28 september - 5 oktober 2020<br /> </td>
  </tr>
 </tbody>
</table>



## Vragen en antwoorden {#questions-and-answers}

**V: Wat is de impact?**

A: Wijzigingen worden vermeld in de [Release-opmerkingen](../../rn/using/release-notes.md), waaronder koppelingen naar gerelateerde documentatie. Adobe raadt ook aan de pagina [Verouderde en verwijderde functies](https://docs.adobe.com/content/help/nl-NL/campaign-standard/using/release-notes/deprecated-features.html) te raadplegen. Deze pagina&#39;s zijn op de upgradedatum van de Stage-omgeving beschikbaar voor de nieuwe release.

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
