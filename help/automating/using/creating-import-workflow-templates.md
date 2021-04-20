---
solution: Campaign Standard
product: campaign
title: Workflowsjablonen maken om data te importeren
description: Leer hoe u werkstroomsjablonen maakt om gegevens te importeren.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
role: Data Architect
level: Experienced
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '1176'
ht-degree: 1%

---


# Workflowsjablonen maken om data te importeren {#import-workflow-template}

Het gebruik van een importsjabloon is de beste manier als u regelmatig bestanden met dezelfde structuur moet importeren.

In dit voorbeeld ziet u hoe u een workflow instelt die opnieuw kan worden gebruikt voor het importeren van profielen die afkomstig zijn van een CRM in de Adobe Campaign-database.

1. Creeer een nieuw werkschemamalplaatje van **[!UICONTROL Resources > Templates > Workflow templates]**.
1. Voeg de volgende activiteiten toe:

   * **[!UICONTROL Load file]**: Definieer de verwachte structuur van het bestand met de gegevens die u wilt importeren.

      >[!NOTE]
      >
      >U kunt slechts gegevens uit één bestand importeren. Als de werkstroom meerdere **[!UICONTROL Load file]** activiteiten heeft, wordt steeds hetzelfde bestand gebruikt.

   * **[!UICONTROL Reconciliation]**: De geïmporteerde gegevens afstemmen op de databasegegevens.
   * **[!UICONTROL Segmentation]**: Maak filters om records op een andere manier te verwerken, afhankelijk van de vraag of ze met elkaar in overeenstemming kunnen worden gebracht.
   * **[!UICONTROL Deduplication]**: Dupliceer de gegevens uit het binnenkomende bestand voordat deze in de database worden ingevoegd.
   * **[!UICONTROL Update data]**: Werk de database bij met de geïmporteerde profielen.

   ![](assets/import_template_example0.png)

1. Configureer de **[!UICONTROL Load file]**-activiteit:

   * Definieer de verwachte structuur door een voorbeeldbestand te uploaden. Het voorbeeldbestand mag slechts een paar regels bevatten, maar alle kolommen die nodig zijn voor het importeren. Controleer en bewerk de bestandsindeling om te controleren of het type van elke kolom correct is ingesteld: tekst, datum, geheel getal, enz. Bijvoorbeeld:

      ```
      lastname;firstname;birthdate;email;crmID
      Smith;Hayden;23/05/1989;hayden.smith@mailtest.com;123456
      ```

   * Selecteer **[!UICONTROL Upload a new file from the local machine]** in de sectie **[!UICONTROL File to load]** en laat het veld leeg. Telkens wanneer een nieuwe werkstroom van dit malplaatje wordt gecreeerd, kunt u hier het dossier specificeren u wilt, zolang het aan de bepaalde structuur beantwoordt.

      U kunt alle opties gebruiken, maar u moet de sjabloon dienovereenkomstig aanpassen. Als u bijvoorbeeld **[!UICONTROL Use the file specified in the inbound transition]** selecteert, kunt u een **[!UICONTROL Transfer file]**-activiteit toevoegen voordat u het bestand ophaalt dat u wilt importeren vanaf een FTP-/SFTP-server.

      Als u wilt dat gebruikers een bestand kunnen downloaden dat fouten bevat die tijdens het importeren zijn opgetreden, schakelt u **[!UICONTROL Keep the rejects in a file]** in en geeft u **[!UICONTROL File name]** op.

      ![](assets/import_template_example1.png)

