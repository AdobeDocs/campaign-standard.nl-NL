---
title: Importsjablonen definiëren
description: Met sjablonen voor importeren kunt u de benodigde instellingen reduceren en gegevens sneller importeren.
page-status-flag: never-activated
uuid: 651eb57c-adac-4e3e-b454-b39aea1f0484
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
discoiquuid: 85d13147-fb31-446a-8476-f112c841fb82
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 68e825bc3b6b7f94f61875e7da2bc8f63f06d9cb

---


# Importsjablonen definiëren{#defining-import-templates}

Met importsjablonen kan de beheerder een bepaald aantal technische importconfiguraties vooraf definiëren. Deze sjablonen kunnen vervolgens beschikbaar worden gesteld aan standaardgebruikers voor het uitvoeren en uploaden van bestanden.

Een importsjabloon wordt gedefinieerd door de functionele beheerder en kan worden beheerd via het menu **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Import templates]** .

![](assets/import_template_list.png)

Er zijn drie standaardsjablonen met de eigenschap Alleen-lezen beschikbaar:

* **[!UICONTROL Update Direct mail quarantines and delivery logs]**: deze sjabloon kan dienen als basis voor nieuwe importbewerkingen om quarantines en leveringslogboeken voor direct mail bij te werken. De workflow van de sjabloon bevat de volgende activiteiten:
* **[!UICONTROL Import data]**: deze sjabloon kan dienen als basis voor nieuwe importbewerkingen om gegevens uit een bestand in de database in te voegen. De workflow van deze sjabloon bevat de volgende activiteiten:

   * **[!UICONTROL Load file]**: Met deze activiteit kunt u een bestand uploaden naar de Adobe Campagne-server.
   * **[!UICONTROL Update data]**: met deze activiteit kunt u gegevens uit het bestand in de database invoegen.

