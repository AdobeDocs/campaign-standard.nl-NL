---
title: Een publiek in een bericht selecteren
description: '"Stapsgewijze procedure voor het kiezen van een e-mailpubliek: belangrijkste doelpopulatie en testprofielen."'
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
translation-type: tm+mt
source-git-commit: 07d68b5bf8d800ebd95919f491e98f1b7a015705

---


# Een publiek in een bericht selecteren{#selecting-an-audience-in-a-message}

Met Adobe Campaign kunt u verschillende profieltypen configureren voor een berichtvenster.

Het publiek kan worden bepaald wanneer het creëren van het bericht via de aanmaaktovenaar of van het berichtdashboard als het bericht reeds is gecreeerd.

>[!NOTE]
>
>Als het publiek is opgebouwd binnen een werkstroom en verrijkt met extra gegevens, zult u deze gegevens niet kunnen gebruiken om een standalone levering te personaliseren. Ze kunnen alleen worden gebruikt vanuit een levering die wordt uitgevoerd in een workflow.

1. Ga vanaf het dashboard naar het blok publiek om te beginnen.

   ![](assets/delivery_audience_definition_1.png)

   Het scherm om het publiek te bepalen dan opent. Het heeft twee lusjes die u toestaan om elk type van publiek afzonderlijk te bepalen dat het bericht zal ontvangen:

   * Doel
   * Testprofielen
   ![](assets/delivery_audience_definition_2.png)

1. Hoofdgedeelte **[!UICONTROL Target]** van e-mail definiëren. Dit is het reguliere doelpubliek van de e-mail.

   Het doel wordt gedefinieerd op het **[!UICONTROL Target]** tabblad en bestaat uit geïdentificeerde profielen uit uw database.

   U kunt uw belangrijkste doel vestigen gebruikend de functionaliteit van de [vraagredacteur](../../automating/using/editing-queries.md#creating-queries) .

   Op dit tabblad bevat het **[!UICONTROL Shortcuts]** palet alleen vooraf gedefinieerde filters en het publiek dat is gedefinieerd in de opgegeven profielen. Op het **[!UICONTROL Explorer]** tabblad hebt u toegang tot extra configuraties.

   U kunt daarom bestaande doelgroepen hergebruiken en combineren, er aanvullende filters op toepassen, enzovoort.

1. Definieer de **[!UICONTROL Test profiles]** gegevens die u voor de e-mail wilt gebruiken. De testprofielen ontvangen de proefdrukken die u vóór kunt verzenden om de e-mail te testen voordat u deze naar het hoofddoel verzendt.

   Raadpleeg de sectie [Testprofielen](../../audiences/using/managing-test-profiles.md) voor meer informatie over het configureren van testprofielen.

Het blok Soorten publiek wordt vervolgens bijgewerkt en toont dat een doel- en testprofiel zijn geselecteerd voor de e-mail in kwestie.

![](assets/delivery_audience_definition_3.png)

