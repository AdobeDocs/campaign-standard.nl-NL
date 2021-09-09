---
solution: Campaign Standard
product: campaign
title: Laatste release
description: Op deze pagina vindt u content van de nieuwste release van Campaign Standard
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
feature: Overview
role: User
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: cedb8a0837d9c0339149efd2a99c777a12ef260d
workflow-type: tm+mt
source-wordcount: '1074'
ht-degree: 38%

---


# Laatste release{#latest-release}

## Release 21.3 - september 2021 {#release-21-3---sept-2021}

De nieuwe functies, verbeteringen en oplossingen die zijn opgenomen in de nieuwste release van Campaign Standard worden hieronder weergegeven.

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

* De veiligheid is verbeterd voor bescherming tegen aanvallen SSRF. (CAMP-47836)
* De lijst met gebruikers is nu beperkt tot alleen beheerders. (CAMP-47260)
* Omgevingsvariabelen kunnen niet meer worden gebruikt als onderdeel van parameteruitbreiding in een URL. (CAMP-47268)

**Verbeteringen**

* Wanneer u een terugkerende levering maakt in een workflow die is gekoppeld aan inhoud van Adobe Experience Manager, wordt de goedkeuringsstatus van de inhoud nu gecontroleerd voordat deze wordt verzonden.
* De verbindingslimiet voor databases wordt nu uitgelijnd met het Campaign-pakket om verbindingsfouten te voorkomen.
* Een nieuwe consistentiecontrole in de publicatie van aangepaste bronnen voorkomt dat gebruikers dubbele indexen maken, waardoor de publicatie mislukt. In een verbeterd foutbericht wordt de gebruiker gevraagd de naam van de index indien nodig te wijzigen.

**Andere wijzigingen**

* De dienst van de Doelen van de Gegevens van Adobe Experience Platform en van het Publiek zijn nu verouderd met Campaign Standard. Als u deze mogelijkheden gebruikt, moet u zich aan de Bronnen en Doelen van Adobe bewegen en uw implementatie aanpassen. [Meer informatie](../../integrating/using/get-started-sources-destinations.md)
* Vervangen en verwijderde functies worden weergegeven op [deze pagina](deprecated-features.md).
* Er is een nieuwe samenvoegingsfunctie &#39;StringAgg&#39; geïntroduceerd om de waarden van een kolom met het type tekenreeks samen te voegen. (CAMP-47077) [Meer informatie](../../automating/using/list-of-functions.md#aggregates)
* De technische workflow **Leveringsindicatoren bijwerken** (updateDeliveryIndicators) is verbeterd en biedt nu betere prestaties.
* Sjablonen voor berichten in de app zijn nu beschikbaar voor alle talen die worden ondersteund in Campaign Standard.
* De de voorbereidingstijd van de levering is geoptimaliseerd voor transactionele berichten door het aantal vraag aan de volgende server tijdens leveringsanalyse te verminderen.
* Gebruikers worden via een nieuw waarschuwingsbericht op de hoogte gesteld van een hoge stuitsnelheid.
* Verbeterde logboekfoutmeldingen en waarschuwingen om foutopsporing eenvoudiger te maken wanneer de trackinglogbestanden niet correct zijn opgehaald. (CAMP-48939, CAMP-47360)
* U kunt URL&#39;s nu volledig aanpassen, inclusief de domeinnaam. [Meer informatie](../../designing/using/personalization.md#personalizing-urls)

**Patches**

* Er is een probleem met time-out verholpen bij het importeren van e-mailinhoud van een URL. (CAMP-49054)
* Correctie van een fout (-69) veroorzaakt door een einde van de sessie, bij het openen van een URL met bladwijzer of het vernieuwen van een pagina vanuit de browser. (CAMP-49003, CAMP-48930, CAMP-48894)
* Er is een probleem verholpen bij het synchroniseren van regels van de verouderde bezorgingsserver naar de nieuwe bezorgingsserver. (CAMP-48923)
* Er is een probleem verholpen bij het laden van een e-mailsjabloon met HTML-tags in de e-mailontwerper. (CAMP-48243)
* Probleem verholpen waarbij Adobe Experience Manager-inhoud niet werd geladen tijdens het maken van transactieberichten met de e-mailontwerper. (CAMP-49075)
* Probleem verholpen in de interface waarbij te veel opvulling werd toegevoegd tussen de bovenste balk en de inhoud.
* Probleem verholpen met transactieberichten die tot een publicatiefout kunnen leiden bij het gebruik van de inhoudsblokken voor campagne in Adobe Experience Manager-inhoud. (CAMP-49233)
* Probleem verholpen dat tot een foutbericht kon leiden wanneer de verificatie mislukte. De gebruiker wordt nu omgeleid naar de aanmeldingspagina.
* Oplossing voor een weergaveprobleem met token waardoor gebruikers een rapport niet konden bewerken of delen.
* Probleem verholpen tijdens de publicatie van een aangepaste bron met behulp van een filterexpressie met een tabelrelatie van 1 tot 2. (CAMP-48740)
* Oplossing voor een probleem met de datumnotatie dat ervoor zorgde dat er geen contactdatums van de levering konden worden opgehaald in workflowovergangen. (CAMP-48871)
* Probleem verholpen waarbij het verzenden van logbestanden tijdens het maken van een aangepaste profieldimensie werd verhinderd.
* Probleem verholpen waarbij leveringen met meerdere taalvarianten kunnen mislukken. Als een gebruiker de standaardtaalvariant verwijdert, moet vanaf nu een andere taalvariant als de standaardvariant worden ingesteld voordat u de talenkopieën maakt. (CAMP-48235)
* Probleem verholpen waarbij e-mailberichten extra witruimten in Outlook lieten weergeven als de gebruiker de optie **Alleen weergeven op mobiele apparaten** had geselecteerd tijdens het ontwerpen van het bericht. (CAMP-48902)
* Probleem verholpen die ervoor zorgde dat de laatste uitvoeringsdatum van het incrementele veld van de vraagactiviteit van het **Verwerkte Gegevens** lusje na het in werking stellen van het stijgende vraagwerkschema mist. (CAMP-48879)
* Probleem verholpen waardoor u geen dynamische segmentcode correct kon definiëren in de workflowactiviteit **Segmentatie**. (CAMP-48727)
* Probleem verholpen waarbij een willekeurige fout optrad tijdens het opslaan van een workflow na het bewerken. (CAMP-48695)
* Probleem verholpen waardoor u geen aangepaste bronnen kon publiceren omdat het gegevensschema van een trigger nog steeds aanwezig was nadat de trigger was verwijderd. (CAMP-48523)
* Probleem verholpen waardoor de aanvragen voor feedbackherhalingen niet konden worden uitgevoerd omdat het InMail-proces de bij te werken leveringslogboeken niet kon ophalen. (CAMP-48705)
* Probleem verholpen waardoor u de uitsluitingsopties niet correct kon definiëren in de **Exclusie**-workflowactiviteit.(CAMP-48355)
* Probleem verholpen die optrad wanneer verrijkingsactiviteiten in workflows abonnementen op of het afstoten van abonnementen op een service betroffen. Deze kwestie leidde tot het vastlopen.
* Probleem verholpen waardoor workflows niet konden worden uitgevoerd.
* Probleem verholpen waarbij de naam van beveiligingsgroepen buiten de box niet kon worden gewijzigd of verwijderd in de gebruikersinterface.
* Probleem verholpen waardoor gebruikers een onvolledige publicatietaak voor gebeurtenissen konden verwijderen.
* Probleem verholpen waarbij de workflow voor het opschonen van de database mislukte met een fout. (CAMP-49097)
