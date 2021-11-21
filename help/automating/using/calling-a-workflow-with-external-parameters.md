---
title: Overzicht
description: In deze sectie wordt beschreven hoe u een workflow met externe parameters kunt aanroepen.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 538056e6-b5c0-4258-a34b-524fe6e3cbbe
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 4%

---

# Overzicht {#calling-a-workflow-with-external-parameters}

Met Campaign Standard kunt u een workflow aanroepen met parameters (een doelnaam, een bestandsnaam die u wilt importeren, een deel van de berichtinhoud, enzovoort). Op deze manier kunt u uw campagneautomatisering eenvoudig integreren met uw externe systeem.

Neem het volgende voorbeeld, waar wij e-mails rechtstreeks van CMS willen verzenden. In dat geval kunt u uw systeem zo configureren dat het publiek en de e-mailinhoud in het CMS worden geselecteerd. Als u op Verzenden klikt, wordt een Campagneworkflow met deze parameters aangeroepen, zodat u deze in de workflow kunt gebruiken om het publiek en de URL-inhoud voor de levering te definiëren.

Het proces om een werkschema met parameters te roepen is het volgende:

1. Declareer de parameters in de **[!UICONTROL External signal]** activiteit. Zie [De parameters in de externe signaalactiviteit declareren](../../automating/using/declaring-parameters-external-signal.md).
1. Configureer de **[!UICONTROL End]** activiteit of de API-aanroep om de parameters te definiëren en de workflow te activeren **[!UICONTROL External signal]** activiteit. Zie [deze pagina](../../automating/using/defining-parameters-calling-workflow.md)
1. Nadat de workflow is geactiveerd, worden de parameters opgenomen in de gebeurtenisvariabelen van de workflow en kunnen deze binnen de workflow worden gebruikt. Zie [deze pagina](../../automating/using/customizing-workflow-external-parameters.md).

![](assets/extsignal_process.png)
