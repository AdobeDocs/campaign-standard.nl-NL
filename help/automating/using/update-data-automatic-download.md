---
title: Gegevens bijwerken op basis van een automatische bestandsdownload
description: 'In het volgende voorbeeld wordt het resultaat getoond van een activiteit van een automatisch gedownload laadbestand via een activiteit van het overdrachtsbestand, gevolgd door een activiteit van updategegevens. '
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
source-git-commit: 7ffa48365875883a98904d6b344ac005afe26e18
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 0%

---


# Gegevens bijwerken op basis van een automatische bestandsdownload {#updating-data-automatic-file-download}

De activiteit van het ladingsdossier structureert hoofdzakelijk de gegevens van een activiteit van het overdrachtsdossier om het in de bestaande gegevens te integreren.

In het volgende voorbeeld wordt het resultaat getoond van een activiteit van een automatisch gedownload laadbestand via een activiteit van het overdrachtsbestand, gevolgd door een activiteit van updategegevens. Deze workflow is bedoeld om de Adobe Campaign-database te verrijken met nieuwe profielen of om bestaande profielen bij te werken aan de hand van de gegevens uit het geïmporteerde bestand.

![](assets/load_file_workflow_ex1.png)

Voer de volgende stappen uit om de workflow te maken:

1. Sleep een [bestandsactiviteit](../../automating/using/transfer-file.md) overbrengen naar uw workflow.
1. Selecteer de activiteit, dan open het gebruikend de ![](assets/edit_darkgrey-24px.png) knoop van de snelle acties die verschijnen.
1. Configureer de activiteit op een manier zodat het bestand dat u wilt herstellen wordt hersteld. Selecteer op het **[!UICONTROL Protocol]** tabblad **SFTP**.
1. Selecteer de **verbindingsparameters gebruiken die zijn gedefinieerd in een optie voor een externe account** .
1. Voer de naam van de externe account in.
1. Voer het **bestandspad op de externe server** in.

   ![](assets/wkf_file_transfer_07.png)

1. Bevestig je activiteit.
1. Sleep een [activiteit van het Dossier](../../automating/using/load-file.md) van de Lading in uw werkschema en plaats het na de **[!UICONTROL Transfer file]** activiteit.
1. Selecteer de activiteit, dan open het gebruikend de ![](assets/edit_darkgrey-24px.png) knoop van de snelle acties die verschijnen.
1. Schakel de **[!UICONTROL File to load]** optie in de **[!UICONTROL Execution]** sectie van het **[!UICONTROL Use the file specified in the inbound transition]** tabblad in.

   ![](assets/wkf_file_loading8.png)

1. Configureer uw activiteit zoals eerder opgegeven.
1. Sleep en zet een [Update gegevensactiviteit](../../automating/using/update-data.md) in uw werkschema neer en plaats het na de **[!UICONTROL Load file]** activiteit, dan vorm het.

Nadat de workflow is gestart, worden de gegevens uit het geüploade bestand geëxtraheerd en vervolgens gebruikt om de Adobe Campaign-database te verrijken.
