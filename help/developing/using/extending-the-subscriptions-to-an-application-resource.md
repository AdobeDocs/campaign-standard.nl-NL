---
title: De lidmaatschappen uitbreiden naar een applicatiebron
description: Leer hoe u het abonnement kunt uitbreiden naar een bron van een toepassing
audience: developing
content-type: reference
topic-tags: use-cases--extending-resources
feature: Data Model
role: Developer
level: Experienced
exl-id: ac9c556d-c0f6-4b33-8855-1f5f669c148f
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 24%

---

# De lidmaatschappen uitbreiden naar een applicatiebron{#extending-the-subscriptions-to-an-application-resource}

In Adobe Campaign worden data van mobiele profielkenmerken die vanaf een mobiel apparaat worden verzonden, opgeslagen in de resource **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** waardoor u de data die u van de abonnees van uw applicaties wilt verzamelen, kunt definiëren. Raadpleeg [deze pagina](../../developing/using/key-steps-to-add-a-resource.md) voor meer informatie over aangepaste bronnen.

Deze bron kan worden uitgebreid om gegevens te verzamelen die u van het mobiele apparaat naar Adobe Campaign wilt verzenden.

1. Selecteer in het geavanceerde menu dat u opent via het Adobe Campaign-logo achtereenvolgens **[!UICONTROL Administration]** > **[!UICONTROL Development]** en **[!UICONTROL Custom resources]**.
1. Klik op **[!UICONTROL Create]** en kies de optie **[!UICONTROL Extend an existing resource]**.
1. Selecteer de **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** bron en klik **[!UICONTROL Create]**.

   ![](assets/in_app_personal_data_4.png)

1. Definieer in de categorie **[!UICONTROL Fields]** van het tabblad **[!UICONTROL Data structure]** de klantgegevens die u van uw mobiele toepassing wilt ophalen door op de knop **[!UICONTROL Add field]** te klikken.

   >[!NOTE]
   >
   >Als u meerdere mobiele toepassingen beheert, moeten alle velden die door al uw toepassingen worden gebruikt, worden vermeld. Met de iOS- of Android-oproep voor verzamelen van PII&#39;s wordt gedefinieerd welke velden door elke toepassing worden vastgelegd.

   ![](assets/in_app_personal_data.png)

1. Voeg een **[!UICONTROL Label]** en een **[!UICONTROL ID]** aan uw nieuw gebied toe. Selecteer **[!UICONTROL Type]** van uw gebied.

   ![](assets/schema_extension_uc9.png)

1. Configureer in de categorie **[!UICONTROL Link to profiles]** de afstemmingssleutel die wordt gebruikt om de profielen uit de Adobe Campaign-database te koppelen aan de abonnees van uw toepassingen, zoals de e-mail.

   Voor uw In-App-berichten kunt u slechts één afstemmingssleutel definiëren voor al uw mobiele toepassingen.

   ![](assets/in_app_personal_data_3.png)

1. **[!UICONTROL Save]** en publiceert u uw aangepaste bron. Raadpleeg deze [pagina](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource) voor meer informatie over de publicatie van aangepaste bronnen.
