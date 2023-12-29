---
title: Profielen exporteren naar een extern bestand
description: Met deze optie kunt u zien hoe u een lijst met profielen in de vorm van een extern bestand exporteert, zodat de gegevens buiten Adobe Campaign kunnen worden gebruikt.
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: fileExport,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 3fc286a9-bba4-4e3d-95cd-600eed4943e7
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 68%

---

# Profielen exporteren naar een extern bestand {#exporting-profiles-external-file}

Het volgende voorbeeld toont hoe u een **[!UICONTROL Extract file]**-activiteit na een **[!UICONTROL Query]**-activiteit configureert.

Het doel van deze workflow is om een lijst met profielen te exporteren naar een extern bestand, zodat de data ook buiten Adobe Campaign kunnen worden gebruikt.

1. Sleep een [Bestand uitpakken](../../automating/using/extract-file.md) activiteit in uw werkschema en plaats het na [Query](../../automating/using/query.md) activiteit.

   In dit voorbeeld wordt de query uitgevoerd op alle profielen met een leeftijd van 18 tot en met 30 jaar.

1. Open de **[!UICONTROL Extract file]** activiteit om deze te bewerken.
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
1. Sleep een [Bestand overbrengen](../../automating/using/transfer-file.md) activiteit na de **[!UICONTROL Extract file]** activiteit om het extractiedossier op een externe rekening terug te krijgen.
1. Open de activiteit en kies de actie **[!UICONTROL File upload]**.

   ![](assets/wkf_data_export11.png)

1. Selecteer het externe account en typ het pad naar de map op de server.

   ![](assets/wkf_data_export12.png)

1. Bevestig uw activiteit en sla de workflow op.
1. Start de workflow.

   Wanneer de workflow correct is uitgevoerd, is het uitgepakte bestand beschikbaar op het externe account.
