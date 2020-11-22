---
solution: Campaign Standard
product: campaign
title: Best practices voor workflows
description: Ontdek hoe u best practices kunt toepassen op uw workflows.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '1071'
ht-degree: 93%

---


# Best practices voor workflows{#workflow-best-practices}

Met Adobe Campaign kunt u allerlei workflows instellen om een breed scala aan taken uit te voeren. Bij het ontwerpen en uitvoeren van uw workflows moet u echter zeer voorzichtig zijn, omdat een slechte implementatie kan leiden tot slechte prestaties, fouten en platformproblemen. Hieronder vindt u een lijst met best practices en tips voor het oplossen van problemen.

>[!NOTE]
>
>Workflowontwerp en -uitvoering moeten worden uitgevoerd door een gevorderde gebruiker van Adobe Campaign.

## Naamgeving{#naming}

Adobe raadt u aan uw workflows expliciet een naam en een label te geven om het oplossen van problemen met workflows te vereenvoudigen. Vul het beschrijvingsveld van de workflow in om een overzicht te geven van het proces dat moet worden uitgevoerd zodat de operator het gemakkelijk kan begrijpen.
Als de workflow deel uitmaakt van een proces waarbij meerdere workflows zijn betrokken, kunt u nummers gebruiken wanneer u een label invoert om deze duidelijk te ordenen.

Bijvoorbeeld:

* 001 - Import - Ontvangers importeren
* 002 - Import - Verkoop importeren
* 003 - Import - Verkoopdetails importeren
* 010 - Export - Leveringslogboeken exporteren
* 011 - Export - Traceringslogboeken exporteren

## Workflows dupliceren{#duplicating-workflows}

U kunt workflows dupliceren. Houd in de **[!UICONTROL Marketing Activities]** de muisaanwijzer boven de workflow en klik op **[!UICONTROL Duplicate element]**. Als de workflow eenmaal is gedupliceerd, worden wijzigingen van de workflow niet overgebracht naar de kopie van de workflow. De kopie van de workflow kan worden bewerkt.

![](assets/duplicating_workflow.png)

## Uitvoering{#execution}

### Aantal workflows

Standaard raden we u aan niet meer dan 20 actieve workflows tegelijk uit te voeren. Nadat deze limiet is bereikt, worden workflows in de wachtrij geplaatst om de prestaties niet te beïnvloeden. Op dezelfde manier raadt Adobe u aan uw workflowuitvoering in de tijd te spreiden.
Het is mogelijk dat u onder specifieke omstandigheden meer dan 20 workflows moet uitvoeren. Dit is niet van toepassing op workflows die wachten op een geplande uitvoering. Als dit het geval is, moet u de gebruiksscenario’s controleren met een Campaign-expert en contact opnemen met de klantenservice van Adobe om de limiet te verhogen.

### Frequentie

Een workflow kan niet vaker dan eenmaal om de tien minuten automatisch worden uitgevoerd.
De herhalingsfrequentie van de activiteit mag niet minder dan 10 minuten zijn. Als de herhalingsfrequentie is ingesteld op 0 (dit is de standaardwaarde), wordt met deze optie geen rekening gehouden en wordt de workflow uitgevoerd volgens de uitvoeringsfrequentie.

### Gepauzeerde workflows

Workflows die langer dan 7 dagen gepauzeerd of mislukt zijn, worden gestopt om minder schijfruimte te verbruiken. De opschoningstaak wordt weergegeven in de workflowlogboeken.

### Overgangen

Een workflow met niet-beëindigde overgangen kan nog steeds worden uitgevoerd: er wordt een waarschuwingsbericht gegenereerd en de workflow wordt gepauzeerd zodra de overgang is bereikt, maar er wordt geen fout gegenereerd. U kunt ook een workflow starten zonder een voltooid ontwerp en dit gaandeweg voltooien.

Raadpleeg [Workflows uitvoeren](../../automating/using/about-workflow-execution.md) voor meer informatie.

### Tijdzone

Met de workfloweigenschappen kunt u een specifieke tijdzone definiëren die standaard wordt gebruikt voor alle activiteiten. Standaard is de tijdzone van de workflow de tijdzone die is gedefinieerd voor de huidige Campaign-operator.

## Activiteit{#activity}

### Aantal activiteiten per workflow {#number-activities}

We raden u aan maximaal 100 activiteiten in één workflow te gebruiken. Bij meer dan 100 activiteiten kunnen er prestatieproblemen optreden bij het ontwerpen en configureren van uw workflow.

### Workflowontwerp

Om ervoor te zorgen dat de workflow op de juiste wijze wordt beëindigd, moet u de laatste overgang van een workflow op zichzelf vermijden door een **[!UICONTROL End activity]** workflow te gebruiken.

Als u toegang wilt tot de gedetailleerde weergave van de overgangen, schakelt u de optie **[!UICONTROL Keep interim results]** in de sectie Execution van de workfloweigenschappen in.

>[!CAUTION]
>
>Deze optie verbruikt veel schijfruimte en is ontworpen om u te helpen een workflow te maken en een correcte configuratie en functionaliteit te garanderen. Laat deze optie uitgeschakeld op productie-instanties.

![](assets/keep_interim_best_practices.png)


### Labelactiviteiten{#activity-labeling}

Tijdens het ontwikkelen van uw workflow wordt een naam gegenereerd voor elke activiteit, zoals voor alle Adobe Campaign-objecten. Terwijl de naam van een activiteit door de tool wordt geproduceerd en niet kan worden bewerkt, raden wij aan om de activiteit te labelen met een expliciete naam wanneer u deze configureert.

