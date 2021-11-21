---
title: Een workflow oproepen met externe parameters
description: In deze sectie wordt beschreven hoe u een workflow met externe parameters kunt aanroepen.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: e6148b40-f608-4aab-81f6-756608c6828e
source-git-commit: 13d419c5fc51845ee14f8a3b288f4c467e0a60d9
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 5%

---

# De parameters in de externe signaalactiviteit declareren {#declaring-the-parameters-in-the-external-signal-activity}

De eerste stap om een werkschema met parameters te roepen is hen in te verklaren **[!UICONTROL External signal]** activiteit.

1. Open de **[!UICONTROL External signal]** activiteit, dan selecteer **[!UICONTROL Parameters]** tab.
1. Klik op de knop **[!UICONTROL Create element]** en geeft u vervolgens de naam en het type van elke parameter op.

   >[!CAUTION]
   >
   >Zorg ervoor dat de naam en het aantal parameters gelijk zijn aan wat er is gedefinieerd bij het aanroepen van de workflow (zie [deze pagina](../../automating/using/defining-parameters-calling-workflow.md)). Bovendien moeten de parametertypen consistent zijn met de waarden die worden verwacht.

   ![](assets/extsignal_declaringparameters_1.png)

1. Zodra de parameters zijn verklaard, voltooi de werkschemaconfiguratie, dan stel het in werking.
