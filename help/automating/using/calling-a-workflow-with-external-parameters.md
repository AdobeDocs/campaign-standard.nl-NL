---
title: Overzicht
description: In deze sectie wordt beschreven hoe u een workflow met externe parameters kunt aanroepen.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 538056e6-b5c0-4258-a34b-524fe6e3cbbe
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 2%

---

# Overzicht {#calling-a-workflow-with-external-parameters}

Met Campaign Standard kunt u een workflow aanroepen met parameters (een doelnaam, een te importeren bestandsnaam, een deel van de berichtinhoud, enzovoort). Op deze manier kunt u uw campagneautomatisering eenvoudig integreren met uw externe systeem.

Neem het volgende voorbeeld, waar wij e-mails rechtstreeks van een CMS willen verzenden. In dat geval kunt u uw systeem zo configureren dat het publiek en de e-mailinhoud in de CMS worden geselecteerd. Als u op Verzenden klikt, wordt een Campagneworkflow met deze parameters aangeroepen, zodat u deze in de workflow kunt gebruiken om het publiek en de URL-inhoud voor de levering te definiëren.

Het proces om een werkschema met parameters te roepen is het volgende:

1. Declareer de parameters in de **[!UICONTROL External signal]** activiteit. Zie [ Verklarend de parameters in de Externe signaalactiviteit ](../../automating/using/declaring-parameters-external-signal.md).
1. Configureer de **[!UICONTROL End]** -activiteit of de API-aanroep om de parameters te definiëren en de **[!UICONTROL External signal]** -activiteit van de workflow te activeren. Zie [ deze pagina ](../../automating/using/defining-parameters-calling-workflow.md)
1. Nadat de workflow is geactiveerd, worden de parameters opgenomen in de gebeurtenisvariabelen van de workflow en kunnen deze binnen de workflow worden gebruikt. Zie [deze pagina](../../automating/using/customizing-workflow-external-parameters.md).

![](assets/extsignal_process.png)
