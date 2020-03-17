---
title: Bestand laden
description: Met de activiteit Bestand laden kunt u gegevens in één gestructureerd formulier importeren en deze gegevens gebruiken in Adobe Campagne.
page-status-flag: never-activated
uuid: 69af12cc-6f82-4977-9f53-aa7bc26f5d7e
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: 584ff893-9b1b-46c9-9628-714ab349ab88
context-tags: fileImport,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 867215b295a7539d8499fa0bb1865605695da020

---


# Bestand laden {#load-file}

## Beschrijving {#description}

![](assets/data_loading.png)

Met deze **[!UICONTROL Load file]** activiteit kunt u gegevens in één gestructureerd formulier importeren en deze gegevens gebruiken in Adobe Campaign. De gegevens worden tijdelijk geïmporteerd en een andere activiteit is nodig om deze definitief te integreren in de Adobe Campaign-database.

## Gebruikscontext {#context-of-use}

De manier waarop de gegevens worden geëxtraheerd, wordt gedefinieerd wanneer de activiteit wordt geconfigureerd. Het te laden bestand kan bijvoorbeeld een lijst met contactpersonen zijn.

>[!CAUTION]
>
>Alleen de &#39;platte&#39; structuurbestanden worden in aanmerking genomen, bijvoorbeeld de bestanden .txt, .csv, enz.

U kunt:

* Gebruik de bestandsstructuur om deze toe te passen op de gegevens van een ander bestand (hersteld met behulp van de **[!UICONTROL Transfer file]** activiteit) of
* Gebruik de structuur en de gegevens uit het bestand om het bestand te importeren in Adobe Campaign.

## Configuratie {#configuration}

De activiteitenconfiguratie omvat twee stappen. Eerst moet u de verwachte bestandsstructuur definiëren door een voorbeeldbestand te uploaden. Als dit is gebeurd, kunt u de oorsprong opgeven van het bestand waarvan de gegevens worden geïmporteerd.

>[!NOTE]
>
>De gegevens van het voorbeeldbestand worden gebruikt voor het configureren van de activiteit, maar worden niet geïmporteerd. We raden u aan een voorbeeldbestand te gebruiken dat weinig gegevens bevat.

1. Sleep een **[!UICONTROL Load file]** activiteit naar uw werkstroom.
1. Selecteer de activiteit, dan open het gebruikend de ![](assets/edit_darkgrey-24px.png) knoop van de snelle acties die verschijnen.
1. Upload het voorbeeldbestand waarmee u de verwachte structuur kunt definiëren wanneer u het uiteindelijke bestand importeert.

   ![](assets/wkf_file_loading.png)

   Nadat het gegevensbestand is geüpload, worden twee nieuwe tabbladen weergegeven in de activiteit: **[!UICONTROL File structure]** en **[!UICONTROL Column definition]**.

1. Ga naar het **[!UICONTROL File structure]** lusje om de structuur te bekijken die automatisch van het steekproefdossier wordt ontdekt.

   Als de bestandsstructuur onjuist is gedetecteerd, hebt u verschillende opties om mogelijke fouten te corrigeren:

   * U kunt kiezen om de structuur van een ander bestand te gebruiken door de **[!UICONTROL Detect structure from a new file]** optie te selecteren.
   * U kunt de standaarddetectieparameters wijzigen om deze aan te passen aan het bestand. In het **[!UICONTROL File type]** veld kunt u opgeven of het bestand dat u wilt importeren, bestaat uit kolommen met een vaste lengte. In dat geval moet u ook het maximumaantal tekens voor elke kolom op het **[!UICONTROL Column definition]** tabblad opgeven.

      Alle detectieopties die nodig zijn om de gegevens uit het bestand correct te herstellen, worden opnieuw gegroepeerd in **[!UICONTROL File format]**. U kunt ze wijzigen en vervolgens de structuur van het laatste bestand dat in de activiteit is geladen, opnieuw detecteren door met deze nieuwe instellingen rekening te houden. Gebruik de **[!UICONTROL Apply configuration]** knop om dit te doen. U kunt bijvoorbeeld een ander kolomscheidingsteken opgeven.

      >[!NOTE]
      >
      >Deze bewerking houdt rekening met het laatste bestand dat in de activiteit is geladen. Als het gedetecteerde bestand groot is, worden in de gegevensvoorvertoning alleen de eerste 30 regels weergegeven.

      ![](assets/wkf_file_loading3.png)

      In de **[!UICONTROL File format]** sectie kunt u met de **[!UICONTROL Check columns from file against column definitions]** optie controleren of de kolommen van het bestand dat u uploadt, overeenkomen met de kolomdefinitie.

      Als het aantal kolommen en/of de naam van kolommen niet overeenkomen met de kolomdefinitie, wordt een foutbericht weergegeven wanneer de workflow wordt uitgevoerd. Als de optie niet is geactiveerd, worden waarschuwingen in het logbestand weergegeven.

      ![](assets/wkf_file_loading_check.png)

