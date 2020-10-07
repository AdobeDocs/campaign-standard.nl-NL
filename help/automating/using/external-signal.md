---
title: Extern signaal
description: De activiteit Extern signaal triggert een workflow wanneer aan sommige voorwaarden wordt voldaan in een andere workflow.
page-status-flag: never-activated
uuid: 884b6daf-bfd9-440b-8336-004b80c76def
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 911c71b5-da8b-4916-b645-13bba6d21715
context-tags: signal,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '600'
ht-degree: 93%

---


# Extern signaal{#external-signal}

## Beschrijving {#description}

![](assets/signal.png)

De activiteit **[!UICONTROL External signal]** triggert een workflow wanneer aan sommige voorwaarden wordt voldaan in een andere workflow of vanaf een REST API-aanroep.

## Gebruikscontext {#context-of-use}

De activiteit **[!UICONTROL External signal]** wordt gebruikt om verschillende processen te organiseren en te regelen die deel uitmaken van hetzelfde klanttraject in verschillende workflows. Deze activiteit maakt het mogelijk een workflow te starten vanuit een andere workflow ter ondersteuning van complexere klanttrajecten, terwijl u in geval van problemen gemakkelijker kunt opvolgen en reageren.

De activiteit **[!UICONTROL External signal]** is ontworpen om als eerste activiteit van een workflow te worden geplaatst. Deze kan worden geactiveerd vanaf de activiteit **[!UICONTROL End]** van een andere workflow of vanaf een REST API-aanroep (zie de [API-documentatie](../../api/using/triggering-a-signal-activity.md) voor meer informatie).

Wanneer deze activiteit wordt geactiveerd, kunnen externe parameters worden gedefinieerd en ter beschikking worden gesteld in de gebeurtenisvariabelen van de workflow. Het proces om een workflow met externe parameters aan te roepen wordt gedetailleerd beschreven in [deze sectie](../../automating/using/calling-a-workflow-with-external-parameters.md).

>[!NOTE]
>
>De activiteit kan niet vaker dan om de 10 minuten worden geactiveerd.

Merk op dat een activiteit **[!UICONTROL External signal]** vanaf verschillende gebeurtenissen kan worden geactiveerd. In dat geval wordt het **[!UICONTROL External signal]** geactiveerd zodra een van de bronworkflows of de API-aanroep wordt uitgevoerd. Hiervoor hoeven niet alle bronworkflows voltooid te zijn.

**Verwante onderwerpen**

* [Hoofdlettergebruik: Externe signaalactiviteit en gegevensinvoer](../../automating/using/external-signal-data-import.md).
* [Hoofdlettergebruik: Een workflow aanroepen om een publiek te maken op basis van een bestand met externe parameters](../../automating/using/use-case-calling-workflow.md)

## Configuratie {#configuration}

Bij het configureren van een extern signaal is het belangrijk om eerst de activiteit **[!UICONTROL External signal]** in de bestemmingsworkflow te configureren. Zodra deze configuratie is uitgevoerd, wordt de activiteit **[!UICONTROL External signal]** van deze workflow beschikbaar om de activiteit **[!UICONTROL End]** van de bronworkflow te configureren.

1. Sleep een activiteit **[!UICONTROL External signal]** en zet deze neer in uw bestemmingsworkflow.
1. Selecteer de activiteit en open deze met de knop ![](assets/edit_darkgrey-24px.png) vanuit de snelle acties die verschijnen.
1. Bewerk het label van de activiteit. Dit label is nodig bij het configureren van de bronworkflow die het **[!UICONTROL External signal]** activeert.

   Als u de workflow wilt aanroepen met parameters, gebruikt u het gebied **[!UICONTROL Parameters]** om deze te declareren. For more on this, refer to this section: [](../../automating/using/declaring-parameters-external-signal.md).

   ![](assets/external_signal_configuration.png)

1. Bevestig de configuratie van uw activiteit, voeg desgewenst nog een willekeurige activiteit toe en sla uw workflow op.

   >[!NOTE]
   >
   >Ga als volgt te werk als u de bestemmingsworkflow wilt activeren vanuit een andere workflow. Als u de bestemmingsworkflow wilt activeren via een REST API-aanroep, raadpleegt u de [API-documentatie](../../api/using/triggering-a-signal-activity.md) voor meer informatie.

1. Open de bronworkflow en selecteer een activiteit **[!UICONTROL End]**. Als er geen activiteit **[!UICONTROL End]** beschikbaar is, voegt u er een toe na de laatste activiteit van een vertakking van de workflow.

   Sommige activiteiten hebben standaard geen uitgaande overgang. Via het tabblad **[!UICONTROL Properties]** van deze activiteiten kunt u een uitgaande overgang toevoegen.

   Ga in een activiteit **[!UICONTROL Update data]** bijvoorbeeld naar het tabblad **[!UICONTROL Transitions]** en schakel de optie **[!UICONTROL Add an outbound transition without the population]** in. Met deze optie kunt u een overgang toevoegen die geen data bevat en geen onnodige ruimte op uw systeem inneemt. Deze overgang wordt alleen gebruikt voor het verbinden van de extra activiteit **[!UICONTROL End]** die de bestemmingsworkflow activeert.

   ![](assets/external_signal_empty_transition.png)

1. Selecteer op het tabblad **[!UICONTROL External signal]** van de activiteit **[!UICONTROL End]** de bestemmingsworkflow en de activiteit **[!UICONTROL External signal]** die binnen die workflow moet worden geactiveerd.

   Wanneer u een activiteit **[!UICONTROL End]** instelt om een andere workflow te activeren, wordt het pictogram ervan bijgewerkt met een aanvullend signaalsymbool.

   Als u de workflow wilt aanroepen met parameters, gebruikt u het gebied **[!UICONTROL Parameters and values]**. For more on this, refer to this section: [](../../automating/using/defining-parameters-calling-workflow.md).

   ![](assets/external_signal_end.png)

1. Sla de bronworkflow op.

Zodra de activiteit **[!UICONTROL End]** van de bronworkflow of de REST API-aanroep is uitgevoerd, wordt de bestemmingsworkflow automatisch geactiveerd vanaf de activiteit **[!UICONTROL External signal]**.

>[!NOTE]
>
>De bestemmingsworkflow moet handmatig worden gestart voordat deze kan worden geactiveerd. Wanneer deze is gestart, wordt de **[!UICONTROL External activity]** geactiveerd en wacht deze op het signaal van de bronworkflow.
