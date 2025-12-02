---
title: Parameters definiëren bij het oproepen van de workflow
description: In deze sectie wordt beschreven hoe u een workflow met externe parameters kunt aanroepen.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: f7de0186-4136-4603-8f80-9f58c641cd9d
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 13%

---

# Parameters definiëren bij het oproepen van de workflow {#defining-the-parameters-when-calling-the-workflow}

In deze sectie wordt beschreven hoe u parameters definieert wanneer u een workflow oproept. Voor meer op hoe te om deze verrichting van een API vraag uit te voeren, verwijs naar de [ REST APIs documentatie ](../../api/using/triggering-a-signal-activity.md).

Controleer voordat u de parameters definieert of:

* De parameters zijn gedeclareerd in de **[!UICONTROL External Signal]** -activiteit. Zie [deze pagina](../../automating/using/declaring-parameters-external-signal.md).
* De workflow met de signaalactiviteit wordt uitgevoerd.

Voer de volgende stappen uit om de **[!UICONTROL End]** -activiteit te configureren:

1. Open de activiteit **[!UICONTROL End]** en selecteer vervolgens de tab **[!UICONTROL External signal]** .
1. Selecteer het werkschema en de externe signaalactiviteit die u wilt roepen.
1. Klik op de knop **[!UICONTROL Create element]** om een parameter toe te voegen en vul vervolgens de naam en waarde van de parameter in.

   * **[!UICONTROL Name]**: de naam die in de **[!UICONTROL External signal]** activiteit (zie [ deze pagina ](../../automating/using/declaring-parameters-external-signal.md)) is verklaard.
   * **[!UICONTROL Value]**: de waarde die u aan de parameter wilt toewijzen. De waarde zou de **Standaardsyntaxis** moeten volgen, die in [ wordt beschreven deze sectie ](../../automating/using/advanced-expression-editing.md#standard-syntax).

   ![](assets/extsignal_definingparameters_2.png)

   >[!CAUTION]
   >
   >Controleer of alle parameters zijn gedeclareerd in de **[!UICONTROL External signal]** -activiteit. Anders treedt er een fout op wanneer de activiteit wordt uitgevoerd.

1. Zodra de parameters zijn bepaald, bevestig de activiteit, dan sparen uw werkschema.
