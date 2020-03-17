---
title: Aangepaste bronnen
description: Meer informatie over het beheer van aangepaste bronnen met API's/
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
source-git-commit: 538739417c4ed28ff2991186dac5fb69d1af3afd

---


# Aangepaste bronnen {#custom-resources}

Adobe Campagne wordt geleverd met een vooraf gedefinieerd gegevensmodel, waarin gegevens via verschillende bronnen worden gedefinieerd. U kunt het gegevensmodel verrijken dat wordt verstrekt door de middelen uit te breiden om uw eigen douanevelden of douanetabellen, zoals aankoop of productlijsten toe te voegen.

De middelen van de douane zijn toegankelijk door APIs gebruikend het **/profileAndServicesExt** eindpunt, en de naam van het douanemiddel.

`https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/<resourceName>/`

>[!NOTE]
>
>Voor middelen die niet uit-van-de-doos zijn, gebruik altijd de <b>&quot;focus&quot;</b> prefix vóór de naam van het middel.

U kunt elke gewenste bewerking uitvoeren met aangepaste bronnen, mits deze zijn gekoppeld aan de tabel Profiel. Neem bijvoorbeeld de onderstaande tabelstructuur:

![alt-tekst](assets/cusresources.png)

In dat geval zijn alle bronnen van de tabellen **Transactie**, **TransactieDetails** en **Product** beschikbaar zolang deze zijn gekoppeld aan de tabel **Profiel** .

<br/>

***Voorbeeldverzoek***

De steekproef krijgt verzoek om tot het uitgebreide profileAndServicesExt middel toegang te hebben.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/\
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
```

Het keert de lijst van alle verbonden douanemiddelen terug. Vervolgens kunt u de bron-URL&#39;s gebruiken om elke API-taak uit te voeren die in deze documentatie wordt beschreven.

```
{
"apiName": "resourceType",
"cusProduct": {
        "content": ...,
        "data": "/profileAndServicesExt/cusProduct/",
        "help": "Product",
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/cusProduct/metadata",
        "name": "cusProduct",
        "type": "collection"
    },
"cusTransaction": {
        "content": ...,
        "data": "/profileAndServicesExt/cusTransaction/",
        "help": "Product",
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/cusTransaction/metadata",
        "name": "cusProduct",
        "type": "collection"
    },
    ...
}
```

Raadpleeg de documentatie bij Campagne voor meer informatie over de extensie van het gegevensmodel:

* [Concepten van gegevensmodellen](../../developing/using/data-model-concepts.md)
* [De API uitbreiden](../../developing/using/about-extending-the-api.md)
* [Koppelingen met andere bronnen definiëren](https://helpx.adobe.com/campaign/standard/developing/using/configuring-the-resource-s-data-structure.html#defining-links-with-other-resources)