* **[!UICONTROL Import list]**: Deze sjabloon kan dienen als basis voor nieuwe importbewerkingen om een publiek van het type **List** te maken op basis van gegevens in een bestand. De workflow van deze sjabloon bevat de volgende activiteiten:

   * **[!UICONTROL Load file]**: Met deze activiteit kunt u een bestand uploaden naar de Adobe Campagne-server.
   * **[!UICONTROL Reconciliation]**: op deze manier kunt u een doeldimensie koppelen aan geïmporteerde gegevens. Zo kunt u een publiek van het type **List** maken. Als de doeldimensie van de geïmporteerde gegevens niet bekend is, is het publiek van het type **Bestand** . Zie [Doeldimensies en bronnen](../../automating/using/query.md#targeting-dimensions-and-resources).
   * **[!UICONTROL Save audience]**: Met deze activiteit kunt u gegevens opslaan die zijn geïmporteerd in de vorm van een publiek van het type **List** . De naam van het opgeslagen publiek komt overeen met de naam van het bestand dat door de gebruiker is geïmporteerd en er wordt een achtervoegsel toegevoegd met de datum en tijd van het importeren. Bijvoorbeeld: &#39;profiles_20150406_151448&#39;.

Deze standaardsjablonen zijn alleen-lezen en zijn niet zichtbaar voor standaardgebruikers. Voer de volgende stappen uit om een sjabloon te maken die beschikbaar is voor gebruikers:

1. Een standaardsjabloon dupliceren. De gedupliceerde sjabloon bevat drie tabbladen:

   * **[!UICONTROL Properties]**: de algemene parameters van de importsjabloon. Op dit tabblad kunt u de sjabloon inschakelen en een voorbeeldbestand uploaden.
   * **[!UICONTROL Workflow]**: importworkflow. Op dit tabblad kunt u de workflowactiviteiten definiëren. Deze activiteiten zijn niet zichtbaar tijdens vereenvoudigde invoer door gebruikers.
   * **[!UICONTROL Executed imports]**: lijst van de invoer die volgens dit model is uitgevoerd. U kunt de status, details en resultaten bekijken van elke import die met deze sjabloon is uitgevoerd. U hebt rechtstreeks vanuit deze lijst toegang tot de workflow (uitgevoerd op transparante wijze voor de gebruiker).

1. Wijzig de naam van de sjabloon op het **[!UICONTROL Properties]** tabblad en voeg een beschrijving toe. Gebruikers kunnen de beschrijving bekijken wanneer de sjabloon beschikbaar is.

   ![](assets/simplified_import_model1.png)

1. Go to the **[!UICONTROL Workflow]** tab. Van hieruit kunt u de workflow die standaard wordt aangeboden verrijken door nieuwe activiteiten toe te voegen die aan uw behoeften voldoen.

   Voor meer op hoe te om de werkschemaactiviteiten te vormen, verwijs naar het gebruiksgeval dat in deze sectie wordt beschreven: [Voorbeeld: Workflowsjabloon](../../automating/using/importing-data.md#example--import-workflow-template)importeren. Met deze gebruiksaanwijzing kunt u een workflow instellen die opnieuw kan worden gebruikt voor het importeren van profielen die afkomstig zijn van een CRM in de Adobe Campagne-database.

1. Sla de sjabloon op zodat de configuratie van de workflow correct in aanmerking wordt genomen.
1. Upload een voorbeeldbestand vanaf het **[!UICONTROL Properties]** tabblad. Het geüploade bestand kan alleen kolommen bevatten die nodig zijn voor toekomstige import of voorbeeldgegevens. Met de gegevens in het voorbeeldbestand kunt u de vereenvoudigde importbewerking testen zodra de workflow is gedefinieerd.

   ![](assets/import_template_sample.png)

   Dit voorbeeldbestand is vervolgens beschikbaar voor gebruikers die de sjabloon gebruiken om een importbewerking uit te voeren. Ze kunnen het bestand downloaden naar hun computer, bijvoorbeeld om het te vullen met gegevens die u wilt importeren. Houd hiermee rekening wanneer u een voorbeeldbestand toevoegt.

1. Sla de sjabloon op. Er wordt nu rekening gehouden met het voorbeeldbestand. U kunt het bestand op elk gewenst moment naar de computer downloaden om de inhoud te controleren of wijzigen door de **[!UICONTROL Drop a new sample file]** optie in te schakelen.

   ![](assets/simplified_import_model2.png)

1. Ga terug naar het **[!UICONTROL Workflow]** lusje en open de **[!UICONTROL Load file]** activiteit om de kolomconfiguratie van het steekproefdossier te controleren en aan te passen dat bij de vorige stap werd geupload.
1. Test het importeren door de workflow te starten. Het voorbeeldbestand dat in stap **5** is geüpload, moet gegevens bevatten.

   De gegevens uit het voorbeeldbestand worden vervolgens echt geïmporteerd. Zorg ervoor dat de gebruikte gegevens klein en fictief zijn om ervoor te zorgen dat de database niet in het gedrang komt.

1. Ga naar het werkschemauitvoeringslogboek, beschikbaar in de actiebar. Als u een fout ontmoet, controleer dat de activiteiten correct worden gevormd.

   ![](assets/simplified_import_model3.png)

1. Stel op het **[!UICONTROL Properties]** tabblad de sjabloon in **[!UICONTROL Import template status]** op **[!UICONTROL Available]** en sla de sjabloon op. Als u het gebruik van deze sjabloon wilt stoppen, kunt u de sjabloon instellen **[!UICONTROL Import template status]** op **[!UICONTROL Archived]**.

De sjabloonworkflow kan worden gewijzigd door het voorbeeldbestand opnieuw te uploaden en de **[!UICONTROL Load file]** configuratie te controleren.

De importsjabloon is nu beschikbaar voor de gebruikers en kan worden gebruikt om bestanden te uploaden.

**Verwante onderwerpen:**

* [Workflows](../../automating/using/get-started-workflows.md)
* [Gegevens importeren](../../automating/using/importing-data.md)
* [Voorbeeld: Workflow-sjabloon importeren](../../automating/using/importing-data.md#example--import-workflow-template)

