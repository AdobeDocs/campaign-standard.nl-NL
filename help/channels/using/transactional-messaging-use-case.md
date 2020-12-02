---
title: Transactionele berichten configureren
description: Leer hoe te om transactioneel overseinen te vormen.
page-status-flag: never-activated
uuid: 4caeadbe-f4a7-43ce-986d-e99fa9ca0d0d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuring-channels
discoiquuid: 3f968556-e774-43dc-a0b8-7188d7665fbc
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 9ad23468d3d1cf386d9558e6cd2344ea2316fc82
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 4%

---


# Transactioneel overseinengebruiksgeval {#transactional-messaging-use-case}

In dit voorbeeld wilt u de Adobe Campaign-functionaliteit voor transactiemeldingen gebruiken om een bevestigingsbericht te verzenden na elke aankoop op uw website, waarbij u uw klanten kunt identificeren via hun CRM-id.

De voorwaarden zijn als volgt:

* Zorg ervoor dat **[!UICONTROL Profile]** middel met een nieuw gebied is uitgebreid dat met identiteitskaart van CRM beantwoordt.

* Creeer en publiceer een douanemiddel die aan aankopen beantwoordt en het verbinden met **[!UICONTROL Profile]** middel. Op deze manier kunt u informatie ophalen uit deze bron om de inhoud van het bericht te verrijken.

* Zie [deze sectie](../../developing/using/key-steps-to-add-a-resource.md) voor meer informatie over het uitbreiden, maken en publiceren van bronnen.

De belangrijkste stappen voor de implementatie van dit gebruiksgeval zijn als volgt. Om een grafische vertegenwoordiging van het transactieoverseinen algemene proces te zien, zie [dit grafiek](../../channels/using/getting-started-with-transactional-msg.md#key-steps).

## Stap 1 - creeer en publiceer de gebeurtenisconfiguratie {#create-event-configuration}

1. Maak een nieuwe gebeurtenis met het kanaal **[!UICONTROL Email]**. Zie [Een gebeurtenis maken](../../channels/using/configuring-transactional-event.md#creating-an-event)

1. Selecteer **[!UICONTROL Profile]** richtend dimensie om een [op profiel-gebaseerd transactionbericht ](../../channels/using/configuring-transactional-event.md#profile-based-transactional-messages) tot stand te brengen.

1. Definieer de kenmerken die beschikbaar zijn om het transactiebericht aan te passen. Voeg in dit voorbeeld de velden CRM-id en Product-id toe. Zie [Gebeurteniskenmerken definiëren](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes).

   ![](assets/message-center_usecase1.png)

1. Als u de inhoud van het bericht wilt verrijken met informatie over de aankopen van de klant, maakt u een verrijking voor de **[!UICONTROL Purchase]**-bron. Zie [De gebeurtenis verrijken](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content).

   ![](assets/message-center_usecase2.png)

1. Creeer samen voorwaarde tussen het gebied van het &quot;Herkenningsteken van het Product&quot;dat eerder aan het bericht werd toegevoegd, en het overeenkomstige gebied van **[!UICONTROL Purchase]** middel.

   ![](assets/message-center_usecase3.png)

1. Bekijk een voorvertoning van de gebeurtenis en publiceer deze. Zie [Een voorvertoning weergeven en de gebeurtenis publiceren](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event).

## Stap 2 - geef en publiceer het transactiebericht {#create-transactional-message} uit

1. Ga naar het transactiebericht dat automatisch werd gecreeerd bij het publiceren van de gebeurtenis. Zie [Transactieberichten benaderen](../../channels/using/editing-transactional-message.md#accessing-transactional-messages).

1. Bewerk het bericht en pas het aan. Zie [Een bericht voor een profieltransactie bewerken](../../channels/using/editing-transactional-message.md#editing-profile-transactional-message).

1. Aangezien u directe toegang tot alle profielinformatie aan [personalize](../../designing/using/personalization.md#inserting-a-personalization-field) uw bericht hebt, selecteer het gebied van &quot;identiteitskaart van CRM&quot;dat u aan **[!UICONTROL Profile]** middel toevoegde.

1. Verrijk de inhoud van het bericht met informatie over de aankopen van de klant door het veld &quot;Productidentificatie&quot; (of een ander veld) in de **[!UICONTROL Purchase]**-bron toe te voegen.

1. U kunt uw bericht testen met een specifiek testprofiel. Zie [Transactiebericht testen](../../channels/using/publishing-transactional-message.md#testing-a-transactional-message).

1. Wanneer de inhoud gereed is, slaat u de wijzigingen op en publiceert u het bericht. Zie [Een transactioneel bericht publiceren](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message).

## Stap 3 - Integreer de gebeurtenis die {#integrate-event-trigger} teweegbrengt

Integreer de gebeurtenis in uw website (zie gebeurtenis die teweegbrengt (../../channels/using/getting-started-with-transactional-msg.md#integration-event-trigger) integreren).

## Stap 4 - Berichtlevering {#message-delivery}

Zodra al deze stappen zijn uitgevoerd, zodra een klant een aankoop doet op uw website, ontvangen zij een bevestigingsbericht met details op hun CRM-id en hun aankoop.