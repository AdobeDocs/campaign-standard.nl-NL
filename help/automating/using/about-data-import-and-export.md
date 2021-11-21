---
title: Informatie over gegevens importeren en exporteren
description: In deze video ziet u de verschillende manieren waarop u gegevens kunt importeren en exporteren met Adobe Campaign.
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
feature: Workflows
role: Data Architect
level: Experienced
exl-id: 208e8629-c3e2-4f36-bae7-46ffc3f56a1b
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 24%

---

# Informatie over gegevens importeren en exporteren{#about-data-import-and-export}

Afhankelijk van uw bedrijfsbehoeften kunt u gegevens op verschillende manieren importeren en exporteren met Adobe Campaign:

* **Pakketten**: pakketten zijn XML-bestanden waarmee u configuraties en gegevenssets van een Adobe Campaign-instantie naar een andere instantie kunt exporteren en importeren. Systeemupdates worden ook uitgevoerd via het importeren van pakketten.
* **Lijsten**: alle lijstschermen kunnen worden gevormd en de getoonde gegevens worden uitgevoerd in een afzonderlijk dossier.
* **Workflows**: importeer gegevens uit bestanden en gebruik deze om de database bij te werken of e-mails te verzenden. U kunt ook gegevens selecteren die u wilt exporteren in bestanden. Workflows zijn de beste manier om regelmatige updates te automatiseren, zoals het importeren van profielen.

   * Met de activiteit **[!UICONTROL Load file]** kunt u data in één gestructureerd formulier importeren en deze data gebruiken in Adobe Campaign. De data worden tijdelijk geïmporteerd en een andere activiteit is nodig om deze definitief te integreren in de Adobe Campaign-database. Raadpleeg voor meer informatie over het gebruik van deze activiteit [deze sectie](../../automating/using/load-file.md).
   * Met de activiteit **[!UICONTROL Transfer file]** kunt u bestanden ontvangen of verzenden, testen of er bestanden aanwezig zijn of een lijst met bestanden weergeven in Adobe Campaign. U kunt deze activiteit gebruiken vóór een **[!UICONTROL Load file]** als u het bestand van een externe bron moet ophalen. Raadpleeg voor meer informatie over het gebruik van deze activiteit [deze sectie](../../automating/using/transfer-file.md).

Bij het ontwerpen van importprocessen kunt u het beste werkstroomsjablonen gebruiken die u aan uw wensen kunt aanpassen. Voor meer informatie over het instellen van een werkstroomsjabloon voor het importeren van gegevens raadpleegt u [dit geval gebruiken](../../automating/using/creating-import-workflow-templates.md).

Adobe Campaign biedt ook een vereenvoudigde manier om reguliere importbewerkingen uit te voeren, die bestaat in het ontwerpen **importsjablonen**. De malplaatjes van de invoer zijn gespecialiseerde werkschemamalplaatjes beschikbaar door een specifiek scherm. Als deze optie eenmaal is ontworpen, hoeft de gebruiker die de importbewerking uitvoert het bestand alleen te uploaden om in een vereenvoudigde weergave te worden geïmporteerd.

**Verwante onderwerpen**:

* [Gegevens importeren met importsjablonen](../../automating/using/importing-data-with-import-templates.md)
* [Importsjablonen definiëren](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates)
* [Pakketten beheren](../../automating/using/managing-packages.md)
