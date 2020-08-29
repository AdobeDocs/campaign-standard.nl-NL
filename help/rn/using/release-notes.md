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
source-git-commit: f45985c030c3d5059bfef444287c10b842298f49
workflow-type: tm+mt
source-wordcount: '1160'
ht-degree: 90%

---


# Laatste release{#latest-release}

[Releaseplanning](../../rn/using/release-planning.md) | [Releases van het Configuratiescherm](https://docs.adobe.com/content/help/nl-NL/control-panel/using/release-notes.html) | [Updates van documentatie](../../rn/using/documentation-updates.md) | [Opmerkingen bij eerdere releases](../../rn/using/release-notes-2020.md) | [Verouderde functies](../../rn/using/deprecated-features.md)

![](assets/do-not-localize/cp-icon.png) **Release van nieuw configuratiescherm in juni** met controle van actieve profielen, controle van de leverbaarheid van subdomeinen en beheer van GPG-sleutels. [Meer informatie](https://docs.adobe.com/content/help/nl-NL/control-panel/using/release-notes.html).

## Release 20.3 - Mei 2020 {#release-20-3---may-2020}

**Nieuwe functies**

<table> 
<thead> 
<tr> 
<th> <strong>Thaise wetgeving inzake de bescherming van persoonsgegevens (PDPA)</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>De Thaise wet inzake de bescherming van persoonsgegevens (PDPA) is de nieuwe privacywet die de vereisten inzake databescherming voor Thailand harmoniseert en moderniseert. Deze verordening is van toepassing op Adobe Campaign-klanten die data beheren voor 'datasubjecten' die inwoner zijn van Thailand.</p>
<p>Naast de privacyopties die al beschikbaar zijn in Adobe Campaign (met inbegrip van toestemmingsbeheer, instellingen voor databehoud en gebruikersrollen), gebruiken we deze gelegenheid om extra functies op te nemen, zodat de gereedheid voor PDPA voor u als klant nog makkelijker wordt:</p>
<ul>
<li>Recht op toegang en recht op verwijdering: we maken gebruik van de functies die voor de AVG (GDPR) en CCPA zijn toegevoegd. <a href="https://helpx.adobe.com/content/help/nl/campaign/kb/acs-privacy.html#righttoaccess">Meer informatie</a> </li>
<li><p>Als u een verzoek om toegang tot persoonsgegevens wilt maken, is het PDPA-wetgevingstype toegevoegd in de Privacy-kernservice. Dit is de enige methode die u moet gebruiken voor alle verzoeken voor toegang en verwijderen. Het gebruik van de Campaign-API en -interface voor toegangs- en verwijderingsverzoeken is verouderd. Zie het artikel <a href="../../rn/using/deprecated-features.md">Vervangen en verwijderde functies</a>.</p></li>
</ul>
<p>Bekijk ook de <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/privacy/privacy-overview.html">Hoe kan ik-video</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>External API-activiteit (GA)</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
  <td> <p>De activiteit <strong>External API</strong> gaat van bèta naar GA. Deze release biedt extra flexibiliteit voor de parser van de JSON-responsstructuur. U kunt nu het volgende:</p>
<ul>
<li>Een geneste JSON met een maximale diepte van 10 niveaus parseren. </li>
<li>Een selectie van eigenschappen parseren als leaf-nodes van een JSON en deze in één tabelrij weergeven.</li>
<li>Een array-object van een JSON selecteren zonder de objectdata te benoemen, en zonder dat deze data op het hoogste niveau moeten staan.</li>
</ul>
<p><strong>Let op:</strong> Klanten moeten <strong>alle External API-activiteiten van de bètaversie in hun workflows vervangen door</strong> External API-activiteiten van de GA-versie. Workflows die de bètaversie van de External API gebruiken, werken niet meer in 20.3.</p>
<p>Raadpleeg voor meer informatie de <a href="../../automating/using/external-api.md">gedetailleerde documentatie</a> en de <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/managing-processes-and-data/data-management-activities/external-api-activity.html">Hoe kan ik-video</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

**Aanvullende capaciteiten** (vanaf 13 juli)

* **Dankzij de AI-technologie kunt u tijd optimaliseren en profielen scoren** . U kunt nu het ontwerp en de levering van klantritten optimaliseren om de voorkeur van elk individu voor de service te voorspellen. Adobe Campaign wordt aangedreven door Journey AI en kan de open tarieven, optimale verzendtijden en waarschijnlijke kosten analyseren en voorspellen op basis van historische betrokkenheidsmaatstaven. [Meer informatie](../../sending/using/predictive.md)
* **De nieuwe privacyverordening** van Brazilië - Naast de privacy-mogelijkheden die al beschikbaar zijn in Campaign, helpt Adobe u uw bereidheid voor de Lei Geral de Proteçao de Datos (LGPD) van Brazilië te vergemakkelijken. Bij het maken van een privacyverzoek is de LGPD-verordening toegevoegd aan de Adobe Privacy Core Service. [Meer informatie](https://helpx.adobe.com/nl/campaign/kb/campaign-privacy-overview.html)

**Verbeteringen**

* Het aantal tekens dat in het veld **Prefix** kan worden gebruikt om [berichten te testen met behulp van doelprofielen](../../sending/using/testing-messages-using-target.md), is verhoogd van 32 naar 500 tekens.
* Het maximale aantal real-time gebeurtenissen dat op een instantie kan worden gepubliceerd, is verhoogd van 350 naar 2000. (CAMP-41608)
* De synchronisatie tussen Adobe Launch en Campaign Standard is verbeterd dankzij de technische workflow SyncWithLaunch. Met deze workflow kunt u alle mobiele eigenschappen van Adobe Launch automatisch importeren in Adobe Campaign Standard. Raadpleeg [deze sectie](../../administration/using/technical-workflows.md) voor meer informatie.

   U moet een ticket indienen bij de klantenservice van Adobe (rechtstreeks of via uw Adobe-contactpersoon) om de technische workflow syncWithLaunch in uw Campaign-instantie te activeren. (CAMP-40082)

**Verbeteringen voor de Email Designer**

* De Email Designer verwerkt nu een flexibelere HTML-indeling dan strikte W3C. (CAMP-42529)
* Probleem verholpen met [klikbare afbeeldingen](../../designing/using/links.md#inserting-a-link) om te voorkomen dat koppelingen naast de afbeelding in contentblokken worden weergegeven. (CAMP-41586)
* Probleem verholpen waarbij het doorsturen naar een landingspagina niet mogelijk is wanneer een categorie voor de [gevolgde URL](../../designing/using/links.md#about-tracked-urls) is toegevoegd in de sjabloon. (CAMP-41537)
* Probleem verholpen met opvulling van knoppen in Outlook.
* Probleem verholpen waarbij HTML-tags in onbewerkte tekst worden weergegeven.
* Bij zoeken in contentblokken worden nu zowel de zoekresultaten van de server als de vooraf geladen resultaten weergegeven. (CAMP-41870)

**Overige wijzigingen**

* De interface voor het publiceren van aangepaste bronnen is verbeterd met duidelijkere foutberichten.
* Ongebruikte leveringstoewijzingen zijn verwijderd uit de interface.
* Onnodige beheerderrollen zijn verwijderd uit de interface.
* Selectievakjes op een landingspagina kunnen nu verplicht zijn.
* Bij het downloaden van het CSV-bestand van een Dynamic-rapport is de limiet van 200 rijen verwijderd. U kunt nu elke rij van uw rapport opnemen. (CAMP-40810)
* De taal ES-VS is toegevoegd aan de lijst met kant-en-klare talen voor meertalige e-mails. (CAMP-42279)
* Bestanden die met de activiteit Transfer File voor bestandsoverdracht zijn gedownload, worden nu na X dagen verwijderd. Het aantal dagen (X) wordt bepaald door het veld **History in days** in het menu **Execution** in de workfloweigenschappen. [Meer informatie](../../automating/using/managing-execution-options.md)

**Experience Platform-integraties**

* De activering van [Adobe Experience Platform-doelgroepen](../../automating/using/aep-targeting-audiences.md) van de activiteit **Read audience** verloopt nu beter en stabieler. Bovendien zijn de logbestanden van workflows nu overzichtelijker en gedetailleerder ten aanzien van activeringstaken, met als resultaat eenvoudigere monitoring en probleemoplossing bij het lezen van Adobe Experience Platform-doelgroepen.

**Patches**

* Probleem verholpen waarbij een ghostbron werd gemaakt tijdens de publicatietaak van een aangepaste bron.
* Probleem verholpen waarbij de marketinghistorie van profielen niet kon worden weergegeven als de profielbron was uitgebreid met een aangepaste bron. (CAMP-41009)
* Probleem verholpen met kant-en-klare sjablonen voor de landingspagina die Franse tekst bevatten bij het openen van de editor. (CAMP-41639)
* Probleem in pushberichten met dynamische content verholpen waardoor emoji&#39;s niet werden weergegeven. (CAMP-40715)
* Probleem verholpen voor de activiteit **Deduplication** dat ertoe kon leiden dat een onjuiste segmentcode werd toegewezen aan een van de uitgaande complement-overgangen. (CAMP-41400)
* Probleem verholpen waardoor geplande rapporten niet konden worden verwijderd. (CAMP-41302)
* Probleem opgelost waarbij een discrepantie optrad tussen het dashboard voor levering en het rapport **Delivery Summary**. (CAMP-41145)
* Probleem verholpen dat leidde tot de overlapping van tekens in gedownloade rapporten.
* Probleem verholpen waardoor de voorvertoning van een levering niet kon werken bij het vervangen van proefversies.
* Correctie van een fout bij het verwijderen van aangepaste velden van een lokaal in-app-bericht.
* Probleem verholpen waardoor de charIndex-functie niet kon werken met een **End**- of **File transfer**-activiteit in een workflow.
* Probleem verholpen in workflows die kon optreden bij het gebruik van een **Enrichtment**-activiteit met twee invoeractiviteiten en targetbronnen die zijn gekoppeld. (CAMP-42133)
* Probleem verholpen waarbij een workflow niet kon worden uitgevoerd wanneer onbekende functies werden gebruikt. (CAMP-41873)
* Probleem verholpen in workflows die kon optreden bij het maken van doelgroepen met gebruik van meerdere **Save audience**-activiteiten met aanvullende uitgaande overgangen. (CAMP-39992)
* Probleem verholpen dat tot datadiscrepantie leidde bij het gebruik van personalisatie in transactie-e-mails. (CAMP-41842)
* Correctie van problemen die optraden bij het verwijderen van aangepaste velden in pushberichtleveringen. (CAMP-37586)
* Probleem verholpen waardoor gebruikers geen wijzigingen konden aanbrengen in rapporten. (CAMP-42505)


![](assets/do-not-localize/cp-icon.png) **Het nieuwe Controlebord kan met certificaatvernieuwing voor subdomeinen CNAME vrijgeven** . [Meer informatie](https://docs.adobe.com/content/help/nl-NL/control-panel/using/release-notes.translate.html).
