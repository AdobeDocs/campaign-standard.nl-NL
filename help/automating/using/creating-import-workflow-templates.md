---
title: Workflowsjablonen maken om gegevens te importeren
description: Leer hoe u werkstroomsjablonen maakt om gegevens te importeren.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 5974a52c-8721-4575-b452-2982d6497235
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '1176'
ht-degree: 1%

---

# Workflowsjablonen maken om gegevens te importeren {#import-workflow-template}

Het gebruik van een importsjabloon is de beste manier als u regelmatig bestanden met dezelfde structuur moet importeren.

In dit voorbeeld ziet u hoe u een workflow instelt die opnieuw kan worden gebruikt voor het importeren van profielen die afkomstig zijn van een CRM in de Adobe Campaign-database.

1. Maak een nieuw werkstroomsjabloon vanuit **[!UICONTROL Resources > Templates > Workflow templates]** .
1. Voeg de volgende activiteiten toe:

   * **[!UICONTROL Load file]**: hiermee definieert u de verwachte structuur van het bestand met de gegevens die u wilt importeren.

     >[!NOTE]
     >
     >U kunt slechts gegevens uit één bestand importeren. Als de workflow meerdere **[!UICONTROL Load file]** -activiteiten bevat, wordt steeds hetzelfde bestand gebruikt.

   * **[!UICONTROL Reconciliation]**: combineer de geïmporteerde gegevens met databasegegevens.
   * **[!UICONTROL Segmentation]**: maak filters om records te verwerken die anders zijn, afhankelijk van de vraag of ze met elkaar in overeenstemming kunnen worden gebracht.
   * **[!UICONTROL Deduplication]**: dupliceer de gegevens uit het binnenkomende bestand voordat deze in de database worden ingevoegd.
   * **[!UICONTROL Update data]**: Werk de database bij met de geïmporteerde profielen.

   ![](assets/import_template_example0.png)

1. Configureer de **[!UICONTROL Load file]** -activiteit:

   * Geef de verwachte structuur op door een voorbeeldbestand te uploaden. Het voorbeeldbestand mag slechts een paar regels bevatten, maar alle kolommen die nodig zijn voor het importeren. Controleer en bewerk de bestandsindeling om ervoor te zorgen dat het type van elke kolom correct is ingesteld: tekst, datum, geheel getal, enz. Bijvoorbeeld:

     ```
     lastname;firstname;birthdate;email;crmID
     Smith;Hayden;23/05/1989;hayden.smith@mailtest.com;123456
     ```

   * Selecteer **[!UICONTROL File to load]** in de sectie **[!UICONTROL Upload a new file from the local machine]** en laat het veld leeg. Telkens wanneer een nieuwe werkstroom van dit malplaatje wordt gecreeerd, kunt u hier het dossier specificeren u wilt, zolang het aan de bepaalde structuur beantwoordt.

     U kunt alle opties gebruiken, maar u moet de sjabloon dienovereenkomstig aanpassen. Als u bijvoorbeeld **[!UICONTROL Use the file specified in the inbound transition]** selecteert, kunt u een **[!UICONTROL Transfer file]** -activiteit toevoegen voordat u het bestand ophaalt dat u wilt importeren van een FTP-/SFTP-server.

     Als u wilt dat gebruikers een bestand kunnen downloaden dat fouten bevat die tijdens het importeren zijn opgetreden, schakelt u de optie **[!UICONTROL Keep the rejects in a file]** in en geeft u **[!UICONTROL File name]** op.

     ![](assets/import_template_example1.png)

