---
solution: Campaign Standard
product: campaign
title: Transactionele berichten beheren
description: Leer hoe u transactieberichten beheert met API's.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: a51943e4da04f5d19aaecdfcf956f5c4f3d804c8
workflow-type: tm+mt
source-wordcount: '678'
ht-degree: 3%

---


# Transactionele berichten beheren {#managing-transactional-messages}

## Informatie over transactieberichten

Nadat u een transactiegebeurtenis hebt gemaakt en gepubliceerd, moet u het activeren van deze gebeurtenis integreren in uw website.

>[!NOTE]
>
>Het vormen van een gebeurtenis wordt voorgesteld in [deze sectie](../../channels/using/configuring-transactional-event.md).

U wilt bijvoorbeeld dat de gebeurtenis &#39;Afkappen met winkelwagentje&#39; wordt geactiveerd wanneer een van uw klanten uw website verlaat voordat ze de producten in hun winkelwagentje kopen. Hiervoor moet uw webontwikkelaar de REST Transaction Messages API gebruiken.

1. De ontwikkelaar verzendt een verzoek volgens de methode van de POST, die [het verzenden van de transactiegebeurtenis ](#sending-a-transactional-event) teweegbrengt.
1. Het antwoord op het verzoek van de POST bevat een Primaire Sleutel, die de ontwikkelaar toestaat om één of veelvoudige verzoeken door een GET verzoek te verzenden. Op deze manier kan hij de [gebeurtenisstatus](#transactional-event-status) verkrijgen.

## Een transactiegebeurtenis verzenden {#sending-a-transactional-event}

De transactionele gebeurtenis wordt verzonden door een verzoek van de POST met de volgende structuur URL:

```
POST https://mc.adobe.io/<ORGANIZATION>/campaign/<transactionalAPI>/<eventID>
```

* **&lt;organization>**: uw persoonlijke ORGANISATIE-ID. Zie [deze sectie](../../api/using/must-read.md).

* **&lt;transactionalapi>**: de Transactional Berichten API endPoints.

   De naam van het Transactionele eindpunt van Berichten API hangt van uw instantieconfiguratie af. Deze komt overeen met de waarde &quot;mc&quot; gevolgd door uw persoonlijke organisatie-id. Laten we het voorbeeld van het Geometrixx-bedrijf nemen, met &#39;geometrixx&#39; als organisatie-id. In dat geval zou het verzoek om POST als volgt zijn:

   `POST https://mc.adobe.io/geometrixx/campaign/mcgeometrixx/<eventID>`

   (Het API-eindpunt voor transactionele berichten is ook zichtbaar tijdens de API-voorvertoning.)

* **&lt;eventid>**: het type gebeurtenis dat u wilt verzenden. Deze id wordt gegenereerd wanneer de gebeurtenisconfiguratie wordt gemaakt (zie [deze sectie](../../channels/using/configuring-transactional-event.md#creating-an-event)).

### POST request header

Het verzoek moet een &quot;Content-Type: application/json&quot;.

U moet een tekenset toevoegen, bijvoorbeeld **utf-8**. Deze waarde is afhankelijk van de REST-toepassing die u gebruikt.

```
-X POST \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-H 'Content-Type: application/json;charset=utf-8' \
-H 'Content-Length:79' \
```

### POST aanvraaginstantie

De gebeurtenisgegevens bevinden zich in de hoofdtekst van de JSON-POST. De gebeurtenisstructuur is afhankelijk van de definitie ervan. De API voorproefknoop in het scherm van de middeldefinitie verstrekt een verzoeksteekproef. Zie [deze sectie](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event).

De volgende optionele parameters kunnen aan de inhoud van de gebeurtenis worden toegevoegd om het verzenden van aan de gebeurtenis gekoppelde transactieberichten te beheren:

* **Vervaldatum**  (optioneel): na deze datum wordt het verzenden van de transactiegebeurtenis geannuleerd.
* **Gepland**  (optioneel): vanaf deze datum wordt de transactie - gebeurtenis verwerkt en wordt het transactiemelding verzonden .

>[!NOTE]
>
>De waarden van de parameters &quot;expiration&quot; en &quot;scheduled&quot; volgen de ISO 8601-indeling. ISO 8601 specificeert het gebruik van de hoofdletter &quot;T&quot; om de datum en de tijd van elkaar te scheiden. Deze kan echter uit de invoer of uitvoer worden verwijderd voor een betere leesbaarheid.

### Antwoord op het verzoek van de POST

De reactie van de POST keert de status van de transactionele gebeurtenis op het tijdstip terug het werd gecreeerd. Om zijn huidige status (gebeurtenisgegevens, gebeurtenisstatus...) terug te winnen, gebruik de Primaire Sleutel door de reactie van de POST in een verzoek van de GET wordt teruggekeerd:

`GET https://mc.adobe.io/<ORGANIZATION>/campaign/<transactionalAPI>/<eventID>/`

<br/>

***Voorbeeldverzoek***

POST vraagt om de gebeurtenis te verzenden.

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/mcAdobe/EVTcartAbandonment \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-H 'Content-Type: application/json;charset=utf-8' \
-H 'Content-Length:79'

{
  "email":"test@example.com",
  "scheduled":"2017-12-01 08:00:00.768Z",
  "expiration":"2017-12-31 08:00:00.768Z",
  "ctx":
  {
    "cartAmount": "$ 125",
    "lastProduct": "Leather motorbike jacket",
    "firstName": "Jack"
  }
}
```

Antwoord op het verzoek van de POST.

```
{
  "PKey":"<PKEY>",
  "ctx":
  {
    "cartAmount": "",
    "lastProduct": "",
    "firstName": ""
  }
  "email":"",
  "scheduled":"2017-12-01 08:00:00.768Z",
  "expiration":"2017-12-31 08:00:00.768Z",
  "href": "mcAdobe/EVTcartAbandonment/<PKEY>",
  "serverUrl":" https://myserver.com ",
  "status":"pending",
  "type":""
}
```

### Status van transactie-gebeurtenis {#transactional-event-status}

In het antwoord kunt u met het veld status weten of de gebeurtenis is verwerkt:

* **in behandeling**: de gebeurtenis is in behandeling - de gebeurtenis neemt deze status over wanneer deze zojuist is geactiveerd.
* **verwerking**: de gebeurtenis is in afwachting van levering - het wordt omgezet in een bericht en het bericht wordt verzonden.
* **gepauzeerd**: het gebeurtenisproces wordt gepauzeerd. Het wordt niet meer verwerkt, maar in een rij in het gegevensbestand van Adobe Campaign bewaard. Raadpleeg [deze sectie](../../channels/using/publishing-transactional-message.md#suspending-a-transactional-message-publication) voor meer informatie.
* **verwerkt**: de gebeurtenis is verwerkt en het bericht is verzonden.
* **genegeerd**: de gebeurtenis werd genegeerd door de levering, typisch wanneer een adres in quarantaine is.
* **deliveryFailed**: Er is een leveringsfout opgetreden tijdens de verwerking van de gebeurtenis.
* **routingFailed**: de verpletterende mislukte fase - dit kan bijvoorbeeld voorkomen wanneer het gespecificeerde type van gebeurtenis niet kan worden gevonden.
* **teOud**: de gebeurtenis is verlopen voordat deze kon worden verwerkt - dit kan om verschillende redenen gebeuren, bijvoorbeeld wanneer een verzending meerdere keren mislukt (dit leidt ertoe dat de gebeurtenis niet meer up-to-date is) of wanneer de server gebeurtenissen niet meer kan verwerken na het overladen.
* **targetFailed**: Campaign Standard kon geen verbinding verrijken die voor bericht het richten wordt gebruikt.
