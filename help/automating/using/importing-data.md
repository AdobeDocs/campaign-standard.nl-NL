---
title: Gegevens importeren
description: Leer hoe u gegevens importeert met een workflow.
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
source-git-commit: 9048e11fe063707e1c6b5a86de095f72d22800c1

---


# Gegevens importeren{#importing-data}

## Gegevens verzamelen {#collecting-data}

U kunt gegevens van een bestand verzamelen om het te verwerken en/of te importeren in de Adobe Campagne-database.

* Met deze **[!UICONTROL Load file]** activiteit kunt u gegevens in één gestructureerd formulier importeren en deze gegevens gebruiken in Adobe Campaign. De gegevens worden tijdelijk geïmporteerd en een andere activiteit is nodig om deze definitief te integreren in de Adobe Campaign-database.

   Raadpleeg [deze sectie](../../automating/using/load-file.md)voor meer informatie over het gebruik van deze activiteit.

* Met deze **[!UICONTROL Transfer file]** activiteit kunt u bestanden ontvangen of verzenden, testen of er bestanden aanwezig zijn of bestanden weergeven in Adobe Campagne.
U kunt deze activiteit vóór een **[!UICONTROL Load file]** voor het geval gebruiken u het dossier van een externe bron moet terugwinnen.

   Raadpleeg [deze sectie](../../automating/using/transfer-file.md)voor meer informatie over het gebruik van deze activiteit.

## Beste werkwijzen importeren {#import-best-practices}

Voorzichtig zijn en het volgen van de weinige hieronder gedetailleerde eenvoudige regels zullen veel helpen om gegevensconsistentie binnen het gegevensbestand te verzekeren en gemeenschappelijke fouten tijdens gegevensbestandupdate of gegevensuitvoer te vermijden.

### Importsjablonen gebruiken {#using-import-templates}

De meeste importworkflows moeten de volgende activiteiten bevatten: **[!UICONTROL Load file]**, **[!UICONTROL Reconciliation]**, **[!UICONTROL Segmentation]**, **[!UICONTROL Deduplication]**, **[!UICONTROL Update data]**.

Door het gebruik van importsjablonen is het heel handig om vergelijkbare importbewerkingen voor te bereiden en te zorgen voor consistentie van de gegevens in de database.

In veel projecten wordt geïmporteerd zonder **[!UICONTROL Deduplication]** activiteit, omdat de bestanden die in het project worden gebruikt geen duplicaten hebben. Soms worden duplicaten weergegeven van het importeren van verschillende bestanden. De-duplicatie is dan moeilijk. Daarom is een deduplicatiestap een goede voorzorgsmaatregel in alle importworkflows.

Ga er niet vanuit dat de binnenkomende gegevens consistent en correct zijn of dat de IT-afdeling of de Adobe Campagneontwikkelaar er zorg voor zal dragen. Houd tijdens het project rekening met het opschonen van gegevens. U kunt gegevens dedupliceren, op elkaar afstemmen en de consistentie behouden bij het importeren van gegevens.

