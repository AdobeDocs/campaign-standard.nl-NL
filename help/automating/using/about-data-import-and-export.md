---
title: Informatie over gegevens importeren en exporteren
description: In deze video ziet u de verschillende manieren waarop u gegevens kunt importeren en exporteren met Adobe Campaign.
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
feature: Workflows
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 208e8629-c3e2-4f36-bae7-46ffc3f56a1b
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 12%

---

# Informatie over gegevens importeren en exporteren{#about-data-import-and-export}

Afhankelijk van uw bedrijfsbehoeften kunt u gegevens op verschillende manieren importeren en exporteren met Adobe Campaign:

* **Pakketten**: de pakketten zijn de dossiers van XML die u toestaan om configuraties en reeksen gegevens van een instantie van Adobe Campaign naar een andere uit te voeren en in te voeren. Systeemupdates worden ook uitgevoerd via het importeren van pakketten.
* **Lijsten**: alle lijstschermen kunnen worden gevormd en de getoonde gegevens die in een afzonderlijk dossier worden uitgevoerd.
* **Werkstromen**: de invoergegevens van dossiers en gebruiken het om het gegevensbestand bij te werken of e-mails te verzenden. U kunt ook gegevens selecteren die u wilt exporteren in bestanden. Workflows zijn de beste manier om regelmatige updates te automatiseren, zoals het importeren van profielen.

   * Met de activiteit **[!UICONTROL Load file]** kunt u data in één gestructureerd formulier importeren en deze data gebruiken in Adobe Campaign. De gegevens worden tijdelijk geïmporteerd en een andere activiteit is nodig om deze definitief in de Adobe Campaign-database te integreren. Voor meer op hoe te om deze activiteit te gebruiken, verwijs naar [&#x200B; deze sectie &#x200B;](../../automating/using/load-file.md).
   * Met de **[!UICONTROL Transfer file]** -activiteit kunt u bestanden ontvangen of verzenden, testen of er bestanden aanwezig zijn of kunt u een lijst met bestanden weergeven in Adobe Campaign. U kunt deze activiteit vóór een **[!UICONTROL Load file]** gebruiken voor het geval u het dossier van een externe bron moet terugwinnen. Voor meer op hoe te om deze activiteit te gebruiken, verwijs naar [&#x200B; deze sectie &#x200B;](../../automating/using/transfer-file.md).

Bij het ontwerpen van importprocessen kunt u het beste werkstroomsjablonen gebruiken die u aan uw wensen kunt aanpassen. Voor meer op hoe te opstelling verwijst een werkschemamalplaatje om gegevens in te voeren, naar [&#x200B; dit gebruiksgeval &#x200B;](../../automating/using/creating-import-workflow-templates.md).

Adobe Campaign biedt ook een vereenvoudigde manier aan om regelmatige invoer uit te voeren die in het ontwerpen van **invoermalplaatjes** bestaat. De malplaatjes van de invoer zijn gespecialiseerde werkschemamalplaatjes beschikbaar door een specifiek scherm. Als deze optie eenmaal is ontworpen, hoeft de gebruiker die de importbewerking uitvoert het bestand alleen te uploaden om in een vereenvoudigde weergave te worden geïmporteerd.

**Verwante onderwerpen**:

* [Gegevens importeren met importsjablonen](../../automating/using/importing-data-with-import-templates.md)
* [Importsjablonen definiëren](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates)
* [Pakketten beheren](../../automating/using/managing-packages.md)
