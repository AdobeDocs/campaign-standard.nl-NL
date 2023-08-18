---
title: Informatie over workflowuitvoering
description: Meer weten over het uitvoeren van workflows?
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 3b95fc66-d6f4-44b2-be33-925c1109a57f
source-git-commit: 6ca3ffe3ba2cf7629e511e4ba035b170b25ad79e
workflow-type: tm+mt
source-wordcount: '353'
ht-degree: 8%

---

# Informatie over workflowuitvoering {#about-workflow-execution}

Een workflow wordt altijd handmatig gestart. Als de toepassing echter eenmaal is gestart, kan deze inactief blijven, afhankelijk van de informatie die in een [Planner](../../automating/using/scheduler.md) activiteit.

>[!IMPORTANT]
>
> Adobe raadt klanten aan niet meer dan 20 actieve workflows tegelijk uit te voeren en de uitvoering van de workflow in de loop der tijd te prioriteren en te verspreiden. Raadpleeg voor meer informatie de beste praktijken in [deze pagina](../../automating/using/best-practices-workflows.md).

Aan uitvoering gerelateerde handelingen (starten, stoppen, pauzeren, enz.) zijn **asynchroon** processen: de opdracht wordt opgeslagen en wordt van kracht zodra de server beschikbaar is om deze toe te passen.

In een werkstroom wordt het resultaat van elke activiteit over het algemeen verzonden naar de volgende activiteit via een overgang, die door een pijl wordt vertegenwoordigd.

Een overgang is niet beëindigd als deze niet aan een doelactiviteit is gekoppeld.

![](assets/wkf_execution_1.png)

>[!NOTE]
>
>Er kan nog steeds een workflow met niet-afgesloten overgangen worden uitgevoerd: er wordt een waarschuwingsbericht gegenereerd en de workflow wordt gepauzeerd zodra de overgang is bereikt, maar dit leidt niet tot een fout. U kunt ook een workflow starten zonder het ontwerp volledig af te ronden en u kunt het tijdens de stappen voltooien.

Nadat een activiteit is uitgevoerd, wordt boven de overgang het aantal records weergegeven dat in de overgang is verzonden.

![](assets/wkf_transition_count.png)

U kunt overgangen openen om te controleren of de verzonden data correct zijn tijdens of na het uitvoeren van de workflow. U kunt de gegevens en de gegevensstructuur weergeven.

Standaard zijn alleen de details van de laatste overgang van de workflow toegankelijk. Als u toegang wilt tot de resultaten van de voorgaande activiteiten, moet u de **[!UICONTROL Keep interim results]** in de **[!UICONTROL Execution]** van de workfloweigenschappen, voordat de workflow wordt gestart.

>[!NOTE]
>
>Deze optie verbruikt veel geheugen en is ontworpen om een workflow te helpen construeren en ervoor te zorgen dat deze correct is geconfigureerd en gedraagt. Laat deze optie uitgeschakeld op productie-instanties.

Wanneer een overgang is geopend, kunt u de overgang bewerken **[!UICONTROL Label]** of een koppeling maken **[!UICONTROL Segment code]** aan de Commissie. Hiervoor bewerkt u de desbetreffende velden en bevestigt u uw wijzigingen.

Met Campaign Standard REST API&#39;s kunt u **start**, **pauzeren**, **resume** en **stoppen** een workflow. U kunt meer details en voorbeelden van de vraag van REST in vinden [API-documentatie.](../../api/using/controlling-a-workflow.md)
