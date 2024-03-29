---
title: In-app-berichten
description: Geef een bericht of waarschuwing weer in de mobiele applicatie met in-app-berichten.
audience: channels
content-type: reference
topic-tags: in-app-messaging
context-tags: delivery,triggers,back
feature: In App
role: User
exl-id: 986646b1-42d5-4169-ac38-d8e612a9a6d3
source-git-commit: 7767b39a48502f97e2b3af9d21a3f49b9283ab2e
workflow-type: tm+mt
source-wordcount: '443'
ht-degree: 84%

---

# Informatie over in-app-berichten{#about-in-app-messaging}

In-app-berichten is een berichtenkanaal waarmee u een bericht kunt weergeven wanneer de gebruiker binnen de mobiele applicatie actief is. Dit berichttype is ter aanvulling van pushmeldingen die worden afgeleverd aan het meldingscentrum van de telefoon van gebruikers. Raadpleeg deze [sectie](../../channels/using/about-push-notifications.md)voor meer informatie over het pushmeldingenkanaal.

Voor dit kanaal moeten mobiele applicaties en worden geïntegreerd met de Adobe Experience Platform SDK. Deze toepassingen moeten worden geactiveerd in de gebruikersinterface voor gegevensverzameling voordat ze beschikbaar zijn in Adobe Campaign voor In-App-leveringen.

![](assets/launch_campaign.png)

Als u in-app-berichten wilt verzenden op mobiele toepassingen met behulp van de Experience Platform SDK, moet u aan de volgende voorwaarden voldoen:

1. Zorg ervoor dat u in Adobe Campaign toegang hebt tot het kanaal **[!UICONTROL In-App]**. Neem contact op met uw accountteam als u geen toegang hebt tot deze kanalen.

1. Om gebruik van mobiele apparaten in Adobe Campaign Standard te kunnen maken met een SDK-toepassing voor Experiencen Cloud, moet een mobiele app worden gemaakt in de gebruikersinterface voor gegevensverzameling en worden geconfigureerd in Adobe Campaign Standard. Raadpleeg deze [pagina](../../administration/using/configuring-a-mobile-application.md) voor de stapsgewijze handleiding.

1. Zodra de configuratie is voltooid, kunt u uw in-app-bericht voorbereiden. Raadpleeg [deze pagina](../../channels/using/preparing-and-sending-an-in-app-message.md#preparing-your-in-app-message) voor meer informatie.

1. Vervolgens kunt u een [in-app-bericht](../../channels/using/customizing-an-in-app-message.md) verzenden of een [bericht van het type lokale melding aanpassen](../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type).

1. Uw levering is nu klaar om te worden verzonden. Raadpleeg deze [pagina](../../channels/using/preparing-and-sending-an-in-app-message.md#sending-your-in-app-message) voor meer informatie.

**Gerelateerde content:**

* [In-app-rapport](../../reporting/using/in-app-report.md)
* [Mobiele gebruiksscenario’s die worden ondersteund in Adobe Campaign Standard](../../administration/using/configuring-rules-launch.md)
* [Campaign Standard mobiele hulplijn](../../channels/using/get-started-communication-channels.md)

## Mobiele profielvelden verwerken met persoonlijke en gevoelige gegevens {#handling-mobile-profile-fields-with-personal-and-sensitive-data}

In Adobe Campaign worden data van mobiele profielkenmerken die vanaf een mobiel apparaat worden verzonden, opgeslagen in de resource **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** waardoor u de data die u van de abonnees van uw applicaties wilt verzamelen, kunt definiëren.

Deze resource moet worden uitgebreid om data te verzamelen die u van het mobiele apparaat naar Adobe Campaign wilt verzenden. Raadpleeg deze [pagina](../../developing/using/extending-the-subscriptions-to-an-application-resource.md) voor de gedetailleerde stappen als u dit wilt doen.

Om personalisatie van uw in-app-berichten veiliger te maken moeten de mobiele profielvelden van deze resource dienovereenkomstig worden geconfigureerd. Wanneer u uw nieuwe mobiele profielvelden maakt, schakelt u in uw **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** de optie **[!UICONTROL Personal and Sensitive]** om deze onbeschikbaar te maken tijdens personalisatie van in-app-berichten.

>[!NOTE]
>
>Als u een bestaande implementatie hebt met een extensie voor aangepaste resources in deze tabel, raden we u aan de velden op de juiste wijze te labelen voordat u ze gebruikt voor de personalisatie van in-app-berichten.

![](assets/in_app_personal_data_2.png)

Zodra uw aangepaste resource voor **[!UICONTROL Subscriptions to an application]** is geconfigureerd en gepubliceerd, kunt u beginnen met de voorbereiding van uw in-app-levering met behulp van de sjabloon **[!UICONTROL Target users based on their Mobile profile (inApp)]**. Alleen niet-persoonlijke en niet-gevoelige velden zijn beschikbaar voor personalisatie vanuit de resource **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]**.

Als u personalisatie met **persoonlijke en gevoelige** velden nodig hebt, raden wij u aan de sjabloon **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]** te gebruiken die over een extra veiligheidsmechanisme beschikt om ervoor te zorgen dat de PII-data van uw gebruikers veilig blijven.
