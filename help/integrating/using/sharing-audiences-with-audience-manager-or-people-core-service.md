---
title: Het delen van publiek met de Audience Manager of de kerndienst van Mensen
description: Leer hoe u uw publiek importeert of exporteert binnen de verschillende Adobe Experience Cloud-oplossingen.
page-status-flag: never-activated
uuid: a3701e72-5846-4241-afee-d713b499a27a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
discoiquuid: 77af0772-52b5-46bc-a964-675b45965524
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f7adb7a4725129727010c2486ca34bbc2021c539
workflow-type: tm+mt
source-wordcount: '807'
ht-degree: 0%

---


# Het delen van publiek met de Audience Manager of de kerndienst van Mensen{#sharing-audiences-with-audience-manager-or-people-core-service}

## Een publiek importeren {#importing-an-audience}

Dankzij de integratie met de basisservice van mensen kan een publiek rechtstreeks in Adobe Campaign worden geïmporteerd via een technische workflow om uw database te verrijken. Raadpleeg deze [documentatie](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segmentation-workflow/seg-publish.html)voor meer informatie over het delen van het publiek in de hoofdservice Personen.

Het importeren van soorten publiek/segmenten van de People core-service in Adobe Campaign kan alleen via het **[!UICONTROL Audiences]** menu worden uitgevoerd door gebruikers die via IMS zijn verbonden (verificatie via Adobe ID).

1. Ga naar het **[!UICONTROL Audiences]** menu.
1. Selecteer in de actiebalk **[!UICONTROL Create]** de optie die u naar het scherm wilt gaan om een publiek te maken.
1. Geef het label van het nieuwe publiek op.
1. Stel het publiek in **[!UICONTROL Type]** op **[!UICONTROL Experience Cloud]** om aan te geven dat het publiek dat wordt gemaakt een publiek is dat is geïmporteerd uit de kernservice Personen.
1. Selecteer in het **[!UICONTROL Name of the shared audience]** veld het publiek dat u wilt importeren. Alleen segmenten kunnen worden geïmporteerd. De korrelige gegevens met inbegrip van zeer belangrijk-waardeparen, eigenschappen en regels worden niet gesteund.

   ![](assets/aam_import_audience.png)

1. Selecteer de corresponderende **[!UICONTROL Shared Data Source]**.

   Als de geselecteerde gegevensbron wordt gevormd om een encryptiealgoritme te gebruiken, biedt een extra optie u de mogelijkheid aan **[!UICONTROL Force reconciliation with a profile]**. Schakel deze optie in als het **[!UICONTROL Channel]** veld van de gegevensbron is ingesteld op E-mail of Mobiel (SMS) en als u profielgegevens wilt gebruiken.

   Als u de optie niet selecteert **[!UICONTROL Force reconciliation with a profile]** en als **[!UICONTROL Channel]** deze in de AMC-gegevensbron is ingesteld op E-mail of Mobiel (SMS), worden alle gecodeerde gedeclareerde id&#39;s gedecodeerd. Een publiek van het type **Bestand** met een lijst van alle e-mailadressen/mobiele telefoonnummers wordt gemaakt/bijgewerkt. Op deze manier gaat er geen e-mailadres of mobiele telefoonnummer verloren tijdens het importeren van een gedeeld publiek via deze integratie, zelfs als dat profiel niet bestaat in Campagne. Dit soort publiek kan niet rechtstreeks worden gebruikt, omdat het handmatig moet worden afgestemd met behulp van workflows.

