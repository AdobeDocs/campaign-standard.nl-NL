---
title: Laatste release
description: Op deze pagina vindt u content van de nieuwste release van Campaign Standard
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
feature: Overview
role: User
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: 7066cf1d8454ffdefa29bff5092ba2c3e1bac705
workflow-type: tm+mt
source-wordcount: '1766'
ht-degree: 99%

---


# Laatste release{#latest-release}

## Release 22.1 - februari 2022 {#feb-2022}

**Nieuwe functies**

<table> 
<thead> 
<tr> 
<th> <strong>Beveiligingsupdate voor beveiligingskwetsbaarheden van Apache Log4j</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>Apache log4j heeft de gerapporteerde kwetsbaarheden in de Apache log4j v2.17.1-release verholpen. Adobe Campaign Standard gebruikt Apache log4j en in deze release is deze nieuwste Apache log4j v2.17.1 inbegrepen </p>
</td> 
</tr> 
</tbody> 
</table>

**Beveiligingsoplossingen**

* Nieuw URL-handtekeningmechanisme voor tracking opgenomen in deze release. Het vorige mechanisme was uitgeschakeld om een probleem te voorkomen waardoor geldige, ondertekende trackingkoppelingen onjuist werden geblokkeerd nadat ze waren gewijzigd door beveiligingstools van derden. (CAMP-48983)

**Verbeteringen**

* Verbeterde verwerking van de rapportagegegevens om overbelasting van het systeem te voorkomen. (CAMP-47578)
* Nadat u uw In-app-berichten hebt verzonden, kunt u er nu voor kiezen om uw levering te deactiveren. Op deze manier kunt u de levering verwijderen zonder rapportgegevens te verliezen. (CAMP-48469)
* Om problemen te voorkomen kunnen gebruikers niet langer dezelfde naam gebruiken voor een aangepaste tabelkolom als de naam die wordt gebruikt voor de automatische primaire sleutel in de database, `"<dataType><resourceName>Id"`. (CAMP-49358)
* U kunt nu uw levering bewaken en taaklogboeken volgen met de nieuwe vervolgkeuzelijst **Taakgeschiedenis** van het dashboard van uw berichten. (CAMP-49840)
* Verbeterde stabiliteit en gezondheid van de database door het verminderen van dode tupels, wanneer een groot aantal berichten in de loop van de tijd over alle kanalen wordt verzonden. (CAMP-49755, CAMP-49792, CAMP-49849)
* Om ervoor te zorgen dat databaseverbindingen automatisch worden vernieuwd in het geval van een databasecrash of opnieuw opstarten, zijn er verbeteringen geïmplementeerd in Campaign Mail Transfer Agent (MTA). (CAMP-48063)


**Patches**

