---
title: Gegevensopname via API's activeren
description: Leer hoe u gegevensinvoer activeert via API's.
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: d67a796a-0730-4502-802c-d0b3583dd1dc
hide: true
hidefromtoc: true
source-git-commit: 110f3ccb5865e70c78e18485b4ff4ba7a648af3f
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 6%

---

# Gegevensopname via API&#39;s activeren {#triggering-data-ingestion-apis}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connector bevindt zich momenteel in bèta, die vaak zonder voorafgaande kennisgeving kan worden bijgewerkt. Klanten moeten op Azure (momenteel alleen in bèta voor Noord-Amerika) worden gehost om toegang te krijgen tot deze mogelijkheden. Neem contact op met de klantenservice van de Adobe als u toegang wilt.

Met Adobe Campaign Standard kunt u de directe invoer van gegevenstoewijzingen via API&#39;s activeren en de status van uw innameverzoeken ophalen.

Op deze pagina wordt beschreven hoe u de ingangsstatus van uw gegevenstoewijzingen kunt activeren en ophalen. Zie voor algemene informatie over Campaign Standard-API&#39;s [deze sectie](../../api/using/get-started-apis.md).

## Vereisten {#prerequisites}

Alvorens APIs te gebruiken, moet de gegevenstoewijzing eerst binnen de interface van het Campaign Standard zijn gevormd en gepubliceerd. Raadpleeg deze secties voor meer informatie hierover:

* [Toewijzingsdefinitie](../../integrating/using/aep-mapping-definition.md)
* [Toewijzingsactivering](../../integrating/using/aep-mapping-activation.md)

Als de gegevenstoewijzing is gemaakt, moet u de bewerking stoppen zodat u deze op elk gewenst moment vanuit de API kunt activeren. Ga als volgt te werk om dit te doen:

1. Ga in Campaign Standard naar de **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Platform]** > **[!UICONTROL Status of data export to platform]** -menu.

1. Dubbelklik op de gegevenstoewijzing om deze te openen en klik vervolgens op de knop **[!UICONTROL Stop]** knop.

   ![](assets/aep_datamapping_stop.png)

1. Uw wijzigingen opslaan

De uitvoering van de gegevenstoewijzing wordt nu gestopt. U kunt Campaign Standard APIs gebruiken om het manueel teweeg te brengen.

## De onmiddellijke inname van gegevenstoewijzing starten {#starting-immediate-ingestion}

De directe opname van een afbeelding XDM in Adobe Experience Platform wordt teweeggebracht met een POST verrichting:

`POST https://mc.adobe.io/<ORGANIZATION>/campaign/dataIngestion/xdmIngestion/<XDM Mapping ID>/ingest`

>[!NOTE]
>
>Voor het uitvoeren van de API-aanroep van ingest POST moet de gebruiker beschikken over **Uitvoering van SQL-functies** rol, die door een beheerder van het Campaign Standard door onder Manuscript kan worden verstrekt uit te voeren JS:
>
>```
>var sqlRoleObj = REST.head.roleBase.sql.get();
>REST.head.securityGroup.Administrators.roles.post(sqlRoleObj);
>```
>

De verrichting van de POST keert informatie betreffende de gecreeerde verzoekstatus terug:

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

De status van een innameverzoek kan met een verrichting van de GET en gewenste verzoekidentiteitskaart in de parameters worden teruggewonnen:

```
GET https://mc.adobe.io/<ORGANIZATION>/campaign/dataIngestion/xdmIngestion/<XDM Mapping ID>/ingest
{"requestId"="<value>"}
```

>[!NOTE]
>
>Gedetailleerde informatie over de status van de XDM-toewijzingsaanvraag en de bijbehorende taken is beschikbaar in de interface van het Campaign Standard, in de **[!UICONTROL Status of data export to platform]** menu (zie [Toewijzingsactivering](../../integrating/using/aep-mapping-activation.md)).

De bewerking GET retourneert de volgende informatie:

* **batchId**: dit veld wordt alleen ingevuld als er een fout is opgetreden na het voorbereiden en uploaden van de batch,
* **info**: de XDM-toewijzingsid,
* **numRecords**: het aantal gegeten records (alleen successtatus),
* **status**: de status van de ingeste aanvraag (geslaagd/mislukt/in uitvoering)

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
