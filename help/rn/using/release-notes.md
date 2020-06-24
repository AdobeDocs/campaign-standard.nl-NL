---
title: Laatste release
description: Deze pagina bevat een overzicht van alle recente releases van Adobe Campaign Standard.
page-status-flag: never-activated
uuid: 1cf2e40c-beca-43db-8261-a1820ee86ad3
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
discoiquuid: 5c7bfb74-4002-4ffe-87e8-bddb41d34b41
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c70d7172af12c2ccad0468f0afdba87bcf4ac839
workflow-type: tm+mt
source-wordcount: '1060'
ht-degree: 0%

---


# Laatste release{#latest-release}

[Release-planning](../../rn/using/release-planning.md) | [Release van het regelpaneel](https://docs.adobe.com/content/help/en/control-panel/using/release-notes.html) | [Documentatie-updates](../../rn/using/documentation-updates.md) | Opmerkingen bij de [vorige release](../../rn/using/release-notes-2020.md) | [Verouderde functies](../../rn/using/deprecated-features.md)

![](assets/do-not-localize/cp-icon.png) **Nieuwe release** van het Configuratiescherm in juni met controle van actieve profielen, controle van de leverbaarheid van subdomeinen en beheer van GPG-sleutels. Zie Opmerkingen bij de release van [het regelpaneel](https://docs.adobe.com/content/help/en/control-panel/using/release-notes.html).

## Release 20.3 - mei 2020 {#release-20-3---may-2020}

**Wat is nieuw?**

<table> 
<thead> 
<tr> 
<th> <strong>Thaise wet inzake de bescherming van persoonsgegevens (PDPA)</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>De Thaise wet inzake de bescherming van persoonsgegevens (PDPA) is de nieuwe privacywet die de vereisten inzake gegevensbescherming voor Thailand harmoniseert en moderniseert. Deze verordening is van toepassing op Adobe Campaign-klanten die gegevens bewaren voor gegevenssubjecten die in dit land verblijven.</p>
<p>Naast de privacy mogelijkheden reeds beschikbaar in Adobe Campaign (met inbegrip van toestemmingsbeheer, de montages van het gegevensbehoud, en gebruikersrollen), nemen wij deze kans aan om extra mogelijkheden te omvatten, helpen uw bereidheid voor PDPA vergemakkelijken:</p>
<ul>
<li>Recht op toegang en recht op verwijdering: wij benutten de capaciteiten die voor de GDPR en de CCPA zijn toegevoegd. <a href="https://helpx.adobe.com/content/help/en/campaign/kb/acs-privacy.html#righttoaccess">Meer informatie</a> </li>
<li><p>Wanneer het creëren van een verzoek van de Privacy, is het PDPA regelgevende type toegevoegd in de Dienst van de Kern van de Privacy. Dit is de methode u voor alle toegang en schrappingsverzoeken zou moeten gebruiken. Het gebruik van de campagne-API en -interface voor toegangs- en verwijderingsverzoeken is afgekeurd.  Zie het artikel <a href="../../rn/using/deprecated-features.md"></a>Vervangen en verwijderde functies.</p></li>
</ul>
<p>Raadpleeg de <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/privacy/privacy-overview.html">Hoe kan ik-video</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>Externe API-activiteit (GA)</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
  <td> <p>De <strong>externe API</strong> -activiteit verloopt van bèta naar GA. Deze release biedt extra flexibiliteit voor de parser van de JSON-responsstructuur. U kunt nu:</p>
<ul>
<li>parseer een geneste JSON met een maximale diepte van 10 niveaus. </li>
<li>Hiermee parseert u geselecteerde eigenschappen als bladknooppunten van een JSON en voegt u deze samen tot één tabelrij.</li>
<li>Selecteer en gebruik een matrixobject van een JSON zonder dat het object een naam moet geven aan de "gegevens" of op het hoofdniveau moet staan.</li>
</ul>
<p><strong>Let op:</strong> Klanten moeten in hun workflows alle API-activiteiten <strong>voor de bètaversie van External API</strong> vervangen door externe API-activiteiten voor GA.  Workflows die de bètaversie van de externe API gebruiken, werken niet meer in 20.3.</p>
<p>Raadpleeg voor meer informatie de <a href="../../automating/using/external-api.md">gedetailleerde documentatie</a> en de <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/managing-processes-and-data/data-management-activities/external-api-activity.html">Hoe kan ik-video</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

![](assets/do-not-localize/cp-icon.png) **Het nieuwe Controlebord kan met certificaatvernieuwing voor subdomeinen CNAME vrijgeven** . Zie Opmerkingen bij de release van [het regelpaneel](https://docs.adobe.com/content/help/en/control-panel/using/release-notes.html).

**Verbeteringen**

* Het aantal tekens dat in het veld **Voorvoegsel** kan worden gebruikt om berichten te [testen met behulp van doelprofielen](../../sending/using/testing-messages-using-target.md) , is verhoogd van 32 naar 500 tekens.
* Het maximumaantal real-time gebeurtenissen dat op een instantie kan worden gepubliceerd, is verhoogd van 350 tot 2000. (CAMP-41608)
* De synchronisatie tussen Adobe Launch en Campaign Standard is verbeterd dankzij de technische workflow syncWithLaunch. Met deze workflow kunt u alle mobiele eigenschappen van Adobe Launch automatisch importeren in Adobe Campaign Standard. Raadpleeg [deze pagina](../../administration/using/technical-workflows.md)voor meer informatie.

   U moet een ticket naar de klantenservice van Adobe verzenden (rechtstreeks of via uw Adobe-contactpersoon) om de technische workflow voor syncWithLaunch in uw Campagne-instantie te activeren. (CAMP-40082)

**Verbeteringen voor e-mailontwerper**

* De e-mailontwerper kan nu een flexibelere HTML-opmaak verwerken dan strikte W3C. (CAMP-42529)
* Probleem verholpen met [klikbare afbeeldingen](../../designing/using/links.md#inserting-a-link) om te voorkomen dat koppelingen naast de afbeelding in inhoudsblokken worden weergegeven. (CAMP-41586)
* Probleem verholpen waarbij de omleiding naar een bestemmingspagina niet mogelijk was wanneer een [bijgehouden URL](../../designing/using/links.md#about-tracked-urls) een categorie in de sjabloon had toegevoegd. (CAMP-41537)
* Probleem verholpen met opvulling van knoppen in Outlook.
* Probleem verholpen waarbij HTML-tags in onbewerkte tekst werden weergegeven.
* Bij zoeken in inhoudsblokken worden nu de zoekresultaten van de server en de vooraf geladen resultaten weergegeven. (CAMP-41870)

**Overige wijzigingen**

* De interface voor het publiceren van aangepaste bronnen is verbeterd met duidelijkere foutberichten.
* De ongebruikte leveringstoewijzingen zijn verwijderd uit de interface.
* De onnodige beheerderrollen zijn verwijderd uit de interface.
* Selectievakjes kunnen nu verplicht zijn op een bestemmingspagina.
* Tijdens het downloaden van het CSV-bestand van een Dynamic-rapport is de limiet van 200 rijen verwijderd. U kunt nu elke rij van uw rapport opnemen. (CAMP-40810)
* De ES-VS-taal is toegevoegd aan de lijst met talen die niet in de verpakking staan voor meertalige e-mails. (CAMP-42279)
* Bestanden die met een overdrachtsbestandsactiviteit zijn gedownload, worden nu na X dagen verwijderd, waarbij X wordt bepaald door de **Geschiedenis in het veld dagen** onder het menu **Uitvoering** in de Workfloweigenschappen. [Meer informatie](../../automating/using/managing-execution-options.md)

**Integratie van Experience Platforms**

* De activering van het publiek [van Adobe](../../automating/using/aep-targeting-audiences.md) Experience Platform vanuit de **Lees-doelactiviteit** is verbeterd en biedt nu betere prestaties en stabiliteit. Bovendien zijn workflowlogbestanden duidelijker en gedetailleerder geworden ten aanzien van activeringstaken, zodat gebruikers van Adobe Experience Platforms gemakkelijker kunnen worden gecontroleerd en probleemoplossing kunnen vinden bij het lezen van doelgroepen.

**Patches**

* Probleem verholpen waarbij een spookbron werd gemaakt tijdens de publicatietaak van een aangepaste bron.
* Probleem verholpen waarbij de marketinggeschiedenis van profielen niet kon worden weergegeven als de profielbron was uitgebreid met een aangepaste bron. (CAMP-41009)
* Probleem verholpen met out-of-the-box landingspagina-sjablonen die de inhoud in het Frans weergaven bij het openen van de editor. (CAMP-41639)
* Probleem verholpen in pushberichten met dynamische inhoud die kan voorkomen dat emojis wordt weergegeven. (CAMP-40715)
* Probleem verholpen in de **deduplicatie** -activiteit die ertoe kon leiden dat een onjuiste segmentcode werd toegewezen aan een van de uitgaande complement-overgangen. (CAMP-41400)
* Probleem verholpen waardoor geplande rapporten niet konden worden verwijderd. (CAMP-41302)
* Probleem opgelost waarbij een discrepantie optrad tussen het dashboard voor levering en het rapport **Afleveringsoverzicht** . (CAMP-41145)
* Probleem verholpen dat leidde tot een weergaveprobleem met tekenoverlapping in gedownloade rapporten.
* Probleem verholpen waardoor de voorvertoning van een levering niet kon werken voor vervanging van proefdrukken.
* Correctie van een fout bij het verwijderen van aangepaste velden van een lokale melding in de app.
* Probleem verholpen waardoor de charIndex-functie niet kon werken met een **End** - of **File-overdrachtactiviteit** in een workflow.
* Probleem verholpen in workflows die kunnen optreden wanneer een **verrijkingsactiviteit** wordt gebruikt met twee invoeractiviteiten, waaronder doelbronnen die er een koppeling tussen hebben. (CAMP-42133)
* Probleem verholpen waarbij een workflow niet kon worden uitgevoerd wanneer onbekende functies werden gebruikt. (CAMP-41873)
* Probleem verholpen in workflows die kunnen optreden wanneer een publiek wordt gemaakt met verschillende activiteiten voor **het opslaan van het publiek** als aanvulling op uitgaande overgangen. (CAMP-39992)
* Probleem verholpen dat tot gegevensdiscrepantie leidde bij het gebruik van personalisatie in transactie-e-mails. (CAMP-41842)
* Correctie van problemen die optraden bij het verwijderen van aangepaste velden in pushberichtleveringen. (CAMP-37586)
* Probleem verholpen waardoor gebruikers geen wijzigingen konden aanbrengen in rapporten. (CAMP-42505)
