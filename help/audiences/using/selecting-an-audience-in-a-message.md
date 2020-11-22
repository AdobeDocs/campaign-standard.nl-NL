---
solution: Campaign Standard
product: campaign
title: Een doelgroep in een bericht selecteren
description: '‘Stapsgewijze procedure voor het kiezen van doelgroepen van een e-mail: belangrijkste doelpopulatie en testprofielen.’'
audience: audiences
content-type: reference
topic-tags: managing-audiences
context-tags: deliveryCreation,wizard;delivery,audience,back
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 83%

---


# Een doelgroep in een bericht selecteren{#selecting-an-audience-in-a-message}

Met Adobe Campaign kunt u verschillende profieltypen configureren binnen de doelgroep van een bericht.

Doelgroepen kunnen worden gedefinieerd bij het maken van het bericht via de wizard Maken of vanaf het berichtdashboard als het bericht al is gemaakt.

>[!NOTE]
>
>Als de doelgroep is opgebouwd binnen een workflow en verrijkt met aanvullende data, kunt u deze data niet gebruiken om een individuele levering te personaliseren. Ze kunnen alleen worden gebruikt vanuit een levering die wordt uitgevoerd in een workflow.

1. Ga vanaf het dashboard naar het blok Audience om te beginnen.

   ![](assets/delivery_audience_definition_1.png)

   Het scherm voor het definiëren van doelgroepen wordt geopend. Het heeft twee tabbladen waarmee u elk type doelgroep die het bericht zal ontvangen, afzonderlijk kunt definiëren:

   * Target
   * Test profiles

   ![](assets/delivery_audience_definition_2.png)

1. Definieer het belangrijkste **[!UICONTROL Target]** van de e-mail. Dit is de gebruikelijke doelgroep van de e-mail.

   Het doel wordt gedefinieerd op het tabblad **[!UICONTROL Target]** en bestaat uit geïdentificeerde profielen uit uw database.

   U kunt het hoofddoel instellen met de functies van de [query-editor](../../automating/using/editing-queries.md#creating-queries).

   Op dit tabblad bevat het palet **[!UICONTROL Shortcuts]** alleen vooraf gedefinieerde filters en de doelgroepen die in de geïdentificeerde profielen zijn gedefinieerd. Op het tabblad **[!UICONTROL Explorer]** hebt u toegang tot aanvullende configuraties.

   U kunt dus bestaande doelgroepen hergebruiken en combineren, er aanvullende filters op toepassen, enzovoort.

1. Definieer de **[!UICONTROL Test profiles]** die u voor de e-mail wilt gebruiken. De testprofielen ontvangen de proeven die u vooraf kunt verzenden om de e-mail te testen voordat u deze naar het hoofddoel verzendt.

   Raadpleeg de sectie [Testprofielen](../../audiences/using/managing-test-profiles.md) voor meer informatie over het configureren van testprofielen.

1. Indien nodig, kunt u een controlegroep bepalen gebruikend het overeenkomstige lusje. Hierdoor kunt u bepaalde profielen van uw doel verwijderen zodat deze het bericht niet ontvangen. For more on this, see [Adding a control group](../../sending/using/control-group.md).

1. U kunt ook substitutieadressen gebruiken om een nauwkeurige vertegenwoordiging van het bericht te krijgen dat het profiel zal ontvangen.  Zie [E-mailberichten testen met doelprofielen](../../sending/using/testing-messages-using-target.md) voor meer informatie.

Het blok Audience wordt vervolgens bijgewerkt en geeft weer dat een doel en testprofielen zijn geselecteerd voor de e-mail in kwestie.

![](assets/delivery_audience_definition_3.png)

