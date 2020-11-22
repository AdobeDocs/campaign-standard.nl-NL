---
solution: Campaign Standard
product: campaign
title: Een workflow maken
description: In deze sectie worden de belangrijkste beginselen en best practice voor het maken van een nieuwe workflow beschreven.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,wizard;workflow,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '958'
ht-degree: 100%

---


# Een workflow maken{#building-a-workflow}

In deze sectie worden de belangrijkste beginselen en best practice voor het maken van een nieuwe workflow beschreven.

## Functioneringsprincipes van workflows{#workflow-operating-principles}

Een workflow is een **reeks configureerbare activiteiten**. Elke activiteit heeft een specifieke rol in het proces. Het resultaat van elke activiteit wordt doorgestuurd naar de volgende activiteit door een **overgang**, die door een pijl wordt vertegenwoordigd.

Het type data dat tussen activiteiten wordt uitgewisseld, kan van invloed zijn op de manier waarop de volgende activiteiten worden geconfigureerd. Als er bijvoorbeeld een populatie is ingesteld vóór een activiteit E-maillevering, kan deze als doel dienen voor de desbetreffende e-mail.

U kunt activiteiten openen om parameters te controleren of te bewerken voor of na het uitvoeren van de workflow.

U kunt overgangen openen om te controleren of de verzonden data correct zijn tijdens of na het uitvoeren van de workflow. Voor toegang tot de gedetailleerde weergave van de overgangen moet u de optie **[!UICONTROL Keep interim results]** in de sectie **[!UICONTROL Execution]** van de workfloweigenschappen selecteren.

>[!CAUTION]
>
>Deze optie verbruikt veel schijfruimte en is ontworpen om u te helpen een workflow te maken en een correcte configuratie en functionaliteit te garanderen. Laat deze optie uitgeschakeld op productie-instanties.

![](assets/workflow_overview.png)


## Een workflow maken {#creating-a-workflow}

U kunt een workflow maken op basis van een programma, een campagne of de lijst met marketingactiviteiten.

