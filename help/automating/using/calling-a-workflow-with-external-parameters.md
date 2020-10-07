---
title: Overzicht
description: In deze sectie wordt beschreven hoe een workflow met externe parameters wordt aangeroepen.
page-status-flag: never-activated
uuid: beccd1b6-8e6d-4504-9152-9ff537459c4a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: 1676da91-55e3-414f-bcd3-bb0804b682bd
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 2%

---


# Overzicht {#calling-a-workflow-with-external-parameters}

Met Campaign Standard kunt u een workflow aanroepen met parameters (een doelnaam, een bestandsnaam die u wilt importeren, een deel van de berichtinhoud, enzovoort). Op deze manier kunt u uw campagneautomatisering eenvoudig integreren met uw externe systeem.

Neem het volgende voorbeeld, waar wij e-mails rechtstreeks van CMS willen verzenden. In dat geval kunt u uw systeem zo configureren dat het publiek en de e-mailinhoud in het CMS worden geselecteerd. Als u op Verzenden klikt, wordt een Campagneworkflow met deze parameters aangeroepen, zodat u deze in de workflow kunt gebruiken om het publiek en de URL-inhoud voor de levering te definiëren.

Het proces om een werkschema met parameters te roepen is het volgende:

1. Declareer de parameters in de **[!UICONTROL External signal]** activiteit. See [Declaring the parameters in the External signal activity](../../automating/using/declaring-parameters-external-signal.md).
1. Configureer de **[!UICONTROL End]** activiteit of de API-aanroep om de parameters te definiëren en de **[!UICONTROL External signal]** workflowactiviteit te activeren. Zie [](../../automating/using/defining-parameters-calling-workflow.md)
1. Nadat de workflow is geactiveerd, worden de parameters opgenomen in de gebeurtenisvariabelen van de workflow en kunnen deze binnen de workflow worden gebruikt. Zie [](../../automating/using/customizing-workflow-external-parameters.md).

![](assets/extsignal_process.png)
