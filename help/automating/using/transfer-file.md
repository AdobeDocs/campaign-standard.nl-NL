---
title: Bestand overbrengen
description: Met de bestandsactiviteit voor overbrengen kunt u bestanden ontvangen of verzenden, testen of er bestanden aanwezig zijn of kunt u een lijst met bestanden weergeven in Adobe Campagne.
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
source-git-commit: ff3b41589f47e7697a69bb68824aefd4d9036793

---


# Bestand overbrengen{#transfer-file}

## Beschrijving {#description}

![](assets/file_transfer.png)

Met deze **[!UICONTROL Transfer file]** activiteit kunt u bestanden ontvangen of verzenden, testen of er bestanden aanwezig zijn of bestanden weergeven in Adobe Campagne.

## Gebruikscontext {#context-of-use}

De manier waarop de gegevens worden geëxtraheerd, wordt gedefinieerd wanneer de activiteit wordt geconfigureerd. Het te laden bestand kan bijvoorbeeld een lijst met contactpersonen zijn.

U kunt deze activiteit gebruiken om gegevens terug te krijgen die dan met de **[!UICONTROL Load file]** activiteit zullen worden gestructureerd.

## Configuratie {#configuration}

1. Zet een **[!UICONTROL Transfer file]** activiteit neer in uw werkschema.
1. Selecteer de activiteit, dan open het gebruikend de ![](assets/edit_darkgrey-24px.png) knoop van de snelle acties die verschijnen.
1. Gebruik de vervolgkeuzelijst in het **[!UICONTROL Action]** veld om een van de volgende handelingen te selecteren:

   ![](assets/wkf_file_transfer_01.png)

   * **Bestanden downloaden**: kunt u een bestand downloaden.
   * **Bestanden uploaden**: kunt u een bestand uploaden. Wanneer u een bestand uploadt uit het Adobe Campaign-bestand, wordt een logbestandvermelding in het **[!UICONTROL Export audits]** menu gegenereerd. Raadpleeg voor meer informatie over exportaudits de sectie [Audit export](../../administration/using/auditing-export-logs.md) .
   * **Testen om te controleren of het bestand bestaat**: kunt u controleren of er een bestand is.
   * **Bestandenlijst**: kunt u een lijst maken van de bestanden die aanwezig zijn in Adobe Campaign.
   Afhankelijk van de geselecteerde actie, zijn één of verscheidene protocollen beschikbaar:

   * **HTTP**: Met dit protocol kunt u beginnen met het downloaden van een bestand van een externe account of van een URL.

      * Klik op de **[!UICONTROL Use connection parameters defined in an external account]** optie, selecteer het account dat u wilt en geef het pad op van het bestand dat u wilt downloaden.

         ![](assets/wkf_file_transfer_03.png)

      * Klik op de **[!UICONTROL Quick configuration]** optie en voer de URL in het veld in dat wordt weergegeven.

         ![](assets/wkf_file_transfer_04.png)
   * **S3**: Met dit protocol kunt u een bestand vanaf een URL of een externe account downloaden via Amazon Simple Storage Service (S3).

      * Selecteer de externe account en geef het pad op van het bestand dat u wilt downloaden.

         ![](assets/wkf_file_transfer_08.png)
   * **SFTP**: Met dit protocol kunt u beginnen met het downloaden van een bestand vanaf een URL of een externe account.

      * Klik op de **[!UICONTROL Use connection parameters defined in an external account]** optie, selecteer het account dat u wilt en geef het pad op van het bestand dat u wilt downloaden.

         ![](assets/wkf_file_transfer_07.png)

         >[!CAUTION]
         >
         >Jokertekens worden ondersteund.

      * Klik op de **[!UICONTROL Quick configuration]** optie en voer de URL in het veld in dat wordt weergegeven.
      * Als u de geïmporteerde bestanden wilt sorteren, selecteert u de **[!UICONTROL Sort alphanumerically]** optie in de **[!UICONTROL Additional options]** sectie. De bestanden worden vervolgens in volgorde verwerkt.

         ![](assets/wkf_file_transfer_sort.png)
   * **Bestand(en) aanwezig op de Adobe Campagneserver**: dit protocol komt overeen met de opslagplaats die de te herstellen bestanden bevat.

      Metatekens of jokertekens (bijvoorbeeld * of ?) kan worden gebruikt om bestanden te filteren.

      Vul dit veld in en bevestig uw activiteit om dit protocol te gebruiken.

      >[!NOTE]
      >
      >Het pad moet relatief zijn ten opzichte van de opslagruimtedirectory van de Adobe Campaign-server. De bestanden bevinden zich in de map **sftp&lt;yourinstancename>/** . U kunt ook niet door de mappen boven de opslagruimte bladeren. Bijvoorbeeld:

      >**user&lt;yourinstancename>/my_recipients.csv** is correct.
      **../hello/my_recipients.csv** is onjuist.
      **/myserver/hello/myrecipients.csv** is onjuist.
   Selecteer het protocol en vul de bijbehorende velden in.

   De **[!UICONTROL Use a dynamic file path]** optie, beschikbaar voor elk protocol, laat u een standaarduitdrukking en gebeurtenisvariabelen gebruiken om de naam van het over te brengen dossier te personaliseren. Raadpleeg voor meer informatie de sectie [Activiteiten aanpassen met gebeurtenisvariabelen](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables) .

