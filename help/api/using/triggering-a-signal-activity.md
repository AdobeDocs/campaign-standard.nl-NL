---
solution: Campaign Standard
product: campaign
title: Een signaalactiviteit activeren
description: Leer hoe u een signaalactiviteit activeert met API's.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 2%

---


# Een signaalactiviteit activeren {#triggering-a-signal-activity}

In een Adobe Campaign Standard-workflow kunnen er een of meer **externe signaalactiviteiten** zijn. Deze activiteiten zijn &#39;listeners&#39; die wachten op activering.

Met Campaign Standard-API&#39;s kunt u een **externe signaalactiviteit** activeren om een workflow aan te roepen. De API-aanroep kan parameters bevatten die worden opgenomen in de gebeurtenisvariabelen van de workflow (een doelnaam, een bestandsnaam die moet worden geïmporteerd, een deel van de berichtinhoud, enz.). Op deze manier kunt u uw campagneautomatisering eenvoudig integreren met uw externe systeem.

>[!NOTE]
>
>Externe signaalactiviteiten kunnen niet vaker dan om de 10 minuten worden geactiveerd en dat de doelworkflow al moet worden uitgevoerd.

Volg onderstaande stappen om een workflow te activeren:

1. Voer een **GET** verzoek op het werkschema uit om de Externe trekker van de signaalactiviteit terug te winnen URL.

   `GET https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>`

1. Voer een **POST** verzoek op teruggekeerde URL uit om de signaalactiviteit, met de **&quot;bron&quot;** parameter in de nuttige lading teweeg te brengen. Dit kenmerk is verplicht, zodat u de activerende aanvraagbron kunt aangeven.

Als u de workflow met parameters wilt aanroepen, voegt u deze toe aan de payload met het kenmerk **&quot;parameters&quot;** . De syntaxis bestaat uit de naam van de parameter gevolgd door de waarde (de volgende typen worden ondersteund: **tekenreeks**, **nummer**, **Booleaanse waarde** en **datum/tijd**).

```
  -X POST <TRIGGER_URL>
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>' \
  -H 'Content-Type: application/json;charset=utf-8' \
  -H 'Content-Length:79' \
  -i
  -d {
  -d    "source":"<SOURCE>",
  -d    "parameters":{
  -d      "<PARAMETER_NAME":"<PARAMETER_VALUE>",
  -d      "<PARAMETER_NAME":"<PARAMETER_VALUE>",
  -d      "<PARAMETER_NAME":"<PARAMETER_VALUE>",  
  -d      "<PARAMETER_NAME":"<PARAMETER_VALUE>"
  -d    }
  -d }
```

>[!NOTE]
>
>Wanneer het toevoegen van een parameter aan de lading, zorg ervoor dat zijn **naam** en **** typewaarden met de informatie verenigbaar zijn die in de Externe signaalactiviteit wordt verklaard. Bovendien mag de omvang van de lading niet groter zijn dan 64 Ko.

<br/>

***Voorbeeldverzoek***

Voer een verzoek van de GET uit op het werkschema.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Het retourneert de activiteit van het workflowsignaal en de bijbehorende trigger-URL.

```
{
"PKey": "<PKEY>",
"activities": {
  "activity": {
    "signal1": {
      ...
      "trigger": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<PKEY>/activities/activity/<PKEY>/trigger/"
        },
        ...
      }
    }
  }
}
```

Om een signaalactiviteit teweeg te brengen, voer een verzoek van de POST op trekkerURL met &quot;bron&quot;uit. Voeg de kenmerken &quot;parameters&quot; toe als u de workflow met parameters wilt aanroepen.

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<PKEY>/activities/activity/<PKEY>/trigger \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-i
-d '{
-d "source":"API",
-d "parameters":{
-d    "audience":"audience",
-d    "email":"anna.varney@mail.com",
-d    "template":"05",
-d    "contentURL":"http://www.adobe.com",
-d    "test":"true",
-d    "segmentCode":"my segment",
-d    "attribute":"2019-04-03 08:17:19.100Z"}
-d  }'
```

<!-- + réponse -->

Als een van de parameters niet wordt gedeclareerd in de externe signaalactiviteit, retourneert de aanvraag van de POST de onderstaande fout die aangeeft welke parameter ontbreekt.

```
RST-360011 An error has occurred - please contact your administrator.
'contentURL' parameter isn't defined in signal activity.
XTK-170006 Unable to parse expression 'HandleTrigger(@name, $(source), $({parameters}))'.
RST-360000 Error while assessing 'HandleTrigger(@name, $(source), $({parameters}))' expression ('xtk:workflow:execution/activities/signal/trigger' resource)
```
