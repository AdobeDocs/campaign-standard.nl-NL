---
title: Transactieberichten beheren
description: Leer hoe u transactieberichten beheert met API's.
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: cd559678dfadc575db42f3101e53bae2b971a049

---


# Transactieberichten beheren {#managing-transactional-messages}

## Informatie over transactieberichten

Nadat u een gebeurtenis hebt gemaakt, moet u de activering van deze gebeurtenis integreren in uw website.

>[!NOTE]
>
>Het creëren van en het publiceren van een gebeurtenis worden voorgesteld in [de documentatie](https://helpx.adobe.com/campaign/standard/administration/using/configuring-transactional-messaging.html)van de Campagne.

U wilt bijvoorbeeld dat de gebeurtenis &#39;Afkappen met winkelwagentje&#39; wordt geactiveerd wanneer een van uw klanten uw website verlaat voordat ze de producten in hun winkelwagentje kopen. Hiervoor moet uw webontwikkelaar de REST Transaction Messages API gebruiken.

1. De ontwikkelaar verzendt een verzoek volgens de methode POST, die het [verzenden van de transactiegebeurtenis](#sending-a-transactional-event)teweegbrengt.
1. Het antwoord op het POST- verzoek bevat een Primaire Sleutel, die de ontwikkelaar toestaat om één of veelvoudige verzoeken door een GET verzoek te verzenden. Op deze manier kan hij de [gebeurtenisstatus](#transactional-event-status)verkrijgen.

## Een transactiegebeurtenis verzenden {#sending-a-transactional-event}

De transactiegebeurtenis wordt verzonden via een POST-aanvraag met de volgende URL-structuur:

```
POST https://mc.adobe.io/<ORGANIZATION>/campaign/<transactionalAPI>/<eventID>
```

* **&lt;ORGANISATIE>**: uw persoonlijke ORGANISATIE-ID. Zie [deze sectie](../../api/using/must-read.md).

* **&lt;transactieAPI>**: de Transactional Berichten API endPoints.

   De naam van het Transactionele eindpunt van Berichten API hangt van uw instantieconfiguratie af. Deze komt overeen met de waarde &quot;mc&quot; gevolgd door uw persoonlijke organisatie-id. Neem het voorbeeld van het bedrijf Geometrixx, met &quot;geometrixx&quot;als zijn organisatieidentiteitskaart In dat geval zou het POST-verzoek als volgt zijn:

   `POST https://mc.adobe.io/geometrixx/campaign/mcgeometrixx/<eventID>`

   (Het API-eindpunt voor transactionele berichten is ook zichtbaar tijdens de API-voorvertoning.)

* **&lt;eventID>**: het type gebeurtenis dat u wilt verzenden. Deze id wordt gegenereerd wanneer de gebeurtenisdefinitie wordt gemaakt. Raadpleeg de [documentatie](https://helpx.adobe.com/campaign/standard/administration/using/configuring-transactional-messaging.html)van de campagne.

### Koptekst POST-verzoek

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

### POST-aanvraaginstantie

De gebeurtenisgegevens bevinden zich in de JSON POST-hoofdtekst. De gebeurtenisstructuur is afhankelijk van de definitie ervan. De API voorproefknoop in het scherm van de middeldefinitie verstrekt een verzoeksteekproef. Raadpleeg de [documentatie](https://helpx.adobe.com/campaign/standard/administration/using/configuring-transactional-messaging.html)van de campagne.

De volgende optionele parameters kunnen aan de inhoud van de gebeurtenis worden toegevoegd om het verzenden van aan de gebeurtenis gekoppelde transactieberichten te beheren:

* **Vervaldatum** (optioneel): na deze datum wordt het verzenden van de transactiegebeurtenis geannuleerd.
* **Gepland** (optioneel): vanaf deze datum wordt de transactie - gebeurtenis verwerkt en wordt het transactiemelding verzonden .

>[!NOTE]
>
>De waarden van de parameters &quot;expiration&quot; en &quot;scheduled&quot; volgen de ISO 8601-indeling. ISO 8601 specificeert het gebruik van de hoofdletter &quot;T&quot; om de datum en de tijd van elkaar te scheiden. Deze kan echter uit de invoer of uitvoer worden verwijderd voor een betere leesbaarheid.

### Antwoord op de POST-aanvraag

De POST-reactie retourneert de status van de transactiegebeurtenis op het moment dat deze werd gemaakt. Om zijn huidige status (gebeurtenisgegevens, gebeurtenisstatus...) terug te winnen, gebruik de Primaire Sleutel door het POST antwoord in een GET verzoek wordt teruggekeerd:

`GET https://mc.adobe.io/<ORGANIZATION>/campaign/<transactionalAPI>/<eventID>/`

<br/>

***Voorbeeldverzoek***

POST-verzoek om de gebeurtenis te verzenden.

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

Antwoord op het POST-verzoek.

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

### Status van een transactiegebeurtenis {#transactional-event-status}

In het antwoord kunt u met het veld status weten of de gebeurtenis is verwerkt:

* **in behandeling**: de gebeurtenis is in behandeling - de gebeurtenis neemt deze status over wanneer deze zojuist is geactiveerd.
* **verwerking**: de gebeurtenis is in afwachting van levering - het wordt omgezet in een bericht en het bericht wordt verzonden.
* **gepauzeerd**: het gebeurtenisproces wordt gepauzeerd. Het wordt niet meer verwerkt, maar in een wachtrij in de Adobe Campagne-database opgeslagen. Raadpleeg de documentatie bij [Campagne voor meer informatie](https://helpx.adobe.com/campaign/standard/channels/using/event-transactional-messages.html#unpublishing-a-transactional-message).
* **verwerkt**: de gebeurtenis is verwerkt en het bericht is verzonden.
* **genegeerd**: de gebeurtenis werd genegeerd door de levering, typisch wanneer een adres in quarantaine is.
* **deliveryFailed**: Er is een leveringsfout opgetreden tijdens de verwerking van de gebeurtenis.
* **routingFailed**: de verpletterende mislukte fase - dit kan bijvoorbeeld voorkomen wanneer het gespecificeerde type van gebeurtenis niet kan worden gevonden.
* **teOud**: de gebeurtenis is verlopen voordat deze kon worden verwerkt - dit kan om verschillende redenen gebeuren, bijvoorbeeld wanneer een verzending meerdere keren mislukt (dit leidt ertoe dat de gebeurtenis niet meer up-to-date is) of wanneer de server gebeurtenissen niet meer kan verwerken na het overladen.
* **targetFailed**: De Standaard van de campagne slaagde er niet in om een verbinding te verrijken die voor bericht het richten wordt gebruikt.
