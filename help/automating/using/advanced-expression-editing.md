---
solution: Campaign Standard
product: campaign
title: Geavanceerde expressies bewerken
description: Met de wizard voor querybewerking kunt u geavanceerde expressies definiëren.
audience: automating
content-type: reference
topic-tags: filtering-data
context-tags: queryFilter,overview;audience,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '1092'
ht-degree: 98%

---


# Geavanceerde expressies bewerken{#advanced-expression-editing}

## Geavanceerde expressies bewerken {#about-advanced-expression-editing}

Als u een expressie bewerkt, moet u handmatig voorwaarden invoeren om een regel te vormen.

In deze modus kunt u geavanceerde functies gebruiken. Met deze functies kunt u de waarden bewerken die worden gebruikt voor het uitvoeren van specifieke query&#39;s, zoals het bewerken van datums, tekenreeksen, numerieke velden, sorteren, enzovoort.

Het is ook mogelijk gebeurtenisvariabelen van workflows te gebruiken wanneer het uitgeven van uitdrukking. Raadpleeg de sectie [Activiteiten aanpassen met gebeurtenisvariabelen](../../automating/using/customizing-workflow-external-parameters.md) voor meer informatie.

U kunt expressies bewerken om:

* Een query te definiëren via de optie **[!UICONTROL Advanced mode]** die beschikbaar is wanneer een regel wordt toegevoegd.

   ![](assets/expression_editor_2.png)

* Een expressie te bewerken in een workflow, bijvoorbeeld om extra data aan een activiteit toe te voegen.
* Een zichtbaarheidsvoorwaarde te bewerken om te bepalen hoe een blok in de HTML-contenteditor wordt weergegeven. In dit geval wordt de expressie bewerkt in JavaScript-indeling en kunnen geavanceerde functies niet als standaard worden gebruikt.

## Een expressie bewerken {#edit-an-expression}

Met de bewerkingsfuncties voor geavanceerde expressies kunt u handmatig een expressie definiëren die specifiek aan uw behoeften voldoet.

U kunt expressies bewerken in het venster Audience tijdens het maken van een e-mail of in een activiteit Query tijdens het maken van een workflow.