Een voorbeeld van een generiek werkschemamalplaatje dat voor het invoeren van gegevens wordt ontworpen is beschikbaar in het [Voorbeeld: Sjabloonsectie voor](#example--import-workflow-template) importworkflow.

>[!NOTE]
>
>U kunt ook [importsjablonen](../../automating/using/importing-data-with-import-templates.md)gebruiken. Het zijn werkstroomsjablonen die zijn gedefinieerd door een beheerder die, nadat ze zijn geactiveerd, alleen de mogelijkheid biedt om het bestand op te geven dat de te importeren gegevens bevat.

**Verwante onderwerpen:**

* [Bestandsactiviteit laden](../../automating/using/load-file.md)
* [Afstemmingsactiviteit](../../automating/using/reconciliation.md)
* [Segmenteringsactiviteit](../../automating/using/segmentation.md)
* [Deduplicatieactiviteit](../../automating/using/deduplication.md)
* [Gegevensactiviteit bijwerken](../../automating/using/update-data.md)

### Vlakke bestandsindelingen gebruiken {#using-flat-file-formats}

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

### Compressie gebruiken {#using-compression}

Gebruik indien mogelijk gecomprimeerde bestanden voor importeren en exporteren. GZIP wordt standaard ondersteund. U kunt voorbewerking toevoegen tijdens het importeren van bestanden of naverwerking bij het extraheren van gegevens, respectievelijk in de **[!UICONTROL Load file]** en de **[!UICONTROL Extract file]** werkstroom.

**Verwante onderwerpen:**

* [Bestandsactiviteit laden](../../automating/using/load-file.md)
* [Bestandsactiviteit extraheren](../../automating/using/extract-file.md)

### Importeren in de Delta-modus {#importing-in-delta-mode}

Regelmatige invoer moet plaatsvinden in de deltamodus. Dit betekent dat alleen gewijzigde of nieuwe gegevens elke keer naar Adobe Campagne worden verzonden in plaats van naar de hele tabel.

Volledige invoer mag alleen voor eerste lading worden gebruikt.

### Behoud van consistentie {#maintaining-consistency}

Houd u aan de volgende beginselen om de consistentie van gegevens in de Adobe Campagne-database te garanderen:

* Als de geïmporteerde gegevens overeenkomen met een referentietabel in Adobe Campaign, moet deze in de workflow overeenkomen met de desbetreffende tabel. Records die niet overeenkomen, moeten worden afgewezen.
* Zorg ervoor dat de geïmporteerde gegevens altijd **&quot;genormaliseerd&quot;** zijn (e-mail, telefoonnummer, direct-mailadres) en dat deze normalisatie betrouwbaar is en in de loop der jaren niet zal veranderen. Als dit niet het geval is, zullen sommige duplicaten waarschijnlijk in het gegevensbestand verschijnen, en aangezien de Campagne van Adobe geen hulpmiddelen verstrekt om &quot;vage&quot;aanpassing te doen, zal het zeer moeilijk zijn om hen te beheren en te verwijderen.
* Transactionele gegevens moeten een afstemmingssleutel hebben en in overeenstemming zijn met de bestaande gegevens om het creëren van duplicaten te voorkomen.
* **Verwante bestanden op volgorde** importeren. Als het importeren uit meerdere bestanden bestaat die van elkaar afhankelijk zijn, moet de workflow ervoor zorgen dat de bestanden in de juiste volgorde worden geïmporteerd. Wanneer een bestand mislukt, worden de andere bestanden niet geïmporteerd.
* **U kunt gegevens dedupliceren**, combineren en de consistentie behouden wanneer u ze importeert.

## Gecodeerde gegevens beheren {#managing-encrypted-data}

In sommige gevallen moeten de gegevens die u wilt importeren, mogelijk worden gecodeerd, bijvoorbeeld als deze PII-gegevens bevatten.

Als u gecodeerde bestanden wilt importeren of exporteren, moet u eerst contact opnemen met de klantenservice van Adobe, zodat deze uw instantie de benodigde opdrachten voor versleuteling/ontsleuteling kunnen geven.

Hiertoe dient u een verzoek in met de volgende gegevens:

* Het **label** dat in de interface van de Campagne zal tonen om het bevel te gebruiken. Bijvoorbeeld &quot;Bestand versleutelen&quot;.
* De **opdracht** om op uw instantie te installeren.
Als u bijvoorbeeld een bestand wilt decoderen met PGP, is de opdracht:

   ```
   <path-to_pgp_if-not_global_or_server/>pgp.exe --decrypt --input nl6/var/vp/import/filename.pgp --passphrase "your password" --recipient recipient @email.com --verbose --output nl6/var/vp/import/filename
   ```

Zodra het verzoek wordt verwerkt, zullen de encryptie/decryptiebevelen op het **!UICONTROL Pre-processing stage]** gebied van de **[!UICONTROL Load file]** en **[!UICONTROL Extract file]** activiteiten beschikbaar zijn. U kunt deze gebruiken om de bestanden te decoderen of te coderen die u wilt importeren of exporteren.

![](assets/preprocessing-encryption.png)

**Verwante onderwerpen:**