1. Ga naar het **[!UICONTROL Column definition]** tabblad om de gegevensindeling voor elke kolom te controleren en pas indien nodig de parameters aan.

   Op het **[!UICONTROL Column definition]** tabblad kunt u nauwkeurig de gegevensstructuur van elke kolom opgeven om gegevens te importeren die geen fouten bevatten (bijvoorbeeld met null-beheer) en deze in overeenstemming te brengen met de typen die al aanwezig zijn in de Adobe Campagne-database voor toekomstige bewerkingen.

   U kunt bijvoorbeeld het label van een kolom wijzigen, het type kolom selecteren (tekenreeks, geheel getal, datum, enzovoort) of zelfs foutverwerking opgeven.

   Raadpleeg de sectie [Kolomindeling](#column-format) voor meer informatie.

   ![](assets/wkf_file_loading4.png)

1. Geef op het **[!UICONTROL Execution]** tabblad op of het bestand moet worden verwerkt voor het laden van gegevens:

   * Komt uit een binnenkomende overgang in het werkschema.
   * Is die u tijdens de vorige stap uploadde.
   * Is een nieuw bestand dat vanaf de lokale computer moet worden geüpload. De **[!UICONTROL Upload a new file from local machine]** optie wordt weergegeven als het uploaden van een eerste bestand al is gedefinieerd in de workflow. Hierdoor kunt u een ander bestand uploaden dat u wilt verwerken als het huidige bestand niet aan uw wensen voldoet.

      ![](assets/wkf_file_loading1.png)

1. Als het bestand waarvan u de gegevens wilt laden, is gecomprimeerd tot een GZIP-bestand (.gz), selecteert u de **[!UICONTROL Decompression]** optie in het **[!UICONTROL Add a pre-processing step]** veld. Hierdoor kunt u het bestand uitpakken voordat u de gegevens laadt. Deze optie is alleen beschikbaar als het bestand afkomstig is van de inkomende overgang van de activiteit.
1. Met de **[!UICONTROL Keep the rejects in a file]** optie kunt u een bestand downloaden dat fouten bevat die tijdens het importeren zijn opgetreden en het vervolgens toepassen in een nabewerkingsfase. Wanneer de optie wordt geactiveerd, wordt de naam van de uitgaande overgang gewijzigd in &quot;Afwijzen&quot;.

   >[!NOTE]
   >
   >Met de **[!UICONTROL Add date and time to the file name]** optie kunt u een tijdstempel toevoegen met de naam van het bestand dat de afwijzing bevat.

   ![](assets/wkf_file_loading_keeprejects.png)

1. Bevestig de configuratie van uw activiteit en sla uw werkschema op.

Als er na het uitvoeren van de workflow een fout optreedt met de activiteit, raadpleegt u de logboeken voor meer informatie over de waarden die niet correct zijn in het bestand. For more on workflows logs, refer to [this section](../../automating/using/executing-a-workflow.md#monitoring)

## Kolomnotatie {#column-format}

Wanneer u een voorbeeldbestand laadt, wordt de kolomindeling automatisch gedetecteerd met de standaardparameters voor elk gegevenstype. U kunt deze standaardparameters wijzigen om de specifieke processen te specificeren die op uw gegevens moeten worden toegepast, in het bijzonder wanneer er een fout of een lege waarde is.

U doet dit door een keuze te maken **[!UICONTROL Edit properties]** uit de snelle handelingen van de kolom waarvan u de indeling wilt definiëren. Het detailvenster voor kolomnotaties wordt geopend.

![](assets/wkf_file_loading4.png)

Vervolgens kunt u de opmaak voor elke kolom wijzigen.

Met de kolomopmaak kunt u de waardeverwerking van elke kolom definiëren:

* **[!UICONTROL Ignore column]**: Deze kolom wordt niet verwerkt tijdens het laden van gegevens.
* **[!UICONTROL Data type]**: geeft het type gegevens aan dat voor elke kolom wordt verwacht.
* **[!UICONTROL Format and separators]**, **Eigenschappen**: Geef de eigenschappen van een tekst, de notatie voor tijd, datum en numerieke waarde op, evenals het scheidingsteken dat is opgegeven in de kolomcontext.

   * **[!UICONTROL Maximum number of characters]**: geeft het maximumaantal tekens voor tekenreekstype-kolommen aan.

      Dit veld moet worden ingevuld bij het laden van bestanden die bestaan uit kolommen met een vaste lengte.

   * **[!UICONTROL Letter case management]**: Hiermee bepaalt u of een proces voor hoofdletters/kleine letters moet worden toegepast op **tekstgegevens** .
   * **[!UICONTROL White space management]**: Geeft aan of bepaalde spaties moeten worden genegeerd in een tekenreeks voor **tekstgegevens** .
   * **[!UICONTROL Time format]**, **[!UICONTROL Date format]**: geeft de indeling op voor **datum**-, **tijd** - en **datum- en tijdgegevens** .
   * **[!UICONTROL Format]**: Hiermee kunt u de notatie definiëren voor numerieke waarden voor **Geheel** en **Zwevend getal** .
   * **[!UICONTROL Separator]**: definieert het scheidingsteken dat wordt opgegeven door de kolomcontext (scheidingsteken voor duizendtallen of decimale scheidingstekens voor numerieke waarden, scheidingsteken voor datums en tijd) voor **datum**, **tijd**, **datum en tijd**, **geheel getal** en gegevens voor **zwevend getal** .

* **[!UICONTROL Remapping of values]**: dit veld is alleen beschikbaar in de configuratie van kolomdetails. Hiermee kunt u bepaalde waarden transformeren wanneer deze worden geïmporteerd. U kunt bijvoorbeeld &quot;three&quot; omzetten in &quot;3&quot;.
* **[!UICONTROL Error processing]**: definieert het gedrag als een fout optreedt.

   * **[!UICONTROL Ignore the value]**: de waarde wordt genegeerd. Er wordt een waarschuwing gegenereerd in het logboek voor workflowuitvoering.
   * **[!UICONTROL Reject the line]**: de gehele lijn wordt niet verwerkt.
   * **[!UICONTROL Use a default value]**: vervangt de waarde die de fout veroorzaakt door een standaardwaarde, die op het **[!UICONTROL Default value]** gebied wordt bepaald.
   * **[!UICONTROL Use a default value in case the value is not remapped]**: vervangt de waarde die de fout veroorzaakt door een standaardwaarde, die in het **[!UICONTROL Default value]** **[!UICONTROL Remapping of values]** gebied wordt bepaald, tenzij een afbeelding voor de onjuiste waarde werd bepaald (zie de bovenstaande optie).
   * **[!UICONTROL Reject the line when there is no remapping value]**: de gehele regel wordt alleen verwerkt als een toewijzing voor de onjuiste waarde is gedefinieerd (zie de bovenstaande **[!UICONTROL Remapping of values]** optie).
   >[!NOTE]
   >
   >**[!UICONTROL Error processing]** betreft fouten met betrekking tot waarden in het geïmporteerde bestand. Een onjuist gegevenstype is bijvoorbeeld aangetroffen (&quot;vier&quot; in letters voor een kolom &quot;Geheel getal&quot;), een tekenreeks die meer tekens bevat dan het toegestane maximum, een datum met onjuiste scheidingstekens, enz. Deze optie heeft echter geen betrekking op fouten die worden gegenereerd door leeg waardebeheer.

* **[!UICONTROL Default value]**: geeft de standaardwaarde op basis van de gekozen foutafhandeling.
* **[!UICONTROL Empty value management]**: geeft aan hoe lege waarden moeten worden beheerd tijdens het laden van gegevens.

   * **[!UICONTROL Generate an error for numerical fields]**: genereert alleen een fout voor numerieke velden. Als dit niet het geval is, wordt een NULL-waarde ingevoegd.
   * **[!UICONTROL Insert NULL in the corresponding field]**: autoriseert lege waarden. De waarde NULL wordt daarom ingevoegd.
   * **[!UICONTROL Generate an error]**: genereert een fout als een waarde leeg is.

## Voorbeeld 1: De database bijwerken {#example-1-update-the-database}

De activiteit van het ladingsdossier structureert hoofdzakelijk de gegevens van een activiteit van het overdrachtsdossier om het in de bestaande gegevens te integreren.

In het volgende voorbeeld wordt het resultaat getoond van een activiteit van een automatisch gedownload laadbestand via een activiteit van het overdrachtsbestand, gevolgd door een activiteit van updategegevens. Deze workflow is bedoeld om de Adobe Campagne-database te verrijken met nieuwe profielen of om bestaande profielen bij te werken aan de hand van de gegevens uit het geïmporteerde bestand.

![](assets/load_file_workflow_ex1.png)

1. Sleep een **[!UICONTROL Transfer file]** activiteit in uw werkschema en vorm het op een manier zodat het het gewenste dossier terugkrijgt.
1. Sleep een **[!UICONTROL Load file]** activiteit naar uw werkstroom en plaats deze na de **[!UICONTROL Transfer file]** activiteit.
1. Selecteer de activiteit, dan open het gebruikend de ![](assets/edit_darkgrey-24px.png) knoop van de snelle acties die verschijnen.
1. Schakel de **[!UICONTROL File to load]** optie in de **[!UICONTROL Execution]** sectie van het **[!UICONTROL Use the file specified in the inbound transition]** tabblad in.

   ![](assets/wkf_file_loading8.png)

1. Configureer uw activiteit zoals eerder opgegeven.
1. Sleep en zet een **[!UICONTROL Update data]** activiteit neer in uw werkschema en plaats het na de **[!UICONTROL Load file]** activiteit, dan vorm het. Zie Gegevens [](../../automating/using/update-data.md)bijwerken.

Nadat de workflow is gestart, worden de gegevens uit het geüploade bestand geëxtraheerd en vervolgens gebruikt om de Adobe Campagne-database te verrijken.

## Voorbeeld 2: Een e-mail verzenden met verrijkte velden {#example-2-email-with-enriched-fields}

<!--A new example showing how to send an email containing additional data retrieved from a load file activity has been added. [Read more](example-2-email-with-enriched-fields)-->

Met de activiteit van het ladingsdossier kunt u ook een e-mail verzenden die met extra gegevens van een extern dossier in het zelfde werkschema wordt verrijkt.

In het onderstaande voorbeeld ziet u hoe u een e-mail verzendt met behulp van aanvullende gegevens die via het laden van het bestand zijn opgehaald uit een extern bestand. In dit voorbeeld bevat het externe bestand een lijst met profielen met het bijbehorende accountnummer. U wilt deze gegevens importeren om een e-mail naar elk profiel met het bijbehorende accountnummer te verzenden.

![](assets/load_file_workflow_ex2.png)

1. Sleep een **[!UICONTROL Query]** activiteit naar uw werkstroom en open deze om het hoofddoel te definiëren.

   <!--The Query activity is presented in the [Query](../../automating/using/query.md) section.-->

1. Sleep een **[!UICONTROL Load file]** activiteit om gegevens toe te wijzen aan een profiel. In dit voorbeeld laadt u een bestand met accountnummers die overeenkomen met bepaalde profielen van de database.

   ![](assets/load_file_activity.png)

1. Sleep een **[!UICONTROL Enrichment]** activiteit naar uw werkstroom en koppel het ladingsdossier en vraagactiviteiten aan het.

1. Selecteer op het **[!UICONTROL Advanced relations]** tabblad van de verrijkingsactiviteit de velden **[!UICONTROL 0 or 1 cardinality simple link]** en definieer de velden die moeten worden gebruikt voor afstemming. Hier gebruiken we de achternaam om de gegevens te combineren met de databaseprofielen.

   ![](assets/load_file_enrichment_relation.png)

1. Selecteer op het **[!UICONTROL Additional data]** tabblad de elementen die u in de e-mail wilt gebruiken. Hier selecteert u Account-nummer (kolom uit het bestand dat u hebt opgehaald via de activiteit van het laadbestand).

   ![](assets/load_file_enrichment_select_element.png)

   <!--![](assets/load_file_enrichment_additional_data.png)-->

   Zie de sectie [Verrijking](../../automating/using/enrichment.md) voor meer informatie.

1. Sleep een **[!UICONTROL Segmentation]** activiteit naar uw werkstroom en open deze om het hoofddoel te verfijnen.

   ![](assets/load_file_segmentation.png)

   Zie de sectie [Segmentatie](../../automating/using/segmentation.md) voor meer informatie.

1. Sleep een **[!UICONTROL Email delivery]** activiteit naar uw werkstroom en open deze.

   <!--The Email delivery activity is presented in the [Email delivery](../../automating/using/email-delivery.md) section.-->

1. Voeg een verpersoonlijkingsgebied toe en selecteer de extra gegevens die in de verrijkingsactiviteit (hier het aantal van de Rekening) van de **[!UICONTROL Additional data (targetData)]** knoop worden bepaald. Hiermee kunt u dynamisch het accountnummer van elk profiel in de e-mailinhoud ophalen.

   ![](assets/load_file_perso_field.png)

1. Sla de e-mail op en start de workflow.

Het e-mailbericht wordt naar het doel verzonden. Elk profiel ontvangt het e-mailbericht met het corresponderende accountnummer.

![](assets/load_file_email.png)
