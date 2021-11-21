---
title: Workflowsjablonen maken om gegevens te importeren
description: Leer hoe u werkstroomsjablonen maakt om gegevens te importeren.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
role: Data Architect
level: Experienced
exl-id: 5974a52c-8721-4575-b452-2982d6497235
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '1172'
ht-degree: 1%

---

# Workflowsjablonen maken om gegevens te importeren {#import-workflow-template}

Het gebruik van een importsjabloon is de beste manier als u regelmatig bestanden met dezelfde structuur moet importeren.

In dit voorbeeld ziet u hoe u een workflow instelt die opnieuw kan worden gebruikt voor het importeren van profielen die afkomstig zijn van een CRM in de Adobe Campaign-database.

1. Een nieuw werkstroomsjabloon maken op basis van **[!UICONTROL Resources > Templates > Workflow templates]**.
1. Voeg de volgende activiteiten toe:

   * **[!UICONTROL Load file]**: Definieer de verwachte structuur van het bestand met de gegevens die u wilt importeren.

      >[!NOTE]
      >
      >U kunt slechts gegevens uit één bestand importeren. Als de workflow meerdere **[!UICONTROL Load file]** wordt telkens hetzelfde bestand gebruikt.

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

   * In de **[!UICONTROL File to load]** sectie, selecteert u **[!UICONTROL Upload a new file from the local machine]** en laat het veld leeg. Telkens wanneer een nieuwe werkstroom van dit malplaatje wordt gecreeerd, kunt u hier het dossier specificeren u wilt, zolang het aan de bepaalde structuur beantwoordt.

      U kunt alle opties gebruiken, maar u moet de sjabloon dienovereenkomstig aanpassen. Als u bijvoorbeeld **[!UICONTROL Use the file specified in the inbound transition]** kunt u een **[!UICONTROL Transfer file]** activiteit voor het ophalen van het bestand dat moet worden geïmporteerd van een FTP-/SFTP-server.

      Als u wilt dat gebruikers een bestand kunnen downloaden dat fouten bevat die tijdens het importeren zijn opgetreden, controleert u de knop **[!UICONTROL Keep the rejects in a file]** en geeft u de **[!UICONTROL File name]**.

      ![](assets/import_template_example1.png)

