---
solution: Campaign Standard
product: campaign
title: Beste werkwijzen in het gegevensmodel in Adobe Campaign Standard
description: Leer meer over de beste werkwijzen bij het ontwerpen van uw Adobe Campaign Standard-gegevensmodel.
audience: developing
content-type: reference
topic-tags: about-custom-resources
context-tags: cusResource,overview;eventCusResource,overview
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '1556'
ht-degree: 1%

---


# Best practices voor het datamodel{#data-model-best-practices}

Dit document bevat belangrijke aanbevelingen bij het ontwerpen van uw Adobe Campaign-gegevensmodel.


>[!NOTE]
>
>Raadpleeg [deze sectie](../../developing/using/key-steps-to-add-a-resource.md)als u bronnen wilt maken en wijzigen om het vooraf gedefinieerde Adobe Campaign-gegevensmodel uit te breiden.
>
>U vindt een representatie van de ingebouwde bronnen in [deze pagina](../../developing/using/datamodel-introduction.md)in het gegevensmodel.

## Overzicht {#overview}

Het Adobe Campaign-systeem is uiterst flexibel en kan verder worden uitgebreid dan de eerste implementatie. Hoewel de mogelijkheden oneindig zijn, is het echter van essentieel belang om verstandige beslissingen te nemen en sterke fundamenten te leggen voor het ontwerpen van uw gegevensmodel.

Dit document biedt veelgebruikte gebruiksscenario&#39;s en aanbevolen procedures voor het leren hoe u Adobe Campaign op de juiste wijze kunt ontwerpen.

## Gegevensmodelarchitectuur {#data-model-architecture}

Adobe Campaign Standard is een krachtig campagnebeheersysteem voor meerdere kanalen waarmee u uw online- en offlinestrategieën kunt uitlijnen en persoonlijke ervaringen voor klanten kunt creëren.

### klantgerichte benadering {#customer-centric-approach}

Hoewel de meeste e-mailserviceproviders via een lijstgerichte aanpak communiceren met klanten, vertrouwt Adobe Campaign op een relationele database om een bredere visie op de klanten en hun kenmerken te kunnen gebruiken.

Deze klantgerichte benadering wordt getoond in de grafiek hieronder. De grijze **profielbron** vertegenwoordigt de belangrijkste klantentabel waaromheen alles wordt gebouwd:

![](assets/customer-centric-data-model.png)

Het standaardgegevensmodel van Adobe Campaign wordt in deze [sectie](../../developing/using/datamodel-introduction.md)weergegeven.

<!--You can find a datamodel representation for the out-of-the-box resources [here](../../developing/using/datamodel-introduction.md).-->

<!--### What is a customer? {#customer-definition}

If you have customer data in more than one system, you need to determine which solution will allow you to identify records as one person. This work might require rules, eventually a match and merge processes to determine the primary record. This primary record should be the one sent to Adobe Campaign.

While some of this data cleansing might be performed in Adobe Campaign, the recommendation is to run these processes outside and only import clean data in Adobe Campaign. You should keep Campaign as a marketing solution more than a data cleansing tool.

Be able to provide a primary customer record which will be sent to Adobe Campaign.-->

### Gegevens voor Adobe Campaign {#data-for-campaign}

Welke gegevens moeten naar Adobe Campaign worden verzonden? Het is van essentieel belang om de gegevens te bepalen die nodig zijn voor uw marketingactiviteiten.

>[!NOTE]
>
>Adobe Campaign is geen data-entrepot. Probeer daarom niet alle mogelijke klanten en hun bijbehorende informatie in Adobe Campaign in te voeren.

Om te beslissen of een attribuut al dan niet nodig zou zijn in Adobe Campaign, moet u bepalen of het onder een van deze categorieën zou vallen:
* Kenmerk dat wordt gebruikt voor **segmentatie**
* Kenmerk dat wordt gebruikt voor **gegevensbeheerprocessen** (bijvoorbeeld geaggregeerde berekening)
* Kenmerk dat wordt gebruikt voor **personalisatie**
* Kenmerk dat wordt gebruikt voor **rapportage** (rapporten kunnen worden gemaakt op basis van aangepaste profielgegevens)