* [Bestand laden](../../automating/using/load-file.md)
* [Bestand uitpakken](../../automating/using/extract-file.md)

## Workflowsjablonen maken om gegevens te importeren {#example--import-workflow-template}

Het gebruik van een importsjabloon is de beste manier als u regelmatig bestanden met dezelfde structuur moet importeren.

In dit voorbeeld ziet u hoe u een workflow instelt die opnieuw kan worden gebruikt voor het importeren van profielen die afkomstig zijn van een CRM in de Adobe Campagne-database.

1. Een nieuw werkstroomsjabloon maken op basis van **[!UICONTROL Resources > Templates > Workflow templates]**.
1. Voeg de volgende activiteiten toe:

   * **[!UICONTROL Load file]**: Definieer de verwachte structuur van het bestand met de gegevens die u wilt importeren.

      >[!NOTE]
      >
      >U kunt slechts gegevens uit één bestand importeren. Als de workflow meerdere **[!UICONTROL Load file]** activiteiten heeft, wordt steeds hetzelfde bestand gebruikt.

   * **[!UICONTROL Reconciliation]**: De geïmporteerde gegevens afstemmen op de databasegegevens.
   * **[!UICONTROL Segmentation]**: Maak filters om records op een andere manier te verwerken, afhankelijk van de vraag of ze met elkaar in overeenstemming kunnen worden gebracht.
   * **[!UICONTROL Deduplication]**: Dupliceer de gegevens uit het binnenkomende bestand voordat deze in de database worden ingevoegd.
   * **[!UICONTROL Update data]**: Werk de database bij met de geïmporteerde profielen.
   ![](assets/import_template_example0.png)

1. Configureer de **[!UICONTROL Load file]** activiteit:

   * Definieer de verwachte structuur door een voorbeeldbestand te uploaden. Het voorbeeldbestand mag slechts een paar regels bevatten, maar alle kolommen die nodig zijn voor het importeren. Controleer en bewerk de bestandsindeling om te controleren of het type van elke kolom correct is ingesteld: tekst, datum, geheel getal, enz. Bijvoorbeeld:

      ```
      lastname;firstname;birthdate;email;crmID
      Smith;Hayden;23/05/1989;hayden.smith@mailtest.com;123456
      ```

   * Selecteer in de **[!UICONTROL File to load]** sectie de velden **[!UICONTROL Upload a new file from the local machine]** en laat deze leeg. Telkens wanneer een nieuwe werkstroom van dit malplaatje wordt gecreeerd, kunt u hier het dossier specificeren u wilt, zolang het aan de bepaalde structuur beantwoordt.

      U kunt alle opties gebruiken, maar u moet de sjabloon dienovereenkomstig aanpassen. Als u bijvoorbeeld een optie selecteert **[!UICONTROL Use the file specified in the inbound transition]**, kunt u een **[!UICONTROL Transfer file]** activiteit toevoegen voordat u het bestand ophaalt dat u wilt importeren van een FTP-/SFTP-server.

      Als u wilt dat gebruikers een bestand kunnen downloaden dat fouten bevat die tijdens het importeren zijn opgetreden, controleert u de **[!UICONTROL Keep the rejects in a file]** optie en geeft u de **[!UICONTROL File name]** optie op.

      ![](assets/import_template_example1.png)