1. Bevestig om het publiek te maken.

   Het publiek wordt vervolgens geïmporteerd via een technische workflow. Het bestaat uit records waarvan de id (&#39;Bezoeker-id&#39; of &#39;Opgegeven ID&#39;) kon worden afgestemd op de profieldimensie. IDs van de de kernde dienstsegmenten van Mensen die niet door Adobe Campaign worden erkend worden niet ingevoerd.

Uw publiek wordt nu geïmporteerd in uw Adobe Campaign-database. Het importproces duurt 24-36 uur om te synchroniseren, wanneer de segmenten direct uit de de kerndienst of Audience Manager van Mensen worden ingevoerd. Na deze periode kun je het nieuwe publiek in Adobe Campaign vinden en gebruiken.

>[!NOTE]
>
>Als u soorten publiek importeert van Adobe Analytics naar Adobe Campaign, moeten deze soorten publiek eerst worden gedeeld in People Core Service of Audience Manager. Dit proces duurt 12-24 uur en moet worden toegevoegd aan de synchronisatie van 24-36 uur met Campagne. In dat specifieke geval kan de tijd voor het delen van het publiek maximaal 60 uur bedragen. Raadpleeg deze [documentatie](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segmentation-workflow/seg-publish.html)voor meer informatie over het delen van het publiek in de People Core-service en Audience Manager van Adobe Analytics.

## Een publiek exporteren {#exporting-an-audience}

Een publiek kan van Adobe Campaign naar Audience Manager of de kerndienst van Mensen worden uitgevoerd gebruikend een werkschema en de **[!UICONTROL Save audience]** activiteit.

Het kan worden uitgevoerd in een nieuwe werkstroom en alleen door gebruikers die via IMS zijn verbonden (verificatie via Adobe ID).

1. Maak een nieuwe workflow op basis van een programma, een campagne of de lijst met marketingactiviteiten.
1. Wijs een reeks profielen aan met behulp van de verschillende beschikbare activiteiten.
1. Na het richten, sleep en laat vallen een **[!UICONTROL Save audience]** activiteit in het werkschema, dan open het.
1. Selecteer **[!UICONTROL Share in Adobe Experience Cloud]**.

   ![](assets/aam_save_audience_activity.png)

1. Geef het publiek op met het **[!UICONTROL Shared audience]** veld. In het venster dat wordt geopend, kunt u een bestaand publiek selecteren of een nieuw publiek maken:

   * Als u een bestaand publiek selecteert, worden alleen de nieuwe records aan het publiek toegevoegd.
   * Als u uw profiellijst naar een nieuw publiek wilt exporteren, vult u het **[!UICONTROL Segment name]** veld in en klikt u **[!UICONTROL Create]** voordat u het nieuwe publiek selecteert.
   ![](assets/aam_save_audience_segment_picker.png)

   Om in overeenstemming te zijn met en te kunnen uitwisselen, moeten de records een Adobe Experience Cloud-id (&#39;Visitor ID&#39; of &#39;Opgegeven ID&#39;) hebben. Niet-compatibele records worden genegeerd bij het importeren en exporteren van soorten publiek.

1. Klik op het vinkje rechtsboven in het scherm om te voltooien.
1. Selecteer de corresponderende **[!UICONTROL Shared Data Source]**.
1. Schakel desgewenst het **[!UICONTROL Generate an outbound transition]** selectievakje in om de profielen te gebruiken die zijn geëxporteerd. Alleen de profielen die met elkaar in overeenstemming kunnen worden gebracht, worden geëxporteerd.
1. Bevestig de configuratie van de activiteit en sla uw werkschema op.
1. Start de workflow om uw publiek te exporteren. De synchronisatie tussen Adobe Campaign en de kerndienst van Mensen kan verscheidene uren vergen

De synchronisatie tussen Adobe Campaign en de kerndienst van Mensen vergt 24-36 uur. Na deze periode kunt u uw nieuwe doelgroep vinden in de hoofdservice Personen en deze opnieuw gebruiken in andere Adobe Experience Cloud-oplossingen. Raadpleeg deze [documentatie](https://docs.adobe.com/content/help/en/core-services/interface/audiences/t-audience-create.html)voor meer informatie over het gebruik van een door Adobe Campaign gedeeld publiek in de Adobe People core-service.

**Verwante onderwerpen:**

* [Workflows](../../automating/using/get-started-workflows.md)
* [Soorten publiek](../../audiences/using/about-audiences.md)

