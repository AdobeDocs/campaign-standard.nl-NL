---
solution: Campaign Standard
product: campaign
title: Informatie over workflowuitvoering
description: Meer weten over het uitvoeren van workflows?
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 8%

---


# Informatie over workflowuitvoering {#about-workflow-execution}

Een workflow wordt altijd handmatig gestart. Nochtans, zodra begonnen, kan het inactief blijven, afhankelijk van de informatie die in een [Planner](../../automating/using/scheduler.md) activiteit wordt gespecificeerd.

>[!CAUTION]
>
> Adobe raadt klanten aan prioriteit te geven aan workflowuitvoering en maximaal 20 gelijktijdige workflowuitvoering uit te voeren om consistent maximale prestaties te behalen voor uw hele exemplaar. Er kunnen meer dan twintig gelijktijdige workflowuitvoeringen worden gepland en deze worden standaard opeenvolgend uitgevoerd. U kunt de standaardinstellingen voor het maximale aantal gelijktijdige workflowuitvoering aanpassen door een ticket naar de klantenservice in te dienen.

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

Standaard zijn alleen de details van de laatste overgang van de workflow toegankelijk. Als u toegang wilt tot de resultaten van de voorgaande activiteiten, moet u de optie **[!UICONTROL Keep interim results]** in de sectie **[!UICONTROL Execution]** van de workfloweigenschappen controleren voordat u de workflow start.

>[!NOTE]
>
>Deze optie verbruikt veel geheugen en is ontworpen om een workflow te helpen construeren en ervoor te zorgen dat deze correct is geconfigureerd en gedraagt. Laat deze optie uitgeschakeld op productie-instanties.

Wanneer een overgang open is, kunt u zijn **[!UICONTROL Label]** uitgeven of **[!UICONTROL Segment code]** aan het verbinden. Hiervoor bewerkt u de desbetreffende velden en bevestigt u uw wijzigingen.

Met Campaign Standard REST API&#39;s kunt u **start**, **pause**, **resume** en **stop** een workflow gebruiken. Meer details en voorbeelden van REST-aanroepen vindt u in de [API-documentatie.](../../api/using/controlling-a-workflow.md)
