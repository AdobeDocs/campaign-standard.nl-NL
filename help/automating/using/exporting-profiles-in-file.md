---
title: Profielen exporteren naar een extern bestand
description: Met deze optie kunt u zien hoe u een lijst met profielen in de vorm van een extern bestand exporteert, zodat de gegevens buiten Adobe Campaign kunnen worden gebruikt.
page-status-flag: never-activated
uuid: 631f0fbd-9e8d-4f77-a338-fcb7f4fc1774
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: a06509f9-4731-4187-b43d-3bfa361284d3
context-tags: fileExport,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 68%

---


# Profielen exporteren naar een extern bestand {#exporting-profiles-external-file}

Het volgende voorbeeld toont hoe u een **[!UICONTROL Extract file]**-activiteit na een **[!UICONTROL Query]**-activiteit configureert.

Het doel van deze workflow is om een lijst met profielen te exporteren naar een extern bestand, zodat de data ook buiten Adobe Campaign kunnen worden gebruikt.

1. Drag and drop an [Extract file](../../automating/using/extract-file.md) activity into your workflow and place it after the [Query](../../automating/using/query.md) activity.

   In dit voorbeeld wordt de query uitgevoerd op alle profielen met een leeftijd van 18 tot en met 30 jaar.

1. Open the **[!UICONTROL Extract file]** activity to edit it.
1. Geef een naam op voor het uitvoerbestand.
1. Voer uitvoerkolommen toe.

   In dit voorbeeld worden e-mailadres, leeftijd, geboortedatum, voornaam en achternaam van de profielen toegevoegd als uitvoerkolommen.

   ![](assets/wkf_data_export6.png)

1. Klik op het tabblad **[!UICONTROL File structure]** om het volgende te definiëren:

   * CSV-uitvoerindeling

      ![](assets/wkf_data_export7.png)

   * Datumnotatie

      ![](assets/wkf_data_export9.png)

1. Bevestig uw activiteit.
1. Drag and drop a [Transfer file](../../automating/using/transfer-file.md) activity after the **[!UICONTROL Extract file]** activity to recover the extract file on an external account.
1. Open de activiteit en kies de actie **[!UICONTROL File upload]**.

   ![](assets/wkf_data_export11.png)

1. Selecteer het externe account en typ het pad naar de map op de server.

   ![](assets/wkf_data_export12.png)

1. Bevestig uw activiteit en sla de workflow op.
1. Start de workflow.

   Wanneer de workflow correct is uitgevoerd, is het uitgepakte bestand beschikbaar op het externe account.
