---
title: De gegevens uit een geïmporteerd bestand dedupliceren
description: In dit voorbeeld wordt getoond hoe u gegevens uit een geïmporteerd bestand kunt dedupliceren voordat u de gegevens in de database laadt.
page-status-flag: never-activated
uuid: 11a22a9c-3bfe-4953-8a52-2f4e93c128fb
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: e7a5e1e7-4680-46c7-98b8-0a47bb7be2b8
context-tags: dedup,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7ffa48365875883a98904d6b344ac005afe26e18
workflow-type: tm+mt
source-wordcount: '328'
ht-degree: 0%

---


# De gegevens uit een geïmporteerd bestand dedupliceren {#deduplicating-the-data-from-an-imported-file}

In dit voorbeeld wordt getoond hoe u gegevens uit een geïmporteerd bestand kunt dedupliceren voordat u de gegevens in de database laadt. Deze procedure verbetert de kwaliteit van de gegevens die in het gegevensbestand worden geladen.

De workflow bestaat uit:

![](assets/deduplication_example2_workflow.png)

* Een bestand dat een lijst met profielen bevat, wordt geïmporteerd met een activiteit [Bestand](../../automating/using/load-file.md) laden. In dit voorbeeld heeft het geïmporteerde bestand de CSV-indeling en bevat het 10 profielen:

   ```
   lastname;firstname;dateofbirth;email
   Smith;Hayden;23/05/1989;hayden.smith@example.com
   Mars;Daniel;17/11/1987;dannymars@example.com
   Smith;Clara;08/02/1989;hayden.smith@example.com
   Durance;Allison;15/12/1978;allison.durance@example.com
   Lucassen;Jody;28/03/1988;jody.lucassen@example.com
   Binder;Tom;19/01/1982;tombinder@example.com
   Binder;Tommy;19/01/1915;tombinder@example.com
   Connor;Jade;10/10/1979;connor.jade@example.com
   Mack;Clarke;02/03/1985;clarke.mack@example.com
   Ross;Timothy;04/07/1986;timross@example.com
   ```

   Dit bestand kan ook worden gebruikt als voorbeeldbestand om de indeling van de kolommen te detecteren en te definiëren. Controleer in het **[!UICONTROL Column definition]** tabblad of elke kolom van het geïmporteerde bestand correct is geconfigureerd.

   ![](assets/deduplication_example2_fileloading.png)

* Een [deduplicatie](../../automating/using/deduplication.md) -activiteit. De deduplicatie wordt direct uitgevoerd na het invoeren van het dossier en alvorens de gegevens in het gegevensbestand op te nemen. Daarom moet zij gebaseerd zijn op de **[!UICONTROL Temporary resource]** resultaten van de **[!UICONTROL Load file]** activiteit.

   In dit voorbeeld willen we één item per uniek e-mailadres in het bestand bewaren. Dubbele identificatie vindt daarom plaats in de **e-mailkolom** van de tijdelijke bron. Twee e-mailadressen staan echter twee keer in het bestand. Twee lijnen worden daarom als duplicaten beschouwd.

   ![](assets/deduplication_example2_dedup.png)

* Met een [updategegevensactiviteit](../../automating/using/update-data.md) kunt u de gegevens uit het deduplicatieproces in de database invoegen. Alleen wanneer de gegevens worden bijgewerkt, worden de geïmporteerde gegevens geïdentificeerd als behorend tot de profieldimensie.

   Hier willen we graag **[!UICONTROL Insert only]** de profielen zien die nog niet bestaan in de database. We gaan dit doen door de e-mailkolom van het bestand en het e-mailveld van de dimensie **Profiel** te gebruiken als de combinatietoets.

   ![](assets/deduplication_example2_writer1.png)

   Geef de toewijzingen op tussen de kolommen van het bestand waaruit u de gegevens en de databasevelden vanaf het **[!UICONTROL Fields to update]** tabblad wilt invoegen.

   ![](assets/deduplication_example2_writer2.png)

Start vervolgens de workflow. De records die tijdens het deduplicatieproces zijn opgeslagen, worden vervolgens toegevoegd aan de profielen in uw database.
