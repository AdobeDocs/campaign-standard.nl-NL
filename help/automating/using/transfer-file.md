---
title: Bestand overbrengen
description: Met de bestandsactiviteit Overdracht kunt u bestanden ontvangen of verzenden, testen of er bestanden aanwezig zijn of kunt u een lijst met bestanden weergeven in Adobe Campaign.
page-status-flag: never-activated
uuid: a2f18118-b681-4310-aee0-9e82179d2032
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: 752f2aed-f897-485e-b329-f3cc1756ee8e
context-tags: fileTransfer,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 175709a41607bb9d64da7fac77dd749fa84f7360
workflow-type: tm+mt
source-wordcount: '1075'
ht-degree: 0%

---


# Bestand overbrengen{#transfer-file}

## Beschrijving {#description}

![](assets/file_transfer.png)

Met deze **[!UICONTROL Transfer file]** activiteit kunt u bestanden ontvangen of verzenden, testen of er bestanden aanwezig zijn of kunt u een lijst met bestanden weergeven in Adobe Campaign.

>[!CAUTION]
>
>Vanaf versie 20.3 worden bestanden die met de **[!UICONTROL Transfer File]** activiteit zijn gedownload, na X dagen verwijderd, waarbij X wordt bepaald door het **[!UICONTROL History in days]** veld onder het **[!UICONTROL Execution]** menu in de Workfloweigenschappen.

## Gebruikscontext {#context-of-use}

De manier waarop de gegevens worden geëxtraheerd, wordt gedefinieerd wanneer de activiteit wordt geconfigureerd. Het te laden bestand kan bijvoorbeeld een lijst met contactpersonen zijn.

U kunt deze activiteit gebruiken om gegevens terug te krijgen die dan met de **[!UICONTROL Load file]** activiteit zullen worden gestructureerd.

**Verwante onderwerpen:**

* [Hoofdlettergebruik: Gegevens bijwerken op basis van een automatische bestandsdownload](../../automating/using/update-data-automatic-download.md)

## Configuratie {#configuration}

1. Zet een **[!UICONTROL Transfer file]** activiteit neer in uw werkschema.
1. Selecteer de activiteit, dan open het gebruikend de ![](assets/edit_darkgrey-24px.png) knoop van de snelle acties die verschijnen.
1. Gebruik de vervolgkeuzelijst in het **[!UICONTROL Action]** veld om een van de volgende handelingen te selecteren:

   ![](assets/wkf_file_transfer_01.png)

   * **Bestanden downloaden**: kunt u een bestand downloaden.
   * **Bestanden uploaden**: kunt u een bestand uploaden. Als u een bestand uploadt vanuit een Adobe Campaign-bestand, wordt een logbestandvermelding in het **[!UICONTROL Export audits]** menu gegenereerd. Raadpleeg voor meer informatie over exportaudits de sectie [Audit export](../../administration/using/auditing-export-logs.md) .
   * **Testen om te controleren of het bestand bestaat**: kunt u controleren of er een bestand is.
   * **Bestandenlijst**: Hiermee kunt u de bestanden weergeven die aanwezig zijn op de server die is gedefinieerd op het **[!UICONTROL Protocol]** tabblad. Deze actie wordt hoofdzakelijk gebruikt voor het zuiveren doeleinden, om te controleren of wordt de activiteit gevormd volgens uw behoeften alvorens de dossiers van de verre server te downloaden.

