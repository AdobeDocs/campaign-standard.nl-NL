---
title: Data-opname via API's activeren
description: Leer hoe u gegevensinvoer activeert via API's.
page-status-flag: never-activated
uuid: 867b1c4b-4c79-4c52-9d0a-ef71993e50a2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuring-channels
discoiquuid: 406c955a-b2d2-4099-9918-95f5fa966067
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 762700893c913d9aea884d00438c84b39a800188
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 5%

---


# Data-opname via API&#39;s activeren {#triggering-data-ingestion-apis}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connector bevindt zich momenteel in bèta, die vaak zonder voorafgaande kennisgeving kan worden bijgewerkt. Klanten moeten op Azure (momenteel alleen in bèta voor Noord-Amerika) worden gehost om toegang te krijgen tot deze mogelijkheden. Neem contact op met de klantenservice van Adobe als u toegang wilt.

Met Adobe Campaign Standard kunt u de directe invoer van gegevenstoewijzingen via API&#39;s activeren en de status van uw innameverzoeken ophalen.

Op deze pagina wordt beschreven hoe u de ingangsstatus van uw gegevenstoewijzingen kunt activeren en ophalen. Zie [deze sectie](../../api/using/get-started-apis.md)voor algemene informatie over Campaign Standard-API&#39;s.

## Vereisten {#prerequisites}

Alvorens APIs te gebruiken, moet de gegevenstoewijzing eerst binnen de interface van Campaign Standard gevormd en gepubliceerd zijn. Raadpleeg de volgende secties voor meer informatie:

* [Toewijzingsdefinitie](../../developing/using/aep-mapping-definition.md)
* [Toewijzingsactivering](../../developing/using/aep-mapping-activation.md)

Als de gegevenstoewijzing is gemaakt, moet u de bewerking stoppen zodat u deze op elk gewenst moment vanuit de API kunt activeren. Ga als volgt te werk om dit te doen:

1. Ga in Campaign Standard naar **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Platform]** > **[!UICONTROL Status of data export to platform]** menu.

1. Dubbelklik op de gegevenstoewijzing om deze te openen en klik vervolgens op de **[!UICONTROL Stop]** knop.

   ![](assets/aep_datamapping_stop.png)

1. Sla uw wijzigingen op

De uitvoering van de gegevenstoewijzing wordt nu gestopt. U kunt Campaign Standard API&#39;s gebruiken om de API&#39;s handmatig te activeren.

## De onmiddellijke inname van gegevenstoewijzing starten {#starting-immediate-ingestion}

De directe opname van een afbeelding XDM in Adobe Experience Platform wordt teweeggebracht met een POST verrichting:

`POST https://mc.adobe.io/<ORGANIZATION>/campaign/dataIngestion/xdmIngestion/<XDM Mapping ID>/ingest`

>[!NOTE]
>
>Om ingest POST API vraag uit te voeren, moet de gebruiker een rol van de **SQL uitvoering** van de functie hebben, die door een beheerder van Campaign Standard door onder JS Manuscript kan worden verstrekt uit te voeren:
>
>`var sqlRoleObj = REST.head.roleBase.sql.get();
REST.head.securityGroup.Administrators.roles.post(sqlRoleObj);`

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
Gedetailleerde informatie over de status van de XDM-toewijzingsaanvraag en de bijbehorende taken is beschikbaar in de Campaign Standard-interface, in het **[!UICONTROL Status of data export to platform]** menu (zie [Toewijzing activeren](../../developing/using/aep-mapping-activation.md)).

De bewerking GET retourneert de volgende informatie:

* **batchId**: dit veld wordt alleen ingevuld als er een fout is opgetreden na het voorbereiden en uploaden van de batch,
* **info**: de XDM-toewijzings-id;
* **numRecords**: het aantal geconsumeerde gegevens (alleen successtatus);
* **status**: de status van de ingeste aanvraag (geslaagd/mislukt/in uitvoering)

Mogelijke reacties op de GET-bewerking zijn:

* Ingest-aanvraag geslaagd:

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

* Ingest-aanvraag is mislukt, waarbij een record is geüpload onder een batch:

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
