---
solution: Campaign Standard
product: campaign
title: Data bijwerken op basis van een automatische bestandsdownload
description: 'In het volgende voorbeeld wordt het resultaat getoond van een automatisch gedownloade activiteit voor het laden van een bestand via een activiteit voor het overdragen van een bestand, gevolgd door een activiteit voor het bijwerken van data. '
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: fileImport,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 79%

---


# Data bijwerken op basis van een automatische bestandsdownload {#updating-data-automatic-file-download}

De activiteit voor het laden van een bestand structureert hoofdzakelijk de data van een activiteit voor het overdragen van een bestand om het in de bestaande data te integreren.

In het volgende voorbeeld wordt het resultaat getoond van een automatisch gedownloade activiteit voor het laden van een bestand via een activiteit voor het overdragen van een bestand, gevolgd door een activiteit voor het bijwerken van data. Deze workflow is bedoeld om de Adobe Campaign-database te verrijken met nieuwe profielen of om bestaande profielen bij te werken aan de hand van de data die uit het geïmporteerde bestand zijn hersteld.

![](assets/load_file_workflow_ex1.png)

Voer de volgende stappen uit om de workflow te maken:

1. Sleep en zet een activiteit [Bestand overdragen](../../automating/using/transfer-file.md) neer in uw workflow.
1. Selecteer de activiteit en open deze met de knop ![](assets/edit_darkgrey-24px.png) vanuit de snelle acties die verschijnen.
1. Configureer de activiteit op een manier zodat het bestand dat u wilt herstellen wordt hersteld. Selecteer op het tabblad **[!UICONTROL Protocol]** de optie **SFTP**.
1. Selecteer de optie **Use connection parameters defined in an external account**.
1. Voer de naam van het externe account in.
1. Voer het **File path on the remote server** in.

   ![](assets/wkf_file_transfer_07.png)

1. Bevestig uw activiteit.
1. Drag and drop a [Load file](../../automating/using/load-file.md) activity into your workflow and place it after the **[!UICONTROL Transfer file]** activity.
1. Selecteer de activiteit en open deze met de knop ![](assets/edit_darkgrey-24px.png) vanuit de snelle acties die verschijnen.
1. Schakel in de sectie **[!UICONTROL File to load]** van het tabblad **[!UICONTROL Execution]** de optie **[!UICONTROL Use the file specified in the inbound transition]** in.

   ![](assets/wkf_file_loading8.png)

1. Configureer uw activiteit zoals eerder opgegeven.
1. Drag and drop an [Update data](../../automating/using/update-data.md) activity into your workflow and place it after the **[!UICONTROL Load file]** activity, then configure it.

Nadat de workflow is gestart, worden de data uit het geüploade bestand geëxtraheerd en vervolgens gebruikt om de Adobe Campaign-database te verrijken.
