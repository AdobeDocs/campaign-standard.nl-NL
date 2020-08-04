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
source-git-commit: 3bd2fdb56fc94cef4e9c21466a33cdad7ac825d2
workflow-type: tm+mt
source-wordcount: '1754'
ht-degree: 94%

---


# Externe API {#external-api}

## Beschrijving {#description}

![](assets/wf_externalAPI.png)

De activiteit **[!UICONTROL External API]** brengt data vanaf een **extern systeem** in de workflow via een **HTTP API**-aanroep.

De eindpunten van het externe systeem kunnen openbare API-eindpunten, klantenbeheersystemen of serverloze applicatie-instanties (bijvoorbeeld [Adobe I/O Runtime](https://www.adobe.io/apis/experienceplatform/runtime.html)) zijn, om maar een paar categorieën te noemen.

>[!NOTE]
>
>Om veiligheidsredenen wordt het gebruik van JSSP&#39;s niet ondersteund in Campaign Standard. Als u code moet uitvoeren, kunt u een Adobe I/O Runtime-instantie aanroepen via de activiteit Externe API.

De belangrijkste kenmerken van deze activiteit zijn:

* Mogelijkheid om data in een JSON-indeling door te geven aan een REST API-eindpunt van derden
* Mogelijkheid om een JSON-antwoord terug te krijgen, het toe te wijzen aan uitvoertabellen en stroomafwaarts door te geven aan andere workflowactiviteiten.
* Het beheer van mislukkingen met een specifieke uitgaande overgang

### Overgang van bèta naar GA {#from-beta-to-ga}

Met de Campaign Standard 20.3-release is de functionaliteit Externe API van bèta naar algemene beschikbaarheid (GA) verplaatst.

>[!CAUTION]
>
>Daardoor moet u, als u bèta-activiteiten voor Externe API gebruikte, deze vervangen door GA-activiteiten voor Externe API in alle workflows.  Workflows die de bètaversie van Externe API gebruiken, werken niet meer vanaf versie 20.3.

Wanneer u activiteiten voor Externe API vervangt, voegt u de nieuwe activiteit Externe API toe aan de workflow, kopieert u handmatig de configuratiedetails en verwijdert u vervolgens de oude activiteit.

>[!NOTE]
>
>U kunt geen koptekstwaarden kopiëren omdat deze binnen de activiteit gemaskeerd zijn.

Vervolgens configureert u opnieuw andere activiteiten in de workflow die verwijzen naar en/of gebruik maken van data uit de bèta-activiteit voor Externe API om in plaats daarvan te verwijzen naar en/of gebruik te maken van data uit de nieuwe activiteit Externe API. Voorbeelden van activiteiten: e-maillevering (personalisatievelden), verrijkingsactiviteit, enz.

### Beperkingen en beveiligingen {#guardrails}

Op deze activiteit zijn de volgende instructies van toepassing:

* 50 MB http response data size limit (5 MB aanbevolen)
* Time-out voor aanvraag bedraagt 10 minuten
* HTTP-omleidingen zijn niet toegestaan
* Niet-HTTPS-URL&#39;s worden geweigerd
* Aanvraagheader ‘Accept: application/json’ en antwoordheader ‘Content-Type: application/json’ zijn toegestaan

>[!NOTE]
>
>Vanaf de release van Campagne 20.4 worden de beperking voor de grootte van de http-responsgegevens en de time-outinstructies voor de respons verlaagd naar respectievelijk 5 MB en 1 minuut.  Hoewel deze wijziging alleen van invloed is op nieuwe externe API-activiteiten, wordt ten zeerste aanbevolen de huidige implementaties van de externe API-activiteit af te stemmen op deze nieuwe instructies om de best practices te volgen.

Voor JSON zijn specifieke beveiligingen ingevoerd:

* **JSON Max Depth**: Beperk de maximumdiepte van een aangepaste geneste JSON die kan worden verwerkt tot 10 niveaus.
* **JSON Max Key Length**: Beperk de maximumlengte van de gegenereerde interne sleutel tot 255. Deze sleutel is gekoppeld aan de kolom-id.
* **JSON Max Duplicate Keys Allowed**: Beperk het maximumaantal dubbele JSON-eigenschapsnamen, die als kolom-id worden gebruikt, tot 150.

De activiteit ondersteunt de JSON-structuur niet als:

* Een matrixobject wordt gecombineerd met andere niet-matrixelementen
* Een JSON-matrixobject is genest binnen een of meer tussenliggende matrixobjecten.

>[!CAUTION]
>
>De externe API-activiteit is bedoeld voor het ophalen van gegevens voor de hele campagne (laatste reeks aanbiedingen, laatste scores, enz.), niet voor het ophalen van specifieke informatie voor elk profiel, omdat dit kan leiden tot de overdracht van grote hoeveelheden gegevens. Als het gebruiksscenario dit vereist, wordt aangeraden om de activiteit [Transfer File](../../automating/using/transfer-file.md) te gebruiken.

## Configuratie {#configuration}

Sleep een activiteit **[!UICONTROL External API]** en zet deze neer in uw workflow en open de activiteit om de configuratie te beginnen.

### Inbound Mapping

Inbound mapping is een tijdelijke tabel die door een vorige binnenkomende activiteit wordt gegenereerd en die als JSON in de gebruikersinterface wordt weergegeven en verzonden.
Op basis van deze tijdelijke tabel kan de gebruiker wijzigingen in binnenkomende data aanbrengen.

![](assets/externalAPI-inbound.png)

Met de vervolgkeuzelijst **Inbound resource** kunt u de activiteit Query selecteren waardoor de tijdelijke tabel zal worden gemaakt.

Met het selectievakje **Add count parameter** wordt een telwaarde toegevoegd voor elke rij die uit de tijdelijke tabel komt. Merk op dat dit selectievakje alleen beschikbaar is als de binnenkomende activiteit een tijdelijke tabel genereert.

Met de sectie **Inbound Columns** kan de gebruiker willekeurige velden uit de tabel met binnenkomende overgangen toevoegen. De geselecteerde kolommen fungeren als de sleutels in het dataobject. Het dataobject in de JSON wordt een matrixlijst met data voor geselecteerde kolommen uit elke rij van de tabel met binnenkomende overgangen.

In het tekstvak **Customize parameter** kunt u een geldige JSON toevoegen met aanvullende data die nodig zijn voor de externe API. Deze aanvullende data worden toegevoegd aan het parameterobject in de gegenereerde JSON.

### Outbound Mapping

Op dit tabblad kunt u de **JSON-voorbeeldstructuur** definiëren die door de API-aanroep wordt geretourneerd.

![](assets/externalAPI-outbound.png)

De JSON-parser is ontworpen voor standaard typen JSON-structuurpatronen, met enkele uitzonderingen. Een voorbeeld van een standaard patroon is:`{“data”:[{“key”:“value”}, {“key”:“value”},...]}`

De JSON-voorbeelddefinitie moet de **volgende kenmerken** hebben:

* **Matrixelementen** moeten eigenschappen op het eerste niveau bevatten (diepere niveaus worden niet ondersteund).
   **Eigenschapsnamen** worden uiteindelijk de kolomnamen voor het uitvoerschema van de tijdelijke uitvoertabel.
* **JSON-elementen** die moeten worden vastgelegd, moeten zich binnen de eerste 10 nestniveaus van het JSON-antwoord bevinden.
* **De kolomnaamdefinitie** is gebaseerd op het eerste element van de ‘data’-matrix.
De definitie van kolommen (toevoegen/verwijderen) en de typewaarde van de eigenschap kunnen in het tabblad **Column definition** worden bewerkt.

Gedrag van het selectievakje **Flatten**:

Het selectievakje Flatten (standaard niet ingeschakeld) wordt opgegeven om aan te geven of de JSON al dan niet moet worden afgevlakt tot een sleutel-/waardetoewijzing.

* Wanneer het **selectievakje is uitgeschakeld** (niet geselecteerd), wordt de voorbeeld-JSON geparseerd om naar een matrixobject te zoeken. De gebruiker moet een bijgesneden versie van de JSON-voorbeeldindeling voor API-antwoorden opgeven, zodat Adobe Campaign precies kan bepalen in welke matrix de gebruiker geïnteresseerd is. Tijdens het ontwerpen van de workflow wordt het pad naar het geneste matrixobject bepaald en opgenomen, zodat het tijdens de uitvoering kan worden gebruikt om toegang te krijgen tot het matrixobject van de JSON-antwoordtekst dat van de API-aanroep is ontvangen.

* Wanneer het **selectievakje is ingeschakeld** (geselecteerd), wordt de voorbeeld-JSON afgevlakt en worden alle eigenschappen die in de opgegeven voorbeeld-JSON zijn gespecificeerd, gebruikt om kolommen van de tijdelijke uitvoertabel te maken en worden deze weergegeven op het tabblad Column definition. Als er een matrixobject in de voorbeeld-JSON voorkomt, worden alle elementen van die matrixobjecten ook afgevlakt.


Als de **parsering wordt gevalideerd**, verschijnt er een bericht waarin u wordt gevraagd de datatoewijzing op het tabblad Column definition aan te passen. In andere gevallen wordt een foutbericht weergegeven.

### Execution

Met dit tabblad kunt u het **HTTPS-eindpunt** definiëren dat data naar ACS zal verzenden. Indien nodig kunt u verificatidata invoeren in de onderstaande velden.
![](assets/externalAPI-execution.png)

### Properties

Op dit tabblad kunt u **algemene eigenschappen** voor de activiteit Externe API bepalen, zoals het weergegeven label in de gebruikersinterface. De interne id kan niet worden aangepast.

![](assets/externalAPI-properties.png)

### Column definition

>[!NOTE]
>
>Dit tabblad wordt weergegeven wanneer de **data-indeling van het antwoord** is voltooid en gevalideerd op het tabblad Outbound Mapping.

Op het tabblad **Column definition** kunt u nauwkeurig de datastructuur van elke kolom opgeven om data te importeren die geen fouten bevatten en deze in overeenstemming te brengen met de typen die al aanwezig zijn in de Adobe Campaign-database voor toekomstige bewerkingen.

![](assets/externalAPI-column.png)

U kunt bijvoorbeeld het label van een kolom wijzigen, het type kolom selecteren (tekenreeks, geheel getal, datum, enzovoort) of zelfs foutverwerking opgeven.

Raadpleeg de sectie [Bestand laden](../../automating/using/load-file.md) voor meer informatie.

### Transition

Op dit tabblad kunt u de **uitgaande overgang** en het label ervan activeren. Deze specifieke overgang is nuttig in het geval van **time-outs** of als de payload de **groottelimiet van data** overschrijdt.

![](assets/externalAPI-transition.png)

### Execution options

Dit tabblad is beschikbaar voor de meeste workflowactiviteiten. Raadpleeg de sectie [Activiteitseigenschappen](../../automating/using/activity-properties.md) voor meer informatie.

![](assets/externalAPI-options.png)

## Problemen oplossen

Er zijn twee soorten logboekberichten die aan deze nieuwe workflowactiviteit worden toegevoegd: informatie en fouten. Ze kunnen u helpen potentiële problemen op te lossen.

### Informatie

Deze logboekberichten worden gebruikt om informatie over nuttige controlepunten tijdens de uitvoering van de workflowactiviteit in een logboek te registreren. Specifiek worden de volgende logboekberichten gebruikt om de eerste poging om toegang tot de API te krijgen evenals een nieuwe poging (en de reden voor mislukking van de eerste poging) in een logboek te registreren.

<table> 
 <thead> 
  <tr> 
   <th> Berichtindeling<br /> </th> 
   <th> Voorbeeld<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Invoking API URL '%s'.</td> 
   <td> <p>Invoking API URL 'https://example.com/api/v1/web-coupon?count=2'.</p></td> 
  </tr> 
  <tr> 
   <td> Retrying API URL '%s', previous attempt failed ('%s').</td> 
   <td> <p>Retrying API URL 'https://example.com/api/v1/web-coupon?count=2', previous attempt failed ('HTTP - 401').</p></td>
  </tr> 
  <tr> 
   <td> Transferring content from '%s' (%s / %s).</td> 
   <td> <p>Transferring content from 'https://example.com/api/v1/web-coupon?count=2' (1234 / 1234).</p></td> 
  </tr>
 </tbody> 
</table>

### Fouten

Deze logboekberichten worden gebruikt om informatie in een logboek te registreren over onverwachte fouten die ertoe kunnen leiden dat de workflowactiviteit mislukt.

<table> 
 <thead> 
  <tr> 
   <th> Code - Berichtindeling<br /> </th> 
   <th> Voorbeeld<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> WKF-560250 - API request body exceeded limit (limit: '%d').</td> 
   <td> <p>API request body exceeded limit (limit: '5242880').</p></td> 
  </tr> 
  <tr> 
   <td> WKF-560239 -  API response exceeded limit (limit: '%d').</td> 
   <td> <p>API response exceeded limit (limit: 5242880').</p></td> 
  </tr> 
  <tr> 
   <td> WKF-560245 - API URL could not be parsed (error: '%d').</td> 
   <td> <p>API URL could not be parsed (error: '-2010').</p>
   <p> Opmerking: Deze fout wordt in een logboek geregistreerd wanneer validatieregels mislukken voor de API URL.</p></td>
  </tr> 
  <tr>
   <td> WKF-560244 - API URL host must not be 'localhost', or IP address literal (URL host: '%s').</td> 
   <td> <p>API URL host must not be 'localhost', or IP address literal (URL host: 'localhost').</p>
    <p>API URL host must not be 'localhost', or IP address literal (URL host: '192.168.0.5').</p>
    <p>API URL host must not be 'localhost', or IP address literal (URL host: '[2001]').</p></td>
  </tr> 
  <tr> 
   <td> WKF-560238 - API URL must be a secure URL (https) (requested URL: '%s').</td> 
   <td> <p>API URL must be a secure URL (https) (requested URL: 'https://example.com/api/v1/web-coupon?count=2').</p></td> 
  </tr> 
  <tr> 
   <td> WKF-560249 - Failed to create request body JSON. Error when adding '%s'.</td> 
   <td> <p>Failed to create request body JSON. Error when adding 'params'.</p>
    <p>Failed to create request body JSON. Error when adding 'data'.</p></td>
  </tr> 
  <tr> 
   <td> WKF-560246 - HTTP header key is bad (header key: '%s').</td> 
   <td> <p>HTTP header key is bad (header key: '%s').</p>
   <p> Opmerking: Deze fout wordt in een logboek geregistreerd wanneer de aangepaste koptekstsleutel niet kan worden gevalideerd volgens <a href="https://tools.ietf.org/html/rfc7230#section-3.2.html">RFC</a></p></td> 
  </tr>
 <tr> 
   <td> WKF-560248 - HTTP header key is not allowed (header key: '%s').</td> 
   <td> <p>HTTP header key is not allowed (header key: 'Accept').</p></td> 
  </tr> 
  <tr> 
   <td> WKF-560247 -  AHTTP header value is bad (header value: '%s').</td> 
   <td> <p>HTTP header value is bad (header value: '%s'). </p>
    <p>Opmerking: Deze fout wordt in een logboek geregistreerd wanneer de aangepaste koptekstwaarde niet kan worden gevalideerd volgens <a href="https://tools.ietf.org/html/rfc7230#section-3.2.html">RFC</a></p></td> 
  </tr> 
  <tr> 
   <td> WKF-560240 - JSON payload has bad property '%s'.</td> 
   <td> <p>JSON payload has bad property 'blah'.</p></td>
  </tr> 
  <tr>
   <td> WKF-560241 - Malformed JSON or unacceptable format.</td> 
   <td> <p>Onjuiste JSON of onaanvaardbare indeling.</p>
   <p>Opmerking: Dit bericht is alleen van toepassing op het parseren van de antwoordtekst van de externe API en wordt in een logboek geregistreerd bij een poging te valideren of de antwoordtekst voldoet aan de JSON-indeling die wordt voorgeschreven door deze activiteit.</p></td>
  </tr>
  <tr> 
   <td> WKF-560246 - Activity failed (reason: '%s').</td> 
   <td> <p>When activity fails due to HTTP 401 error response - Activity failed (reason: 'HTTP - 401')</p>
        <p>When activity fails due to a failed internal call - Activity failed (reason: 'iRc - -Nn').</p>
        <p>When activity fails due to an invalid Content-Type header. - Activity failed (reason: 'Content-Type - application/html').</p></td> 
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