1. Configureer de **[!UICONTROL Reconciliation]** activiteit. Het doel van deze activiteit in dit verband is de identificatie van de binnenkomende gegevens.

   * Selecteer **[!UICONTROL Relations]** en definieer op het **[!UICONTROL Create element]** tabblad een koppeling tussen de geïmporteerde gegevens en de ontvangers voor dimensie (zie [Doelafmetingen en -bronnen](../../automating/using/query.md#targeting-dimensions-and-resources)). In dit voorbeeld, wordt het de douaneveld van identiteitskaart van **CRM** gebruikt om te creëren toetreedt voorwaarde. Gebruik het veld of de combinatie van velden die u nodig hebt, zolang u unieke records kunt identificeren.
   * Laat op het **[!UICONTROL Identification]** tabblad de **[!UICONTROL Identify the document from the working data]** optie uitgeschakeld.
   ![](assets/import_template_example2.png)

1. Configureer de **[!UICONTROL Segmentation]** activiteit om onderling afgestemde ontvangers in één overgang en ontvangers op te halen die niet in overeenstemming konden worden gebracht maar die voldoende gegevens in een tweede overgang hebben.

   De overgang met onderling verzochte ontvangers kan dan worden gebruikt om het gegevensbestand bij te werken. De overgang met onbekende ontvangers kan dan worden gebruikt om nieuwe ontvankelijke ingangen in het gegevensbestand tot stand te brengen als een minimumreeks informatie in het dossier beschikbaar is.

   Ontvangers die niet in overeenstemming kunnen worden gebracht en niet genoeg gegevens hebben, worden in een complementaire uitgaande overgang geselecteerd en kunnen in een afzonderlijk bestand worden geëxporteerd of eenvoudig worden genegeerd.

   * Stel op het **[!UICONTROL General]** tabblad van de activiteit de gewenste set in **[!UICONTROL Resource type]** op **[!UICONTROL Temporary resource]** en selecteer deze **[!UICONTROL Reconciliation]** .
   * Controleer op het **[!UICONTROL Advanced options]** tabblad de **[!UICONTROL Generate complement]** optie om te zien of een record niet in de database kan worden ingevoegd. Indien nodig kunt u de aanvullende gegevens verder verwerken: bestand exporteren, lijst bijwerken, enz.
   * In het eerste segment van het **[!UICONTROL Segments]** lusje, voeg een het filtreren voorwaarde op de binnenkomende bevolking toe om slechts verslagen te selecteren waarvoor identiteitskaart van CRM van het profiel niet aan 0 is. Op deze manier worden gegevens uit het bestand die overeenkomen met profielen uit de database, geselecteerd in die subset.

      ![](assets/import_template_example3.png)

   * Voeg een tweede segment toe dat onverzoenbare records selecteert die voldoende gegevens hebben om in de database te worden ingevoegd. Bijvoorbeeld: e-mailadres, voornaam en achternaam. Voor records die niet in overeenstemming zijn, is de CRM-id-waarde van het profiel gelijk aan 0.

      ![](assets/import_template_example3_2.png)

   * Alle records die niet in de eerste twee subsets zijn geselecteerd, worden in de **[!UICONTROL Complement]** subset geselecteerd.

1. Vorm de **[!UICONTROL Update data]** activiteit die na de eerste uitgaande overgang van de eerder gevormde **[!UICONTROL Segmentation]** activiteit wordt gevestigd.

   * Selecteren **[!UICONTROL Update]** alsof **[!UICONTROL Operation type]** de binnenkomende overgang alleen ontvangers bevat die al in de database aanwezig zijn.
   * Selecteer **[!UICONTROL Identification]** en definieer op het **[!UICONTROL Using reconciliation criteria]** tabblad een sleutel tussen de **[!UICONTROL Dimension to update]** - in dit geval Profielen - en de koppeling die in de **[!UICONTROL Reconciliation]** activiteit is gemaakt. In dit voorbeeld wordt het aangepaste veld **CRM-id** gebruikt.

      ![](assets/import_template_example6.png)

   * Geef op het **[!UICONTROL Fields to update]** tabblad de velden in de profieldimensie op die moeten worden bijgewerkt met de waarde van de corresponderende kolom in het bestand. Als de namen van de bestandskolommen identiek of bijna identiek zijn aan de namen van de afmetingsvelden van de ontvangers, kunt u de toverknop gebruiken om de verschillende velden automatisch aan te passen.

      ![](assets/import_template_example6_2.png)

      >[!NOTE]
      >
      >Als u directe mails naar deze profielen wilt verzenden, moet u ook een postadres opgeven. Deze informatie is namelijk van wezenlijk belang voor de provider van de directe mail. Controleer ook of het **[!UICONTROL Address specified]** vak in de gegevens van uw profielen is ingeschakeld. Als u deze optie vanuit een workflow wilt bijwerken, voegt u eenvoudig een element toe aan de velden die u wilt bijwerken, geeft u **1** op als **[!UICONTROL Source]** en selecteert u het `postalAddress/@addrDefined` veld als **[!UICONTROL Destination]**. Zie **[!UICONTROL Address specified]** dit document [voor meer informatie over direct mail en het gebruik van de](../../channels/using/about-direct-mail.md#recommendations)optie.

1. Configureer de **[!UICONTROL Deduplication]** activiteit die zich na de overgang bevindt en die niet-compatibele profielen bevat:

   * Stel op het **[!UICONTROL Properties]** tabblad de tijdelijke bron in die wordt gegenereerd door de **[!UICONTROL Resource type]** **[!UICONTROL Reconciliation]** activiteit van de workflow.

      ![](assets/import_template_example4.png)

   * In dit voorbeeld wordt het e-mailveld gebruikt om unieke profielen te zoeken. U kunt elk veld gebruiken waarvan u zeker weet dat het is ingevuld en deel uitmaakt van een unieke combinatie.
   * Kies een **[!UICONTROL Deduplication method]**. In dit geval bepaalt de toepassing automatisch welke records worden bijgehouden in het geval van duplicaten.
   ![](assets/import_template_example7.png)

1. Vorm de **[!UICONTROL Update data]** activiteit die na de eerder gevormde **[!UICONTROL Deduplication]** activiteit wordt gevestigd.

   * Selecteer deze optie **[!UICONTROL Insert only]** als **[!UICONTROL Operation type]** de inkomende overgang alleen profielen bevat die niet in de database voorkomen.
   * Selecteer **[!UICONTROL Identification]** en definieer op het **[!UICONTROL Using reconciliation criteria]** tabblad een sleutel tussen de **[!UICONTROL Dimension to update]** - in dit geval Profielen - en de koppeling die in de **[!UICONTROL Reconciliation]** activiteit is gemaakt. In dit voorbeeld wordt het aangepaste veld **CRM-id** gebruikt.

      ![](assets/import_template_example6.png)

   * Geef op het **[!UICONTROL Fields to update]** tabblad de velden in de profieldimensie op die moeten worden bijgewerkt met de waarde van de corresponderende kolom in het bestand. Als de namen van de bestandskolommen identiek of bijna identiek zijn aan de namen van de afmetingsvelden van de ontvangers, kunt u de toverknop gebruiken om de verschillende velden automatisch aan te passen.

      ![](assets/import_template_example6_2.png)

      >[!NOTE]
      >
      >Als u directe mails naar deze profielen wilt verzenden, moet u ook een postadres opgeven. Deze informatie is namelijk van wezenlijk belang voor de provider van de directe mail. Controleer ook of het **[!UICONTROL Address specified]** vak in de gegevens van uw profielen is ingeschakeld. Als u deze optie vanuit een workflow wilt bijwerken, voegt u eenvoudig een element toe aan de velden die u wilt bijwerken, geeft u **1** op als **[!UICONTROL Source]** en selecteert u het veld **[Postadres/@addrDefined]** als **[!UICONTROL Destination]**. Zie **[!UICONTROL Address specified]** dit document [voor meer informatie over direct mail en het gebruik van de](../../channels/using/about-direct-mail.md#recommendations)optie.

1. Na de derde overgang van de **[!UICONTROL Segmentation]** activiteit, voeg een **[!UICONTROL Extract file]** activiteit en een **[!UICONTROL Transfer file]** activiteit toe als u spoor van gegevens wilt houden die niet in het gegevensbestand worden opgenomen. Configureer die activiteiten om de kolom die u nodig hebt te exporteren en om het bestand over te brengen naar een FTP- of SFTP-server waar u het bestand kunt ophalen.
1. Voeg een **[!UICONTROL End]** activiteit toe en sla het werkschemamalplaatje op.

De sjabloon kan nu worden gebruikt en is beschikbaar voor elke nieuwe workflow. Alles is dan nodig om het bestand op te geven dat de gegevens bevat die in de **[!UICONTROL Load file]** activiteit moeten worden geïmporteerd.

![](assets/import_template_example9.png)