1. Configureer de **[!UICONTROL Reconciliation]** activiteit. Het doel van deze activiteit in dit verband is de identificatie van de binnenkomende gegevens.

   * In de **[!UICONTROL Relations]** tab, selecteert u **[!UICONTROL Create element]** en definieert u een koppeling tussen de geïmporteerde gegevens en de ontvangers voor dimensie (zie [Doeldimensies en bronnen](../../automating/using/query.md#targeting-dimensions-and-resources)). In dit voorbeeld wordt **CRM-id** Het aangepaste gebied wordt gebruikt om tot de te verbinden voorwaarde te leiden. Gebruik het veld of de combinatie van velden die u nodig hebt, zolang u unieke records kunt identificeren.
   * In de **[!UICONTROL Identification]** tabblad, laat de **[!UICONTROL Identify the document from the working data]** optie uitgeschakeld.

   ![](assets/import_template_example2.png)

1. Configureer de **[!UICONTROL Segmentation]** activiteit om verenigde ontvangers in één overgang en ontvangers terug te winnen die niet in overeenstemming konden worden gebracht maar die genoeg gegevens in een tweede overgang hebben.

   De overgang met onderling verzochte ontvangers kan dan worden gebruikt om het gegevensbestand bij te werken. De overgang met onbekende ontvangers kan dan worden gebruikt om nieuwe ontvankelijke ingangen in het gegevensbestand tot stand te brengen als een minimumreeks informatie in het dossier beschikbaar is.

   Ontvangers die niet in overeenstemming kunnen worden gebracht en niet genoeg gegevens hebben, worden in een complementaire uitgaande overgang geselecteerd en kunnen in een afzonderlijk bestand worden geëxporteerd of eenvoudig worden genegeerd.

   * In de **[!UICONTROL General]** tabblad van de activiteit, stelt u de **[!UICONTROL Resource type]** tot **[!UICONTROL Temporary resource]** en selecteert u **[!UICONTROL Reconciliation]** als de beoogde set.
   * In de **[!UICONTROL Advanced options]** tabblad, controleert u de **[!UICONTROL Generate complement]** om te kunnen zien of kan om het even welk verslag niet in het gegevensbestand worden opgenomen. Indien nodig kunt u de aanvullende gegevens verder verwerken: bestand exporteren, lijst bijwerken, enz.
   * In het eerste segment van het **[!UICONTROL Segments]** tabblad, voegt u een filtervoorwaarde toe aan de binnenkomende populatie om alleen records te selecteren waarvoor de CRM-id van het profiel niet gelijk is aan 0. Op deze manier worden gegevens uit het bestand die overeenkomen met profielen uit de database, geselecteerd in die subset.

      ![](assets/import_template_example3.png)

   * Voeg een tweede segment toe dat onverzoenbare records selecteert die voldoende gegevens hebben om in de database te worden ingevoegd. Bijvoorbeeld: e-mailadres, voornaam en achternaam. Voor records die niet in overeenstemming zijn, is de CRM-id-waarde van het profiel gelijk aan 0.

      ![](assets/import_template_example3_2.png)

   * Alle records die niet in de eerste twee subsets zijn geselecteerd, worden geselecteerd in het dialoogvenster **[!UICONTROL Complement]**.

1. Configureer de **[!UICONTROL Update data]** activiteit die na de eerste uitgaande overgang van wordt gevestigd **[!UICONTROL Segmentation]** eerder geconfigureerde activiteit.

   * Selecteren **[!UICONTROL Update]** als **[!UICONTROL Operation type]** aangezien de binnenkomende overgang slechts ontvangers bevat die reeds in het gegevensbestand aanwezig zijn.
   * In de **[!UICONTROL Identification]** tab, selecteert u **[!UICONTROL Using reconciliation criteria]** en definieert u een sleutel tussen de **[!UICONTROL Dimension to update]** - Profielen in dit geval - en de koppeling die in het dialoogvenster **[!UICONTROL Reconciliation]** activiteit. In dit voorbeeld wordt **CRM-id** aangepast veld wordt gebruikt.

      ![](assets/import_template_example6.png)

   * In de **[!UICONTROL Fields to update]** , geeft u de velden in de profieldimensie aan die u wilt bijwerken met de waarde van de corresponderende kolom in het bestand. Als de namen van de bestandskolommen identiek of bijna identiek zijn aan de namen van de afmetingsvelden van de ontvangers, kunt u de toverknop gebruiken om de verschillende velden automatisch aan te passen.

      ![](assets/import_template_example6_2.png)

      >[!NOTE]
      >
      >Als u directe mails naar deze profielen wilt verzenden, moet u ook een postadres opgeven. Deze informatie is namelijk van wezenlijk belang voor de provider van de directe mail. Zorg er ook voor dat de **[!UICONTROL Address specified]** in de gegevens van uw profielen is ingeschakeld. Als u deze optie vanuit een workflow wilt bijwerken, voegt u eenvoudig een element toe aan de bij te werken velden en geeft u **1** als **[!UICONTROL Source]** en selecteert u de `postalAddress/@addrDefined` veld als **[!UICONTROL Destination]**. Voor meer informatie over direct mail en het gebruik van **[!UICONTROL Address specified]** optie, zie [dit document](../../channels/using/about-direct-mail.md#recommendations).

1. Configureer de **[!UICONTROL Deduplication]** activiteit die zich na de overgang bevindt die niet-compatibele profielen bevat:

   * In de **[!UICONTROL Properties]** tabblad, stelt u de **[!UICONTROL Resource type]** aan de tijdelijke bron die door de **[!UICONTROL Reconciliation]** activiteit van de workflow.

      ![](assets/import_template_example4.png)

   * In dit voorbeeld wordt het e-mailveld gebruikt om unieke profielen te zoeken. U kunt elk veld gebruiken waarvan u zeker weet dat het is ingevuld en deel uitmaakt van een unieke combinatie.
   * Kies een **[!UICONTROL Deduplication method]**. In dit geval bepaalt de toepassing automatisch welke records worden bijgehouden in het geval van duplicaten.

   ![](assets/import_template_example7.png)

1. Configureer de **[!UICONTROL Update data]** activiteit die zich na de **[!UICONTROL Deduplication]** eerder geconfigureerde activiteit.

   * Selecteren **[!UICONTROL Insert only]** als **[!UICONTROL Operation type]** omdat de inkomende overgang alleen profielen bevat die niet aanwezig zijn in de database.
   * In de **[!UICONTROL Identification]** tab, selecteert u **[!UICONTROL Using reconciliation criteria]** en definieert u een sleutel tussen de **[!UICONTROL Dimension to update]** - Profielen in dit geval - en de koppeling die in het dialoogvenster **[!UICONTROL Reconciliation]** activiteit. In dit voorbeeld wordt **CRM-id** aangepast veld wordt gebruikt.

      ![](assets/import_template_example6.png)

   * In de **[!UICONTROL Fields to update]** , geeft u de velden in de profieldimensie aan die u wilt bijwerken met de waarde van de corresponderende kolom in het bestand. Als de namen van de bestandskolommen identiek of bijna identiek zijn aan de namen van de afmetingsvelden van de ontvangers, kunt u de toverknop gebruiken om de verschillende velden automatisch aan te passen.

      ![](assets/import_template_example6_2.png)

      >[!NOTE]
      >
      >Als u directe mails naar deze profielen wilt verzenden, moet u ook een postadres opgeven. Deze informatie is namelijk van wezenlijk belang voor de provider van de directe mail. Zorg er ook voor dat de **[!UICONTROL Address specified]** in de gegevens van uw profielen is ingeschakeld. Als u deze optie vanuit een workflow wilt bijwerken, voegt u eenvoudig een element toe aan de bij te werken velden en geeft u **1** als **[!UICONTROL Source]** en selecteert u de **[postalAddress/@addrDefined]** veld als **[!UICONTROL Destination]**. Voor meer informatie over direct mail en het gebruik van **[!UICONTROL Address specified]** optie, zie [dit document](../../channels/using/about-direct-mail.md#recommendations).

1. Na de derde overgang van de **[!UICONTROL Segmentation]** activiteit, voeg een **[!UICONTROL Extract file]** en **[!UICONTROL Transfer file]** activiteit als u spoor van gegevens wilt houden die niet in het gegevensbestand worden opgenomen. Configureer die activiteiten om de kolom die u nodig hebt te exporteren en om het bestand over te brengen naar een FTP- of SFTP-server waar u het bestand kunt ophalen.
1. Een **[!UICONTROL End]** en sla het werkstroomsjabloon op.

De sjabloon kan nu worden gebruikt en is beschikbaar voor elke nieuwe workflow. Het bestand met de gegevens die u wilt importeren in het dialoogvenster **[!UICONTROL Load file]** activiteit.

![](assets/import_template_example9.png)
