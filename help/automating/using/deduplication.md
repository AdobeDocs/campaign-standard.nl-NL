---
title: Deduplicatie
description: Met de deduplicatieactiviteit kunt u duplicaten in het resultaat of de resultaten van de binnenkomende activiteiten verwijderen.
page-status-flag: never-activated
uuid: 11a22a9c-3bfe-4953-8a52-2f4e93c128fb
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: e7a5e1e7-4680-46c7-98b8-0a47bb7be2b8
context-tags: dedup,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c3911232a3cce00c2b9a2e619f090a7520382dde
workflow-type: tm+mt
source-wordcount: '567'
ht-degree: 0%

---


# Deduplicatie{#deduplication}

## Beschrijving {#description}

![](assets/deduplication.png)

Met de **[!UICONTROL Deduplication]** activiteit kunt u duplicaten verwijderen uit het resultaat of de resultaten van de binnenkomende activiteiten.

## Gebruikscontext {#context-of-use}

De **[!UICONTROL Deduplication]** activiteit wordt over het algemeen gebruikt na doelactiviteiten of na het importeren van een bestand en vóór activiteiten die het gebruik van gerichte gegevens mogelijk maken.

Tijdens deduplicatie worden inkomende overgangen afzonderlijk verwerkt. Als profiel &#39;A&#39; bijvoorbeeld aanwezig is in het resultaat van query 1 en ook in het resultaat van query 2, wordt het profiel niet gededupliceerd.

Daarom wordt geadviseerd dat een deduplicatie slechts één inkomende overgang heeft. Om dit te doen, kunt u uw verschillende vragen combineren door activiteiten te gebruiken die aan uw het richten behoeften zoals verenigingsactiviteit, een intersectieactiviteit, enz. beantwoorden. Bijvoorbeeld:

![](assets/dedup_bonnepratique.png)

**Verwante onderwerpen**

* [Hoofdlettergebruik: Duplicaten identificeren vóór levering](../../automating/using/identifying-duplicated-before-delivery.md)
* [Hoofdlettergebruik: De gegevens uit een geïmporteerd bestand dedupliceren](../../automating/using/deduplicating-data-imported-file.md)

## Configuratie {#configuration}

Om een deduplicatieactiviteit te vormen, moet u een etiket, de methode en de deduplicatiecriteria, evenals de opties met betrekking tot het resultaat ingaan.

1. Sleep een **[!UICONTROL Deduplication]** activiteit naar uw werkstroom.
1. Selecteer de activiteit, dan open het gebruikend de ![](assets/edit_darkgrey-24px.png) knoop van de snelle acties die verschijnen.

   ![](assets/deduplication_1.png)

1. Selecteer de **[!UICONTROL Resource type]** wijze waarop de deduplicatie moet worden uitgevoerd:

   * **[!UICONTROL Database resource]** indien de deduplicatie wordt uitgevoerd op gegevens die al in de database aanwezig zijn. Selecteer de **[!UICONTROL Filtering dimension]** en de **[!UICONTROL Targeting dimension]** afbeelding, afhankelijk van de gegevens die u wilt dedupliceren. Standaard wordt deduplicatie uitgevoerd op de **profielen**.
   * **[!UICONTROL Temporary resource]** indien de deduplicatie wordt uitgevoerd op de tijdelijke gegevens van de werkstroom: Selecteer het bestand **[!UICONTROL Targeted set]** met de gegevens die u wilt dedupliceren. Dit gebruik kan voorkomen na het invoeren van een dossier of als de gegevens in het gegevensbestand (met een segmentcode, bijvoorbeeld) werden verrijkt.

1. Selecteer de **[!UICONTROL Number of unique records to keep]**. De standaardwaarde voor dit veld is 1. Met de waarde 0 kunt u alle duplicaten behouden.

   Bijvoorbeeld, als de verslagen A en B als duplicaten van verslag Y worden beschouwd, en een verslag C als duplicaat van verslag Z wordt beschouwd:

   * Als de waarde van het veld 1 is: alleen de Y- en Z-gegevens worden bewaard.
   * Wanneer de waarde van het veld 0 is: alle registers worden bijgehouden.
   * Als de waarde van het veld 2 is: de registers C en Z worden bijgehouden en twee registers van A, B en Y worden, bij toeval of afhankelijk van de daarna gekozen deduplicatiemethode, bijgehouden.

1. Definieer de **[!UICONTROL Duplicate identification]** criteria door voorwaarden toe te voegen in de opgegeven lijst. Geef de velden en/of expressies op waarvoor de duplicaten met dezelfde waarden kunnen worden geïdentificeerd: e-mailadres, voornaam, achternaam, enz. In de volgorde van de voorwaarden kunt u opgeven welke voorwaarden eerst moeten worden verwerkt.
1. Selecteer in de vervolgkeuzelijst de **[!UICONTROL Deduplication method]** volgende opties:

   * **[!UICONTROL Choose for me]**: Hiermee selecteert u willekeurig de record die u uit de duplicaten wilt verwijderen.
   * **[!UICONTROL Following a list of values]**: Hiermee kunt u een prioriteit voor een of meer velden definiëren. Als u de waarden wilt definiëren, selecteert u een veld of maakt u een expressie. Voeg vervolgens de waarde(n) toe aan de desbetreffende tabel. Als u een nieuw veld wilt definiëren, klikt u op de **[!UICONTROL Add]** knop boven de lijst met waarden.

      ![](assets/deduplication_2.png)

   * **[!UICONTROL Non-empty value]**: Hiermee kunt u records bewaren waarvoor de waarde van de geselecteerde expressie niet leeg is als prioriteit.

      ![](assets/deduplication_3.png)

   * **[!UICONTROL Using an expression]**: hiermee kunt u de records bijhouden waarin de waarde van de ingevoerde expressie het kleinst of het grootst is.

      ![](assets/deduplication_4.png)

1. Indien nodig, beheer de [Overgangen](../../automating/using/activity-properties.md) van de activiteit om tot de geavanceerde opties voor de uitgaande bevolking toegang te hebben.
1. Bevestig de configuratie van uw activiteit en sla uw werkschema op.
