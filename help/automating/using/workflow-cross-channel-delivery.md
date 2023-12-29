---
title: Kanaallevering
description: In deze gebruiksaanwijzing ziet u hoe u een levering via meerdere kanalen kunt maken
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: workflow,use-case,query,wait,delivery
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 9cee2005-a99b-47cb-b573-a25812614409
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '856'
ht-degree: 84%

---

# Een kanaaloverschrijdende levering maken{#cross-channel-delivery}

Ontdek in dit document de volgende functionaliteit van Adobe Campaign met behulp van een standaardscenario: een workflow voor kanaaloverschrijdende levering maken.

Het is de bedoeling een doelgroep te selecteren uit de ontvangers in de database en deze te segmenteren in twee verschillende groepen met als doel een e-mail naar de eerste groep en een sms-bericht naar de tweede groep te sturen.

![](assets/wkf_segment_overview.png)

Raadpleeg de volgende documenten voor meer informatie over workflows en de verschillende kanalen die beschikbaar zijn in Adobe Campaign:

* [Workflows detecteren](../../automating/using/get-started-workflows.md)
* [Communicatiekanalen detecteren](../../channels/using/get-started-communication-channels.md)

## Een workflow maken {#creating-workflow}

U moet eerst het doel definiëren als u twee verschillende leveringen naar een bepaalde groep wilt verzenden.

Hiervoor moet u een query maken om de ontvangers te identificeren en daar hebt u een workflow voor nodig.

Maak een nieuwe workflow in het programma of de campagne van uw keuze:

1. Klik in **[!UICONTROL Marketing Activities]** op **[!UICONTROL Create]** en selecteer **[!UICONTROL Workflow]**.
1. Selecteer **[!UICONTROL New Workflow]** als workflowtype en klik op **[!UICONTROL Next]**.
1. Voer de eigenschappen van de workflow in en klik op **[!UICONTROL Create]**.

De gedetailleerde stappen voor het maken van een workflow worden uitgelegd in de sectie [Een workflow maken](../../automating/using/building-a-workflow.md).

## Query-activiteiten maken {#creating-query-activity}

U hebt toegang tot de interface van een workflow zodra deze is gemaakt.

Voeg een queryactiviteit aan uw workflow toe om doelgericht de profielen te benaderen die uw leveringen zullen ontvangen.

1. Sleep in **[!UICONTROL Activities]** > **[!UICONTROL Targeting]** een [Query](../../automating/using/query.md)-activiteit en zet deze neer.
1. Dubbelklik op de activiteit.
1. Blader in het **[!UICONTROL Target]** tabblad door de sneltoetsen en selecteer een van uw [doelgroepen](../../audiences/using/about-audiences.md).
1. Sleep de sneltoets naar de bewerkingszone. Afhankelijk van het geselecteerde type sneltoets wordt een venster weergegeven.
1. Configureer de targetingelementen en bevestig uw query.

![](assets/wkf_segment_query.png)

U kunt een query voor een of meerdere elementen maken.

Gebruik de knop **[!UICONTROL Count]** om een schatting te bekijken van het aantal profielen waarop de query zich richt.

## Een segmentatieactiviteit maken {#creating-segmentation-activity}

Zodra uw doel door de queryactiviteit is geïdentificeerd, moet u een criterium selecteren om het doel in twee verschillende populaties te segmenteren: een gedeelte ontvangt een e-mail en het andere gedeelte ontvangt een sms.

U moet een [Segmentering](../../automating/using/segmentation.md) activiteit om één of verscheidene segmenten van een bevolking tot stand te brengen die stroomopwaarts in een vraag wordt berekend.

![](assets/wkf_segment_activity.png)

De groep **Email** richt zich op ontvangers waarvoor een e-mailadres, maar geen mobiel telefoonnummer is gedefinieerd. De **sms**-groep bevat de ontvangers van wie het mobiele telefoonnummer in het profiel is opgeslagen.

De eerste overgang configureren (e-mail):

1. In het tabblad **[!UICONTROL Segments]** is standaard een eerste segment geplaatst. Bewerk de eigenschappen om dat segment te configureren.

   ![](assets/wkf_segment_properties.png)

1. Selecteer de **[!UICONTROL Email]** van het profiel als filtercriterium.

   ![](assets/wkf_segment_email.png)

1. Selecteer de operator **[!UICONTROL Is not empty]** in het nieuwe venster dat op het scherm wordt geopend.

   ![](assets/wkf_segment_email_not_empty.png)