* Er is een probleem opgelost met de optie **Rapport nu verzenden** in dynamische rapporten: de PDF-generatietaken mislukten bij leveringen met multivarianten. (CAMP-49120)
* Er is een probleem opgelost waarbij gebruikers de content van Adobe Experience Manager (AEM) niet konden vernieuwen of ontkoppelen van hun Adobe Campaign Standard-leveringen wanneer gedupliceerde content in AEM dezelfde sleutel deelde (cq:uuid). (CAMP-49161)
* Er is een fout opgelost bij het openen van een instantie waar pagina&#39;s niet werden geladen, leveringen niet konden worden geopend of eventuele wijzigingen in behandeling niet konden worden opgeslagen. (CAMP-50195)
* Er is een probleem opgelost dat verhinderde dat waarschuwingscriteria voor levering werden geopend als het veld **Leveringsfilter** dat door dit criterium werd toegepast, niet was ingevuld. (CAMP-49093)
* Er is een probleem opgelost bij het bewerken van de knop **Secundair** in In-app-leveringen waardoor er geen rekening kon worden gehouden met wijzigingen. (CAMP-50250)
* Er is een fout opgelost in Japanse instanties waardoor gebruikers Meerdere keren per dag konden kiezen als **Uitvoerfrequentie** in de activiteit **Planner**. (CAMP-50247)
* Er is een probleem opgelost bij het werken in een Japanse gebruikersinterface die een foutbericht weergaf bij het selecteren van een tijd in een Planner-activiteit. (CAMP-49289)
* Er is een fout opgelost met pushmeldingsrapporten waarin afgewezen pushmeldingen werden weergegeven als **Open** in plaats van **Impressie**. (CAMP-45980)
* Er is een probleem opgelost dat tot fouten kon leiden bij het openen van een rapport. (CAMP-49222)
* Er is een probleem opgelost dat ertoe kon leiden dat de e-mailvoorbereiding mislukte nadat een koppeling naar AEM-content was verwijderd. (CAMP-49877)
* Om verschillende problemen op te lossen is het mechanisme voor opnieuw proberen verbeterd voor leveringen met content die is geïmporteerd via een URL. [Meer informatie](../../designing/using/using-existing-content.md#retrieving-content-from-a-url-automatically-at-preparation-time) (CAMP-48888)
* Er is een probleem opgelost dat optrad na het maken van een nieuw filter in een aangepaste bron en het vervolgens te gebruiken als een afstemmingssleutel op een landingspagina. Als de aangepaste bron opnieuw is gepubliceerd, is het filter verwijderd uit de lijst met beschikbare afstemmingssleutels voor de landingspagina. (CAMP-49516)
* Er is een probleem opgelost in landingspagina&#39;s bij het gebruik van dynamische voorwaarden met selectievakjes. (CAMP-48604)
* Er is een probleem opgelost dat optrad in een **Query**-activiteit na gebruik van de filtervoorwaarde In of vóór oktober. Bij het werken vanuit een instantie die is ingesteld op een Europese tijdzone, toonde de geselecteerde maand voor het filter september in plaats van oktober, als gevolg van een probleem bij het omrekenen van de tijdzone. (CAMP-48602)
* Adobe Campaign verzendt nu e-mailberichten met 7-bits codering in plaats van 8-bits om de levering te optimaliseren. Hierdoor wordt voorkomen dat tussenliggende relais de DKIM-handtekening ongeldig maken, wat de authenticiteit van de berichten kan beïnvloeden. (CAMP-49016)
* De prestaties bij het dupliceren van audiences zijn verbeterd om problemen bij het werken met grote audiences te voorkomen. (CAMP-49639)
* Er is een probleem opgelost waardoor een aangepast filter de juiste resultaten niet kon weergeven bij gebruik in een **Query**-activiteit. (CAMP-49417)
* Er is een fout opgelost die een foutbericht weergaf bij een poging om een fragment te gebruiken in een levering met een komma in de naam. Het probleem is opgelost. Er kunnen nu komma&#39;s worden gebruikt in de namen van fragmenten. (CAMP-49216)


## Release 21.3 - september 2021 {#release-21-3---sept-2021}

De nieuwe functies, verbeteringen en oplossingen die in de laatste release van Campaign Standard zijn opgenomen, worden hieronder weergegeven.

**Nieuwe functies**

<table> 
<thead> 
<tr> 
<th> <strong>Uniforme Experience Cloud-interface</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>De kopbalk van Adobe Campaign is veranderd voor een uniforme, verbeterde ervaring voor alle Experience Cloud-producten en -services. Deze wijzigingen maken het u als volgt gemakkelijker:</p>
<ul>
<li>Eenvoudiger overschakelen tussen uw organisaties of naar een andere applicatie.</li>
<li>Verbeterde Help voor gebruikers - De Experience League is in het product opgenomen, zodat de zoekresultaten ook resultaten van communityforums en meer videocontent omvatten; hierdoor krijgt u gemakkelijker toegang tot meer content om optimaal te profiteren van de applicatie. We hebben ook een feedbackmechanisme toegevoegd aan het menu Help, waardoor het gemakkelijker is om problemen te melden of uw ideeën te delen.</li>
<li>Verbeterde meldingen - De vervolgkeuzelijst Meldingen bevat nu twee tabbladen: één voor uw eigen productmeldingen en één voor meer algemene productmeldingen.</li>
</ul>
<p>Raadpleeg de <a href="../../start/using/interface-description.md#top-bar">gedetailleerde documentatie</a> voor meer informatie.
</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>Audittrail</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>Met de nieuwe functie Audittrail wordt in real time een uitgebreide lijst met acties en gebeurtenissen in Adobe Campaign vastgelegd. Het bevat een manier om zelf toegang te krijgen tot een geschiedenis van gegevens om vragen te beantwoorden zoals:</p>
<ul>
<li>Wat is er gebeurd met deze workflow en wie heeft deze voor het laatst bijgewerkt?</li>
<li>Wie heeft de laatste wijzigingen doorgevoerd?</li>
<li>Wat was de vorige staat?</li>
</ul>
<p>Adobe Campaign controleert nu de acties voor het maken, bewerken en verwijderen van: workflows, opties, aangepaste bronnen. Wijzigingen van deze items worden ook bijgehouden.</p>
<p>Raadpleeg de <a href="../../administration/using/audit.md">gedetailleerde documentatie</a> voor meer informatie.</p>
</td> 
</tr> 
</tbody> 
</table>


<table> 
<thead> 
<tr> 
<th> <strong>Diagnostische modus voor workflows</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>U kunt de workflows van Campaign nu uitvoeren in de diagnostische modus. In deze modus wordt informatie geregistreerd om problemen met de uitvoering van probleemoplossingen te helpen oplossen. Het volledige uitvoeringsplan wordt geregistreerd als een workflowquery standaard meer dan één minuut duurt.</p>
<p>Raadpleeg de <a href="../../automating/using/managing-execution-options.md">gedetailleerde documentatie</a> voor meer informatie.</p>
</td> 
</tr> 
</tbody> 
</table>

**Beveiligingsverbeteringen**

* De beveiliging is verbeterd voor bescherming tegen SSRF-aanvallen. (CAMP-47836)
* De lijst met gebruikers is nu beperkt tot alleen beheerders. (CAMP-47260)
* Omgevingsvariabelen kunnen niet meer worden gebruikt als onderdeel van parameteruitbreiding in een URL. (CAMP-47268)

**Verbeteringen**

* Wanneer u een terugkerende levering maakt in een workflow die is gekoppeld aan inhoud van Adobe Experience Manager, wordt de goedkeuringsstatus van de inhoud nu gecontroleerd voordat deze wordt verzonden.
* De verbindingslimiet voor databases wordt nu uitgelijnd met het Campaign-pakket om verbindingsfouten te voorkomen.
* Een nieuwe consistentiecontrole in de publicatie van aangepaste bronnen voorkomt dat gebruikers dubbele indexen maken, waardoor de publicatie mislukt. Een verbeterd foutbericht vraagt de gebruiker de naam van de index indien nodig te wijzigen. [Meer informatie](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource)

**Andere wijzigingen**

* Adobe Experience Platform Data Connector en de service Doelgroepbestemmingen zijn nu verouderd met Campaign Standard. Als u deze functies gebruikt moet u naar Bronnen en bestemmingen van Adobe gaan en uw implementatie aanpassen. [Meer informatie](../../integrating/using/get-started-sources-destinations.md)
* Verouderde en verwijderde functies worden op [deze pagina](deprecated-features.md) weergegeven.
* Er is een nieuwe samenvoegingsfunctie &#39;StringAgg&#39; geïntroduceerd om de waarden van een kolom met het type tekenreeks samen te voegen. (CAMP-47077) [Meer informatie](../../automating/using/list-of-functions.md#aggregates)
* De technische workflow **Leveringsindicatoren bijwerken** (updateDeliveryIndicators) is verbeterd voor betere prestaties.
* Sjablonen voor berichten in de app zijn nu beschikbaar voor alle talen die worden ondersteund in Campaign Standard.
* De voorbereidingstijd van de levering is geoptimaliseerd voor transactionele berichten door het aantal oproepen aan de trackingserver tijdens de analyse van de levering te verminderen.
* Gebruikers worden met een nieuw waarschuwingsbericht op de hoogte gebracht van een hoog bouncepercentage.
* Verbeterde foutmeldingen en waarschuwingen in het logboekbestand om foutopsporing eenvoudiger te maken wanneer de trackinglogbestanden niet correct zijn opgehaald. (CAMP-48939, CAMP-47360)
* U kunt URL&#39;s nu volledig aanpassen, inclusief de domeinnaam. [Meer informatie](../../designing/using/personalization.md#personalizing-urls)

**Patches**

* Er is een probleem met time-out verholpen bij het importeren van e-mailinhoud van een URL. (CAMP-49054)
* Er is een fout (-69) verholpen die werd veroorzaakt door een einde van de sessie bij het openen van een URL gemarkeerd met een bladwijzer of bij het vernieuwen van een pagina vanuit de browser. (CAMP-49003, CAMP-48930, CAMP-48894)
* Er is een probleem verholpen bij het synchroniseren van regels van de verouderde bezorgingsserver naar de nieuwe bezorgingsserver. (CAMP-48923)
* Er is een probleem verholpen bij het laden van een e-mailsjabloon met HTML-tags in de e-mailontwerper. (CAMP-48243)
* Er is een probleem verholpen waarbij de content van Adobe Experience Manager niet werd geladen tijdens het maken van transactieberichten met de e-mailontwerper. (CAMP-49075)
* Er is een probleem verholpen in de interface waarbij te veel opvulling werd toegevoegd tussen de bovenste balk en de content.
* Er is een probleem verholpen met transactieberichten die tot een publicatiefout konden leiden bij het gebruik van Campaign-contentblokken in de content van Adobe Experience Manager. (CAMP-49233)
* Er is een probleem verholpen dat tot een foutbericht kon leiden wanneer de verificatie mislukte. De gebruiker wordt nu omgeleid naar de aanmeldingspagina.
* Er is een tokenweergaveprobleem verholpen waardoor gebruikers een rapport niet konden bewerken of delen.
* Er is een probleem verholpen tijdens de publicatie van een aangepaste bron met behulp van een filterexpressie met 1-n tabelrelaties. (CAMP-48740)
* Er is een probleem verholpen met de datumopmaak waardoor er geen contactdatums van de levering konden worden opgehaald in workflowovergangen. (CAMP-48871)
* Er is een probleem verholpen waardoor de extensie geen logbestanden kon verzenden tijdens het maken van een aangepaste profieldimensie.
* Er is een probleem verholpen waarbij leveringen met meerdere taalvarianten soms mislukten. Als een gebruiker de standaardtaalvariant verwijdert, moet voortaan een andere taalvariant als de standaardvariant worden ingesteld voordat u de talenkopieën maakt. (CAMP-48235)
* Er is een probleem verholpen waarbij e-mailberichten in Outlook extra witruimten bevatten als de gebruiker de optie **Alleen weergeven op mobiele apparaten** had geselecteerd tijdens het ontwerpen van het bericht. (CAMP-48902)
* Er is een probleem verholpen waardoor de laatste uitvoeringsdatum van het veld met incrementele queryactiviteiten ontbrak op het tabblad **Verwerkte gegevens** na het uitvoeren van de incrementele queryworkflow. (CAMP-48879)
* Er is een probleem verholpen waardoor u een dynamische segmentcode in de workflowactiviteit **Segmentatie** niet correct kon definiëren. (CAMP-48727)
* Er is een probleem verholpen dat willekeurig optrad tijdens het opslaan van een workflow na bewerking. (CAMP-48695)
* Er is een probleem verholpen waardoor u geen aangepaste bronnen kon publiceren omdat het gegevensschema van een trigger nog steeds aanwezig was, zelfs nadat de trigger was verwijderd. (CAMP-48523)
* Er is een probleem verholpen waardoor de aanvragen voor feedbackherhalingen niet werden uitgevoerd omdat het InMail-proces de bij te werken leveringslogboeken niet kon ophalen. (CAMP-48705)
* Er is een probleem verholpen waardoor u de uitsluitingsopties in de workflowactiviteit **Exclusie** niet correct kon definiëren.(CAMP-48355)
* Er is een probleem verholpen dat optrad wanneer verrijkingsactiviteiten in workflows betrekking hadden op lidmaatschappen of afmeldingen van services. Dit probleem leidde tot vastlopen.
* Er is een probleem verholpen waardoor workflows niet konden worden uitgevoerd.
* Er is een probleem verholpen waarbij gebruikers de gebruiksklare beveiligingsgroepen in de gebruikersinterface niet kon hernoemen of verwijderen.
* Er is een probleem verholpen waardoor gebruikers een onvolledige publicatietaak voor gebeurtenissen niet konden verwijderen.
* Er is een probleem verholpen waarbij de workflow voor het opschonen van de database mislukte met een fout. (CAMP-49097)
