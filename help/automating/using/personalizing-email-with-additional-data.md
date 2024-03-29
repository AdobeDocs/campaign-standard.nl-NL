---
title: Een e-mail met aanvullende gegevens personaliseren
description: Dit gebruiksgeval stelt voor hoe te om verschillende soorten extra gegevens aan een vraag toe te voegen en het als verpersoonlijkingsgebied in een e-mail te gebruiken.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: query,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: b207dc73-03dc-4f25-95e5-573e4b4bce54
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '480'
ht-degree: 81%

---

# Een e-mail met aanvullende gegevens personaliseren {#example--personalizing-an-email-with-additional-data}

In het volgende voorbeeld ziet u hoe u verschillende typen aanvullende gegevens toevoegt aan een query en hoe u deze gebruikt als een verpersoonlijkingsveld in een e-mailbericht. Meer informatie over het verrijken van de gegevens waarop een **[!UICONTROL Query]** activiteit, zie [deze sectie](../../automating/using/query.md#enriching-data).

In dit voorbeeld worden [aangepaste bronnen](../../developing/using/data-model-concepts.md) gebruikt:

* De **profielbron** werd uitgebreid om een veld toe te voegen waarin de loyaliteitspunten van elk profiel kunnen worden opgeslagen.
* Er is een **transactiebron** gemaakt waarmee alle aankopen die door de profielen in de database zijn uitgevoerd, worden geïdentificeerd. De datum, de prijs en het gekochte product worden voor elke transactie opgeslagen.
* Er is een **productbron** gemaakt die verwijst naar de producten die kunnen worden gekocht.

We willen nu een e-mail sturen naar alle profielen waarvoor ten minste één transactie is opgeslagen. Via deze e-mail ontvangen de klanten een herinnering van de laatste uitgevoerde transactie en een overzicht van al hun transacties: het aantal gekochte producten, het uitgegeven totaalbedrag en het totale aantal loyaliteitspunten dat ze hebben opgebouwd.

De workflow wordt als volgt weergegeven:

![](assets/enrichment_example1.png)

1. Voeg een [Query](../../automating/using/query.md) activiteit, waardoor u zich kunt richten op de profielen die minstens één transactie hebben uitgevoerd.

   ![](assets/enrichment_example2.png)

1. Op het tabblad **[!UICONTROL Additional data]** van de query definieert u de verschillende data die in de uiteindelijke e-mail moeten komen:

   * Het eenvoudige veld van de **profieldimensie** die overeenkomt met de loyaliteitspunten. Raadpleeg de sectie [Een eenvoudig veld toevoegen](../../automating/using/query.md#adding-a-simple-field).
   * Twee aggregaten gebaseerd op de transactieverzameling: het aantal gekochte producten en het totale bestede bedrag. U kunt deze toevoegen vanaf het tabblad **[!UICONTROL Data]** van het samengevoegde configuratievenster. Gebruik de aggregaten **Count** en **Sum**. Raadpleeg de sectie [Een aggregaat toevoegen](../../automating/using/query.md#adding-an-aggregate).
   * Een verzameling waarmee het bestede bedrag, de datum en het product van de laatste uitgevoerde transactie wordt geretourneerd.

     Hiervoor moet u de verschillende velden toevoegen die u wilt weergeven op het tabblad **[!UICONTROL Data]** van het configuratievenster van de verzameling.

     Als u alleen de meest recente transactie wilt retourneren, moet u &quot;1&quot; voor **[!UICONTROL Number of lines to return]** invoeren en een aflopende sortering toepassen voor het veld **Date** van de verzameling. Hiervoor gebruikt u het tabblad **[!UICONTROL Sort]**.

     Raadpleeg de secties [Een verzameling toevoegen](../../automating/using/query.md#adding-a-collection) en [Aanvullende data sorteren](../../automating/using/query.md#sorting-additional-data).

   ![](assets/enrichment_example4.png)

1. Als u wilt controleren dat de data correct door de uitgaande overgang van de activiteit worden overgebracht, start u de workflow voor de eerste keer (zonder de activiteit **[!UICONTROL Email delivery]**) en opent u de uitgaande overgang van de query.

   ![](assets/enrichment_example5.png)

1. Een [E-maillevering](../../automating/using/email-delivery.md) activiteit. Voeg de personalisatievelden toe aan de e-mail die overeenkomen met de data die in de query zijn berekend. Deze zijn beschikbaar via de koppeling **[!UICONTROL Additional data (targetData)]** van de verkennertool voor personalisatievelden.

   ![](assets/enrichment_example3.png)

Uw workflow kan nu worden uitgevoerd. De profielen die in de query worden getarget, ontvangen een gepersonaliseerde e-mail met de data die van hun transacties zijn berekend.
