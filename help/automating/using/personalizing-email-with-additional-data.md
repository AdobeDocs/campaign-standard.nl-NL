---
title: Een e-mail aanpassen met aanvullende gegevens
description: Dit gebruiksgeval stelt voor hoe te om verschillende soorten extra gegevens aan een vraag toe te voegen en het als verpersoonlijkingsgebied in een e-mail te gebruiken.
page-status-flag: never-activated
uuid: b3c629fa-370e-481c-b347-fcf9f5a5e847
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 8d46ce28-0101-4f13-865a-2208ed6d6139
context-tags: query,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2d994d85f126951215f1227301599c554c1f12c8
workflow-type: tm+mt
source-wordcount: '479'
ht-degree: 0%

---


# Een e-mail aanpassen met aanvullende gegevens {#example--personalizing-an-email-with-additional-data}

In het volgende voorbeeld ziet u hoe u verschillende typen aanvullende gegevens toevoegt aan een query en hoe u deze gebruikt als een verpersoonlijkingsveld in een e-mailbericht. Zie **[!UICONTROL Query]** deze sectie [voor meer informatie over het verrijken van de gegevens waarop een](../../automating/using/query.md#enriching-data)activiteit is gericht.

In dit voorbeeld worden [aangepaste bronnen](../../developing/using/data-model-concepts.md) gebruikt:

* Het **profielmiddel** werd uitgebreid om een gebied toe te voegen dat de loyaliteitspunten van elk profiel om toelaat worden bewaard.
* Er is een **bron voor transacties** gemaakt en alle aankopen die door de profielen in de database worden uitgevoerd, worden geïdentificeerd. De datum, de prijs en het gekochte product worden voor elke transactie opgeslagen.
* Er is een **productbron** gemaakt en er wordt verwezen naar de producten die u kunt kopen.

Het doel is een e-mail te verzenden naar de profielen waarvoor ten minste één transactie is opgeslagen. Via deze e-mail ontvangen de klanten een herinnering aan de laatste uitgevoerde transactie en een overzicht van al hun transacties: het aantal aangekochte producten, het totale aantal uitgegeven producten, een herinnering aan het totale aantal loyaliteitspunten dat zij hebben opgebouwd.

De workflow wordt als volgt weergegeven:

![](assets/enrichment_example1.png)

1. Voeg een activiteit van de [Vraag](../../automating/using/query.md) toe, die u toestaat om de profielen te richten die minstens één transactie hebben uitgevoerd.

   ![](assets/enrichment_example2.png)

   Definieer op het **[!UICONTROL Additional data]** tabblad van de query de verschillende gegevens die in de laatste e-mail moeten worden weergegeven:

   * Het eenvoudige gebied van de **profieldimensie** die aan de loyaliteitspunten beantwoordt. Raadpleeg de sectie Een eenvoudig veld [](../../automating/using/query.md#adding-a-simple-field) toevoegen.
   * Twee aggregaten gebaseerd op de transactieverzameling: het aantal aangekochte producten en het totale bestede bedrag. U kunt ze toevoegen vanaf het **[!UICONTROL Data]** tabblad van het geaggregeerde configuratievenster met behulp van de aggregaten **Aantal** en **Som** . Raadpleeg het gedeelte [Een aggregaat](../../automating/using/query.md#adding-an-aggregate) toevoegen.
   * Een inning die het bestede bedrag, de datum, en het product van de laatste uitgevoerde transactie terugkeert.

      Hiervoor moet u de verschillende velden toevoegen die u wilt weergeven op het **[!UICONTROL Data]** tabblad van het verzamelingsconfiguratievenster.

      Als u alleen de meest recente transactie wilt retourneren, moet u &quot;1&quot; voor de verzameling invoeren **[!UICONTROL Number of lines to return]** en een aflopende sortering toepassen in het veld **Datum** van de verzameling op het **[!UICONTROL Sort]** tabblad.

      Raadpleeg de secties [Een verzameling](../../automating/using/query.md#adding-a-collection) toevoegen en [Extra gegevens](../../automating/using/query.md#sorting-additional-data) sorteren.
   ![](assets/enrichment_example4.png)

   Als u zou willen controleren dat de gegevens correct door de uitgaande overgang van de activiteit worden overgebracht, begin het werkschema voor het eerst (zonder de **[!UICONTROL Email delivery]** activiteit) en open de uitgaande overgang van de vraag.

   ![](assets/enrichment_example5.png)

1. Voeg een [e-mailleveringsactiviteit](../../automating/using/email-delivery.md) toe. Voeg in de e-mailinhoud de personalisatievelden in die overeenkomen met de gegevens die in de query zijn berekend. U kunt het vinden via de **[!UICONTROL Additional data (targetData)]** verbinding van de verpersoonlijkingsgebiedsverkenner.

   ![](assets/enrichment_example3.png)

Uw workflow kan nu worden uitgevoerd. De profielen die in de vraag worden bedoeld zullen een gepersonaliseerde e-mail ontvangen die de gegevens bevat die van hun transacties worden berekend.