Het maken van een marketingactiviteit wordt gedetailleerd beschreven in de sectie [Marketingactiviteiten maken](../../start/using/marketing-activities.md#creating-a-marketing-activity).

1. Nadat u een type marketingactiviteit voor de workflow hebt gemaakt, selecteert u de sjabloon die u wilt gebruiken.

   ![](assets/workflow_creation_1.png)

   >[!NOTE]
   >
   >Elke marketingactiviteit biedt standaard diverse typen aan. Hiermee kunt u bepaalde parameters vooraf configureren al naar gelang uw behoeften. Raadpleeg de sectie [Sjablonen beheren](../../start/using/marketing-activity-templates.md) voor meer informatie.

1. Voer de algemene eigenschappen van de workflow in.

   ![](assets/workflow_creation_2.png)

   U kunt een naam invoeren in het veld **Label** en de id wijzigen. De activiteitennaam en de bijbehorende id verschijnen in de interface, maar deze zijn niet zichtbaar voor de berichtontvangers.

   >[!NOTE]
   >
   >U kunt uw workflow in een bovenliggende campagne maken vanuit de lijst met marketingactiviteiten. U kunt deze workflow koppelen aan een campagne door een campagne te selecteren die al is gemaakt.

   U kunt een beschrijving toevoegen die de gebruiker in de content van de campagne kan zien.

   Om het gemakkelijker te maken om workflows te vinden en problemen op te lossen als ze niet naar behoren functioneren, wordt u aangeraden om uw workflows duidelijke namen en labels te geven. Vul het beschrijvingsveld van de workflow in om het uit te voeren proces samen te vatten, zodat de operator het gemakkelijk kan begrijpen.

1. Bevestig het maken van de activiteit. Het dashboard voor die activiteit wordt dan weergegeven. Raadpleeg de sectie [Workflowinterface](../../automating/using/workflow-interface.md) voor meer informatie.

1. Zodra de workflow klaar is om te worden geconfigureerd, kunt u toegang krijgen tot extra opties door op de knop **[!UICONTROL Edit properties]** te klikken. U kunt bijvoorbeeld een specifieke tijdzone definiëren die standaard in alle activiteiten van de workflow moet worden gebruikt. Standaard is de tijdzone van de workflow de tijdzone die is gedefinieerd voor de huidige Campaign-operator.

   ![](assets/workflow_properties.png)

**Verwant onderwerp:**

* Video [Een workflow maken](https://docs.adobe.com/content/help/en/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html)
* [Workfloweigenschappen](../../automating/using/managing-execution-options.md)

## Activiteiten toevoegen en koppelen {#adding-and-linking-activities}

U moet nu de verschillende activiteiten definiëren en deze koppelen in het diagram.

>[!NOTE]
>
>Als het palet niet wordt weergegeven, klikt u op de eerste knop van de werkbalk om het weer te geven.

De activiteiten zijn per categorie gegroepeerd in de verschillende secties van het palet.

* De eerste sectie bevat [targetingactiviteiten](../../automating/using/about-targeting-activities.md)
* De tweede sectie bevat de [uitvoeringsactiviteiten](../../automating/using/about-execution-activities.md), die hoofdzakelijk worden gebruikt voor de coördinatie van andere activiteiten.
* De derde sectie bevat activiteiten die kunnen worden gebruikt om berichten via verschillende [kanalen](../../automating/using/about-channel-activities.md) te verzenden. De activiteiten in deze sectie kunnen variëren, afhankelijk van de kanalen die op uw instantie zijn ingeschakeld.
* De vierde sectie bevat [activiteiten op het gebied van bestandsmanipulatie en databeheer](../../automating/using/about-data-management-activities.md).

Het diagram maken:

1. Voeg een activiteit toe door het uit het palet te slepen en het neer te zetten in het diagram.

   Voeg bijvoorbeeld een activiteit **[Start](../../automating/using/start-and-end.md)** en vervolgens een activiteit **[E-maillevering](../../automating/using/email-delivery.md)** toe aan het diagram.

1. Koppel de activiteiten door de activiteitovergang **Start** te slepen en neer te zetten op de activiteit **E-maillevering**.

   >[!NOTE]
   >
   >U kunt een activiteit automatisch aan de vorige koppelen door de nieuwe activiteit aan het einde van de overgang van de vorige activiteit te plaatsen.

1. Voeg de benodigde activiteiten toe en koppel deze aan elkaar om uw workflow te voltooien.

   >[!NOTE]
   >
   >U kunt bestaande activiteiten ook dupliceren door deze te kopiëren en te plakken. Op deze manier behoudt u de instellingen die oorspronkelijk zijn gedefinieerd. Raadpleeg [Workflowactiviteiten dupliceren](../../automating/using/workflow-interface.md#duplicating-workflow-activities) voor meer informatie hierover.

Als uw workflowactiviteiten aan elkaar zijn gekoppeld, kunt u de overgangen tussen de activiteiten aanpassen met het **label** van uw keuze. Dubbelklik hiertoe op de overgang om de eigenschappen ervan te openen.

Bovendien is het voor de activiteiten **[!UICONTROL Targeting]** en **[!UICONTROL Data management (ETL)]** mogelijk om **segmentcodes** te definiëren voor hun uitgaande overgangen. Vervolgens kunt u rapporten maken op basis van deze segmentcodes om de efficiëntie van uw marketingcampagnes te meten. Raadpleeg [deze sectie](../../reporting/using/creating-a-report-workflow-segment.md) voor meer informatie.

**Gebruiksscenario&#39;s voor workflows:**

* [Gebruiksscenario: Eenmaal per week een e-maillevering maken](../../automating/using/workflow-weekly-offer.md)
* [Gebruiksscenario: Een levering maken die is gesegmenteerd op locatie](../../automating/using/workflow-segmentation-location.md)
* [Gebruiksscenario: Leveringen maken met een aanvulling](../../automating/using/workflow-created-query-with-complement.md)
* [Gebruiksscenario: Retargeting van een workflow om een nieuwe levering te zenden naar personen die het bericht niet hebben geopend](../../automating/using/workflow-cross-channel-retargeting.md)

## Activiteiten configureren {#configuring-activities}

Standaard zijn de activiteiten niet ingesteld en worden de data niet correct verwerkt als ze niet zijn geconfigureerd. Elke activiteit bevat verschillende tabbladen om specifieke configuraties en generieke opties voor activiteiten te beheren, zoals uitgaande overgangen, labels, enz.

1. Controleer of alle activiteiten correct zijn gekoppeld. Voor sommige activiteiten moet de structuur of aard van de binnenkomende data worden gedetecteerd om de correcte configuratie-opties aan te bieden.
1. Dubbelklik op een activiteit of selecteer deze en klik op de **[!UICONTROL Edit]** contextafhankelijke actie om het configuratievenster te openen.
1. Bewerk het label van de activiteit.
1. Definieer alle verschillende opties die u nodig hebt om de data te verwerken. Raadpleeg de specifieke sectie over de activiteit in deze documentatie voor meer informatie over de mogelijke opties voor elke activiteit.
1. Sla de activiteit op en herhaal deze bewerkingen voor elke activiteit van de workflow.
1. Sla de workflow op.
