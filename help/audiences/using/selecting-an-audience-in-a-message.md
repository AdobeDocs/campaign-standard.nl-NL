---
title: Een doelgroep in een bericht selecteren
description: '‘Stapsgewijze procedure voor het kiezen van doelgroepen van een e-mail: belangrijkste doelpopulatie en testprofielen.’'
page-status-flag: never-activated
uuid: 7d8f8446-f2e0-49c1-83f6-9667b29bc228
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-audiences
discoiquuid: 158da6ff-8899-4e7b-b925-8a42c3de46a1
context-tags: deliveryCreation,wizard;delivery,audience,back
internal: n
snippet: y
translation-type: ht
source-git-commit: 07d68b5bf8d800ebd95919f491e98f1b7a015705
workflow-type: ht
source-wordcount: '294'
ht-degree: 100%

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

Het blok Audience wordt vervolgens bijgewerkt en geeft weer dat een doel en testprofielen zijn geselecteerd voor de e-mail in kwestie.

![](assets/delivery_audience_definition_3.png)

