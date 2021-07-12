---
solution: Campaign Standard
product: campaign
title: Een transactioneel bericht testen
description: Leer hoe je een transactiebericht test in Adobe Campaign.
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: Transactional Messaging
role: User
level: Intermediate
exl-id: 5138826d-ae08-403b-91ef-91027ef6e78e
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 40%

---

# Een transactioneel bericht testen {#testing-a-transactional-message}

Voordat u uw transactiebericht publiceert, kunt u een specifiek testprofiel maken waarmee u het bericht correct kunt controleren.

## Een specifiek testprofiel definiëren {#defining-specific-test-profile}

Definieer een testprofiel dat aan uw gebeurtenis wordt gekoppeld. Hiermee kunt u een voorbeeld van uw bericht bekijken en een relevante proefdruk verzenden.

1. Van [transactioneel berichtdashboard](../../channels/using/editing-transactional-message.md#accessing-transactional-messages), klik **[!UICONTROL Create test profile]** knoop.

   ![](assets/message-center_test-profile.png)

1. Geef de informatie die u wilt verzenden op in de JSON-indeling in de sectie **[!UICONTROL Event data used for personalization]**. Dit is de content die wordt gebruikt wanneer een voorbeeld van het bericht wordt weergegeven en wanneer het testprofiel de proef ontvangt.

   ![](assets/message-center_event-data.png)

   >[!NOTE]
   >
   >Als u uw bericht hebt verrijkt, kunt u ook informatie invoeren die betrekking heeft op een andere tabel, zoals **[!UICONTROL Profile]**. Zie [De gebeurtenis verrijken](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content) en [Een transactiebericht aanpassen](../../channels/using/editing-transactional-message.md#personalizing-a-transactional-message).

1. Zodra gecreeerd, zal het testprofiel vooraf gespecificeerd in het transactiebericht zijn. Klik op het blok **[!UICONTROL Test profiles]** van het bericht om het doel van de proef te controleren.

   ![](assets/message-center_5.png)

U kunt ook een nieuw testprofiel maken of een profiel gebruiken dat al in het menu **[!UICONTROL Test profiles]** staat. Dit doet u als volgt:

1. Klik in de linkerbovenhoek op het logo **[!UICONTROL Adobe Campaign]** en selecteer **[!UICONTROL Profiles & audiences]** > **[!UICONTROL Test profiles]**.
1. Selecteer in de sectie **[!UICONTROL Event]** de gebeurtenis die u zojuist hebt gemaakt. In dit voorbeeld selecteert u Cart abandonment (EVTcartAbandonment).
1. Geef in het tekstvak **[!UICONTROL Event data]** de informatie op die u in de JSON-indeling wilt verzenden.

   ![](assets/message-center_3.png)

1. Sla uw wijzigingen op.
1. [Open het ](../../channels/using/editing-transactional-message.md#accessing-transactional-messages) bericht dat u hebt gemaakt en selecteer het bijgewerkte testprofiel.

**Verwante onderwerpen:**

* [Testprofielen beheren](../../audiences/using/managing-test-profiles.md)
* [Doelgroepen maken](../../audiences/using/creating-audiences.md)

## De proefdruk verzenden {#sending-proof}

Nadat u een of meer specifieke testprofielen hebt gemaakt en uw transactiebericht hebt opgeslagen, kunt u een proefdruk verzenden om dit te testen.

![](assets/message-center_10.png)

De stappen voor het verzenden van een proefdruk worden beschreven in de sectie [Proofs verzenden](../../sending/using/sending-proofs.md).
