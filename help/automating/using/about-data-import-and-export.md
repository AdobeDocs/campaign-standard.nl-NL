---
title: Informatie over importeren en exporteren van gegevens
description: Leer meer over de verschillende manieren om gegevens te importeren en te exporteren met Adobe Campaign.
page-status-flag: never-activated
uuid: f6810364-555c-4b72-8a9c-4ae2fcb2ba63
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
discoiquuid: 31215773-6c0c-48f1-9101-da0ea2a366da
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0deabe17442b679a340a4497945837b83b4c9207
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 0%

---


# Informatie over importeren en exporteren van gegevens{#about-data-import-and-export}

Afhankelijk van uw bedrijfsbehoeften kunt u gegevens op verschillende manieren importeren en exporteren met Adobe Campagne:

* **Pakketten**: pakketten zijn XML-bestanden waarmee u configuraties en gegevenssets van een Adobe Campagne-instantie kunt exporteren en importeren naar een andere instantie. Systeemupdates worden ook uitgevoerd via het importeren van pakketten.
* **Lijsten**: alle lijstschermen kunnen worden gevormd en de getoonde gegevens worden uitgevoerd in een afzonderlijk dossier.
* **Workflows**: importeer gegevens uit bestanden en gebruik deze om de database bij te werken of e-mails te verzenden. U kunt ook gegevens selecteren die u wilt exporteren in bestanden. Workflows zijn de beste manier om regelmatige updates te automatiseren, zoals het importeren van profielen.

   * Met deze **[!UICONTROL Load file]** activiteit kunt u gegevens in één gestructureerd formulier importeren en deze gegevens gebruiken in Adobe Campaign. De gegevens worden tijdelijk geïmporteerd en een andere activiteit is nodig om deze definitief te integreren in de Adobe Campaign-database. Raadpleeg [deze sectie](../../automating/using/load-file.md)voor meer informatie over het gebruik van deze activiteit.
   * Met deze **[!UICONTROL Transfer file]** activiteit kunt u bestanden ontvangen of verzenden, testen of er bestanden aanwezig zijn of bestanden weergeven in Adobe Campagne. U kunt deze activiteit vóór een **[!UICONTROL Load file]** voor het geval gebruiken u het dossier van een externe bron moet terugwinnen. Raadpleeg [deze sectie](../../automating/using/transfer-file.md)voor meer informatie over het gebruik van deze activiteit.

Bij het ontwerpen van importprocessen kunt u het beste werkstroomsjablonen gebruiken die u aan uw wensen kunt aanpassen. Raadpleeg het [volgende gebruiksgeval](../../automating/using/creating-import-workflow-templates.md)voor meer informatie over het instellen van een werkstroomsjabloon voor het importeren van gegevens.

Adobe Campagne biedt ook een vereenvoudigde manier om reguliere importbewerkingen uit te voeren, die bestaat in het ontwerpen van **importsjablonen**. De malplaatjes van de invoer zijn gespecialiseerde werkschemamalplaatjes beschikbaar door een specifiek scherm. Als deze optie eenmaal is ontworpen, hoeft de gebruiker die de importbewerking uitvoert het bestand alleen te uploaden om in een vereenvoudigde weergave te worden geïmporteerd.

**Verwante onderwerpen**:

* [Gegevens importeren met importsjablonen](../../automating/using/importing-data-with-import-templates.md)
* [Importsjablonen definiëren](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates)
* [Pakketten beheren](../../automating/using/managing-packages.md)