### Dupliceren van activiteiten{#activity-duplicating}

U kunt kopiëren en plakken gebruiken om bestaande activiteiten te dupliceren. Op deze manier behoudt u de instellingen die oorspronkelijk zijn gedefinieerd. Raadpleeg [Workflowactiviteiten dupliceren](../../automating/using/workflow-interface.md) voor meer informatie.

### Activiteit Planner{#acheduler-activity}

Bij het samenstellen van uw workflow gebruikt u slechts één **[!UICONTROL Scheduler activity]** per vertakking. Als dezelfde vertakking van een workflow meerdere planners heeft (die met elkaar gekoppeld zijn), zal het aantal uit te voeren taken exponentieel worden vermenigvuldigd, waardoor de database aanzienlijk overbelast zou worden.

U kunt een voorbeeld bekijken van de volgende tien uitvoeringen van uw workflows door op **[!UICONTROL Preview next executions]** te klikken.

![](assets/preview_scheduler.png)

Raadpleeg de [activiteit Planner](../../automating/using/scheduler.md) voor meer informatie.

## Een workflow met parameters aanroepen{#workflow-with-parameters}

Zorg ervoor dat de naam en het aantal parameters gelijk zijn aan wat er is gedefinieerd bij het aanroepen van de workflow (zie [deze pagina](../../automating/using/defining-parameters-calling-workflow.md). De parametertypen moeten ook consistent zijn met de waarden die worden verwacht.

Zorg ervoor dat alle parameters zijn gedeclareerd in de **[!UICONTROL External signal activity]**. Anders treedt er een fout op wanneer de activiteit wordt uitgevoerd.

Zie [Een workflow met externe parameters aanroepen](../../automating/using/calling-a-workflow-with-external-parameters.md) voor meer informatie.

## Pakketten exporteren{#exporting-packages}

Als u pakketten wilt exporteren, mogen de resources die worden geëxporteerd, geen standaard-id’s bevatten. Daarom moeten de id’s van resources die kunnen worden geëxporteerd, worden gewijzigd door een andere naam te gebruiken dan de sjablonen die standaard worden geleverd door Adobe Campaign Standard.
Zie [Pakketten beheren](../../automating/using/managing-packages.md) voor meer informatie.

## Lijsten exporteren{#exporting-lists}

Met de optie voor het exporteren van lijsten kunt u standaard maximaal 100.000 regels exporteren, gedefinieerd door de optie **Nms_ExportListLimit**. Deze optie kan door de functionele beheerder worden beheerd onder **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]**.
Zie [Lijsten exporteren](../../automating/using/exporting-lists.md) voor meer informatie.

## Problemen oplossen{#workflow-troubleshooting}

Adobe Campaign biedt verschillende logboeken om meer inzicht te krijgen in problemen met workflows.

### Workflowlogboeken gebruiken{#using-workflow-logs}

U kunt workflowlogboeken openen om de uitvoering van uw activiteiten te controleren. De uitgevoerde bewerkingen en uitvoeringsfouten worden in chronologische volgorde geïndexeerd. Het tabblad Logs bestaat uit de geschiedenis van de uitvoering van alle of enkele geselecteerde activiteiten.
Op het tabblad Tasks wordt de volgorde van uitvoering van de activiteiten weergegeven. Klik op een taak voor meer informatie over een activiteit.
Raadpleeg [De uitvoering van workflows controleren](../../automating/using/monitoring-workflow-execution.md) voor meer informatie.

#### Problemen met databeheeractiviteiten oplossen{#troubleshooting-data-management-activities}

U kunt SQL-query’s analyseren op het tabblad Log.

1. Klik in de werkruimte van de workflow op **[!UICONTROL Edit properties]**.
1. Schakel in **[!UICONTROL General]** > **[!UICONTROL Execution]** de opties **[!UICONTROL Save SQL queries in the log]** en **[!UICONTROL Execute in the engine]** in en klik op **[!UICONTROL Confirm]**.

**Voer de volgende stappen uit om SQL-query’s weer te geven in Log:**
1. Klik op **[!UICONTROL Log and Tasks]**.
1. Open op het tabblad **[!UICONTROL Logs]** het deelvenster **[!UICONTROL Search]**.
1. Schakel **[!UICONTROL Display SQL logs only]** in.

De query wordt weergegeven in de kolom **[!UICONTROL Message]** van de logboeken.

### Leveringslogboeken gebruiken{#using-delivery-logs}

Met leveringslogboeken kunt u het succes van uw leveringen controleren. Uitsluitingslogboeken retourneren uitsluitingsberichten tijdens de voorbereiding van de verzending. Verzendingslogboeken geven de status van de levering voor elk profiel weer.
Raadpleeg [Leveringsfouten begrijpen](../../sending/using/understanding-delivery-failures.md) voor meer informatie.

### Leveringswaarschuwingen gebruiken{#delivery-alerting}

De functie voor leveringswaarschuwingen is een systeem voor waarschuwingsbeheer waardoor een groep gebruikers automatisch meldingen kan ontvangen die informatie bevatten over de uitvoering van hun leveringen.
Raadpleeg [Leveringswaarschuwingen](../../sending/using/receiving-alerts-when-failures-happen.md) voor meer informatie.

**Verwante onderwerpen:**

* [Foutbeheer](../../automating/using/monitoring-workflow-execution.md)
