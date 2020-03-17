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
source-git-commit: 14f764b92fef81c06551fb0f13b11b41e94095f0

---


# Laatste release{#latest-release}

[Release-planning](https://helpx.adobe.com/campaign/kb/acs-release-planning.html) | [Release](https://docs.adobe.com/content/help/en/control-panel/using/release-notes.html) van het regelpaneel| [Documentatiebijwerkingen](../../rn/using/documentation-updates.md) | [Opmerkingen bij](../../rn/using/release-notes-2019.md) vorige release| [Verouderde functies](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html)

## Release 20.1.4 - februari 2020 {#release-20-1-4---february-2020}

* Probleem verholpen bij het openen van een activiteit van het **leespubliek** voor bestaande workflows. (CAMP-41002)

## Release 20.1.3 - februari 2020 {#release-20-1-3---february-2020}

* Oplossing voor een regressieprobleem dat in 20.1 door CAMP-39273 werd geïntroduceerd voor klanten die de maas gebruikten. CAMP-39273 werd teruggedraaid.

## Release 20.1.2 - februari 2020 {#release-20-1-2---february-2020}

**Verbeteringen voor e-mailontwerper**

* Probleem verholpen waarbij een HTML-tagelement in een verouderd fragment werd toegevoegd bij het patchen van het element en het opslaan van de inhoud. (CAMP-40685)
* Probleem verholpen waarbij ruimte werd toegevoegd bij gebruik van dynamische inhoud. (CAMP-40605)
* Probleem verholpen bij het configureren van een transactiesjabloon voor e-mail. (CAMP-40604)

## Release 20.1 - februari 2020 {#release-20-1---february-2020}

**Wat is nieuw?**


<table> 
 <thead> 
  <tr> 
   <th> <strong>Adobe Experience Platform Data Connector (bèta)</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>De Adobe Experience Platform Data Connector is nu geïntegreerd met Adobe Campaign Standard. U kunt uw Campagnegegevens op het Platform van de Ervaring van Adobe ter beschikking stellen door de gegevens van XTK (gegevens die in Campagne worden opgenomen) aan het Model van de Gegevens van het Platform van de Ervaring van Adobe (XDM) toe te wijzen. </p>
    <p>Deze mogelijkheid is alleen beschikbaar voor klanten die in Azure worden gehost. Raadpleeg de <a href="../../administration/using/aep-about-data-connector.md">gedetailleerde documentatie</a> en de video <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/administrating/adobe-experience-platform-data-connector/understanding-the-adobe-experience-platform-data-connector.html">waarin u kunt zien hoe u deze functie en de voorwaarden</a>kunt activeren.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Bestemmingen voor het publiek (bèta) </strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Met de doelsoorten voor het publiek kunt u segmenten van het Adobe Experience Platform naar de Adobe-campagne delen.</p>
    <p>Deze mogelijkheid is alleen beschikbaar voor klanten die in Azure worden gehost. Raadpleeg de <a href="../../audiences/using/aep-about-audience-destinations-service.md">gedetailleerde documentatie</a> en de video <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.html">waarin u kunt zien hoe u deze functie en de voorwaarden</a>kunt activeren. </p>
   </td> 
  </tr> 
 </tbody> 
</table>

**Verbeteringen**

* Globale beschikbaarheid van de verbeterde MTA: berichten (inclusief transactiemeldingen) worden nu verzonden door de Adobe Campagne Enhanced MTA, die een geüpgrade verzendende infrastructuur biedt die verbeterde levering, doorvoer en stuiteringsafhandeling mogelijk maakt. [Meer informatie](https://helpx.adobe.com/campaign/kb/campaign-enhanced-mta.html)

* Tijdzonebeheer is verbeterd. U kunt nu een [specifieke tijdzone](../../automating/using/building-a-workflow.md) definiëren voor een volledige workflow. De geselecteerde tijdzone is van toepassing op alle activiteiten van de workflow. De informatie over timezone die voor de exploitant of de server is gevormd wordt nu getoond in de interface (in logboeken, en na het selecteren van een timezone). (CAMP-37672)

* De Standaard APIs van de campagne staat u nu toe om paginering uit te voeren wanneer het gebruiken van grote lijsten, door de `_forcePagination=true` parameter aan uw vraag URL toe te voegen. [Meer informatie](../../api/using/pagination.md)

* De id van het leveringslogboek (die een unieke identificatie voor elk logboek) is nu beschikbaar in de Logboeken van de Levering en het Volgen logboekmiddelen voor alle het richten dimensies. Hierdoor kunnen verzendende of trackinglogboeken bijvoorbeeld tijdens het exporteren worden geïdentificeerd. [Meer informatie](../../automating/using/exporting-logs.md)

**Verbeteringen voor e-mailontwerper**

* Ontbrekende verplichte tekstinstructies toegevoegd bij het maken van een publiek.
* Probleem verholpen door te klikken op de knop Inhoud **** wijzigen in de wizard van de oude e-maileditor.
* Probleem opgelost waarbij kopteksten niet konden worden uitgelijnd met de inhoud in het rapport Servicesamenvatting. (CAMP-38103)
* Probleem verholpen waardoor dynamische inhoudvarianten niet konden worden verwijderd zonder dat dit van invloed was op de rest van de onderwerpregel. (CAMP-40096)
* Probleem verholpen met A/B-tests bij gebruik van de B-variant op de onderwerpregel. (CAMP-40327)
* Probleem verholpen waarbij bestanden niet konden worden gesleept en neergezet wanneer de functie HTML importeren uploaden werd gebruikt. (CAMP-39326)
* Probleem verholpen waarbij tekst uit een teksteditor niet kon worden gekopieerd en geplakt. (CAMP-39028)
* Probleem verholpen waardoor het woord &#39;suggesties&#39; niet kon worden weergegeven. (CAMP-38970)
* Probleem verholpen waardoor gebruikers fragmenten niet konden opslaan. (ATU-2447)
* Probleem verholpen waarbij wordt voorkomen dat dynamische structuren worden gedupliceerd. (CAMP-38367)
* Probleem verholpen waarbij dynamische inhoud de voorwaarden tijdens het dupliceren niet kon behouden. (CAMP-39051)

**Overige wijzigingen**

* Het filter &quot;Aflevering met voorbereiding mislukt&quot; houdt nu rekening met de aanmaakdatum van de leveringen in plaats van met de laatste wijzigingsdatum.
* De organisatorische eenheid van de de veiligheidsgroep van Beheerders kan niet meer worden veranderd.
* Wanneer u een profiel maakt, moet u het veld Organizer-eenheid nu invullen.
* Een Experience Cloud Trigger kan nu alleen worden verwijderd als zowel de gebeurtenis als de transactiesjabloon die eraan gekoppeld zijn, worden verwijderd.
* Adobe Creative SDK is uit bedrijf genomen. Het is nu afgekeurd in de Standaard van de Campagne. Zie de pagina [Vervangen en verwijderde functies](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html).


**Patches**

* Probleem verholpen tijdens het uitvoeren van een privacyaanvraag voor verwijderen waardoor gebruikersgegevens niet konden worden verwijderd in uitsluitingslogboeken. (CAMP-39003)
* Probleem verholpen dat tot toegankelijkheidsproblemen leidde bij het wijzigen van het formaat van tekst in een containerelement.
* Probleem verholpen waarbij gebruikers het pop-upmenu Kalender dat tijdens marketingactiviteiten wordt weergegeven tijdens de muisaanwijzer niet konden negeren.
* Probleem verholpen in de **[!UICONTROL External API]** activiteit die de **[!UICONTROL Confirm]** knop weergaf, zelfs als er geen gegevens waren gewijzigd.
* Probleem verholpen bij het gebruik van een **[!UICONTROL Union]** activiteit op query&#39;s met verschillende doelafmetingen. De overgangsgegevens toonden slechts verslagen van de belangrijkste reeks gericht dimensie. (CAMP-36831)
* Probleem verholpen dat tot een fout kon leiden wanneer een **[!UICONTROL Reconciliation]** activiteit in specifieke contexten werd gebruikt, bijvoorbeeld bij twee binnenkomende activiteiten, waarvan één een uitsluitingsactiviteit was. (CAMP-37490)
* Problemen met de prestaties die konden optreden bij het selecteren en bijwerken van testprofielen zijn opgelost. (CAMP-37976)
* Probleem verholpen waarbij foutpagina&#39;s konden worden weergegeven wanneer een abonnement werd genomen of wanneer een abonnement werd genomen via bestemmingspagina&#39;s. (CAMP-37771)
* Probleem verholpen dat optrad bij het uploaden van inhoud in ZIP-indeling, waarbij in de HTML naar PNG-bestanden werd verwezen met de extensie ervan in hoofdletters. (CAMP-37913)
* Probleem verholpen waardoor berichten in de app niet konden worden verzonden wanneer een testprofiel aan de levering werd toegevoegd.
* Probleem verholpen met de werkstroomactiviteit van de externe API die mislukte wanneer deze was gekoppeld aan verrijkingsactiviteiten.
* Probleem verholpen waarbij de status van SMS-berichten onjuist kon worden weergegeven.
* Probleem verholpen met aangepaste bronnen die ervoor zorgden dat dubbele vermeldingen onder verschillende API-eindpunten werden weergegeven.
* Probleem verholpen waardoor bestemmingspagina&#39;s na publicatie niet beschikbaar waren. (CAMP-38695)
* Oplossing van een probleem dat optrad bij het weergeven van gegevens van een overgang van een doorsnede die uit twee verschillende bronnen afkomstig was. (CAMP-38974)
* Probleem verholpen waarbij de opsommingswaarde in een leveringssjabloon onjuist werd ingesteld. (CAMP-38388)
* Probleem verholpen met bulkleveringen via e-mail waarbij de status In behandeling van de leveringen en de status Verzonden als Voltooid werden weergegeven. (CAMP-35355)
* Probleem verholpen waarbij het domein van de afzender onjuist werd weergegeven in Dynamische rapportage. (CAMP-33123)
* Probleem verholpen dat discrepantie veroorzaakte in tellingen van Unsubscription in Dynamic reporting. (CAMP-39949)
* Probleem verholpen waarbij adressen niet konden worden weergegeven in het scherm Logboeken verzenden bij het verzenden van In-App-berichten.
* Probleem verholpen waarbij het verzenden van SMS-logs niet met het juiste aantal berichten kon worden bijgewerkt. (CAMP-38395)
* Probleem verholpen waarbij de berichttokens voor pushberichten konden worden bijgewerkt met het abonnement op de toepassing. (CAMP-39273)
