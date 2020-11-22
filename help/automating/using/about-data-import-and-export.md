---
solution: Campaign Standard
product: campaign
title: Informatie over data importeren en exporteren
description: In deze video ziet u de verschillende manieren waarop u gegevens kunt importeren en exporteren met Adobe Campaign.
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 24%

---


# Informatie over data importeren en exporteren{#about-data-import-and-export}

Afhankelijk van uw bedrijfsbehoeften kunt u gegevens op verschillende manieren importeren en exporteren met Adobe Campaign:

* **Pakketten**: pakketten zijn XML-bestanden waarmee u configuraties en gegevenssets van een Adobe Campaign-instantie naar een andere instantie kunt exporteren en importeren. Systeemupdates worden ook uitgevoerd via het importeren van pakketten.
* **Lijsten**: alle lijstschermen kunnen worden gevormd en de getoonde gegevens worden uitgevoerd in een afzonderlijk dossier.
* **Workflows**: importeer gegevens uit bestanden en gebruik deze om de database bij te werken of e-mails te verzenden. U kunt ook gegevens selecteren die u wilt exporteren in bestanden. Workflows zijn de beste manier om regelmatige updates te automatiseren, zoals het importeren van profielen.

   * Met de activiteit **[!UICONTROL Load file]** kunt u data in één gestructureerd formulier importeren en deze data gebruiken in Adobe Campaign. De data worden tijdelijk geïmporteerd en een andere activiteit is nodig om deze definitief te integreren in de Adobe Campaign-database. Raadpleeg [deze sectie](../../automating/using/load-file.md)voor meer informatie over het gebruik van deze activiteit.
   * Met de activiteit **[!UICONTROL Transfer file]** kunt u bestanden ontvangen of verzenden, testen of er bestanden aanwezig zijn of een lijst met bestanden weergeven in Adobe Campaign. U kunt deze activiteit vóór een **[!UICONTROL Load file]** voor het geval gebruiken u het dossier van een externe bron moet terugwinnen. Raadpleeg [deze sectie](../../automating/using/transfer-file.md)voor meer informatie over het gebruik van deze activiteit.

Bij het ontwerpen van importprocessen kunt u het beste werkstroomsjablonen gebruiken die u aan uw wensen kunt aanpassen. Raadpleeg het [volgende gebruiksgeval](../../automating/using/creating-import-workflow-templates.md)voor meer informatie over het instellen van een werkstroomsjabloon voor het importeren van gegevens.

Adobe Campaign biedt ook een vereenvoudigde manier om reguliere importbewerkingen uit te voeren, die bestaat uit het ontwerpen van **importsjablonen**. De malplaatjes van de invoer zijn gespecialiseerde werkschemamalplaatjes beschikbaar door een specifiek scherm. Als deze optie eenmaal is ontworpen, hoeft de gebruiker die de importbewerking uitvoert het bestand alleen te uploaden om in een vereenvoudigde weergave te worden geïmporteerd.

**Verwante onderwerpen**:

* [Data importeren met importsjablonen](../../automating/using/importing-data-with-import-templates.md)
* [Importsjablonen definiëren](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates)
* [Pakketten beheren](../../automating/using/managing-packages.md)
