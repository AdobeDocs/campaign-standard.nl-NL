---
solution: Campaign Standard
product: campaign
title: Transactionele berichten voor profielen
description: Ontdek hoe u een transactioneel bericht voor een profiel maakt en publiceert.
audience: channels
content-type: reference
topic-tags: transactional-messaging
translation-type: tm+mt
source-git-commit: a0ad969c86a5047f3f967a21fdc2d6040d7d939f
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Transactionele berichten voor profielen{#profile-transactional-messages}

U kunt transactionele berichten verzenden die op klantmarketingprofielen zijn gebaseerd en waarmee u het volgende kunt doen:

* De typologieregels voor marketing toepassen, zoals **[!UICONTROL Address on denylist]** of [moeheidsregels](../../sending/using/fatigue-rules.md).
* De koppeling voor het opzeggen van abonnementen in de berichten opnemen.
* De transactionele berichten aan de globale leveringsrapportage toevoegen.
* De transactionele berichten in het klanttraject gebruiken.

Nadat u een gebeurtenis (een ongebruikte winkelwagen zoals in het [voorbeeld](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle) hierboven) hebt gemaakt en gepubliceerd, wordt het bijbehorende transactionele bericht automatisch gemaakt.

De configuratiestappen worden weergegeven in de sectie [Een gebeurtenis voor het verzenden van een transactioneel bericht voor een profiel configureren](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message).

Om ervoor te zorgen dat de gebeurtenis het verzenden van een transactioneel bericht activeert, moet u het bericht personaliseren en het vervolgens testen en publiceren.

>[!NOTE]
>
>Om toegang te hebben tot transactionele berichten moet u deel uitmaken van de beveiligingsgroep **[!UICONTROL Administrators (all units)]**.
>
>De moeheidsregels zijn compatibel met transactieberichten voor profielen. Zie [Moeheidsregels](../../sending/using/fatigue-rules.md).

## Een transactioneel bericht voor een profiel verzenden {#sending-a-profile-transactional-message}

De stappen voor het maken, personaliseren en publiceren van een transactioneel bericht voor een profiel zijn dezelfde als voor een transactioneel bericht voor een gebeurtenis. Zie [Transactieberichten voor gebeurtenissen](../../channels/using/event-transactional-messages.md).

De verschillen worden hieronder vermeld.

1. Ga naar het transactionele bericht dat is gemaakt om het te bewerken.
1. Klik in het transactionele bericht op de sectie **[!UICONTROL Content]**. Naast de transactionele sjabloon kunt u ook elke gewenste e-mailsjabloontargeting kiezen **[!UICONTROL Profile]**.

   ![](assets/message-center_marketing_templates.png)

1. Selecteer de standaard e-mailsjabloon.

   Net als bij alle marketing-e-mails bevat deze een koppeling voor het opzeggen van abonnementen.

   ![](assets/message-center_marketing_perso_unsubscription.png)

   Bovendien hebt u, in tegenstelling tot configuraties die op realtimegebeurtenissen zijn gebaseerd, directe toegang tot alle profielinformatie om uw bericht te personaliseren. Zie [Een personalisatieveld invoegen](../../designing/using/personalization.md#inserting-a-personalization-field).

1. Sla uw wijzigingen op en publiceer het bericht. Zie [Een transactioneel bericht publiceren](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message).

## De levering van een transactioneel bericht voor een profiel controleren {#monitoring-a-profile-transactional-message-delivery}

Zodra het bericht is gepubliceerd en uw website-integratie is voltooid, kunt u de levering controleren.

1. Klik op het pictogram rechtsonder in het blok **[!UICONTROL Deployment]** om het logboek voor de verzending van berichten weer te geven.

   Voor meer informatie over het openen van de logboeken raadpleegt u [De levering controleren](../../sending/using/monitoring-a-delivery.md).

1. Selecteer het tabblad **[!UICONTROL Sending logs]**. In de kolom **[!UICONTROL Status]** geeft **[!UICONTROL Sent]** aan dat er een profiel is ingeschreven.

   ![](assets/message-center_marketing_sending_logs.png)

1. Selecteer **[!UICONTROL Exclusions logs]** lusje om ontvangers te bekijken die van het berichtdoel, zoals adressen op lijst van afgewezen personen zijn uitgesloten.

   ![](assets/message-center_marketing_exclusion_logs.png)

Voor elk profiel dat is uitgeschreven, is de typologieregel **[!UICONTROL Address on denylist]** niet van toepassing op de bijbehorende ontvanger.

Deze regel maakt deel uit van een specifieke typologie die op alle transactionele berichten van toepassing is op basis van de tabel **[!UICONTROL Profile]**.

![](assets/message-center_marketing_typology.png)

**Verwante onderwerpen**:

* [Website-integratie](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)
* [Typologieën](../../sending/using/about-typology-rules.md)
