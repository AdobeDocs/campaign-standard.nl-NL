---
title: Informatie over workflowuitvoering
description: Meer weten over het uitvoeren van workflows?
page-status-flag: never-activated
uuid: ff02b74e-53e8-49c6-bf8e-0c729eaa7d25
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: 906c85ea-83b7-4268-86da-cd353f1dc591
context-tags: workflow,overview;workflow,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '374'
ht-degree: 8%

---


# Informatie over workflowuitvoering {#about-workflow-execution}

Een workflow wordt altijd handmatig gestart. Nochtans, zodra begonnen, kan het inactief blijven, afhankelijk van de informatie die in een activiteit van de [Planner](../../automating/using/scheduler.md) wordt gespecificeerd.

>[!CAUTION]
>
> Adobe raadt klanten aan prioriteit te geven aan workflowuitvoering en maximaal 20 gelijktijdige workflowuitvoering uit te voeren om consistent maximale prestaties te behalen voor de hele instantie. Er kunnen meer dan twintig gelijktijdige workflowuitvoeringen worden gepland en deze worden standaard opeenvolgend uitgevoerd. U kunt de standaardinstellingen voor het maximale aantal gelijktijdige workflowuitvoering aanpassen door een ticket naar de klantenservice in te dienen.

Aan uitvoering gerelateerde handelingen (starten, stoppen, pauzeren, enz.) zijn **asynchrone** processen: de opdracht wordt opgeslagen en wordt van kracht zodra de server beschikbaar is om deze toe te passen.

In een werkstroom wordt het resultaat van elke activiteit over het algemeen verzonden naar de volgende activiteit via een overgang, die door een pijl wordt vertegenwoordigd.

Een overgang is niet beëindigd als deze niet aan een doelactiviteit is gekoppeld.

![](assets/wkf_execution_1.png)

>[!NOTE]
>
>Een workflow met niet-afgesloten overgangen kan nog steeds worden uitgevoerd: er wordt een waarschuwingsbericht gegenereerd en de workflow wordt gepauzeerd zodra de overgang is bereikt , maar dit leidt niet tot een fout . U kunt ook een workflow starten zonder het ontwerp volledig af te ronden en u kunt het tijdens de stappen voltooien.

Nadat een activiteit is uitgevoerd, wordt boven de overgang het aantal records weergegeven dat in de overgang is verzonden.

![](assets/wkf_transition_count.png)

U kunt overgangen openen om te controleren of de verzonden data correct zijn tijdens of na het uitvoeren van de workflow. U kunt de gegevens en de gegevensstructuur weergeven.

Standaard zijn alleen de details van de laatste overgang van de workflow toegankelijk. Als u toegang wilt tot de resultaten van de voorgaande activiteiten, moet u de **[!UICONTROL Keep interim results]** optie in het **[!UICONTROL Execution]** gedeelte van de workfloweigenschappen controleren voordat u de workflow start.

>[!NOTE]
>
>Deze optie verbruikt veel geheugen en is ontworpen om een workflow te helpen construeren en ervoor te zorgen dat deze correct is geconfigureerd en gedraagt. Laat deze optie uitgeschakeld op productie-instanties.

Wanneer een overgang is geopend, kunt u de overgang bewerken **[!UICONTROL Label]** of er een koppeling **[!UICONTROL Segment code]** aan maken. Hiervoor bewerkt u de desbetreffende velden en bevestigt u uw wijzigingen.

Met Campaign Standard REST API&#39;s kunt u een workflow **starten**, **pauzeren**, **hervatten** en **stoppen** . Meer details en voorbeelden van REST-aanroepen vindt u in de [API-documentatie.](../../api/using/controlling-a-workflow.md)