1. In de **[!UICONTROL Additional options]** sectie, die afhankelijk is van het geselecteerde protocol, kunt u parameters toevoegen aan uw protocol. U kunt:

   * **[!UICONTROL Delete the source files after transfer]**
   * **[!UICONTROL Disable passive mode]**
   * **[!UICONTROL List all files]**: deze optie is beschikbaar wanneer u de **[!UICONTROL File listing]** actie selecteert. Hiermee kunt u alle bestanden indexeren die aanwezig zijn op de server in de gebeurtenisvariabele **vars.filenames** waarin de bestandsnamen worden gescheiden door de tekens **&#39;n&#39;** .

1. In het **[!UICONTROL If no files are found]** gedeelte van het **[!UICONTROL Advanced options]** tabblad kunt u specifieke handelingen configureren als er fouten of onbestaande bestanden worden gedetecteerd wanneer de activiteit wordt gestart.

   U kunt ook nieuwe pogingen definiëren. De verschillende pogingen worden weergegeven in het logboek voor workflowuitvoering.

   ![](assets/wkf_file_transfer_09.png)

1. Bevestig de configuratie van uw activiteit en sla uw werkschema op.

## Historialisatie-instellingen {#historization-settings}

Telkens wanneer een **[!UICONTROL Transfer file]** activiteit wordt uitgevoerd, slaat het de geupload of gedownloade dossiers in een specifieke omslag op. Er wordt één map gemaakt voor elke **[!UICONTROL Transfer file]** activiteit van een workflow. Daarom is het belangrijk om de grootte van deze omslag te kunnen beperken om fysieke ruimte op de server te bewaren.

Hiervoor kunt u **[!UICONTROL Historization settings]** in het gedeelte **[!UICONTROL Advanced options]** van de **[!UICONTROL Transfer File]** activiteit definiëren.

**[!UICONTROL Historization settings]** toestaan om een maximumaantal bestanden of totale grootte voor de map van de activiteit te definiëren. Standaard zijn 100 bestanden en 50 MB geautoriseerd.

Telkens wanneer de activiteit wordt uitgevoerd, wordt de omslag gecontroleerd als volgt:

* Alleen bestanden die meer dan 24 uur vóór de uitvoering van de activiteit zijn gemaakt, worden in aanmerking genomen.
* Als het aantal bestanden waarmee rekening wordt gehouden groter is dan de waarde van de **[!UICONTROL Maximum number of files]** parameter, worden de oudste bestanden verwijderd totdat het **[!UICONTROL Maximum number of files]** toegestane aantal is bereikt.
* Als de totale grootte van de bestanden waarmee rekening wordt gehouden groter is dan de waarde van de **[!UICONTROL Maximum size (in MB)]** parameter, worden de oudste bestanden verwijderd totdat de **[!UICONTROL Maximum size (in MB)]** toegestane waarde is bereikt.

>[!NOTE]
Als de activiteit niet opnieuw wordt uitgevoerd, zal zijn omslag niet worden gecontroleerd noch worden leeggemaakt. Wees daarom voorzichtig bij het overdragen van grote bestanden.

## Voorbeeld {#example}

Het volgende voorbeeld toont de configuratie van een activiteit van de **Overdracht** van het Dossier die dan door een activiteit van het Dossier **van de** Lading dan een activiteit van de Gegevens **van de** Update zal worden gevolgd. Het doel van deze workflow is om de Adobe Campagne-databaseprofielen toe te voegen of bij te werken met de gegevens die door de workflow worden hersteld.

1. Sleep een **bestandsactiviteit** overbrengen naar uw workflow.
1. Selecteer de activiteit, dan open het gebruikend de ![](assets/edit_darkgrey-24px.png) knoop van de snelle acties die verschijnen.
1. Selecteer op het **[!UICONTROL Protocol]** tabblad **SFTP**.
1. Selecteer de **verbindingsparameters gebruiken die zijn gedefinieerd in een optie voor een externe account** .
1. Voer de naam van de externe account in.
1. Voer het **bestandspad op de externe server** in.

   ![](assets/wkf_file_transfer_07.png)

1. Bevestig uw activiteit en sla uw werkschema op.

