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
source-wordcount: '188'
ht-degree: 13%

---


# Parameters definiëren bij het aanroepen van de workflow {#defining-the-parameters-when-calling-the-workflow}

In deze sectie wordt beschreven hoe u parameters definieert wanneer u een workflow oproept. Raadpleeg de documentatie [van de](../../api/using/triggering-a-signal-activity.md)REST API&#39;s voor meer informatie over het uitvoeren van deze bewerking vanuit een API-aanroep.

Voordat u de parameters definieert, moet u ervoor zorgen dat:

* De parameters zijn gedeclareerd in de **[!UICONTROL External Signal]** activiteit. Zie [deze pagina](../../automating/using/declaring-parameters-external-signal.md).
* De workflow met de signaalactiviteit wordt uitgevoerd.

Volg onderstaande stappen om de **[!UICONTROL End]** activiteit te configureren:

1. Open the **[!UICONTROL End]** activity, then select the **[!UICONTROL External signal]** tab.
1. Selecteer het werkschema en de externe signaalactiviteit die u wilt roepen.
1. Klik op de **[!UICONTROL Create element]** knop om een parameter toe te voegen en vul vervolgens de naam en waarde van de parameter in.

   * **[!UICONTROL Name]**: de naam die is gedeclareerd in de **[!UICONTROL External signal]** activiteit (zie [deze pagina](../../automating/using/declaring-parameters-external-signal.md)).
   * **[!UICONTROL Value]**: de waarde die u aan de parameter wilt toewijzen. De waarde moet de **standaardsyntaxis** volgen, die in [deze sectie](../../automating/using/advanced-expression-editing.md#standard-syntax)wordt beschreven.

   ![](assets/extsignal_definingparameters_2.png)

   >[!CAUTION]
   >
   >Make sure that all the parameters have been declared in the **[!UICONTROL External signal]** activity. Anders treedt er een fout op wanneer de activiteit wordt uitgevoerd.

1. Zodra de parameters zijn bepaald, bevestig de activiteit, dan sparen uw werkschema.
