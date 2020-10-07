---
title: De data uit een geïmporteerd bestand dedupliceren
description: In dit voorbeeld wordt getoond hoe u data uit een geïmporteerd bestand kunt dedupliceren voordat u de data in de database laadt.
page-status-flag: never-activated
uuid: 11a22a9c-3bfe-4953-8a52-2f4e93c128fb
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: e7a5e1e7-4680-46c7-98b8-0a47bb7be2b8
context-tags: dedup,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '328'
ht-degree: 89%

---


# De data uit een geïmporteerd bestand dedupliceren {#deduplicating-the-data-from-an-imported-file}

In dit voorbeeld wordt getoond hoe u data uit een geïmporteerd bestand kunt dedupliceren voordat u de data in de database laadt. Deze procedure verbetert de kwaliteit van de data die in de database worden geladen.

De workflow bestaat uit:

![](assets/deduplication_example2_workflow.png)

* A file that contains a list of profiles is imported using a [Load file](../../automating/using/load-file.md) activity. In dit voorbeeld heeft het geïmporteerde bestand de csv-indeling en bevat het 10 profielen:

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

   Dit bestand kan ook worden gebruikt als voorbeeldbestand om de indeling van de kolommen te detecteren en te definiëren. Controleer in het tabblad **[!UICONTROL Column definition]** of elke kolom van het geïmporteerde bestand correct is geconfigureerd.

   ![](assets/deduplication_example2_fileloading.png)

* Een [deduplicatie](../../automating/using/deduplication.md) -activiteit. De deduplicatie wordt uitgevoerd direct na het importeren van het bestand en vóór het invoegen van de data in de database. Daarom moet deze gebaseerd zijn op de **[!UICONTROL Temporary resource]** van de activiteit **[!UICONTROL Load file]**.

   In dit voorbeeld willen we één vermelding per uniek e-mailadres in het bestand behouden. Dubbele identificatie vindt daarom plaats in de kolom **email** van de tijdelijke resource. Twee e-mailadressen staan echter twee keer in het bestand. Daarom worden twee regels als duplicaten beschouwd.

   ![](assets/deduplication_example2_dedup.png)

* An [Update data](../../automating/using/update-data.md) activity allows you to insert the data kept from the deduplication process into the database. Pas wanneer de data worden bijgewerkt, worden de geïmporteerde data geïdentificeerd als behorend tot de profieldimensie.

   Hier willen we **[!UICONTROL Insert only]** uitvoeren op de profielen die nog niet bestaan in de database. We gaan dit doen door de e-mailkolom van het bestand en het e-mailveld van de dimensie **Profile** te gebruiken als de afstemmingssleutel.

   ![](assets/deduplication_example2_writer1.png)

   Geef de toewijzingen op tussen de kolommen van het bestand waaruit u de data en de databasevelden vanaf het tabblad **[!UICONTROL Fields to update]** wilt invoegen.

   ![](assets/deduplication_example2_writer2.png)

Start vervolgens de workflow. De records die tijdens het deduplicatieproces zijn opgeslagen, worden vervolgens toegevoegd aan de profielen in uw database.