1. Voeg een tweede filtercriterium **[!UICONTROL Mobile]** toe en selecteer de operator **[!UICONTROL Is empty]**.

   ![](assets/wkf_segment_mobile_empty.png)

   Alle profielen die afkomstig zijn van de query met een e-mailadres, maar zonder mobiel telefoonnummer, staan in deze overgang.

1. Bewerk het overgangslabel om de workflow te verduidelijken. Bevestig uw wijzigingen.

   ![](assets/wkf_segment_transition_label.png)

Uw eerste overgang is geconfigureerd. De tweede overgang (sms) configureren:

1. Klik op de knop **[!UICONTROL Add an element]** om een nieuwe overgang toe te voegen.
1. Definieer een voorwaarde waarmee u alle profielen met mobiele telefoonnummers kunt ophalen. Maak hiervoor een regel in het veld **[!UICONTROL Mobile]** met de logische operator **[!UICONTROL Is not empty]**.

   ![](assets/wkf_segment_mobile_not_empty.png)

   Alle profielen die afkomstig zijn van de query en waarvoor een mobiel telefoonnummer is gedefinieerd, bevinden zich in deze overgang.

1. U kunt het label van de overgang bewerken. Bevestig uw wijzigingen.

Uw tweede overgang is nu ook geconfigureerd.

![](assets/wkf_segment_transitions.png)

## Leveringen maken {#creating-deliveries}

Aangezien twee overgangen reeds werden gecreeerd, moet u twee soorten leveringen aan de uitgaande overgangen van de activiteit van de Segmentatie nu toevoegen: en [E-maillevering](../../automating/using/email-delivery.md) en [Levering via SMS](../../automating/using/sms-delivery.md) activiteit.

Gebruik Adobe Campaign om leveringen aan een workflow toe te voegen. Om dit te kunnen doen, selecteert u een levering in de categorie **[!UICONTROL Channels]** van het activiteitenpalet van uw workflow.

![](assets/wkf_segment_deliveries1.png)

Een e-maillevering maken:

1. Sleep een [E-maillevering](../../automating/using/email-delivery.md) activiteit na het eerste segment.
1. Dubbelklik op de activiteit om deze te bewerken.
1. Selecteer **[!UICONTROL Simple email]**.
1. Selecteer **[!UICONTROL Add an outbound transition with the population]** en klik op **[!UICONTROL Next]**.

   ![](assets/wkf_segment_deliveries2.png)

   De uitgaande overgang maakt het mogelijk om de populatie en de trackinglogboeken te herstellen. Gebruik dit bijvoorbeeld om een tweede e-mail te sturen naar de personen die niet in de eerste e-mail hebben geklikt.

1. Selecteer een e-mailsjabloon en klik op **[!UICONTROL Next]**.
1. Voer de e-maileigenschappen in en klik op **[!UICONTROL Next]**.
1. Selecteer **[!UICONTROL Use the Email Designer]** om de lay-out van uw e-mail te bepalen.
1. Bewerk de content en sla deze op.
1. In de **[!UICONTROL Schedule]** van het berichtdashboard, unselect **[!UICONTROL Request confirmation before sending messages]** -optie.

Een sms-levering maken:

1. Sleep een [Levering via SMS](../../automating/using/sms-delivery.md) activiteit na het andere segment.
1. Dubbelklik op de activiteit om deze te bewerken.
1. Selecteer **[!UICONTROL SMS]** en klik op **[!UICONTROL Next]**.
1. Selecteer een sms-sjabloon en klik op **[!UICONTROL Next]**.
1. Voer de sms-eigenschappen in en klik op **[!UICONTROL Next]**.
1. Bewerk de content en sla deze op.

U kunt de workflow starten zodra de leveringen zijn gemaakt en bewerkt.

![](assets/wkf_segment_deliveries.png)

## De workflow uitvoeren {#running-the-workflow}

Als de workflow eenmaal is gestart, is de doelgroep voor de **[!UICONTROL Query]** activiteiten worden gesegmenteerd om een e-mail- of sms-levering te ontvangen.

Klik op de knop **[!UICONTROL Start]** op de actiebalk om de workflow uit te voeren.

U kunt uw leveringen bekijken in het geavanceerde menu **[!UICONTROL Marketing plans]** > **[!UICONTROL Marketing activities]**, te bereiken via het Adobe Campaign-logo. Klik op de levering en vervolgens op de knop **[!UICONTROL Reports]** voor toegang tot de [leveringsrapporten](../../reporting/using/about-dynamic-reports.md#accessing-dynamic-reports), zoals het leveringsoverzicht, het openingspercentage of de e-mailweergave volgens de inbox van de ontvangers.
