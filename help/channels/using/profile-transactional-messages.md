---
title: Transactieberichten profileren
description: Leer hoe u een bericht voor een profieltransactie maakt en publiceert.
page-status-flag: never-activated
uuid: a8efe979-74ae-46ff-a305-b86a90679581
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: transactional-messaging
discoiquuid: dcb90afc-42c3-419e-8345-79cddf969e41
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Transactieberichten profileren{#profile-transactional-messages}

U kunt transactieberichten verzenden die op klanten marketing profielen worden gebaseerd, die u toestaan:

* Pas de typologieregels voor marketing toe, zoals **[!UICONTROL Blacklisted address]** of [vermoeidheidsregels](../../administration/using/fatigue-rules.md).
* Neem de koppeling voor het opzeggen van abonnementen op in de berichten.
* Voeg de transactieberichten aan de globale levering toe rapporteert.
* Hefboomwerking de transactionele berichten in de klantenreis.

Nadat u een gebeurtenis hebt gemaakt en gepubliceerd (de winkelwagentje zoals in het [voorbeeld](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle) hierboven), wordt het bijbehorende transactiemelding automatisch gemaakt.

De configuratiestappen worden voorgesteld in het [Vormen van een gebeurtenis om een sectie van het profieltransactiebericht](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) te verzenden.

Als de gebeurtenis het verzenden van een transactiemelding moet activeren, moet u het bericht personaliseren, het vervolgens testen en publiceren.

>[!NOTE]
>
>Om tot transactieberichten toegang te hebben, moet u deel van de **[!UICONTROL Administrators (all units)]** veiligheidsgroep uitmaken.
>
>De regels van de moeheid zijn compatibel met de berichten van de profieltransactie. Zie [Vermoeidheidsregels](../../administration/using/fatigue-rules.md).

## Een bericht voor een profieltransactie verzenden {#sending-a-profile-transactional-message}

De stappen voor het maken, personaliseren en publiceren van een bericht voor een profieltransactie zijn hetzelfde als voor een bericht voor een gebeurtenistransactie. Zie Transactieberichten voor [gebeurtenissen](../../channels/using/event-transactional-messages.md).

De verschillen worden hieronder vermeld.

1. Ga het transactiemelding dat werd gecreeerd om het uit te geven.
1. Klik in het transactiebericht op de **[!UICONTROL Content]** sectie. Naast de transactiesjabloon kunt u ook elke gewenste e-mailsjabloon kiezen **[!UICONTROL Profile]**.

   ![](assets/message-center_marketing_templates.png)

1. Selecteer de standaard e-mailsjabloon.

   Net als bij alle e-mails over marketingdoeleinden, bevat deze koppeling een koppeling om je abonnement op te zeggen.

   ![](assets/message-center_marketing_perso_unsubscription.png)

   Ook, in tegenstelling tot configuraties die op gebeurtenissen in real time worden gebaseerd, hebt u directe toegang tot alle profielinformatie om uw bericht te personaliseren. Zie Een verpersoonlijkingsveld [invoegen](../../designing/using/personalization.md#inserting-a-personalization-field).

1. Sla uw wijzigingen op en publiceer het bericht. Zie [Transactiebericht](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message)publiceren.

## De berichtlevering van een profieltransactie controleren {#monitoring-a-profile-transactional-message-delivery}

Zodra het bericht wordt gepubliceerd en uw plaatsintegratie wordt gedaan, kunt u de levering controleren.

1. Klik op het pictogram rechtsonder in het **[!UICONTROL Deployment]** blok om het logboek voor de verzending van berichten weer te geven.

   Voor meer informatie bij de toegang tot van de logboeken, zie de [Controle van de levering](../../sending/using/monitoring-a-delivery.md).

1. Selecteer het **[!UICONTROL Sending logs]** tabblad. In de **[!UICONTROL Status]** kolom **[!UICONTROL Sent]** geeft u aan dat er een profiel is geselecteerd.

   ![](assets/message-center_marketing_sending_logs.png)

1. Selecteer het **[!UICONTROL Exclusions logs]** tabblad om ontvangers te bekijken die zijn uitgesloten van het berichtdoel, zoals adressen op de zwarte lijst.

   ![](assets/message-center_marketing_exclusion_logs.png)

Voor elk profiel dat is uitgeschakeld, is de **[!UICONTROL Blacklisted address]** typologieregel niet van toepassing op de bijbehorende ontvanger.

Deze regel maakt deel uit van een specifieke typologie die op alle transactionele berichten van toepassing is die op de **[!UICONTROL Profile]** lijst worden gebaseerd.

![](assets/message-center_marketing_typology.png)

**Verwante onderwerpen**:

* [Site-integratie](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)
* [Typologieën](../../administration/using/about-typology-rules.md)

