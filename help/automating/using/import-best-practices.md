---
title: Beste werkwijzen importeren
description: Leer meer over de beste praktijken om te volgen wanneer het invoeren van gegevens in het gegevensbestand.
page-status-flag: never-activated
uuid: d909d26a-cf50-46af-ae09-f0fd7258ca27
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: 75b83165-dcbd-4bb7-b703-ed769f489b16
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b4d0aa1a9f116f022890d5eccd87730a7a513103
workflow-type: tm+mt
source-wordcount: '546'
ht-degree: 0%

---


# Beste werkwijzen importeren {#import-best-practices}

Voorzichtig zijn en het volgen van de weinige hieronder gedetailleerde eenvoudige regels zullen veel helpen om gegevensconsistentie binnen het gegevensbestand te verzekeren en gemeenschappelijke fouten tijdens gegevensbestandupdate of gegevensuitvoer te vermijden.

## Importsjablonen gebruiken {#using-import-templates}

De meeste importworkflows moeten de volgende activiteiten bevatten: **[!UICONTROL Load file]**, **[!UICONTROL Reconciliation]**, **[!UICONTROL Segmentation]**, **[!UICONTROL Deduplication]**, **[!UICONTROL Update data]**.

Door het gebruik van importsjablonen is het heel handig om vergelijkbare importbewerkingen voor te bereiden en te zorgen voor consistentie van de gegevens in de database.

In veel projecten wordt geïmporteerd zonder **[!UICONTROL Deduplication]** activiteit, omdat de bestanden die in het project worden gebruikt geen duplicaten hebben. Soms worden duplicaten weergegeven van het importeren van verschillende bestanden. De-duplicatie is dan moeilijk. Daarom is een deduplicatiestap een goede voorzorgsmaatregel in alle importworkflows.

Ga niet uit van de veronderstelling dat de inkomende gegevens consistent en correct zijn, of dat de afdeling van IT of de supervisor van Adobe Campaign het zal behandelen. Houd tijdens het project rekening met het opschonen van gegevens. U kunt gegevens dedupliceren, op elkaar afstemmen en de consistentie behouden bij het importeren van gegevens.

Een voorbeeld van een generiek werkschemamalplaatje dat voor het invoeren van gegevens wordt ontworpen is beschikbaar in het [Voorbeeld: Sjabloonsectie voor](../../automating/using/creating-import-workflow-templates.md) importworkflow.

>[!NOTE]
>
>U kunt ook [importsjablonen](../../automating/using/importing-data-with-import-templates.md)gebruiken. Het zijn werkstroomsjablonen die zijn gedefinieerd door een beheerder die, nadat ze zijn geactiveerd, alleen de mogelijkheid biedt om het bestand op te geven dat de te importeren gegevens bevat.

**Verwante onderwerpen:**

* [Bestandsactiviteit laden](../../automating/using/load-file.md)
* [Afstemmingsactiviteit](../../automating/using/reconciliation.md)
* [Segmenteringsactiviteit](../../automating/using/segmentation.md)
* [Deduplicatieactiviteit](../../automating/using/deduplication.md)
* [Gegevensactiviteit bijwerken](../../automating/using/update-data.md)

## Vlakke bestandsindelingen gebruiken {#using-flat-file-formats}

De meest efficiënte indeling voor importeren is platte bestanden. Vlakke bestanden kunnen in de bulkmodus op databaseniveau worden geïmporteerd.

Bijvoorbeeld:

* Scheidingsteken: tab of puntkomma
* Eerste regel met kopteksten
* Geen scheidingsteken voor tekenreeks
* Datumnotatie: YYYY/MM/DD HH:mm:SS

Voorbeeld van te importeren bestand:

```
lastname;firstname;birthdate;email;crmID
Smith;Hayden;23/05/1989;hayden.smith@example.com;124365
Mars;Daniel;17/11/1987;dannymars@example.com;123545
Smith;Clara;08/02/1989;hayden.smith@example.com;124567
Durance;Allison;15/12/1978;allison.durance@example.com;120987
```

## Compressie gebruiken {#using-compression}

Gebruik indien mogelijk gecomprimeerde bestanden voor importeren en exporteren. GZIP wordt standaard ondersteund. U kunt voorbewerking toevoegen tijdens het importeren van bestanden of naverwerking bij het extraheren van gegevens, respectievelijk in de **[!UICONTROL Load file]** en de **[!UICONTROL Extract file]** werkstroom.

**Verwante onderwerpen:**

* [Bestandsactiviteit laden](../../automating/using/load-file.md)
* [Bestandsactiviteit extraheren](../../automating/using/extract-file.md)

## Importeren in de Delta-modus {#importing-in-delta-mode}

Regelmatige invoer moet plaatsvinden in de deltamodus. Dit betekent dat alleen gewijzigde of nieuwe gegevens telkens naar Adobe Campaign worden verzonden in plaats van naar de hele tabel.

Volledige invoer mag alleen voor eerste lading worden gebruikt.

## Behoud van consistentie {#maintaining-consistency}

Om de consistentie van de gegevens in de Adobe Campaign-database te waarborgen, volgt u de volgende beginselen:

* Als de geïmporteerde gegevens overeenkomen met een referentietabel in Adobe Campaign, moet de tabel in de workflow overeenkomen met die tabel. Records die niet overeenkomen, moeten worden afgewezen.
* Zorg ervoor dat de geïmporteerde gegevens altijd **&quot;genormaliseerd&quot;** zijn (e-mail, telefoonnummer, direct-mailadres) en dat deze normalisatie betrouwbaar is en in de loop der jaren niet zal veranderen. Als dit niet het geval is, zullen sommige duplicaten waarschijnlijk in het gegevensbestand verschijnen, en aangezien Adobe Campaign geen hulpmiddelen verstrekt om &quot;vage&quot;aanpassing te doen, zal het zeer moeilijk zijn om hen te beheren en te verwijderen.
* Transactionele gegevens moeten een afstemmingssleutel hebben en in overeenstemming zijn met de bestaande gegevens om het creëren van duplicaten te voorkomen.
* **Verwante bestanden op volgorde** importeren. Als het importeren uit meerdere bestanden bestaat die van elkaar afhankelijk zijn, moet de workflow ervoor zorgen dat de bestanden in de juiste volgorde worden geïmporteerd. Wanneer een bestand mislukt, worden de andere bestanden niet geïmporteerd.
* **U kunt gegevens dedupliceren**, combineren en de consistentie behouden wanneer u ze importeert.
