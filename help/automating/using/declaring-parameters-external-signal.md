---
solution: Campaign Standard
product: campaign
title: Een workflow aanroepen met externe parameters
description: In deze sectie wordt beschreven hoe een workflow met externe parameters wordt aangeroepen.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 5%

---


# De parameters in de externe signaalactiviteit {#declaring-the-parameters-in-the-external-signal-activity} declareren

De eerste stap om een werkschema met parameters te roepen is hen in een **[!UICONTROL External signal]** activiteit te verklaren.

1. Open de **[!UICONTROL External signal]** activiteit, dan selecteer **[!UICONTROL Parameters]** tabel.
1. Klik op de knop **[!UICONTROL Create element]** en geef vervolgens de naam en het type van elke parameter op.

   >[!CAUTION]
   >
   >Zorg ervoor dat de naam en het aantal parameters identiek zijn aan wat wordt bepaald wanneer het roepen van het werkschema (zie [deze pagina](../../automating/using/defining-parameters-calling-workflow.md)). Bovendien moeten de parametertypen consistent zijn met de waarden die worden verwacht.

   ![](assets/extsignal_declaringparameters_1.png)

1. Zodra de parameters zijn verklaard, voltooi de werkschemaconfiguratie, dan stel het in werking.
