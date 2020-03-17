---
title: Externe API
description: null
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: externalAPI,workflow,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6f7f4f3d81f4e6a540b3317f283c1e2311ccc65a

---


# Externe API {#external-api}

## Beschrijving {#description}

![](assets/wf_externalAPI.png)

De **[!UICONTROL External API]** activiteit brengt gegevens in het werkschema van een **extern systeem** via een **REST API** vraag.

De REST-eindpunten kunnen een clientbeheersysteem, een [Adobe I/O-runtime](https://www.adobe.io/apis/experienceplatform/runtime.html) -instantie of een Experience Cloud REST-eindpunten zijn (Data Platform, Target, Analytics, Campaign, enz.).

>[!NOTE]
>
>Om veiligheidsredenen wordt het gebruik van JSSPs niet gesteund in de Norm van de Campagne. Als u code moet uitvoeren, kunt u een Adobe I/O Runtime instantie via de Externe API activiteit roepen.

>[!IMPORTANT]
>
>Deze mogelijkheid is momenteel beschikbaar in bèta. U moet de gebruiksovereenkomst accepteren voordat u begint met het gebruik van de externe API-activiteit. Houd er rekening mee dat deze bètamogelijkheid nog niet door Adobe commercieel is uitgebracht en dat deze niet door Adobe Client Care wordt ondersteund. De bètafunctie bevat mogelijk fouten en werkt mogelijk niet zo goed als andere vrijgegeven functies.

De belangrijkste kenmerken van deze activiteit zijn:

* Mogelijkheid om gegevens in een JSON-indeling door te geven aan een ander REST API-eindpunt
* Mogelijkheid om een JSON-reactie terug te ontvangen, deze toe te wijzen aan uitvoertabellen en stroomafwaarts door te geven aan andere workflowactiviteiten.
* Het beheer van de mislukking met een uitgaande specifieke overgang

Voor deze activiteit zijn de volgende voorzorgsmaatregelen getroffen:

* 5MB http-limiet voor gegevensgrootte
* De time-out van het verzoek is 60 seconden
* HTTP-omleidingen zijn niet toegestaan
* Niet-HTTPS-URL&#39;s worden geweigerd
* &quot;Accepteren: application/json&quot;-aanvraagheader en &quot;Content-Type: application/json&quot;-responsheader is toegestaan

>[!CAUTION]
>
>Houd er rekening mee dat de activiteit bedoeld is voor het ophalen van gegevens voor de hele campagne (laatste reeks aanbiedingen, laatste scores, enz.) niet voor het ophalen van specifieke informatie voor elk profiel, omdat dit kan leiden tot grote hoeveelheden gegevens die worden overgedragen. Als het gebruiksgeval dit vereist, is de aanbeveling om de activiteit van het Dossier [van de](../../automating/using/transfer-file.md) Overdracht te gebruiken.

## Configuratie {#configuration}

Sleep en zet een **[!UICONTROL External API]** activiteit neer in uw werkschema en open de activiteit om de configuratie te beginnen.

### Binnenkomende toewijzing

De binnenkomende afbeelding is een tijdelijke lijst die door een vorige binnenkomende activiteit wordt geproduceerd die als JSON in UI zal worden getoond en worden verzonden.
Gebaseerd op deze tijdelijke lijst, kan de gebruiker wijziging aan binnenkomende gegevens aanbrengen.

![](assets/externalAPI-inbound.png)

Het **Binnenkomende middeldrop** laat u de vraagactiviteit selecteren die tot de tijdelijke lijst zal leiden.

Met het selectievakje **Telparameter** toevoegen wordt een telwaarde ingesteld voor elke rij die uit de tijdelijke tabel komt. Merk op dat dit checkbox slechts beschikbaar is als de binnenkomende activiteit een tijdelijke lijst produceert.

Met de sectie **Binnenkomende kolommen** kan de gebruiker alle velden uit de binnenkomende overgangstabel toevoegen. De geselecteerde kolom(men) zijn de sleutels in het gegevensobject. Het gegevensobject in de JSON wordt een arraylijst met gegevens voor geselecteerde kolommen uit elke rij van de binnenkomende overgangstabel.

In het tekstvak parametertekst **** aanpassen kunt u een geldige JSON toevoegen met aanvullende gegevens die nodig zijn voor de externe API. Deze aanvullende gegevens worden toegevoegd aan het paramideobject in de gegenereerde JSON.

### Uitgaande toewijzing

Op dit tabblad kunt u de voorbeeld- **JSON-structuur** definiëren die door de API-aanroep wordt geretourneerd.

![](assets/externalAPI-outbound.png)

Het JSON-structuurpatroon is: `{“data”:[{“key”:“value”}, {“key”:“value”},...]}`

De JSON-voorbeelddefinitie moet de **volgende kenmerken** hebben:

* **data** is een verplichte eigenschapnaam in de JSON, de inhoud van &quot;data&quot; is een JSON-array.
* **Array-elementen** moeten eigenschappen op het eerste niveau bevatten (diepere niveaus worden niet ondersteund).
   **Namen** van eigenschappen worden uiteindelijk kolomnamen voor het uitvoerschema van de tijdelijke uitvoertabel.
* **De kolomnaamdefinitie** is gebaseerd op het eerste element van de array &#39;data&#39;.
De definitie van kolommen (toevoegen/verwijderen) en de typewaarde van het bezit kunnen in de de definitietabel **van de** Kolom worden uitgegeven.

Als de **parsering wordt gevalideerd** , verschijnt er een bericht waarin u wordt gevraagd de gegevenstoewijzing op het tabblad &quot;Kolomdefinitie&quot; aan te passen. In andere gevallen wordt een foutbericht weergegeven.

### Uitvoering

Dit lusje laat u het Eindpunt **bepalen** HTTPS dat gegevens naar ACS zal verzenden. Indien nodig kunt u verificatiegegevens invoeren in de onderstaande velden.
![](assets/externalAPI-execution.png)

### Eigenschappen

Op dit tabblad kunt u **algemene eigenschappen** voor de externe API-activiteit instellen, zoals het weergegeven label in de gebruikersinterface. De interne id kan niet worden aangepast.

![](assets/externalAPI-properties.png)

### Kolomdefinitie

>[!NOTE]
>
>Dit tabblad wordt weergegeven wanneer de indeling **van de** reactiegegevens is voltooid en gevalideerd op het tabblad Uitgaande toewijzing.

Op het tabblad **Kolomdefinitie** kunt u nauwkeurig de gegevensstructuur van elke kolom opgeven om gegevens te importeren die geen fouten bevatten en deze in overeenstemming te brengen met de typen die al aanwezig zijn in de Adobe Campagne-database voor toekomstige bewerkingen.

![](assets/externalAPI-column.png)

U kunt bijvoorbeeld het label van een kolom wijzigen, het type kolom selecteren (tekenreeks, geheel getal, datum, enzovoort) of zelfs foutverwerking opgeven.

Raadpleeg de sectie Bestand [](../../automating/using/load-file.md) laden voor meer informatie.

### Overgang

Op dit tabblad kunt u de **uitgaande overgang** en het label ervan activeren. Deze specifieke overgang is nuttig in het geval van **onderbreking** of als de lading de grens **van de** gegevensgrootte overschrijdt.

![](assets/externalAPI-transition.png)

### Uitvoeropties

Dit tabblad is beschikbaar voor de meeste workflowactiviteiten. Raadpleeg de sectie [Activiteiteneigenschappen](../../automating/using/executing-a-workflow.md#activity-properties) voor meer informatie.

![](assets/externalAPI-options.png)

## Problemen oplossen

Er zijn twee soorten logboekberichten die aan deze nieuwe werkschemaactiviteit worden toegevoegd: informatie en fouten. Ze kunnen u helpen potentiële problemen op te lossen.

### Informatie

Deze logboekberichten worden gebruikt om informatie over nuttige controlepunten tijdens de uitvoering van de werkschemaactiviteit te registreren. Specifiek, worden de volgende logboekberichten gebruikt om de eerste poging evenals een nieuwe poging (en reden voor mislukking van eerste poging) te registreren om tot API toegang te hebben.

<table> 
 <thead> 
  <tr> 
   <th> Berichtindeling<br /> </th> 
   <th> Voorbeeld<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> API-URL '%s' aanroepen.</td> 
   <td> <p>API-URL 'https://example.com/api/v1/web-coupon?count=2' aanroepen.</p></td> 
  </tr> 
  <tr> 
   <td> API-URL '%s' opnieuw proberen, vorige poging mislukt ('%s').</td> 
   <td> <p>Opnieuw proberen van API URL 'https://example.com/api/v1/web-coupon?count=2', vorige poging mislukt ('HTTP - 401').</p></td>
  </tr> 
  <tr> 
   <td> Inhoud overbrengen van '%s' (%s / %s).</td> 
   <td> <p>Inhoud overbrengen van 'https://example.com/api/v1/web-coupon?count=2' (1234 / 1234).</p></td> 
  </tr>
 </tbody> 
</table>

### Fouten

Deze logboekberichten worden gebruikt om informatie over onverwachte foutenvoorwaarden te registreren, die de werkschemaactiviteit kunnen uiteindelijk veroorzaken om te ontbreken.

<table> 
 <thead> 
  <tr> 
   <th> Code - Berichtenopmaak<br /> </th> 
   <th> Voorbeeld<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> WKF-560250 - De limiet voor de body van de API-aanvraag is overschreden (limiet: '%d').</td> 
   <td> <p>Hoofdtekst van API-verzoek is overschreden (limiet: "5242880").</p></td> 
  </tr> 
  <tr> 
   <td> WKF-560239 - API-respons overschrijdt limiet (limiet: '%d').</td> 
   <td> <p>Limiet voor API-reactie overschreden (limiet: 5242880").</p></td> 
  </tr> 
  <tr> 
   <td> WKF-560245 - API-URL kan niet worden geparseerd (fout: '%d').</td> 
   <td> <p>API-URL kan niet worden geparseerd (fout: "-2010").</p>
   <p> Opmerking: Deze fout wordt geregistreerd wanneer API URL bevestigingsregels ontbreekt.</p></td>
  </tr> 
  <tr>
   <td> WKF-560244 - de gastheer van API URL moet niet "localhost"zijn, of IP adres letterlijk (gastheer URL: '%s').</td> 
   <td> <p>API URL-host mag geen 'localhost' of letterlijk IP-adres (URL-host: "localhost").</p>
    <p>API URL-host mag geen 'localhost' of letterlijk IP-adres (URL-host: "192.168.0.5").</p>
    <p>API URL-host mag geen 'localhost' of letterlijk IP-adres (URL-host: "[2001]").</p></td>
  </tr> 
  <tr> 
   <td> WKF-560238 - API URL moet een veilige URL (https) zijn (gevraagde URL: '%s').</td> 
   <td> <p>API-URL moet een beveiligde URL (https) zijn (aangevraagde URL: "https://example.com/api/v1/web-coupon?count=2').</p></td> 
  </tr> 
  <tr> 
   <td> WKF-560249 - Kan aanvraagbody JSON niet maken. Fout bij het toevoegen van '%s'.</td> 
   <td> <p>Failed to create request body JSON. Fout bij het toevoegen van 'params'.</p>
    <p>Failed to create request body JSON. Fout bij het toevoegen van 'data'.</p></td>
  </tr> 
  <tr> 
   <td> WKF-560246 - HTTP-headersleutel is ongeldig (headersleutel: '%s').</td> 
   <td> <p>HTTP-headersleutel is ongeldig (headersleutel: '%s').</p>
   <p> Opmerking: Deze fout wordt geregistreerd als de aangepaste headersleutel niet kan worden gevalideerd volgens <a href="https://tools.ietf.org/html/rfc7230#section-3.2.html">RFC</a></p></td> 
  </tr>
 <tr> 
   <td> WKF-560248 - HTTP-headersleutel is niet toegestaan (headersleutel: '%s').</td> 
   <td> <p>HTTP-headersleutel is niet toegestaan (headersleutel: "Accepteren").</p></td> 
  </tr> 
  <tr> 
   <td> WKF-560247 - AHTTP-headerwaarde is ongeldig (headerwaarde: '%s').</td> 
   <td> <p>HTTP-headerwaarde is ongeldig (headerwaarde: '%s'). </p>
    <p>Opmerking: Deze fout wordt geregistreerd als de aangepaste headerwaarde niet kan worden gevalideerd volgens <a href="https://tools.ietf.org/html/rfc7230#section-3.2.html">RFC</a></p></td> 
  </tr> 
  <tr> 
   <td> WKF-560240 - JSON-payload heeft ongeldige eigenschap '%s'.</td> 
   <td> <p>JSON payload heeft ongeldige eigenschap 'blah'.</p></td>
  </tr> 
  <tr>
   <td> WKF-560241 - Onjuist gevormde JSON of onacceptabel formaat.</td> 
   <td> <p>Onjuiste JSON of onaanvaardbare indeling.</p>
   <p>Opmerking: Dit bericht is alleen van toepassing op het parseren van de responsstructuur van de externe API en wordt vastgelegd wanneer wordt geprobeerd te valideren of de responsstructuur voldoet aan de JSON-indeling die is ingesteld door deze activiteit.</p></td>
  </tr>
  <tr> 
   <td> WKF-560246 - De activiteit is mislukt (reden: '%s').</td> 
   <td> <p>Wanneer de activiteit wegens de foutenreactie van HTTP 401 ontbreekt - de Activiteit ontbrak (reden: 'HTTP - 401')</p>
        <p>Wanneer de activiteit wegens een ontbroken interne vraag ontbreekt - de Activiteit ontbrak (reden: 'iRc - -Nn').</p>
        <p>Wanneer de activiteit wegens een ongeldige inhoud-Type kopbal ontbreekt. - Activiteit mislukt (reden: 'Content-Type - application/html').</p></td> 
  </tr>
 </tbody> 
</table>

<!--
## Example: Managing coupons with External API Activity

This example illustrates how to **add coupon value** retrieving by a REST call to profiles and then sending an email containing these coupon values.

The workflow is presented as follows:

![](assets/externalAPI_activity_example1.png)

1. Drag and drop an **External API** activity
    1. Parse the JSON sample responsa as {"data":[{"code":"value"}]}.
    1. Add the **Rest endpoint URL** and define authentication setting if needed
    ![](assets/externalAPI_activity_example2.png)
    1. In the **column definition** tab, add a new column called **code** that will store the code value.
        ![](assets/externalAPI_activity_example3.png)
    1. Enabled an **outbound transition** to manage request failures.
1. Drag and drop a **Query** activity
    1. Configure the **Target** tab to query all the **@adobe.com** email. For different Query samples, refer to the [Query](../../automating/using/query.md) section.
    1. In the **additional data** tab, add a new column based on **rowId()** function. This additional column allows you to reconciliate coupon code with the profile ID..
        ![](assets/externalAPI_activity_example4.png)

        >[!NOTE]
        >
        >This reconciliation approach means that the profile query number is equal to the number of coupon values returned by the REST call.
1. Once this two activities are configured, drag and drop an **Enrichment** activity to associate coupon values with profiles.
    1. Select the previous Query activity in the **primarySet** field.
        ![](assets/externalAPI_activity_example5.png)
    1. Create a new relation in the **Advanced relations** tab, and add the following reconciliation criteria:
    1. **@expr1** coming grom the Query activity in the source expression field.
    1. **@lineNum** as an expression that returns the line number for each coupon value in the destination field.
        ![](assets/externalAPI_activity_example6.png)
        More information on the enrichment activity are available [here](../../automating/using/enrichment.md)

    1. The transition **Data Structure** will contain:
        ![](assets/externalAPI_activity_example7.png)
1. Finally drag and drop a **Send via Email** activity.
    You can modify your email template by adding the **code** personnalized field.

-->