1. Selecteer het protocol dat u wilt gebruiken:
   * [HTTP](#HTTP-configuration-wf)
   * [SFTP](#SFTP-configuration-wf)
   * [Amazon S3](#S3-configuration-wf)
   * [Microsoft Azure Blob-opslag](#azure-blob-configuration-wf)
   * [Bestand(en) aanwezig op de Adobe Campaign-server](#files-server-configuration-wf)

1. In de **[!UICONTROL Additional options]** sectie, die afhankelijk is van het geselecteerde protocol, kunt u parameters toevoegen aan uw protocol. U kunt:

   * **[!UICONTROL Delete the source files after transfer]**
   * **[!UICONTROL Disable passive mode]**
   * **[!UICONTROL List all files]**: deze optie is beschikbaar wanneer u **[!UICONTROL File listing]** action.in het **[!UICONTROL General]** tabblad selecteert. Hiermee kunt u alle bestanden indexeren die aanwezig zijn op de server in de gebeurtenisvariabele **vars.filenames** waarin de bestandsnamen worden gescheiden door de tekens **&#39;n&#39;** .

1. In het **[!UICONTROL If no files are found]** gedeelte van het **[!UICONTROL Advanced options]** tabblad kunt u specifieke handelingen configureren als er fouten of onbestaande bestanden worden gedetecteerd wanneer de activiteit wordt gestart.

   U kunt ook nieuwe pogingen definiëren. De verschillende pogingen worden weergegeven in het logboek voor workflowuitvoering.

   ![](assets/wkf_file_transfer_09.png)

1. Bevestig de configuratie van uw activiteit en sla uw werkschema op.

### Configuratie met HTTP {#HTTP-configuration-wf}

Met het HTTP-protocol kunt u een bestand downloaden van een externe account of van een URL.

Met dit profiel kunt u **[!UICONTROL Use connection parameters defined in an external account]** optie kiezen. Selecteer in dit geval de account die u wilt downloaden en geef het pad op van het bestand dat u wilt downloaden.
![](assets/wkf_file_transfer_03.png)

U kunt ook de **[!UICONTROL Quick configuration]** optie kiezen. U hoeft de URL alleen in te voeren in het veld URL.
![](assets/wkf_file_transfer_04.png)

### Configuratie met SFTP {#SFTP-configuration-wf}

Met het SFTP-protocol kunt u beginnen met het downloaden van een bestand vanaf een URL of een externe account.

Met dit profiel kunt u **[!UICONTROL Use connection parameters defined in an external account]** optie kiezen, vervolgens het account selecteren dat u wilt en het pad opgeven van het bestand dat u wilt downloaden.
![](assets/wkf_file_transfer_07.png)

>[!CAUTION]
>
>Jokertekens worden ondersteund.

U kunt ook de **[!UICONTROL Quick configuration]** optie kiezen. U hoeft de URL alleen in te voeren in het veld URL.

### Configuratie met Amazon S3 {#S3-configuration-wf}

Met het Amazon S3-protocol kunt u een bestand vanaf een URL of een externe account downloaden via Amazon Simple Storage Service (S3).

1. Selecteer een externe Amazon S3-account. Raadpleeg deze [pagina](../../administration/using/external-accounts.md#amazon-s3-external-account)voor meer informatie.

2. Kies of u wilt **[!UICONTROL Define a file path]** of **[!UICONTROL Use a dynamic file path]**.

3. Geef het pad op van het bestand dat u wilt downloaden.

   ![](assets/wkf_file_transfer_08.png)

4. Als u de bronbestanden wilt verwijderen wanneer de overdracht is voltooid, selecteert u **[!UICONTROL Delete the source files after transfer]**.

### Configuratie met Microsoft Azure Blob-opslag {#azure-blob-configuration-wf}

Met het Microsoft Azure Blob-protocol hebt u toegang tot blob op een Microsoft Azure Blob Storage-account.

1. Selecteer een **[!UICONTROL Microsoft Azure Blob]** externe account. Raadpleeg deze [pagina](../../administration/using/external-accounts.md#microsoft-azure-external-account)voor meer informatie.

1. Kies of u wilt **[!UICONTROL Define a file path]** of **[!UICONTROL Use a dynamic file path]**.

   ![](assets/wkf_file_transfer_10.png)

1. Geef het pad op van het bestand dat u wilt downloaden. Dit pad kan overeenkomen met meerdere blokken. In dat geval activeert de **[!UICONTROL File transfer]** activiteit de uitgaande overgang eenmaal per aangetroffen blok. Vervolgens worden ze in alfabetische volgorde verwerkt.

   >[!CAUTION]
   >
   >Jokertekens worden niet ondersteund om overeen te komen met meerdere bestandsnamen. In plaats daarvan moet u een voorvoegsel invoeren. Alle blob-namen die overeenkomen met dat voorvoegsel komen in aanmerking.

   U vindt onder een lijst met voorbeelden van bestandspaden:

   * **&quot;campagne/&quot;**: komt overeen met alle balken in de map Campagne in de hoofdmap van de container.
   * **&quot;campagne/nieuw-&quot;**: komt overeen met alle basen met een bestandsnaam die begint met &quot;new-&quot; en zich bevindt in de map Campagne.
   * **&quot;&quot;**: door een leeg pad toe te voegen, kunt u alle balken afstemmen die in de container beschikbaar zijn.

### Configuratie met bestanden aanwezig op de Adobe Campaign-server {#files-server-configuration-wf}

Het **[!UICONTROL File(s) present on the Adobe Campaign server]** protocol komt overeen met de opslagplaats die de te herstellen bestanden bevat.
Metatekens of jokertekens (bijvoorbeeld * of ?) kan worden gebruikt om bestanden te filteren.

Kies of u wilt **[!UICONTROL Define a file path]** of **[!UICONTROL Use a dynamic file path]** de **[!UICONTROL Use a dynamic file path]** optie, laat u een standaarduitdrukking en gebeurtenisvariabelen gebruiken om de naam van het over te brengen dossier te personaliseren. Raadpleeg voor meer informatie de sectie [Activiteiten aanpassen met gebeurtenisvariabelen](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables) .

Het pad moet relatief zijn ten opzichte van de opslagruimtedirectory van de Adobe Campaign-server. De bestanden bevinden zich in de map **sftp&lt;yourinstancename>/** . U kunt ook niet door de mappen boven de opslagruimte bladeren. Bijvoorbeeld:

    >**user&amp;lt;yourinstancename>/my_recipients.csv** is correct.
    >
    >**../hello/my_recipients.csv** is onjuist.
    >
    >**//myserver/hello/myrecipients.csv** is onjuist.

## Historialisatie-instellingen {#historization-settings}

Telkens wanneer een **[!UICONTROL Transfer file]** activiteit wordt uitgevoerd, slaat het de geupload of gedownloade dossiers in een specifieke omslag op. Er wordt één map gemaakt voor elke **[!UICONTROL Transfer file]** activiteit van een workflow. Daarom is het belangrijk om de grootte van deze omslag te kunnen beperken om fysieke ruimte op de server te bewaren.

Hiervoor kunt u **[!UICONTROL Historization settings]** in het gedeelte **[!UICONTROL Advanced options]** van de **[!UICONTROL Transfer File]** activiteit definiëren.

**[!UICONTROL Historization settings]** toestaan om een maximumaantal bestanden of totale grootte voor de map van de activiteit te definiëren. Standaard zijn 100 bestanden en 50 MB geautoriseerd.

Telkens wanneer de activiteit wordt uitgevoerd, wordt de omslag gecontroleerd als volgt:

* Alleen bestanden die meer dan 24 uur vóór de uitvoering van de activiteit zijn gemaakt, worden in aanmerking genomen.
* Als het aantal bestanden waarmee rekening wordt gehouden groter is dan de waarde van de **[!UICONTROL Maximum number of files]** parameter, worden de oudste bestanden verwijderd totdat het **[!UICONTROL Maximum number of files]** toegestane aantal is bereikt.
* Als de totale grootte van de bestanden waarmee rekening wordt gehouden groter is dan de waarde van de **[!UICONTROL Maximum size (in MB)]** parameter, worden de oudste bestanden verwijderd totdat de **[!UICONTROL Maximum size (in MB)]** toegestane waarde is bereikt.

>[!NOTE]
>
>Als de activiteit niet opnieuw wordt uitgevoerd, zal zijn omslag niet worden gecontroleerd noch worden leeggemaakt. Wees daarom voorzichtig bij het overdragen van grote bestanden.