Als er niet in een van deze elementen valt, hebt u deze eigenschap waarschijnlijk niet nodig in Adobe Campaign.

### Datatypen {#data-types}

Volg onderstaande aanbevolen procedures om gegevens in te stellen in Adobe Campaign om een goede architectuur en prestaties van uw systeem te garanderen:
* De lengte voor een tekenreeksveld moet altijd met de kolom worden gedefinieerd. Standaard is de maximumlengte in Adobe Campaign 255 tekens, maar Adobe raadt u aan het veld korter te houden als u al weet dat de grootte een kortere lengte niet overschrijdt.
* Het is acceptabel om in Adobe Campaign een veld te hebben dat korter is dan in het bronsysteem als u er zeker van bent dat de grootte in het bronsysteem is overschat en niet zou worden bereikt. Dit kan een kortere tekenreeks of een kleiner geheel getal in Adobe Campaign betekenen.

## Gegevensstructuur configureren {#configuring-data-structure}

Deze sectie schetst beste praktijken wanneer het [vormen van de gegevensstructuur](../../developing/using/configuring-the-resource-s-data-structure.md)van een middel.

### Id&#39;s {#identifiers}

Adobe Campaign-bronnen hebben drie id&#39;s en u kunt een extra id toevoegen.

In de volgende tabel worden deze id&#39;s en hun doel beschreven.

>[!NOTE]
>
>De weergavenaam is de naam van het veld dat via de gebruikersinterface van Adobe Campaign aan de gebruiker wordt weergegeven. De technische naam is de daadwerkelijke gebiedsnaam in de middeldefinitie (en de naam van de lijstkolom).

