---
title: Een workflow oproepen met externe parameters
description: In deze sectie wordt beschreven hoe u een workflow met externe parameters kunt aanroepen.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: f7de0186-4136-4603-8f80-9f58c641cd9d
source-git-commit: 13d419c5fc51845ee14f8a3b288f4c467e0a60d9
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 13%

---

# Parameters definiëren bij het oproepen van de workflow {#defining-the-parameters-when-calling-the-workflow}

In deze sectie wordt beschreven hoe u parameters definieert wanneer u een workflow oproept. Raadpleeg voor meer informatie over het uitvoeren van deze bewerking vanuit een API-aanroep de [REST APIs-documentatie](../../api/using/triggering-a-signal-activity.md).

Voordat u de parameters definieert, moet u ervoor zorgen dat:

* De parameters zijn gedeclareerd in de **[!UICONTROL External Signal]** activiteit. Zie [deze pagina](../../automating/using/declaring-parameters-external-signal.md).
* De workflow met de signaalactiviteit wordt uitgevoerd.

Om het **[!UICONTROL End]** Voer de volgende stappen uit:

1. Open de **[!UICONTROL End]** activiteit, dan selecteer **[!UICONTROL External signal]** tab.
1. Selecteer het werkschema en de externe signaalactiviteit die u wilt roepen.
1. Klik op de knop **[!UICONTROL Create element]** om een parameter toe te voegen, vult dan zijn naam en waarde in.

   * **[!UICONTROL Name]**: de naam die is gedeclareerd in het **[!UICONTROL External signal]** activiteit (zie [deze pagina](../../automating/using/declaring-parameters-external-signal.md)).
   * **[!UICONTROL Value]**: de waarde die u aan de parameter wilt toewijzen. De waarde moet volgen op de **Standaardsyntaxis**, beschreven in [deze sectie](../../automating/using/advanced-expression-editing.md#standard-syntax).

   ![](assets/extsignal_definingparameters_2.png)

   >[!CAUTION]
   >
   >Controleer of alle parameters zijn gedeclareerd in het dialoogvenster **[!UICONTROL External signal]** activiteit. Anders treedt er een fout op wanneer de activiteit wordt uitgevoerd.

1. Zodra de parameters zijn bepaald, bevestig de activiteit, dan sparen uw werkschema.
