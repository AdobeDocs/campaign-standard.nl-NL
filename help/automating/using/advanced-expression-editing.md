---
title: Geavanceerde expressies bewerken
description: Met de wizard Query Edition kunt u geavanceerde expressies definiëren.
page-status-flag: never-activated
uuid: a635f999-27ce-41e0-a88c-8a3882e31efe
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: filtering-data
discoiquuid: 4375153c-0621-4d4c-bfcc-66d157f04f6c
context-tags: queryFilter,overview;audience,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Geavanceerde expressies bewerken{#advanced-expression-editing}

## Geavanceerde expressies bewerken {#about-advanced-expression-editing}

Als u een expressie bewerkt, moet u handmatig voorwaarden invoeren om een regel te vormen.

In deze modus kunt u geavanceerde functies gebruiken. Met deze functies kunt u de waarden bewerken die worden gebruikt voor het uitvoeren van specifieke query&#39;s, zoals datums, tekenreeksen, numerieke velden, sorteren, enzovoort.

Het is ook mogelijk om gebeurtenisvariabelen te gebruiken wanneer het uitgeven van uitdrukking. Raadpleeg voor meer informatie de sectie [Activiteiten aanpassen met gebeurtenisvariabelen](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables) .

U kunt expressies bewerken om:

* Definieer een query via de **[!UICONTROL Advanced mode]** optie die beschikbaar is wanneer een regel wordt toegevoegd.

   ![](assets/expression_editor_2.png)

* Een expressie bewerken in een workflow. Bijvoorbeeld, om extra gegevens aan een activiteit toe te voegen.
* Bewerk een zichtbaarheidsvoorwaarde om te bepalen hoe een blok in de HTML-inhoudseditor wordt weergegeven. In dit geval wordt de expressie bewerkt in JavaScript-indeling en kunnen geavanceerde functies niet als standaard worden gebruikt.

## Een expressie bewerken {#edit-an-expression}

Met de geavanceerde expressies kunt u handmatig een expressie definiëren die specifiek aan uw behoeften voldoet.

Het uitgeven van uitdrukkingen kan in het venster van de Publiek worden gebruikt terwijl het creëren van een e-mail of in een activiteit van de Vraag terwijl het creëren van een werkschema.

1. Open het venster voor het bewerken van expressies via een van de methoden die worden beschreven in de sectie [Over geavanceerde bewerking](../../automating/using/advanced-expression-editing.md#about-advanced-expression-editing) van expressies. Het omvat de volgende elementen:

   * Een invoerveld waarin de expressie wordt gedefinieerd.
   * De lijst van beschikbare gebieden die in de uitdrukking kunnen worden gebruikt en aan de het richten dimensie van de vraag beantwoorden (zie het [richten dimensies en middelen](../../automating/using/query.md#targeting-dimensions-and-resources)).
   * De lijst met beschikbare functies, gesorteerd op categorie.
   ![](assets/expression_editor_1.png)

1. Bewerk de expressie door een expressie rechtstreeks in het desbetreffende veld in te voeren of door de lijsten met beschikbare velden en functies te gebruiken.

   Als u dubbelklikt op een veld of expressie, wordt dit toegevoegd aan de expressie waarin de cursor wordt geplaatst.

   Het is mogelijk om gebeurtenisvariabelen van workflows te gebruiken om een expressie te bouwen. Raadpleeg voor meer informatie de sectie [Activiteiten aanpassen met gebeurtenisvariabelen](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables) .

1. Geef uw regel indien nodig een specifieke naam. De ingevoerde naam wordt als regelnaam weergegeven in de werkruimte van de queryeditor.

Als u een expressie bewerkt, kunt u de expressie Soorten publiek aanpassen om uw populatie zo nodig te richten.

**Verwante onderwerpen:**

* [Expressiesyntaxis](../../automating/using/advanced-expression-editing.md#expression-syntax)
* [Lijst met functies](../../automating/using/list-of-functions.md)

## Expressiesyntaxis {#expression-syntax}

### Standaardsyntaxis {#standard-syntax}

De standaardexpressies bestaan uit een of meer voorwaarden die voldoen aan de volgende syntaxiselementen:

* Elke voorwaarde heeft de vorm van **&lt;value1> &lt;compare operator> &lt;value2>** waarbij:

   * **&lt;value1>** is een veld of een functie. Bijvoorbeeld **@created** for the date a profile was created or **Year(@created)** for the year a profile was.
   * **&lt;vergelijkingsoperator>** is een van de operatoren die worden vermeld in de sectie [Vergelijkingsoperatoren](../../automating/using/advanced-expression-editing.md#comparison-operators) . Deze operator definieert de vergelijkingsmethode tussen **&lt;value1>** en **&lt;value2>**.
   * **&lt;value2>** is een veld, een functie of een waarde die handmatig wordt ingevoerd.
   >[!NOTE]
   >
   >De typegegevens **&lt;value1>** en **&lt;value2>** moeten identiek zijn. Als **&lt;value1>** bijvoorbeeld een datum is, moet **&lt;value2>** ook een datum zijn.

* Als u meerdere voorwaarden wilt gebruiken, kunt u deze combineren met logische operatoren.

   * **[!UICONTROL AND]**: twee voorwaarden zijn doorsnede.
   * **[!UICONTROL OR]**: twee voorwaarden zijn gecombineerd .

Bijvoorbeeld:

```
Year(@created) = Year(GetDate()) AND Month(@created) = Month(GetDate())
```

In dit voorbeeld worden de profielen gebruikt waarvan de aanmaakdatum in de huidige maand en het huidige jaar ligt.

### JavaScript-syntaxis {#javascript-syntax}

Wanneer u de zichtbaarheidsvoorwaarden definieert voor een tekstblok van de HTML-inhoudseditor, moet u een expressie gebruiken met syntaxis voor JavaScript-typen.

JavaScript-expressies bestaan uit een of meerdere voorwaarden en gebruiken de volgende syntaxiselementen:

* Elke voorwaarde heeft de vorm van **&lt;context> &lt;vergelijkingsoperator> &lt;value2>** waarbij:

   * **&lt;context>** is een veld of functie waarmee u de context kunt opgeven. Bijvoorbeeld **context.profile.@email** voor het e-mailadres of de **context.profile.firstName.length()** van een profiel voor het aantal tekens in de voornaam van een profiel.
   * **&lt;vergelijkingsoperator>** is een van de operatoren die worden vermeld in de sectie [Vergelijkingsoperatoren](../../automating/using/advanced-expression-editing.md#comparison-operators) . Deze operator definieert de vergelijkingsmethode tussen **&lt;context>** en **&lt;value2>**.
   * **&lt;value2>** is een veld, een functie of een waarde die handmatig wordt ingevoerd.
   >[!NOTE]
   De **&lt;context>** en **&lt;value2>** typegegevens moeten identiek zijn. Als **&lt;context>** bijvoorbeeld een datum is, moet **&lt;value2>** ook een datum zijn.

* Als u meerdere voorwaarden wilt gebruiken, kunt u deze combineren met logische operatoren.

   * **[!UICONTROL &&]**: twee voorwaarden zijn doorsnede.
   * **[!UICONTROL ||]**: twee voorwaarden zijn gecombineerd .

Bijvoorbeeld:

```
context.profile.age > 21 && context.profile.firstName.length() > 0
```

In dit voorbeeld worden profielen ouder dan 21 jaar en met voornaam opgegeven (gesymboliseerd door het feit dat het veld **firstName** ten minste één teken bevat).

## Vergelijkingsoperatoren {#comparison-operators}

Voor sommige regels, laat de vraagredacteur u een waarde kiezen om uw voorwaarde te bepalen.

De voorwaarden moeten aan waarden door één van de volgende exploitanten worden verbonden.

<table> 
 <thead> 
  <tr> 
   <th> Operator<br /> </th> 
   <th> Standaardsyntaxis<br /> </th> 
   <th> JavaScript-syntaxis<br /> </th> 
   <th> Beschrijving<br /> </th> 
   <th> Voorbeeld<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <span class="uicontrol">Gelijk aan</span><br /> </td> 
   <td> =<br /> </td> 
   <td> ==<br /> </td> 
   <td> De eerste waarde moet volledig identiek zijn aan de tweede waarde.<br /> </td> 
   <td> <strong>@lastName = Martin</strong> haalt profielen op waarvan de achternaam 'Martin' is, met alleen deze identieke tekens.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Groter dan</span><br /> </td> 
   <td> &gt;<br /> </td> 
   <td> &gt;<br /> </td> 
   <td> De eerste waarde moet categorisch meer zijn dan de tweede waarde.<br /> </td> 
   <td> <strong>@age &gt; 50</strong> haalt profielen op die ouder zijn dan '50', dus '51', '52' enzovoort.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Kleiner dan</span><br /> </td> 
   <td> &lt;<br /> </td> 
   <td> &lt;<br /> </td> 
   <td> De eerste waarde moet categorisch kleiner zijn dan de tweede waarde.<br /> </td> 
   <td> <strong>@created &lt; DaysAgo(100)</strong> retrieve all profiles created in the database less than 100 days ago.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Groter dan of gelijk aan</span><br /> </td> 
   <td> &gt;=<br /> </td> 
   <td> &gt;=<br /> </td> 
   <td> De eerste waarde moet groter zijn dan of gelijk zijn aan de tweede waarde.<br /> </td> 
   <td> <strong>@age &gt;= 30</strong> haalt profielen van 30 jaar en ouder op.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Kleiner dan of gelijk aan</span><br /> </td> 
   <td> &lt;=<br /> </td> 
   <td> &lt;=<br /> </td> 
   <td> De eerste waarde moet kleiner zijn dan of gelijk zijn aan de tweede waarde.<br /> </td> 
   <td> <strong>@age &lt;= 60</strong> haalt profielen van 60 jaar of ouder op.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Verschil </span><br /> </td> 
   <td> !=<br /> </td> 
   <td> !=<br /> </td> 
   <td> De eerste waarde moet anders zijn dan de tweede waarde.<br /> </td> 
   <td> <strong>@language != Engels</strong> haalt profielen op die niet als Engels sprekend zijn gedefinieerd.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Bevat</span><br /> </td> 
   <td> IN<br /> </td> 
   <td> N.v.t.<br /> </td> 
   <td> De eerste waarde moet de tweede waarde bevatten.<br /> </td> 
   <td> <strong>@domain IN mail</strong>. Hier worden alle domeinnamen met de waarde 'mail' geretourneerd in het resultaat. Daarom zal de domeinnaam 'gmail.com' deel uitmaken van de geretourneerde resultaten.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">leuk</span><br /> </td> 
   <td> LIKE<br /> </td> 
   <td> N.v.t.<br /> </td> 
   <td> <span class="uicontrol">Zoals</span> lijkt het op de operator <span class="uicontrol">Bevat</span> . Hiermee kunt u een <span class="uicontrol">%</span> jokerteken invoegen in de waarde die wordt doorzocht.<br /> </td> 
   <td> <strong>@lastName LIKE Mart%n</strong>. Hier fungeert het substitutieteken <strong>%</strong> als een "joker" om de naam "Martin" te zoeken in het hypothetische geval dat de spelling niet correct is.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Niet leuk</span><br /> </td> 
   <td> NOT<br /> </td> 
   <td> N.v.t.<br /> </td> 
   <td> Is gelijkaardig aan <span class="uicontrol">als</span>. Hiermee kunt u de ingevoerde waarde niet herstellen. Ook hier moet de ingevoerde waarde het teken <span class="uicontrol">%</span> wild bevatten.<br /> </td> 
   <td> <strong>@lastName NOT Smi%h</strong>. Hier komen de ontvangers overeen met de naam 'Smi%h' (dus Smith, enz.) niet worden geretourneerd.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Is leeg</span><br /> </td> 
   <td> IS NULL<br /> </td> 
   <td> N.v.t.<br /> </td> 
   <td> De eerste waarde moet overeenkomen met een lege waarde.<br /> </td> 
   <td> <strong>@mobilePhone IS NULL</strong> haalt alle profielen op waarvan het mobiele-telefoonnummer niet is opgegeven.<br /> </td> 
  </tr> 
 </tbody> 
</table>