1. Open het venster voor het bewerken van expressies via een van de methoden die worden beschreven in de sectie [Geavanceerde expressies bewerken](../../automating/using/advanced-expression-editing.md#about-advanced-expression-editing). Dit venster omvat de volgende elementen:

   * Een invoerveld waarin de expressie wordt gedefinieerd.
   * De lijst met beschikbare velden die in de expressie kunnen worden gebruikt en overeenkomen met de doeldimensie van de query (zie [Doeldimensies en resources](../../automating/using/query.md#targeting-dimensions-and-resources)).
   * De lijst met beschikbare functies, gesorteerd op categorie.

   ![](assets/expression_editor_1.png)

1. Bewerk de expressie door een expressie rechtstreeks in het desbetreffende veld in te voeren of door de lijsten met beschikbare velden en functies te gebruiken.

   Als u dubbelklikt op een veld of expressie, wordt dit toegevoegd aan de expressie waarin de cursor is geplaatst.

   Het is mogelijk om gebeurtenisvariabelen van workflows te gebruiken om een expressie samen te stellen. Raadpleeg de sectie [Activiteiten aanpassen met gebeurtenisvariabelen](../../automating/using/customizing-workflow-external-parameters.md) voor meer informatie.

1. Geef uw regel indien nodig een specifieke naam. De ingevoerde naam wordt als regelnaam weergegeven in de werkruimte van de query-editor.

Als u een expressie bewerkt, kunt u de expressie Audiences aanpassen om uw populatie zo nodig doelgericht te benaderen.

**Verwante onderwerpen:**

* [Expressiesyntaxis](../../automating/using/advanced-expression-editing.md#expression-syntax)
* [Lijst met functies](../../automating/using/list-of-functions.md)

## Expressiesyntaxis {#expression-syntax}

### Standaardsyntaxis {#standard-syntax}

De standaardexpressies bestaan uit een of meer voorwaarden die voldoen aan de volgende syntaxiselementen:

* Elke voorwaarde heeft de volgende vorm: **&lt;value1> &lt;comparison operator> &lt;value2>** waarbij:

   * **&lt;value1>** een veld of een functie is. Bijvoorbeeld **@created** voor de datum waarop een profiel is gemaakt of **Year(@created)** voor het jaar waarin een profiel is gemaakt.
   * **&lt;comparison operator>** een van de operatoren is die worden vermeld in de sectie [Vergelijkingsoperatoren](../../automating/using/advanced-expression-editing.md#comparison-operators). Deze operator definieert de vergelijkingsmethode tussen **&lt;value1>** en **&lt;value2>**.
   * **&lt;value2>** een veld, een functie of een waarde is die handmatig wordt ingevoerd.

   >[!NOTE]
   >
   >De typegegevens voor **&lt;value1>** en **&lt;value2>** moeten identiek zijn. Als **&lt;value1>** bijvoorbeeld een datum is, moet **&lt;value2>** ook een datum zijn.

* Als u meerdere voorwaarden wilt gebruiken, kunt u deze combineren met logische operatoren.

   * **[!UICONTROL AND]**: Twee voorwaarden hebben een doorsnede.
   * **[!UICONTROL OR]**: Twee voorwaarden zijn gecombineerd.

Bijvoorbeeld:

```
Year(@created) = Year(GetDate()) AND Month(@created) = Month(GetDate())
```

In dit voorbeeld worden de profielen doelgericht benaderd waarvan de aanmaakdatum in de huidige maand en het huidige jaar ligt.

### JavaScript-syntaxis {#javascript-syntax}

Wanneer u de zichtbaarheidsvoorwaarden definieert voor een tekstblok van de HTML-contenteditor, moet u een expressie gebruiken met syntaxis voor JavaScript-typen.

JavaScript-expressies bestaan uit een of meer voorwaarden en gebruiken de volgende syntaxiselementen:

* Elke voorwaarde heeft de volgende vorm: **&lt;context> &lt;comparison operator> &lt;value2>** waarbij:

   * **&lt;context>** een veld of functie is waarmee u de context kunt opgeven. Bijvoorbeeld **context.profile.@email** voor het e-mailadres van een profiel of **context.profile.firstName.length()** voor het aantal tekens in de voornaam van een profiel.
   * **&lt;comparison operator>** een van de operatoren is die worden vermeld in de sectie [Vergelijkingsoperatoren](../../automating/using/advanced-expression-editing.md#comparison-operators). Deze operator definieert de vergelijkingsmethode tussen **&lt;context>** en **&lt;value2>**.
   * **&lt;value2>** een veld, een functie of een waarde is die handmatig wordt ingevoerd.

   >[!NOTE]
   De typegegevens voor **&lt;context>** en **&lt;value2>** moeten identiek zijn. Als **&lt;context>** bijvoorbeeld een datum is, moet **&lt;value2>** ook een datum zijn.

* Als u meerdere voorwaarden wilt gebruiken, kunt u deze combineren met logische operatoren.

   * **[!UICONTROL &&]**: Twee voorwaarden hebben een doorsnede.
   * **[!UICONTROL ||]**: Twee voorwaarden zijn gecombineerd.

Bijvoorbeeld:

```
context.profile.age > 21 && context.profile.firstName.length() > 0
```

In dit voorbeeld worden profielen die ouder zijn dan 21 jaar en waarvan de voornaam is opgegeven (gesymboliseerd door het feit dat het veld **firstName** ten minste één teken bevat), doelgericht benaderd.

## Vergelijkingsoperatoren {#comparison-operators}

Voor sommige regels kunt u met de query-editor een waarde kiezen om uw voorwaarde te definiëren.

De voorwaarden moeten aan waarden zijn gekoppeld aan de hand van een van de volgende operatoren.

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
   <td> <span class="uicontrol">Equal to</span> <br /> </td> 
   <td> =<br /> </td> 
   <td> ==<br /> </td> 
   <td> De eerste waarde moet volledig identiek zijn aan de tweede waarde.<br /> </td> 
   <td> <strong>@lastName = Martin</strong> haalt profielen op waarvan de achternaam 'Martin' is, met alleen deze identieke tekens.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Greater than</span> <br /> </td> 
   <td> &gt;<br /> </td> 
   <td> &gt;<br /> </td> 
   <td> De eerste waarde moet categorisch groter zijn dan de tweede waarde.<br /> </td> 
   <td> <strong>@age &gt; 50</strong> haalt profielen op die ouder zijn dan 50, dus 51, 52 enzovoort.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Less than</span> <br /> </td> 
   <td> &lt;<br /> </td> 
   <td> &lt;<br /> </td> 
   <td> De eerste waarde moet categorisch kleiner zijn dan de tweede waarde.<br /> </td> 
   <td> <strong>@created &lt; DaysAgo(100)</strong> haalt alle profielen op die minder dan 100 dagen geleden in de database zijn gemaakt.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Greater than or equal to</span> <br /> </td> 
   <td> &gt;=<br /> </td> 
   <td> &gt;=<br /> </td> 
   <td> De eerste waarde moet groter zijn dan of gelijk zijn aan de tweede waarde.<br /> </td> 
   <td> <strong>@age &gt;= 30</strong> haalt profielen van 30 jaar en ouder op.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Less than or equal to</span> <br /> </td> 
   <td> &lt;=<br /> </td> 
   <td> &lt;=<br /> </td> 
   <td> De eerste waarde moet kleiner zijn dan of gelijk zijn aan de tweede waarde.<br /> </td> 
   <td> <strong>@age &lt;= 60</strong> haalt profielen van 60 jaar of jonger op.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Different </span> <br /> </td> 
   <td> !=<br /> </td> 
   <td> !=<br /> </td> 
   <td> De eerste waarde moet afwijken van de tweede waarde.<br /> </td> 
   <td> <strong>@language != English</strong> haalt profielen op die niet als Engelssprekend zijn gedefinieerd.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Contains</span> <br /> </td> 
   <td> IN<br /> </td> 
   <td> N.v.t.<br /> </td> 
   <td> De eerste waarde moet de tweede waarde bevatten.<br /> </td> 
   <td> <strong>@domain IN mail</strong>. Hier worden alle domeinnamen met de waarde 'mail' geretourneerd in het resultaat. Daarom zal de domeinnaam ‘gmail.com’ deel uitmaken van de geretourneerde resultaten.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Like</span> <br /> </td> 
   <td> LIKE<br /> </td> 
   <td> N.v.t.<br /> </td> 
   <td> <span class="uicontrol">Like</span> lijkt heel sterk op de operator <span class="uicontrol">Contains</span>. Hiermee kunt u een jokerteken <span class="uicontrol">%</span> invoegen in de waarde die wordt gezocht.<br /> </td> 
   <td> <strong>@lastName LIKE Mart%n</strong>. Hier fungeert het vervangende teken <strong>%</strong> als een jokerteken om de naam ‘Martin’ te zoeken in het hypothetische geval dat de spelling niet correct is.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Not like</span> <br /> </td> 
   <td> NOT<br /> </td> 
   <td> N.v.t.<br /> </td> 
   <td> Heeft overeenkomsten met <span class="uicontrol">Like</span>. Hiermee kunt u de ingevoerde waarde overslaan. Ook hier moet de ingevoerde waarde het jokerteken <span class="uicontrol">%</span> bevatten.<br /> </td> 
   <td> <strong>@lastName NOT Smi%h</strong>. Hier worden de ontvangers die overeenkomen met de naam ‘Smi%h’ (dus Smith, enz.) niet geretourneerd.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Is empty</span> <br /> </td> 
   <td> IS NULL<br /> </td> 
   <td> N.v.t.<br /> </td> 
   <td> De eerste waarde moet overeenkomen met een lege waarde.<br /> </td> 
   <td> <strong>@mobilePhone IS NULL</strong> haalt alle profielen op waarvan het mobiele telefoonnummer niet is opgegeven.<br /> </td> 
  </tr> 
 </tbody> 
</table>

