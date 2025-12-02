---
title: Doelgroepen delen met Audience Manager of de People core-service
description: Leer hoe u uw publiek importeert of exporteert binnen de verschillende Adobe Experience Cloud-oplossingen.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
feature: People Core Service Integration
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: b0d063de-863c-42e7-98dd-c4c86da3281e
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '790'
ht-degree: 2%

---

# Doelgroepen delen met Audience Manager of de People core-service{#sharing-audiences-with-audience-manager-or-people-core-service}

## Een publiek importeren {#importing-an-audience}

Dankzij de integratie met de basisservice van mensen kan een publiek rechtstreeks in Adobe Campaign worden geïmporteerd via een technische workflow om uw database te verrijken. Voor meer informatie over publiek dat in de kerndienst van Mensen deelt, verwijs naar deze [&#x200B; documentatie &#x200B;](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-publish.html?lang=nl-NL).

Het importeren van soorten publiek/segmenten van de People core-service in Adobe Campaign kan alleen via het menu **[!UICONTROL Audiences]** worden uitgevoerd door gebruikers die via IMS zijn verbonden (verificatie via Adobe ID).

1. Ga naar het menu **[!UICONTROL Audiences]** .
1. Selecteer in de actiebalk **[!UICONTROL Create]** die u naar het scherm wilt gaan om een publiek te maken.
1. Geef het label van het nieuwe publiek op.
1. Stel het publiek **[!UICONTROL Type]** in op **[!UICONTROL Experience Cloud]** om aan te geven dat het publiek dat wordt gemaakt een publiek is dat is geïmporteerd uit de kernservice Personen.
1. Selecteer in het veld **[!UICONTROL Name of the shared audience]** het publiek dat u wilt importeren. Alleen segmenten kunnen worden geïmporteerd. De korrelige gegevens met inbegrip van zeer belangrijk-waardeparen, eigenschappen en regels worden niet gesteund.

   ![](assets/aam_import_audience.png)

1. Selecteer de overeenkomende **[!UICONTROL Shared Data Source]** .

   Als de geselecteerde gegevensbron is geconfigureerd voor het gebruik van een versleutelingsalgoritme, kunt u met een extra optie **[!UICONTROL Force reconciliation with a profile]** . Schakel deze optie in als het veld **[!UICONTROL Channel]** van de gegevensbron is ingesteld op E-mail of Mobiel (SMS) en als u profielgegevens wilt gebruiken.

   Als u **[!UICONTROL Force reconciliation with a profile]** niet selecteert en als **[!UICONTROL Channel]** in AMC-gegevensbron is ingesteld op E-mail of Mobiel (SMS), worden alle gecodeerde gedeclareerde id&#39;s gedecodeerd. Een publiek van type **Dossier** met een lijst van alle e-mailadressen/mobiele telefoonaantallen wordt gecreeerd/bijgewerkt. Op deze manier gaat er geen e-mailadres of mobiele telefoonnummer verloren tijdens het importeren van een gedeeld publiek via deze integratie, zelfs als dat profiel niet bestaat in Campagne. Dit soort publiek kan niet rechtstreeks worden gebruikt, omdat het handmatig moet worden afgestemd met behulp van workflows.

1. Bevestig om het publiek te maken.

   Het publiek wordt vervolgens geïmporteerd via een technische workflow. Het bestaat uit records waarvan de id (&#39;Bezoeker-id&#39; of &#39;Opgegeven ID&#39;) kon worden afgestemd op de profieldimensie. IDs van de de kernde dienstsegmenten van Mensen die niet door Adobe Campaign worden erkend worden niet ingevoerd.

Uw publiek wordt nu geïmporteerd in uw Adobe Campaign-database. Het importeren duurt 24-36 uur om te synchroniseren, wanneer segmenten rechtstreeks worden geïmporteerd uit de People core-service of Audience Manager. Na deze periode kun je het nieuwe publiek in Adobe Campaign vinden en gebruiken.

>[!NOTE]
>
>Als u soorten publiek importeert van Adobe Analytics naar Adobe Campaign, moeten deze soorten publiek eerst worden gedeeld in People Core Service of Audience Manager. Dit proces duurt 12-24 uur en moet worden toegevoegd aan de synchronisatie van 24-36 uur met Campagne. In dat specifieke geval kan de tijd voor het delen van het publiek maximaal 60 uur bedragen. Voor meer informatie over het publiek dat van Adobe Analytics in de dienst van de Kern van Mensen en de manager van het Publiek deelt, verwijs naar deze [&#x200B; documentatie &#x200B;](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-publish.html?lang=nl-NL).

## Een publiek exporteren {#exporting-an-audience}

Een publiek kan van Adobe Campaign naar Audience Manager of de de kerndienst van Mensen worden uitgevoerd gebruikend een werkschema en de **[!UICONTROL Save audience]** activiteit.

Het kan worden uitgevoerd in een nieuwe werkstroom en alleen door gebruikers die via IMS zijn verbonden (verificatie via Adobe ID).

1. Maak een nieuwe workflow op basis van een programma, een campagne of de lijst met marketingactiviteiten.
1. Wijs een reeks profielen aan met behulp van de verschillende beschikbare activiteiten.
1. Nadat u een **[!UICONTROL Save audience]** -activiteit als doel hebt opgegeven, sleept u deze naar de workflow en opent u deze.
1. Selecteer **[!UICONTROL Share in Adobe Experience Cloud]**.

   ![](assets/aam_save_audience_activity.png)

1. Geef het publiek op met het veld **[!UICONTROL Shared audience]** . In het venster dat wordt geopend, kunt u een bestaand publiek selecteren of een nieuw publiek maken:

   * Als u een bestaand publiek selecteert, worden alleen de nieuwe records aan het publiek toegevoegd.
   * Als u uw profiellijst naar een nieuw publiek wilt exporteren, vult u het veld **[!UICONTROL Segment name]** in en klikt u op **[!UICONTROL Create]** voordat u het nieuwe publiek selecteert.

   ![](assets/aam_save_audience_segment_picker.png)

   Om met elkaar in overeenstemming te kunnen worden gebracht en uitgewisseld, moeten de records een Adobe Experience Cloud-id (&#39;bezoeker-id&#39; of &#39;Opgegeven ID&#39;) hebben. Niet-compatibele records worden genegeerd bij het importeren en exporteren van soorten publiek.

1. Klik op het vinkje rechtsboven in het scherm om te voltooien.
1. Selecteer de overeenkomende **[!UICONTROL Shared Data Source]** .
1. Schakel desgewenst het selectievakje **[!UICONTROL Generate an outbound transition]** in om de profielen te gebruiken die zijn geëxporteerd. Alleen de profielen die in overeenstemming kunnen worden gebracht, worden geëxporteerd.
1. Bevestig de configuratie van de activiteit en sla uw werkschema op.
1. Start de workflow om uw publiek te exporteren. De synchronisatie tussen Adobe Campaign en de kerndienst van Mensen kan verscheidene uren vergen

De synchronisatie tussen Adobe Campaign en de kerndienst van Mensen vergt 24-36 uur. Na deze periode, zult u uw nieuw publiek in de de kerndienst van Mensen kunnen vinden en het in andere oplossingen van Adobe Experience Cloud hergebruiken. Voor meer informatie bij het gebruiken van een Adobe Campaign gedeeld publiek in de kerndienst van de Mensen van Adobe, verwijs naar deze [&#x200B; documentatie &#x200B;](https://experienceleague.adobe.com/docs/core-services/interface/audiences/t-audience-create.html?lang=nl-NL).

**Verwante onderwerpen:**

* [Workflows](../../automating/using/get-started-workflows.md)
* [Doelgroepen](../../audiences/using/about-audiences.md)
