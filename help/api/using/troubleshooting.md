---
solution: Campaign Standard
product: campaign
title: Problemen oplossen
description: Meer informatie over algemene problemen met betrekking tot Campaign Standard API's.
audience: developing
content-type: reference
topic-tags: use-case--extending-the-api
feature: API
role: Gegevensengineer
level: Ervaren
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '359'
ht-degree: 0%

---


# Problemen oplossen {#troubleshooting}

* **Wanneer u naar de Adobe.io-console gaat, treedt de volgende fout op: &quot;De console van de Adobe I/O is slechts beschikbaar om leden van ondernemingsrekeningen te selecteren. Als u van mening bent dat u toegang zou moeten hebben, gelieve uw Beheerder van het Systeem te contacteren.&quot;**

U kunt alleen API-sleutels maken voor de IMS-organisaties waarvan u de beheerder bent. Als dit bericht wordt weergegeven en u API-sleutels wilt maken, vraagt u een van de beheerders van de IMS-organisatie.

* **Wanneer u een aanvraag voor Adobe.io doet, krijgt u {&quot;error_code&quot;:&quot;403023&quot;,&quot;message&quot;:&quot;Profile is not valid&quot;}**

Dit betekent dat er een probleem is met de IMS-provisioning van uw specifieke campagneproduct: het IMS-team moet dit probleem verhelpen.

Als u meer details wilt opvragen, kunt u de IMS API met uw token aanroepen om te zien hoe uw IMS-profiel eruitziet: U moet een prodCtx hebben waar organisation_id het zelfde is als die u in u URL voor Adobe.io plaatst om uw verzoek te kunnen leiden.
Als de IMS-voorziening ontbreekt, moet deze worden hersteld.

```
-X GET https://mc.adobe.io/{ORGANIZATION}/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

De volgende fout wordt geretourneerd.

```
{"error_code":"403023","message":"Profile is not valid"}
```

Controleer uw IMS-profiel met deze aanvraag.

```
-X GET https://ims-na1.adobelogin.com/ims/profile/v1 \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

In de reactie, moet de waarde ORGANIZATION_ID het zelfde in uw eerste verzoek van de GET zijn.

```
{
  "countryCode": "FR",
  "mrktPermEmail": null,
  "projectedProductContext": [
    {
    "prodCtx": {
      "statusCode": "ACTIVE",
      "ident": "ZQ9FRQK7BF09YXAESFY9DDQP1G",
      "modDts": 1448307260000,
      "organization_id": "actest",
      "owningEntity": "6096892F54B5819E0A4C98A2@AdobeOrg",
      "serviceCode": "dma_tartan",
      "label": "Adobe Marketing Cloud",
      "serviceLevel": "standard",
      "createDts": 1421181343000,
      "deal_id": " "
      }
    }
  ]
}
```

* **Wanneer u een aanvraag doet naar Adobe.io, krijgt u {&quot;code&quot;:500, &quot;message&quot;:&quot;Oeps. Er ging iets mis. Controleer de URI en probeer het opnieuw.&quot;}**

Adobe.io declareert uw ongeldige URI: De URI die u aanvraagt, is naar alle waarschijnlijkheid ongeldig. Op Adobe.io wanneer u de dienst van de Campagne selecteert, krijgt u een plukker met een lijst van mogelijke organisatie_ids. U moet controleren dat u kiest u in uw URL plaatst.

* **Wanneer u een aanvraag doet naar Adobe.io, krijgt u {&quot;error_code&quot;:&quot;401013&quot;,&quot;message&quot;:&quot;Oauth token is not valid&quot;}**

Uw token is ongeldig (onjuiste IMS-aanroep die wordt gebruikt om een token te genereren) of uw token is verlopen.

* **Ik zie mijn profiel niet na creatie**

Afhankelijk van de instantieconfiguratie, moet het gecreeerde profiel aan **orgUnit** worden geassocieerd. Raadpleeg [deze sectie](../../api/using/creating-profiles.md) voor meer informatie over het toevoegen van dit veld in uw project.

<!-- * (error duplicate key : quand tu crées un profile qui existe déjà , il faut faire un patch pour updater le profile plutôt qu’un POST)

With Curl
List all profiles

Create a profile

Update the mobilePhone attribute of a profile

API Calls on Service

GET the list of services

-->

<!--

How to find and use a filter?
Error codes:

* PAtch sur Age = message d'erreur :
500
Cannot update the 'age' property that is read-only
'age' property is not valid for the 'profile' resource.
-->

<!--
How to filter a list of subscribed profiles with available profile filters ? by date (by les filtres dispo sur la ressource) ?

Pattern classique :

recupérer la liste des subscriptions filtrées d'un profile
1) get sur profile
2) recup PKey
3) get sur PKey
4) get sur href des subscriptions

Comment savoir quel filtre appliquer ?

1) get sur metadata de profile
2) retourne description de la collection subscription
3) get sur la valeur du champ resTarget
4) get sur le href dans filters
5) retourne les filtres applicables sur l'url des data.

-->
