---
solution: Campaign Standard
product: campaign
title: Overzicht
description: In deze sectie wordt beschreven hoe u een workflow met externe parameters kunt aanroepen.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
translation-type: tm+mt
source-git-commit: 05b6a9caebdd65f20357070af8bd44cb8ba146c7
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 4%

---


# Overzicht {#calling-a-workflow-with-external-parameters}

Met Campaign Standard kunt u een workflow aanroepen met parameters (een doelnaam, een bestandsnaam die u wilt importeren, een deel van de berichtinhoud, enzovoort). Op deze manier kunt u uw campagneautomatisering eenvoudig integreren met uw externe systeem.

Neem het volgende voorbeeld, waar wij e-mails rechtstreeks van CMS willen verzenden. In dat geval kunt u uw systeem zo configureren dat het publiek en de e-mailinhoud in het CMS worden geselecteerd. Als u op Verzenden klikt, wordt een Campagneworkflow met deze parameters aangeroepen, zodat u deze in de workflow kunt gebruiken om het publiek en de URL-inhoud voor de levering te definiëren.

Het proces om een werkschema met parameters te roepen is het volgende:

1. Declareer de parameters in **[!UICONTROL External signal]** activiteit. Zie [De parameters in de Externe signaalactiviteit declareren](../../automating/using/declaring-parameters-external-signal.md).
1. Configureer de **[!UICONTROL End]**-activiteit of de API-aanroep om de parameters te definiëren en de workflow **[!UICONTROL External signal]**-activiteit te activeren. Zie [deze pagina](../../automating/using/defining-parameters-calling-workflow.md)
1. Nadat de workflow is geactiveerd, worden de parameters opgenomen in de gebeurtenisvariabelen van de workflow en kunnen deze binnen de workflow worden gebruikt. Zie [deze pagina](../../automating/using/customizing-workflow-external-parameters.md).

![](assets/extsignal_process.png)
