---
title: Gebruiksscenario voor transactionele berichten
description: Ontdek een end-to-end voorbeeld van de Adobe Campaign functionaliteit voor transactioneel overseinen.
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: Transactional Messaging
role: User
level: Intermediate
exl-id: ee1a9705-4c21-4d46-a178-fde2e059f443
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '504'
ht-degree: 4%

---

# Gebruiksscenario voor transactionele berichten {#transactional-messaging-use-case}

In dit voorbeeld wilt u de Adobe Campaign-functionaliteit voor transactiemeldingen gebruiken om een bevestigingsbericht te verzenden na elke aankoop op uw website, waarbij u uw klanten kunt identificeren via hun CRM-id.

De voorwaarden zijn als volgt:

* Zorg ervoor dat de **[!UICONTROL Profile]** resource is uitgebreid met een nieuw veld dat overeenkomt met de CRM-id.

* Een aangepaste bron voor aankopen maken en publiceren en deze koppelen aan de **[!UICONTROL Profile]** resource. Op deze manier kunt u informatie ophalen uit deze bron om de inhoud van het bericht te verrijken.

Ga voor meer informatie over het uitbreiden, maken en publiceren van bronnen naar [deze sectie](../../developing/using/key-steps-to-add-a-resource.md).

De belangrijkste stappen voor de implementatie van dit gebruiksgeval worden hieronder weergegeven.

>[!NOTE]
>
>Voor een grafische vertegenwoordiging van het transactieoverseinen algemene proces, zie [dit schema](../../channels/using/getting-started-with-transactional-msg.md#key-steps).

## Stap 1 - creeer en publiceer de gebeurtenisconfiguratie {#create-event-configuration}

1. Een nieuwe gebeurtenis maken met de opdracht **[!UICONTROL Email]** kanaal. Zie [Een gebeurtenis maken](../../channels/using/configuring-transactional-event.md#creating-an-event).

1. Selecteer de **[!UICONTROL Profile]** dimensie als doel instellen voor een [op profielen gebaseerd transactiemelding](../../channels/using/configuring-transactional-event.md#profile-based-transactional-messages).

1. Definieer de kenmerken die beschikbaar zijn om het transactiebericht aan te passen. Voeg in dit voorbeeld de velden CRM-id en Product-id toe. Zie [Gebeurteniskenmerken definiëren](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes).

   ![](assets/message-center_usecase1.png)

1. Om de berichtinhoud met informatie betreffende de aankopen van de klant te verrijken, creeer een verrijking gericht op **[!UICONTROL Purchase]** resource. Zie [De gebeurtenis verrijken](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content).

   ![](assets/message-center_usecase2.png)

1. Maak een samenvoegvoorwaarde tussen het veld &quot;Product-id&quot; dat eerder aan de gebeurtenis is toegevoegd en het bijbehorende veld in het dialoogvenster **[!UICONTROL Purchase]** resource.

   ![](assets/message-center_usecase3.png)

1. Omdat dit verplicht is voor op profielen gebaseerde gebeurtenissen, moet u ook een verrijking maken die gericht is op de **[!UICONTROL Profile]** resource.

1. Creeer samen voorwaarde tussen het gebied van &quot;identiteitskaart van CRM&quot;dat eerder aan het bericht werd toegevoegd, en het overeenkomstige gebied van **[!UICONTROL Profile]** bron die u hebt uitgebreid. <!--What's the purpose to have created a CRM ID for this event and to have the CRM ID as a join condition? could it be any other field provided you created it in the event?-->

   ![](assets/message-center_usecase4.png)

1. In de **[!UICONTROL Targeting enrichment]** selecteert u de verrijking op het tabblad **[!UICONTROL Profile]** bron, die als berichtdoel tijdens de uitvoering van de levering zal worden gebruikt.

   ![](assets/message-center_usecase5.png)

1. Bekijk een voorvertoning van de gebeurtenis en publiceer deze. Zie [Een voorvertoning weergeven en de gebeurtenis publiceren](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event).

## Stap 2 - geef en publiceer het transactiebericht uit {#create-transactional-message}

1. Ga naar het transactiebericht dat automatisch werd gecreeerd bij het publiceren van de gebeurtenis. Zie [Toegang tot transactieberichten](../../channels/using/editing-transactional-message.md#accessing-transactional-messages).

1. Bewerk het bericht en pas het aan. Zie [Een bericht voor een profieltransactie bewerken](../../channels/using/editing-transactional-message.md#editing-profile-transactional-message).

1. Via aansluiting met het veld CRM-id dat u hebt toegevoegd aan het veld **[!UICONTROL Profile]** bron, hebt u directe toegang tot alle profielinformatie aan [personaliseren](../../designing/using/personalization.md#inserting-a-personalization-field) uw bericht.

   ![](assets/message-center_usecase6.png)

1. Via afstemming met het veld &quot;Product identifier&quot; kunt u de inhoud van het bericht verrijken met informatie over de aankopen van de klant door een veld van het **[!UICONTROL Purchase]** resource.

   ![](assets/message-center_usecase7.png)

   Selecteer **[!UICONTROL Insert personalization field]** in de contextuele werkbalk. Van de **[!UICONTROL Context]** > **[!UICONTROL Transactional event]** > **[!UICONTROL Event context]** knooppunt, het knooppunt openen dat overeenkomt met het **[!UICONTROL Purchase]** aangepaste bron en selecteer een willekeurig veld.

1. U kunt uw bericht testen met een specifiek testprofiel. Zie [Transactiebericht testen](../../channels/using/testing-transactional-message.md#testing-a-transactional-message).

1. Wanneer de inhoud gereed is, slaat u de wijzigingen op en publiceert u het bericht. Zie [Een transactioneel bericht publiceren](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message).

## Stap 3 - Integreer de gebeurtenis die teweegbrengt {#integrate-event-trigger}

Integreer de gebeurtenis in uw website. Zie [De gebeurtenis die leidt tot integratie](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger).

## Stap 4 - Berichtlevering {#message-delivery}

Zodra al deze stappen zijn uitgevoerd, zodra een klant producten van uw website koopt, ontvangen zij een gepersonaliseerd bevestigingsbericht met informatie over hun aankoop.
