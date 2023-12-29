---
title: De lidmaatschappen uitbreiden naar een applicatiebron
description: Leer hoe u het abonnement kunt uitbreiden naar een toepassingsbron
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
ht-degree: 10%

---

# De lidmaatschappen uitbreiden naar een applicatiebron{#extending-the-subscriptions-to-an-application-resource}

In Adobe Campaign worden gegevens van kenmerken van mobiele apparaten opgeslagen in **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** bron waarmee u de gegevens kunt definiëren die u van de abonnees van uw toepassingen wilt verzamelen. Raadpleeg voor meer informatie over aangepaste bronnen [deze pagina](../../developing/using/key-steps-to-add-a-resource.md).

Deze bron kan worden uitgebreid om gegevens te verzamelen die u van het mobiele apparaat naar Adobe Campaign wilt verzenden.

1. Selecteer in het geavanceerde menu dat u opent via het Adobe Campaign-logo achtereenvolgens **[!UICONTROL Administration]** > **[!UICONTROL Development]** en **[!UICONTROL Custom resources]**.
1. Klikken **[!UICONTROL Create]** en kiest u **[!UICONTROL Extend an existing resource]** -optie.
1. Selecteer de **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** bron en klik op **[!UICONTROL Create]**.

   ![](assets/in_app_personal_data_4.png)

1. In de **[!UICONTROL Fields]** categorie **[!UICONTROL Data structure]** , definieert u de klantgegevens die u van uw mobiele toepassing wilt ophalen door op de knop **[!UICONTROL Add field]** knop.

   >[!NOTE]
   >
   >Als u meerdere mobiele toepassingen beheert, moeten alle velden die door al uw toepassingen worden gebruikt, worden vermeld. De iOS- of Android-aanroep voor verzamelen van PII&#39;s bepaalt welke velden door elke toepassing worden vastgelegd.

   ![](assets/in_app_personal_data.png)

1. Voeg een **[!UICONTROL Label]** en **[!UICONTROL ID]** naar uw nieuwe veld. Selecteer de velden **[!UICONTROL Type]**.

   ![](assets/schema_extension_uc9.png)

1. In de **[!UICONTROL Link to profiles]** , configureert u de afstemmingssleutel die wordt gebruikt om de profielen van de Adobe Campaign-database te koppelen aan de abonnees van uw toepassingen, zoals de e-mail.

   Voor uw In-App-berichten kunt u slechts één afstemmingssleutel definiëren voor al uw mobiele toepassingen.

   ![](assets/in_app_personal_data_3.png)

1. **[!UICONTROL Save]** en publiceert u uw aangepaste bron. Raadpleeg voor meer informatie over de publicatie van aangepaste bronnen de volgende [page](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).
