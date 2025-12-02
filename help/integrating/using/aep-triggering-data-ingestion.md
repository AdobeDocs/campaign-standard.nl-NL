---
title: Gegevensopname via API's activeren
description: Leer hoe u gegevensinvoer activeert via API's.
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Microsoft CRM Integration
old-role: Data Architect
role: Developer
level: Experienced
exl-id: d67a796a-0730-4502-802c-d0b3583dd1dc
hide: true
hidefromtoc: true
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 6%

---

# Gegevensopname via API&#39;s activeren {#triggering-data-ingestion-apis}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connector bevindt zich momenteel in bèta, die vaak zonder voorafgaande kennisgeving kan worden bijgewerkt. Klanten moeten op Azure (momenteel alleen in bèta voor Noord-Amerika) worden gehost om toegang te krijgen tot deze mogelijkheden. Neem contact op met de klantenservice van Adobe als u toegang wilt.

Met Adobe Campaign Standard kunt u de directe invoer van gegevenstoewijzingen via API&#39;s activeren en de status van uw innameverzoeken ophalen.

Op deze pagina wordt beschreven hoe u de ingangsstatus van uw gegevenstoewijzingen kunt activeren en ophalen. Voor globale informatie over Campaign Standard APIs, verwijs naar [&#x200B; deze sectie &#x200B;](../../api/using/get-started-apis.md).

## Vereisten {#prerequisites}

Voordat u de API&#39;s kunt gebruiken, moet de gegevenstoewijzing eerst zijn geconfigureerd en gepubliceerd in de Campaign Standard-interface. Raadpleeg deze secties voor meer informatie hierover:

* [Toewijzingsdefinitie](../../integrating/using/aep-mapping-definition.md)
* [Toewijzingsactivering](../../integrating/using/aep-mapping-activation.md)

Als de gegevenstoewijzing is gemaakt, moet u de bewerking stoppen zodat u deze op elk gewenst moment vanuit de API kunt activeren. Ga als volgt te werk om dit te doen:

1. Ga in Campaign Standard naar het menu **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Platform]** > **[!UICONTROL Status of data export to platform]** .

1. Dubbelklik op de gegevenstoewijzing om deze te openen en klik vervolgens op de knop **[!UICONTROL Stop]** .

   ![](assets/aep_datamapping_stop.png)

1. Uw wijzigingen opslaan

De uitvoering van de gegevenstoewijzing wordt nu gestopt. U kunt Campaign Standard API&#39;s gebruiken om deze handmatig te activeren.

## De onmiddellijke inname van gegevenstoewijzing starten {#starting-immediate-ingestion}

Directe opname van een XDM-toewijzing in Adobe Experience Platform wordt geactiveerd met een POST-bewerking:

`POST https://mc.adobe.io/<ORGANIZATION>/campaign/dataIngestion/xdmIngestion/<XDM Mapping ID>/ingest`

>[!NOTE]
>
>Om ingeste POST API vraag uit te voeren, moet de gebruiker een **SQL rol van de functieuitvoering** hebben, die door een beheerder van Campaign Standard door onder Manuscript uit te voeren JS kan worden verstrekt:
>
>```
>var sqlRoleObj = REST.head.roleBase.sql.get();
>REST.head.securityGroup.Administrators.roles.post(sqlRoleObj);
>```
>

De POST verrichting keert informatie betreffende de gecreeerde verzoekstatus terug:

* Verzoek is verzonden voor XDM-toewijzing:

```
{
"requestId": <value>,
"info": "Ingestion request submitted successfully for the Mapping ID: <value>",
"status":"Success"
}
```

* Verzoek voor XDM-toewijzing is al in behandeling:

```
{
"requestId": <value>,
"info": "Ingestion request already in progress for the Mapping ID: <value>",
"status":"In Progress"
}
```

* Verzoek is mislukt omdat de XDM-toewijzing niet is gepubliceerd of is gestopt:

```
{
"info": "Unable to submit data ingestion request, XDM Mapping ID: <value> is not stopped",
"status": "Failed"
}
{
"info": "Unable to submit data ingestion request, XDM Mapping ID: <value> is not published",
"status": "Failed"
}
```

## De status van een innameverzoek ophalen {#retrieving-status}

De status van een innameverzoek kan worden opgehaald met een GET-bewerking en de gewenste aanvraag-id in de parameters:

```
GET https://mc.adobe.io/<ORGANIZATION>/campaign/dataIngestion/xdmIngestion/<XDM Mapping ID>/ingest
{"requestId"="<value>"}
```

>[!NOTE]
>
>De gedetailleerde informatie over de status van het XDM kaartverzoekverzoek en zijn verwante banen is beschikbaar in de interface van Campaign Standard, in het **[!UICONTROL Status of data export to platform]** menu (zie [&#x200B; de activering van de Afbeelding &#x200B;](../../integrating/using/aep-mapping-activation.md)).

De GET-bewerking retourneert de volgende informatie:

* **batchId**: dit gebied wordt bevolkt slechts als de mislukking na partij voorkwam en uploadt,
* **info**: XDM afbeelding identiteitskaart,
* **numRecords**: het aantal verslagen die (successtatus slechts) zijn opgenomen,
* **status**: De ingest aanvraagstatus (succes/ontbroken/lopend)

Mogelijke reacties op de GET-bewerking zijn:

* Ontvangen aanvraag:

  ```
  {
  "batchId": "",
  "info": "Mapping Id: <value>. ",
  "numRecords": 15,
  "requestId": 3520,
  "status": "Success"
  }
  ```

* Ingest-verzoek is mislukt omdat 0 record is ingevoerd:

  ```
  {
  "batchId": "",
  "info": "Mapping Id: <value>. ACP-880056 Failed to fetch the record from the database.",
  "numRecords": 0,
  "requestId": 3520,
  "status": "Failed"
  }
  ```

* Ingest-aanvraag is mislukt, met een record geüpload onder een batch:

  ```
  {
  "batchId": "<value>",
  "info": "Mapping Id: <value>. ACP-880096 Sync Job failed to upload. Please check the error in the Platform UI.",
  "numRecords": 0,
  "requestId": <value>,
  "status": "Failed"
  }
  ```

* De intentieverzoek aborteerde na het opnemen van sommige verslagen (dit kan in botsingsscenario&#39;s gebeuren):

  ```
  {
  "batchId": "",
  "info": "Mapping Id: <value>. Ingestion request aborted due to some issue with data ingestion service. Please submit a new request",
  "numRecords": 0,
  "requestId": <value>,
  "status": "Aborted"
  }
  ```

* Voorlopig verzoek (wanneer de aanvraag is geüpload naar de gegevens in een batch of wanneer de batch wordt voorbereid voor de aanvraag):

  ```
  {
  "batchId": "",
  "info": "Mapping Id: <value>.",
  "numRecords": 0,
  "requestId": <value>,
  "status": "In Progress"
  }
  ```
