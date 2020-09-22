---
title: Opmerkingen bij de releases in 2020
description: Deze pagina bevat een overzicht van alle releases van Adobe Campaign Standard in 2020.
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
source-git-commit: 0b82a9dc86ec9e48e25f1ffe53188ba916a9d074
workflow-type: tm+mt
source-wordcount: '2951'
ht-degree: 95%

---


# Opmerkingen bij de releases in 2020{#release-notes-2020}

[Releaseplanning](https://docs.adobe.com/content/help/nl-NL/campaign-standard/using/release-notes/release-planning.html) | [Releases van het Configuratiescherm](https://docs.adobe.com/content/help/nl-NL/control-panel/using/release-notes.html) | [Updates van documentatie](../../rn/using/documentation-updates.md) | [Opmerkingen bij eerdere releases](../../rn/using/release-notes-2019.md) | [Verouderde functies](https://docs.adobe.com/content/help/nl-NL/campaign-standard/using/release-notes/deprecated-features.html)

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


![](assets/do-not-localize/cp-icon.png) **Het nieuwe Controlebord kan met certificaatvernieuwing voor subdomeinen CNAME vrijgeven** . [Meer informatie](https://docs.adobe.com/content/help/nl-NL/control-panel/using/release-notes.html).

## Release 20.2 - april 2020 {#release-20-2---april-2020}

**Nieuwe functies**

<table> 
 <thead> 
  <tr> 
   <th> <strong>Azure Blob-integratie</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>De Azure Blob Storage-connector kan nu worden gebruikt voor het importeren of exporteren van data naar Adobe Campaign met behulp van een workflowactiviteit <strong>Bestandsoverdracht</strong>. </p>
    <p>Raadpleeg de <a href="../../administration/using/external-accounts.md#microsoft-azure-external-account">gedetailleerde documentatie</a> voor meer informatie.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>E-mails testen met doelprofielen</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Naast testprofielen kunt u nu uw e-mails testen op echte doelprofielen. Zo krijgt u een exacte weergave van het bericht dat het profiel ontvangt: aangepaste velden, dynamische en gepersonaliseerde informatie, inclusief aanvullende data van workflows, enz. </p>
    <p>Raadpleeg de <a href="../../sending/using/testing-messages-using-target.md">gedetailleerde documentatie</a> en de <a href="https://docs.adobe.com/content/help/nl/campaign-standard-learn/tutorials/communication-channels/email/profile-substitution.html">videotutorial</a>voor meer informatie. </p>
   </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Nieuwe mogelijkheden worden in april beschikbaar gesteld in het Configuratiescherm van Campaign, waaronder Google TXT-recordbeheer, bewaking van de databaseruimte en e-mailwaarschuwingen. Raadpleeg de [Opmerking bij de release van het Configuratiescherm](https://docs.adobe.com/content/help/nl-NL/control-panel/using/release-notes.html) voor meer informatie over deze functies.

**Verbeteringen**

* De gebruikerservaring met transactionele berichten is uitgebreid en de interfaceconsistentie is verbeterd. [Meer informatie](../../channels/using/getting-started-with-transactional-msg.md)
* U kunt nu in Campaign Standard proeven naar testprofielen verzenden met behulp van aanvullende data uit workflows.
* Beveiligingen voor de activiteit Externe API zijn bijgewerkt. [Meer informatie](../../automating/using/external-api.md)

**Verbeteringen voor de Email Designer**

* Probleem verholpen dat invloed had op escape-tekens wanneer meerdere keren op een gepersonaliseerde afbeelding werd geklikt.
* Probleem verholpen bij het dupliceren van dynamische tekstcomponenten waarbij de verkeerde regel werd gedupliceerd. (CAMP-41249)
* Probleem met opvulling in Outlook verholpen bij het definiëren van opvulling op tabelniveau in plaats van op div-niveau.
* Probleem verholpen waarbij de breedte van een afbeelding werd gewijzigd wanneer naar de HTML-modus werd overgeschakeld. (CAMP-41116)
* Probleem verholpen waarbij de sociale-mediacomponent niet toegankelijk was wanneer alternatieve tekst voor de pictogrammen werd opgegeven. (CAMP-41345)
* Probleem verholpen waarbij zichtbare `<br>`-tags werden weergegeven bij gebruik van kopiëren en plakken in de Email Designer.
* Probleem verholpen waarbij HTML-tags in de e-mail werden weergegeven nadat er van HTML-content naar tekst zonder opmaak werd overgeschakeld. (CAMP-41138)
* Probleem verholpen waarbij het weergeven van knoppen met slechts één gedefinieerde rand werd voorkomen.
* Probleem verholpen in HTML-inspringing waardoor de voettekst van e-mails in Microsoft Outlook naar links werd verplaatst. (CAMP-40987)
* Probleem verholpen waarbij personalisatievelden die verwijzen naar een verzamelingskenmerk dat is gedefinieerd in HTML, in de normale tekstcontent werden gekopieerd wanneer naar de modus voor tekst zonder opmaak werd geschakeld. (CAMP-40365)
* Probleem verholpen waarbij werd voorkomen dat koppelingen werden ingevoegd op een tekstsegment dat is geselecteerd. (CAMP-41406)
* Probleem verholpen waarbij de datum werd gewijzigd wanneer een tijdzone werd geselecteerd in de query-editor. (CAMP-38277)

**Overige wijzigingen**

* De kant-en-klare workflow voor **KPI-afstemming met Adobe Analytics** loopt nu tot de huidige datum in plaats van één dag.
* De MCPNS biedt geen ondersteuning voor het toevoegen van zowel APNS als APNS-SANDBOX als platforms in een app. Nadat u het certificaat hebt toegevoegd in Adobe Campaign Standard, kunt u de instellingen nu niet meer terugzetten omdat er slechts één APNS-platform (productie of sandbox) aan de MCPNS-app kan worden toegevoegd.

**Experience Platform-integraties**

>[!NOTE]
>
>De functies van het Adobe Experience Platform in de Campaign Standard worden momenteel in bèta weergegeven en kunnen vaak en zonder kennisgeving worden bijgewerkt. Raadpleeg de gedetailleerde documentatie: [Experience Platform-gegevensconnector](../../developing/using/aep-about-data-connector.md), [Audience Destinations](../../audiences/using/aep-about-audience-destinations-service.md)

* In workflowlogboeken wordt om de 10 minuten het aantal records weergegeven dat al is verwerkt door de taak die momenteel wordt uitgevoerd in Campaign.
* Probleem verholpen dat kon optreden bij het importeren van een Adobe Experience Platform-profiel dat uit de database was verwijderd.
* Probleem verholpen in workflowlogboeken waarbij een onjuist resultaat kon worden weergegeven voor het totale aantal geïmporteerde records.

**Patches**

* Probleem verholpen met de workflowactiviteit **Verrijking** dat kon optreden wanneer spaties werden toegevoegd in het veld **Alias** en waarbij vervolgens een nieuw rij-item werd gemaakt. (CAMP-39229)
* Probleem verholpen waarbij elk testprofiel als doel kon worden ingesteld bij het verzenden van een proefbericht.
* Probleem verholpen dat optrad na het ongedaan maken van de publicatie van een gebeurtenisconfiguratie en het verwijderen ervan. [Meer informatie](../../administration/using/configuring-transactional-messaging.md#deleting-an-event)
* Probleem verholpen waarbij de knop **Opslaan** verdween bij het aanbrengen van wijzigingen in workflows.
* Probleem verholpen bij het handmatig verwijderen van een privacyaanvraag in Campaign nadat deze was verwerkt. Hierdoor konden data die aan de aanvraag waren gekoppeld, niet worden verwijderd, zelfs niet na opschoning.
* Probleem verholpen dat kon optreden tijdens het voorvertonen of verzenden van berichten met speciale tekens uit Adobe Experience Manager.
* Probleem verholpen dat in workflows kon voorkomen wanneer een activiteit met verschillende binnenkomende overgangen werd uitgevoerd.
* Probleem verholpen waarbij standaardgebruikers de abonnementen op een applicatie niet konden gebruiken als de doeldimensie in een workflowquery of een levering. (CAMP-37618)

## Release 20.1.4 - februari 2020 {#release-20-1-4---february-2020}

* Probleem verholpen bij het openen van een activiteit **Doelgroep lezen** voor bestaande workflows. (CAMP-41002)

## Release 20.1.3 - februari 2020 {#release-20-1-3---february-2020}

* Probleem met regressie verholpen dat in 20.1 door CAMP-39273 werd geïntroduceerd voor klanten die de loophole gebruikten. CAMP-39273 werd teruggedraaid.

## Release 20.1.2 - februari 2020 {#release-20-1-2---february-2020}

**Verbeteringen voor de Email Designer**

* Probleem verholpen waarbij een HTML-code-element in een verouderd fragment werd toegevoegd bij het toevoegen van patches aan het element en het opslaan van de content. (CAMP-40685)
* Probleem verholpen waarbij een spatie werd toegevoegd bij het gebruik van dynamische content. (CAMP-40605)
* Probleem verholpen bij het configureren van een transactionele e-mailsjabloon. (CAMP-40604)

## Release 20.1 - februari 2020 {#release-20-1---february-2020}

**Nieuwe functies**


<table> 
 <thead> 
  <tr> 
   <th> <strong>Adobe Experience Platform-gegevensconnector (bèta)</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>De Adobe Experience Platform-gegevensconnector is nu geïntegreerd met Adobe Campaign Standard. U kunt uw Campaign-data ter beschikking stellen op het Adobe Experience Platform door de XTK-data (data die in Campaign worden opgenomen) toe te wijzen aan het Adobe Experience Platform-gegevensmodel (XDM). </p>
    <p>Deze mogelijkheid is alleen beschikbaar voor klanten die in Azure worden gehost. Raadpleeg de <a href="../../developing/using/aep-about-data-connector.md">gedetailleerde documentatie</a> en de <a href="https://docs.adobe.com/content/help/nl/campaign-learn/campaign-standard-tutorials/administrating/adobe-experience-platform-data-connector/understanding-the-adobe-experience-platform-data-connector.html">video met instructies</a> voor meer informatie over deze mogelijkheid en de voorwaarden om deze te activeren.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Audience Destinations (bèta) </strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Met Audience Destinations kunt u segmenten van het Adobe Experience Platform delen met Adobe Campaign.</p>
    <p>Deze mogelijkheid is alleen beschikbaar voor klanten die in Azure worden gehost. Raadpleeg de <a href="../../audiences/using/aep-about-audience-destinations-service.md">gedetailleerde documentatie</a> en de <a href="https://docs.adobe.com/content/help/nl/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.html">video met instructies</a> voor meer informatie over deze mogelijkheid en de voorwaarden om deze te activeren. </p>
   </td> 
  </tr> 
 </tbody> 
</table>

**Verbeteringen**

* Algemene beschikbaarheid van de verbeterde MTA: berichten (inclusief transactionele berichten) worden nu verzonden door de Adobe Campaign Enhanced MTA, die een geüpgrade verzendinfrastructuur biedt die verbeterde leverbaarheid, doorvoer en afhandeling van niet-bezorgde berichten mogelijk maakt. [Meer informatie](https://helpx.adobe.com/campaign/kb/campaign-enhanced-mta.html)

* Tijdzonebeheer is verbeterd. U kunt nu een [specifieke tijdzone](../../automating/using/building-a-workflow.md) definiëren voor een volledige workflow. De geselecteerde tijdzone is van toepassing op alle activiteiten van de workflow. De informatie over de tijdzone die voor de operator of de server is geconfigureerd, wordt nu weergegeven in de interface (in logboeken, en na het selecteren van een tijdzone). (CAMP-37672)

* Met Campaign Standard-API&#39;s kunt u nu paginering uitvoeren bij het gebruik van grote tabellen, door de parameter `_forcePagination=true` aan uw aanroep-URL toe te voegen. [Meer informatie](../../api/using/pagination.md)

* De id van het leveringslogboek (een unieke identificatie voor elk logboek) is nu beschikbaar in de resources Leveringslogboeken en Trackinglogboeken voor alle targetingdimensies. Hierdoor kunnen verzend- of trackinglogboeken bijvoorbeeld tijdens het exporteren worden geïdentificeerd. [Meer informatie](../../automating/using/exporting-logs.md)

**Verbeteringen voor de Email Designer**

* Ontbrekende verplichte tekstinstructies toegevoegd bij het maken van een doelgroep.
* Probleem verholpen bij het klikken op de knop **Change content** in de wizard van de verouderde e-maileditor.
* Probleem verholpen waarbij kopteksten niet konden worden uitgelijnd met de content in het rapport Service Summary. (CAMP-38103)
* Probleem verholpen waardoor dynamische contentvarianten niet konden worden verwijderd zonder dat dit een impact had op de rest van de onderwerpregel. (CAMP-40096)
* Probleem met A/B-tests verholpen bij gebruik van de B-variant op de onderwerpregel. (CAMP-40327)
* Probleem verholpen waarbij bestanden niet konden worden gesleept en neergezet wanneer de functie voor het uploaden van HTML-import werd gebruikt. (CAMP-39326)
* Probleem verholpen waarbij tekst uit een teksteditor niet kon worden gekopieerd en geplakt. (CAMP-39028)
* Probleem verholpen waardoor de woordsuggesties niet konden worden weergegeven. (CAMP-38970)
* Probleem verholpen waardoor gebruikers fragmenten niet konden opslaan. (ATU-2447)
* Probleem verholpen waarbij werd voorkomen dat dynamische structuren werden gedupliceerd. (CAMP-38367)
* Probleem verholpen waarbij dynamische content de voorwaarden niet kon behouden tijdens het dupliceren. (CAMP-39051)

**Overige wijzigingen**

* Het filter voor leveringen met mislukte voorbereiding houdt nu rekening met de aanmaakdatum van de leveringen in plaats van met de laatste wijzigingsdatum.
* De organisatorische eenheid van de beveiligingsgroep Beheerders kan niet meer worden veranderd.
* Wanneer u een profiel maakt, moet u het veld Organisatorische eenheid nu invullen.
* Een Experience Cloud Trigger kan nu alleen worden verwijderd als zowel de gebeurtenis als de transactionele sjabloon die eraan gekoppeld is, worden verwijderd.
* Adobe Creative SDK is uit bedrijf genomen. Deze kan niet meer worden gebruikt in Campaign Standard. Zie de pagina [Verouderde en verwijderde functies](https://docs.adobe.com/content/help/nl-NL/campaign-standard/using/release-notes/deprecated-features.html).


**Patches**

* Probleem verholpen tijdens het uitvoeren van een privacyaanvraag voor verwijderen waardoor gebruikersgegevens niet konden worden verwijderd in uitsluitingslogboeken. (CAMP-39003)
* Probleem verholpen dat tot toegankelijkheidsproblemen leidde bij het wijzigen van het formaat van tekst in een containerelement.
* Probleem verholpen waarbij gebruikers het pop-upmenu voor de agenda dat bij het aanwijzen van marketingactiviteiten wordt weergegeven, niet konden negeren.
* Probleem verholpen in de activiteit **[!UICONTROL External API]** waarbij de knop **[!UICONTROL Confirm]** werd weergegeven, zelfs als er geen data waren gewijzigd.
* Probleem verholpen bij het gebruik van een activiteit **[!UICONTROL Union]** op query&#39;s met verschillende doeldimensies. De overgangsdata gaven alleen records weer van de doeldimensie van de hoofdreeks. (CAMP-36831)
* Probleem verholpen dat tot een fout kon leiden wanneer een activiteit **[!UICONTROL Reconciliation]** in specifieke contexten werd gebruikt, bijvoorbeeld bij twee binnenkomende activiteiten, waarvan één een uitsluitingsactiviteit was. (CAMP-37490)
* Problemen met de prestaties verholpen die konden optreden bij het selecteren en bijwerken van testprofielen. (CAMP-37976)
* Probleem verholpen waarbij foutpagina&#39;s konden worden weergegeven bij het inschrijven of uitschrijven via landingspagina&#39;s. (CAMP-37771)
* Probleem verholpen dat optrad bij het uploaden van content in zip-indeling, waarbij in de HTML naar PNG-bestanden werd verwezen met de extensie ervan in hoofdletters. (CAMP-37913)
* Probleem verholpen waardoor berichten in de app niet konden worden verzonden tijdens het toevoegen van een testprofiel aan de levering.
* Probleem verholpen met de workflowactiviteit Externe API die mislukte wanneer deze was gekoppeld aan verrijkingsactiviteiten.
* Probleem verholpen waarbij de status van sms-berichten onjuist kon worden weergegeven.
* Probleem verholpen met aangepaste resources die ervoor zorgden dat dubbele vermeldingen onder verschillende API-eindpunten werden weergegeven.
* Probleem verholpen waardoor landingspagina&#39;s na publicatie niet beschikbaar waren. (CAMP-38695)
* Probleem verholpen dat optrad bij het weergeven van data van een overgang Doorsnede die uit twee verschillende resources afkomstig was. (CAMP-38974)
* Probleem verholpen waarbij de opsommingswaarde in een leveringssjabloon onjuist werd ingesteld. (CAMP-38388)
* Probleem verholpen met bulkleveringen via e-mail waarbij de status van de leveringen als In behandeling en de status Verzonden als Voltooid werden weergegeven. (CAMP-35355)
* Probleem verholpen waarbij het domein van de afzender onjuist werd weergegeven in Dynamische rapportage. (CAMP-33123)
* Probleem verholpen dat discrepantie veroorzaakte in tellingen van uitschrijvingen in Dynamische rapportage. (CAMP-39949)
* Probleem verholpen waarbij adressen niet konden worden weergegeven in het scherm Sending logs bij het verzenden van in-app-berichten.
* Probleem verholpen waarbij sms-verzendlogboeken niet konden worden bijgewerkt met het juiste aantal niet-bezorgde berichten. (CAMP-38395)
* Loophole verholpen waarbij de tokens voor pushberichten konden worden bijgewerkt met POST-aanroepen van abonnementen op de applicatie. (CAMP-39273)