1. Configureer de **[!UICONTROL Reconciliation]** -activiteit. Het doel van deze activiteit in dit verband is de identificatie van de binnenkomende gegevens.

   * In het **[!UICONTROL Relations]** lusje, selecteer **[!UICONTROL Create element]** en bepaal een verband tussen de ingevoerde gegevens en de ontvangers gericht op afmeting (zie [&#x200B; het richten dimensies en middelen &#x200B;](../../automating/using/query.md#targeting-dimensions-and-resources)). In dit voorbeeld, wordt het **douanegebied van identiteitskaart van 0&rbrace; CRM &lbrace;gebruikt om te creëren zich bij voorwaarde aansluit.** Gebruik het veld of de combinatie van velden die u nodig hebt, zolang u unieke records kunt identificeren.
   * Laat op het tabblad **[!UICONTROL Identification]** de optie **[!UICONTROL Identify the document from the working data]** uitgeschakeld.

   ![](assets/import_template_example2.png)

1. Configureer de **[!UICONTROL Segmentation]** -activiteit om onderling afgestemde ontvangers in één overgang en ontvangers op te halen die niet in overeenstemming konden worden gebracht maar die voldoende gegevens in een tweede overgang hebben.

   De overgang met onderling verzochte ontvangers kan dan worden gebruikt om het gegevensbestand bij te werken. De overgang met onbekende ontvangers kan dan worden gebruikt om nieuwe ontvankelijke ingangen in het gegevensbestand tot stand te brengen als een minimumreeks informatie in het dossier beschikbaar is.

   Ontvangers die niet in overeenstemming kunnen worden gebracht en niet genoeg gegevens hebben, worden in een complementaire uitgaande overgang geselecteerd en kunnen in een afzonderlijk bestand worden geëxporteerd of eenvoudig worden genegeerd.

   * Stel op het tabblad **[!UICONTROL General]** van de activiteit de waarde **[!UICONTROL Resource type]** in op **[!UICONTROL Temporary resource]** en selecteer **[!UICONTROL Reconciliation]** als doelset.
   * Controleer op het tabblad **[!UICONTROL Advanced options]** de optie **[!UICONTROL Generate complement]** om te zien of een record niet in de database kan worden ingevoegd. Indien nodig kunt u de aanvullende gegevens verder verwerken: bestanden exporteren, lijst bijwerken, enz.
   * In het eerste segment van het tabblad **[!UICONTROL Segments]** voegt u een filtervoorwaarde toe aan de binnenkomende populatie om alleen records te selecteren waarvoor de CRM-id van het profiel niet gelijk is aan 0. Op deze manier worden gegevens uit het bestand die overeenkomen met profielen uit de database, geselecteerd in die subset.

     ![](assets/import_template_example3.png)

   * Voeg een tweede segment toe dat onverzoenbare records selecteert die voldoende gegevens hebben om in de database te worden ingevoegd. Bijvoorbeeld: e-mailadres, voornaam en achternaam. Voor records die niet in overeenstemming zijn, is de CRM-id-waarde van het profiel gelijk aan 0.

     ![](assets/import_template_example3_2.png)

   * Alle records die niet in de eerste twee subsets zijn geselecteerd, worden in de **[!UICONTROL Complement]** geselecteerd.

1. Configureer de **[!UICONTROL Update data]** -activiteit die zich na de eerste uitgaande overgang van de eerder geconfigureerde **[!UICONTROL Segmentation]** -activiteit bevindt.

   * Selecteer **[!UICONTROL Update]** als **[!UICONTROL Operation type]** omdat de inkomende overgang alleen ontvangers bevat die al in de database aanwezig zijn.
   * Selecteer op het tabblad **[!UICONTROL Identification]** **[!UICONTROL Using reconciliation criteria]** en definieer een sleutel tussen **[!UICONTROL Dimension to update]** (In dit geval Profielen) en de koppeling die in de **[!UICONTROL Reconciliation]** -activiteit is gemaakt. In dit voorbeeld, wordt het **douanegebied van identiteitskaart van 0&rbrace; CRM &lbrace;gebruikt.**

     ![](assets/import_template_example6.png)

   * Geef op het tabblad **[!UICONTROL Fields to update]** de velden in de profieldimensie op die moeten worden bijgewerkt met de waarde van de corresponderende kolom in het bestand. Als de namen van de bestandskolommen identiek of bijna identiek zijn aan de namen van de afmetingsvelden van de ontvangers, kunt u de toverknop gebruiken om de verschillende velden automatisch aan te passen.

     ![](assets/import_template_example6_2.png)

     >[!NOTE]
     >
     >Als u directe mails naar deze profielen wilt verzenden, moet u ook een postadres opgeven. Deze informatie is namelijk van wezenlijk belang voor de provider van de directe mail. Controleer ook of het vak **[!UICONTROL Address specified]** in de gegevens van uw profielen is ingeschakeld. Om deze optie van een werkschema bij te werken, voeg eenvoudig een element aan de bij te werken gebieden toe, en specificeer **1** als **[!UICONTROL Source]** en selecteer het `postalAddress/@addrDefined` gebied als **[!UICONTROL Destination]**. Voor meer op directe post en het gebruik van de **[!UICONTROL Address specified]** optie, zie [&#x200B; dit document &#x200B;](../../channels/using/about-direct-mail.md#recommendations).

1. Configureer de **[!UICONTROL Deduplication]** -activiteit die zich bevindt na de overgang met niet-compatibele profielen:

   * Stel op het tabblad **[!UICONTROL Properties]** de **[!UICONTROL Resource type]** in op de tijdelijke bron die is gegenereerd op basis van de **[!UICONTROL Reconciliation]** -activiteit van de workflow.

     ![](assets/import_template_example4.png)

   * In dit voorbeeld wordt het e-mailveld gebruikt om unieke profielen te zoeken. U kunt elk veld gebruiken waarvan u zeker weet dat het is ingevuld en deel uitmaakt van een unieke combinatie.
   * Kies een **[!UICONTROL Deduplication method]** . In dit geval bepaalt de toepassing automatisch welke records worden bijgehouden in het geval van duplicaten.

   ![](assets/import_template_example7.png)

1. Configureer de **[!UICONTROL Update data]** -activiteit die zich bevindt na de **[!UICONTROL Deduplication]** -activiteit die eerder is geconfigureerd.

   * Selecteer **[!UICONTROL Insert only]** as **[!UICONTROL Operation type]** omdat de inkomende overgang alleen profielen bevat die niet aanwezig zijn in de database.
   * Selecteer op het tabblad **[!UICONTROL Identification]** **[!UICONTROL Using reconciliation criteria]** en definieer een sleutel tussen **[!UICONTROL Dimension to update]** (In dit geval Profielen) en de koppeling die in de **[!UICONTROL Reconciliation]** -activiteit is gemaakt. In dit voorbeeld, wordt het **douanegebied van identiteitskaart van 0&rbrace; CRM &lbrace;gebruikt.**

     ![](assets/import_template_example6.png)

   * Geef op het tabblad **[!UICONTROL Fields to update]** de velden in de profieldimensie op die moeten worden bijgewerkt met de waarde van de corresponderende kolom in het bestand. Als de namen van de bestandskolommen identiek of bijna identiek zijn aan de namen van de afmetingsvelden van de ontvangers, kunt u de toverknop gebruiken om de verschillende velden automatisch aan te passen.

     ![](assets/import_template_example6_2.png)

     >[!NOTE]
     >
     >Als u directe mails naar deze profielen wilt verzenden, moet u ook een postadres opgeven. Deze informatie is namelijk van wezenlijk belang voor de provider van de directe mail. Controleer ook of het vak **[!UICONTROL Address specified]** in de gegevens van uw profielen is ingeschakeld. Om deze optie van een werkschema bij te werken, voeg eenvoudig een element aan de bij te werken gebieden toe, en specificeer **1** als **[!UICONTROL Source]** en selecteer **[postalAddress/@addrDefined]** gebied als **[!UICONTROL Destination]**. Voor meer op directe post en het gebruik van de **[!UICONTROL Address specified]** optie, zie [&#x200B; dit document &#x200B;](../../channels/using/about-direct-mail.md#recommendations).

1. Voeg na de derde overgang van de **[!UICONTROL Segmentation]** -activiteit een **[!UICONTROL Extract file]** activiteit en een **[!UICONTROL Transfer file]** activiteit toe als u wilt bijhouden welke gegevens niet in de database zijn ingevoegd. Configureer die activiteiten om de kolom die u nodig hebt te exporteren en om het bestand over te brengen naar een FTP- of SFTP-server waar u het bestand kunt ophalen.
1. Voeg een **[!UICONTROL End]** -activiteit toe en sla de werkstroomsjabloon op.

De sjabloon kan nu worden gebruikt en is beschikbaar voor elke nieuwe workflow. U hoeft alleen het bestand op te geven dat de gegevens bevat die u wilt importeren in de **[!UICONTROL Load file]** -activiteit.

![](assets/import_template_example9.png)
