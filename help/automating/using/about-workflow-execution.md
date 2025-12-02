---
title: Informatie over workflowuitvoering
description: Meer weten over het uitvoeren van workflows?
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 3b95fc66-d6f4-44b2-be33-925c1109a57f
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 8%

---

# Informatie over workflowuitvoering {#about-workflow-execution}

Een workflow wordt altijd handmatig gestart. Nochtans, zodra begonnen, kan het inactief blijven, afhankelijk van de informatie die in a [ wordt gespecificeerd planner ](../../automating/using/scheduler.md) activiteit.

>[!IMPORTANT]
>
> Adobe raadt klanten aan om niet meer dan 20 actieve workflows tegelijk uit te voeren en om prioriteiten te stellen voor de uitvoering van de workflow en deze in de loop der tijd te verspreiden. Voor meer op dit, verwijs naar de beste praktijken die in [ worden verstrekt deze pagina ](../../automating/using/best-practices-workflows.md).

De uitvoering verwante acties (begin, einde, pauze, enz.) zijn **asynchrone** processen: het bevel wordt bewaard en zal van kracht worden zodra de server beschikbaar is om het toe te passen.

In een werkstroom wordt het resultaat van elke activiteit over het algemeen verzonden naar de volgende activiteit via een overgang, die door een pijl wordt vertegenwoordigd.

Een overgang is niet beëindigd als deze niet aan een doelactiviteit is gekoppeld.

![](assets/wkf_execution_1.png)

>[!NOTE]
>
>Er kan nog steeds een workflow met niet-afgesloten overgangen worden uitgevoerd: er wordt een waarschuwingsbericht gegenereerd en de workflow wordt gepauzeerd zodra de overgang is bereikt, maar dit leidt niet tot een fout. U kunt ook een workflow starten zonder het ontwerp volledig af te ronden en u kunt het tijdens de stappen voltooien.

Nadat een activiteit is uitgevoerd, wordt boven de overgang het aantal records weergegeven dat in de overgang is verzonden.

![](assets/wkf_transition_count.png)

U kunt overgangen openen om te controleren of de verzonden data correct zijn tijdens of na het uitvoeren van de workflow. U kunt de gegevens en de gegevensstructuur weergeven.

Standaard zijn alleen de details van de laatste overgang van de workflow toegankelijk. Als u toegang wilt tot de resultaten van de voorgaande activiteiten, moet u de optie **[!UICONTROL Keep interim results]** in het gedeelte **[!UICONTROL Execution]** van de workfloweigenschappen controleren voordat u de workflow start.

>[!NOTE]
>
>Deze optie verbruikt veel geheugen en is ontworpen om een workflow te helpen construeren en ervoor te zorgen dat deze correct is geconfigureerd en gedraagt. Laat deze optie uitgeschakeld op productie-instanties.

Wanneer een overgang is geopend, kunt u de **[!UICONTROL Label]** ervan bewerken of een **[!UICONTROL Segment code]** eraan koppelen. Hiervoor bewerkt u de desbetreffende velden en bevestigt u uw wijzigingen.

Gebruikend Campaign Standard REST APIs, kunt u **beginnen,** pauzeren **,** hervatten **en** ophouden **een werkschema.** U kunt meer details en voorbeelden van de vraag van REST in de [ API documentatie vinden.](../../api/using/controlling-a-workflow.md)