| Weergavenaam | Technische naam | Beschrijving | Best practices |
|--- |--- |--- |--- |
|  | PKey | <ul><li>De PKey is de fysieke primaire sleutel van een Adobe Campaign lijst.</li><li>Deze id is gewoonlijk uniek voor een specifieke Adobe Campaign-instantie.</li><li>In Adobe Campaign Standard is deze waarde niet zichtbaar voor de eindgebruiker (behalve in URL&#39;s).</li></ul> | <ul><li>Via het [API-systeem](../../api/using/get-started-apis.md)is het mogelijk een PKey-waarde op te halen (dit is een gegenereerde/gehashte waarde, niet de fysieke sleutel).</li><li>Het wordt afgeraden dit te gebruiken voor iets anders dan het ophalen, bijwerken of verwijderen van records via de API.</li></ul> |
| Id | name or internalName | <ul><li>Deze informatie is een unieke id van een record in een tabel. Deze waarde kan handmatig worden bijgewerkt.</li><li>Deze id behoudt de waarde wanneer deze wordt geïmplementeerd in een andere instantie van Adobe Campaign. De naam moet anders zijn dan de gegenereerde waarde om via een pakket te kunnen worden geëxporteerd.</li><li>Dit is niet de werkelijke primaire sleutel van de tabel.</li></ul> | <ul><li>Gebruik geen speciale tekens zoals spatie &quot;&quot;, puntkolom &quot;:&quot; of afbreekstreepje &quot;-&quot;.</li><li>Al deze tekens worden vervangen door een onderstrepingsteken &quot;_&quot; (toegestaan teken). &quot;abc-def&quot; en &quot;abc:def&quot; worden bijvoorbeeld opgeslagen als &quot;abc_def&quot; en worden elkaar overschreven.</li></ul> |
| Label | label | <ul><li>Het label is de bedrijfsidentificatie van een object of record in Adobe Campaign.</li><li>Voor dit object zijn spaties en speciale tekens toegestaan.</li><li>Het garandeert niet dat een record uniek is.</li></ul> | <ul><li>Het wordt aanbevolen een structuur voor de objectlabels te bepalen.</li><li>Dit is de meest gebruikersvriendelijke oplossing om een record of object voor een Adobe Campaign-gebruiker te identificeren.</li></ul> |
| ACS-id | acsId | <ul><li>Er kan een extra id worden gegenereerd: de [ACS-ID](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources).</li><li>Aangezien de PKey niet in het gebruikersinterface van Adobe Campaign kan worden gebruikt, is dit een oplossing om een unieke waarde te verkrijgen die tijdens de toevoeging van een profielverslag wordt geproduceerd.</li><li>De waarde kan alleen automatisch worden gegenereerd als de optie is ingeschakeld in de bron voordat een record in Adobe Campaign wordt ingevoegd.</li></ul> | <ul><li>Deze UUID kan worden gebruikt als een verzoeningssleutel.</li><li>Een automatisch gegenereerde ACS-id kan niet worden gebruikt als referentie in een workflow of in een pakketdefinitie.</li><li>Deze waarde is specifiek voor een Adobe Campaign-instantie.</li></ul> |

### Identificatiesleutels {#keys}

Elke bron die in Adobe Campaign wordt gemaakt, moet ten minste één unieke [identificatietoets](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys)hebben.

<!--Most organizations are importing records from external systems. While the physical key of a resource lies behind the PKey attribute, it is possible to determine a custom key in addition.

This custom key is the actual record primary key in the external system feeding Adobe Campaign.

When an out-of-the-box resource has both an internal auto-generated and an internal custom key, the internal key will be set as a unique index in the physical database table.-->

Bij het maken van een aangepaste bron hebt u twee opties:

* Een combinatie van automatisch gegenereerde sleutel en interne aangepaste sleutel. Deze optie is interessant als uw systeemsleutel een samengestelde sleutel of niet een geheel is. Geheel getal zorgt voor hogere prestaties in grote tabellen en sluit zich aan bij andere tabellen.
* De primaire sleutel gebruiken als de primaire sleutel van het externe systeem. Deze oplossing heeft doorgaans de voorkeur, omdat deze de aanpak van het importeren en exporteren van gegevens vereenvoudigt, met een consistente sleutel tussen verschillende systemen.

Identificatietoetsen mogen niet worden gebruikt als referentie in workflows.

<!--For more on defining identification keys, see [this section](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys).-->

### Indexen {#indexes}

Adobe Campaign voegt automatisch een [index](../../developing/using/configuring-the-resource-s-data-structure.md#defining-indexes) toe aan alle primaire en interne sleutels die in een bron zijn gedefinieerd.

* Adobe raadt aan aanvullende indexen te definiëren, omdat dit de prestaties ten goede kan komen.
* Voeg echter niet te veel indexen toe omdat deze ruimte in de database gebruiken. Veel indexen kunnen ook een negatief effect hebben op de prestaties.
* Selecteer zorgvuldig de indexen die moeten worden gedefinieerd.

<!--For more on defining indexes, see [this section](../../developing/using/configuring-the-resource-s-data-structure.md#defining-indexes).

When you are performing an initial import with very high volumes of data insert in Adobe Campaign database, it is recommended to run that import without custom indexes at first. It will allow to accelerate the insertion process. Once you’ve completed this important import, it is possible to enable the index(es).-->

### Koppelingen {#links}

Het definiëren van koppelingen met andere bronnen wordt in [deze sectie](../../developing/using/configuring-the-resource-s-data-structure.md#defining-links-with-other-resources)weergegeven.

* Hoewel het mogelijk is om zich bij om het even welke lijst in een werkschema aan te sluiten, adviseert Adobe het bepalen van gemeenschappelijke verbindingen tussen middelen direct in de definitie van de gegevensstructuur.
* De verbinding zou in groepering met de daadwerkelijke gegevens in uw lijsten moeten worden bepaald. Een verkeerde definitie kan van invloed zijn op gegevens die via koppelingen zijn opgehaald, bijvoorbeeld gegevens die onverwacht worden gedupliceerd.
* Geef de koppeling een consistente naam met de naam van de bron: de naam van de koppeling moet helpen begrijpen wat de verre tabel is.
* Geef een koppeling met &quot;id&quot; geen naam als achtervoegsel. Geef de naam bijvoorbeeld &quot;transactie&quot; en niet &quot;transactie-id&quot;.

<!--For more on defining links with other resources, see [this section](../../developing/using/configuring-the-resource-s-data-structure.md#defining-links-with-other-resources).-->

## Prestaties {#performance}

Volg onderstaande aanbevolen procedures om te zorgen voor betere prestaties op elk gewenst moment.

### Algemene aanbevelingen {#general-recommendations}

* Gebruik geen bewerkingen zoals &quot;CONTAINS&quot; in query&#39;s. Als u weet waarvoor wordt verwacht en waarvoor wordt gefilterd, past u dezelfde voorwaarde toe met een &quot;GELIJK AAN&quot; of andere specifieke filteroperatoren.
* Vermijd het samenvoegen met niet-geïndexeerde velden terwijl u gegevens samenstelt in workflows.
* Probeer en zorg ervoor de processen zoals de invoer en de uitvoer van bedrijfsuren gebeuren.
* Zorg ervoor dat er een schema is voor alle dagelijkse activiteiten en houd zich aan het schema.
* Als een of weinig van de dagelijkse processen mislukken en als het verplicht is om het op die zelfde dag in werking te stellen, zorg ervoor er geen conflicterende processen lopen wanneer het handproces wordt opgeheven aangezien dit de systeemprestaties zou kunnen beïnvloeden.
* Zorg ervoor dat de dagelijkse campagne niet wordt uitgevoerd tijdens het importproces of wanneer een handmatig proces wordt uitgevoerd.
* Gebruik een of meer referentietabellen in plaats van een veld in elke rij te dupliceren. Wanneer u sleutel-/waardeparen gebruikt, verdient het de voorkeur een numerieke sleutel te kiezen.
* Een korte tekenreeks blijft acceptabel. Als referentietabellen al in een extern systeem zijn geïnstalleerd, wordt de gegevensintegratie met Adobe Campaign vergemakkelijkt door dit systeem opnieuw te gebruiken.

### Een-op-veel relaties {#one-to-many-relationships}

* Gegevensontwerp beïnvloedt bruikbaarheid en functionaliteit. Als u uw gegevensmodel met vele één-aan-vele verhoudingen ontwerpt, maakt het voor gebruikers moeilijker om zinvolle logica in de toepassing te construeren. Een-op-veel filterlogica kan voor niet-technische marketers moeilijk zijn om correct te construeren en te begrijpen.
* Het is goed om alle essentiële gebieden in één lijst te hebben omdat het het voor gebruikers gemakkelijker maakt om vragen te bouwen. Soms is het ook handig om bepaalde velden te dupliceren naar andere tabellen als u samenvoeging kunt voorkomen.
* Bepaalde ingebouwde functies kunnen niet verwijzen naar een-op-een-relatie, zoals de formule en levering van de Afweging van aanbiedingen.

### Grote tabellen {#large-tables}

Hieronder vindt u een aantal aanbevolen procedures voor het ontwerpen van uw gegevensmodel met behulp van grote tabellen en complexe verbindingen.

* Verminder het aantal kolommen, met name door de kolommen te identificeren die niet worden gebruikt.
* Optimaliseer de relaties van het gegevensmodel door complexe verbindingen, zoals verbindingen op verschillende voorwaarden en/of meerdere kolommen te vermijden.
* Voor verbindingssleutels, gebruik altijd numerieke gegevens eerder dan karakterkoorden.
* Verminder zoveel u de diepte van logboekbehoud kunt. Als u een diepere geschiedenis nodig hebt, kunt u berekeningen samenvoegen en/of aangepaste logboektabellen verwerken om de grotere geschiedenis op te slaan.