1. Configureer de **[!UICONTROL Reconciliation]**-activiteit. Het doel van deze activiteit in dit verband is de identificatie van de binnenkomende gegevens.

   * Selecteer **[!UICONTROL Relations]** op het tabblad **[!UICONTROL Create element]** en definieer een koppeling tussen de geïmporteerde gegevens en de ontvangers voor dimensie (zie [Doelafmetingen en bronnen](../../automating/using/query.md#targeting-dimensions-and-resources)). In dit voorbeeld wordt het aangepaste veld **CRM ID** gebruikt om de verbindingsvoorwaarde te maken. Gebruik het veld of de combinatie van velden die u nodig hebt, zolang u unieke records kunt identificeren.
   * Laat op het tabblad **[!UICONTROL Identification]** de optie **[!UICONTROL Identify the document from the working data]** uitgeschakeld.

   ![](assets/import_template_example2.png)

1. Configureer de **[!UICONTROL Segmentation]**-activiteit om onderling afgestemde ontvangers in één overgang en ontvangers op te halen die niet in overeenstemming konden worden gebracht, maar die voldoende gegevens in een tweede overgang hebben.

   De overgang met onderling verzochte ontvangers kan dan worden gebruikt om het gegevensbestand bij te werken. De overgang met onbekende ontvangers kan dan worden gebruikt om nieuwe ontvankelijke ingangen in het gegevensbestand tot stand te brengen als een minimumreeks informatie in het dossier beschikbaar is.

   Ontvangers die niet in overeenstemming kunnen worden gebracht en niet genoeg gegevens hebben, worden in een complementaire uitgaande overgang geselecteerd en kunnen in een afzonderlijk bestand worden geëxporteerd of eenvoudig worden genegeerd.

   * Stel op het tabblad **[!UICONTROL General]** van de activiteit **[!UICONTROL Resource type]** in op **[!UICONTROL Temporary resource]** en selecteer **[!UICONTROL Reconciliation]** als doelset.
   * Controleer op het tabblad **[!UICONTROL Advanced options]** de optie **[!UICONTROL Generate complement]** om te kunnen zien of een record niet in de database kan worden ingevoegd. Indien nodig kunt u de aanvullende gegevens verder verwerken: bestand exporteren, lijst bijwerken, enz.
   * In het eerste segment van het **[!UICONTROL Segments]** lusje, voeg een het filtreren voorwaarde op de binnenkomende bevolking toe om slechts verslagen te selecteren waarvoor identiteitskaart van CRM van het profiel niet gelijk aan 0 is. Op deze manier worden gegevens uit het bestand die overeenkomen met profielen uit de database, geselecteerd in die subset.

      ![](assets/import_template_example3.png)

   * Voeg een tweede segment toe dat onverzoenbare records selecteert die voldoende gegevens hebben om in de database te worden ingevoegd. Bijvoorbeeld: e-mailadres, voornaam en achternaam. Voor records die niet in overeenstemming zijn, is de CRM-id-waarde van het profiel gelijk aan 0.

      ![](assets/import_template_example3_2.png)

   * Alle verslagen die niet in de eerste twee subsets worden geselecteerd worden geselecteerd in **[!UICONTROL Complement]**.

1. Vorm de **[!UICONTROL Update data]** activiteit die na de eerste uitgaande overgang van de **[!UICONTROL Segmentation]** eerder gevormde activiteit wordt gevestigd.

   * Selecteer **[!UICONTROL Update]** als **[!UICONTROL Operation type]** omdat de binnenkomende overgang alleen ontvangers bevat die al in de database aanwezig zijn.
   * Selecteer **[!UICONTROL Identification]** op het tabblad **[!UICONTROL Using reconciliation criteria]** en definieer een sleutel tussen **[!UICONTROL Dimension to update]** - In dit geval Profielen - en de koppeling die wordt gemaakt in de **[!UICONTROL Reconciliation]**-activiteit. In dit voorbeeld wordt het aangepaste veld **CRM ID** gebruikt.

      ![](assets/import_template_example6.png)

   * Geef op het tabblad **[!UICONTROL Fields to update]** de velden in de profieldimensie op die moeten worden bijgewerkt met de waarde van de corresponderende kolom in het bestand. Als de namen van de bestandskolommen identiek of bijna identiek zijn aan de namen van de afmetingsvelden van de ontvangers, kunt u de toverknop gebruiken om de verschillende velden automatisch aan te passen.

      ![](assets/import_template_example6_2.png)

      >[!NOTE]
      >
      >Als u directe mails naar deze profielen wilt verzenden, moet u ook een postadres opgeven. Deze informatie is namelijk van wezenlijk belang voor de provider van de directe mail. Controleer ook of het vak **[!UICONTROL Address specified]** in de gegevens van uw profielen is ingeschakeld. Als u deze optie vanuit een workflow wilt bijwerken, voegt u eenvoudig een element toe aan de velden die u wilt bijwerken, geeft u **1** op als **[!UICONTROL Source]** en selecteert u het veld `postalAddress/@addrDefined` als **[!UICONTROL Destination]**. Zie [dit document](../../channels/using/about-direct-mail.md#recommendations) voor meer informatie over direct mail en het gebruik van de optie **[!UICONTROL Address specified]**.

1. Configureer de **[!UICONTROL Deduplication]**-activiteit die zich na de overgang bevindt en die niet-compatibele profielen bevat:

   * Stel op het tabblad **[!UICONTROL Properties]** de **[!UICONTROL Resource type]** in op de tijdelijke bron die wordt gegenereerd door de **[!UICONTROL Reconciliation]**-activiteit van de workflow.

      ![](assets/import_template_example4.png)

   * In dit voorbeeld wordt het e-mailveld gebruikt om unieke profielen te zoeken. U kunt elk veld gebruiken waarvan u zeker weet dat het is ingevuld en deel uitmaakt van een unieke combinatie.
   * Kies een **[!UICONTROL Deduplication method]**. In dit geval bepaalt de toepassing automatisch welke records worden bijgehouden in het geval van duplicaten.

   ![](assets/import_template_example7.png)

1. Vorm **[!UICONTROL Update data]** activiteit die na **[!UICONTROL Deduplication]** eerder gevormde activiteit wordt gevestigd.

   * Selecteer **[!UICONTROL Insert only]** als **[!UICONTROL Operation type]** aangezien de binnenkomende overgang slechts profielen bevat die niet in het gegevensbestand aanwezig zijn.
   * Selecteer **[!UICONTROL Identification]** op het tabblad **[!UICONTROL Using reconciliation criteria]** en definieer een sleutel tussen **[!UICONTROL Dimension to update]** - In dit geval Profielen - en de koppeling die wordt gemaakt in de **[!UICONTROL Reconciliation]**-activiteit. In dit voorbeeld wordt het aangepaste veld **CRM ID** gebruikt.

      ![](assets/import_template_example6.png)

   * Geef op het tabblad **[!UICONTROL Fields to update]** de velden in de profieldimensie op die moeten worden bijgewerkt met de waarde van de corresponderende kolom in het bestand. Als de namen van de bestandskolommen identiek of bijna identiek zijn aan de namen van de afmetingsvelden van de ontvangers, kunt u de toverknop gebruiken om de verschillende velden automatisch aan te passen.

      ![](assets/import_template_example6_2.png)

      >[!NOTE]
      >
      >Als u directe mails naar deze profielen wilt verzenden, moet u ook een postadres opgeven. Deze informatie is namelijk van wezenlijk belang voor de provider van de directe mail. Controleer ook of het vak **[!UICONTROL Address specified]** in de gegevens van uw profielen is ingeschakeld. Als u deze optie vanuit een workflow wilt bijwerken, voegt u eenvoudig een element toe aan de velden die u wilt bijwerken, geeft u **1** op als **[!UICONTROL Source]** en selecteert u het veld **[postalAddress/@addrDefined]** als **[!UICONTROL Destination]**. Zie [dit document](../../channels/using/about-direct-mail.md#recommendations) voor meer informatie over direct mail en het gebruik van de optie **[!UICONTROL Address specified]**.

1. Na de derde overgang van de **[!UICONTROL Segmentation]** activiteit, voeg **[!UICONTROL Extract file]** activiteit en **[!UICONTROL Transfer file]** activiteit toe als u spoor van gegevens wilt houden die niet in het gegevensbestand worden opgenomen. Configureer die activiteiten om de kolom die u nodig hebt te exporteren en om het bestand over te brengen naar een FTP- of SFTP-server waar u het bestand kunt ophalen.
1. Voeg een **[!UICONTROL End]** activiteit toe en sla het werkschemamalplaatje op.

De sjabloon kan nu worden gebruikt en is beschikbaar voor elke nieuwe workflow. Alles is dan nodig om het bestand op te geven dat de gegevens bevat die in de **[!UICONTROL Load file]**-activiteit moeten worden geïmporteerd.

![](assets/import_template_example9.png)
