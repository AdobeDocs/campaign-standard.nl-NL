---
title: De abonnementen uitbreiden naar een applicatieresource
description: null
page-status-flag: never-activated
uuid: 8879b427-b31b-4311-bf54-258a91b1fb78
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: use-cases--extending-resources
discoiquuid: 59faa74e-86fc-42d3-90da-f48580b5ec13
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 25%

---


# De abonnementen uitbreiden naar een applicatieresource{#extending-the-subscriptions-to-an-application-resource}

In Adobe Campaign worden data van mobiele profielkenmerken die vanaf een mobiel apparaat worden verzonden, opgeslagen in de resource **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** waardoor u de data die u van de abonnees van uw applicaties wilt verzamelen, kunt definiëren. For more information on custom resources, refer to [this page](../../developing/using/key-steps-to-add-a-resource.md).

Deze bron kan worden uitgebreid om gegevens te verzamelen die u van het mobiele apparaat naar Adobe Campaign wilt verzenden.

1. Selecteer in het geavanceerde menu dat u opent via het Adobe Campaign-logo achtereenvolgens **[!UICONTROL Administration]** > **[!UICONTROL Development]** en **[!UICONTROL Custom resources]**.
1. Klik **[!UICONTROL Create]** en kies de **[!UICONTROL Extend an existing resource]** optie.
1. Select the **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** resource and click **[!UICONTROL Create]**.

   ![](assets/in_app_personal_data_4.png)

1. Definieer in de **[!UICONTROL Fields]** categorie van het **[!UICONTROL Data structure]** tabblad de klantgegevens die u van uw mobiele toepassing wilt ophalen door op de **[!UICONTROL Add field]** knop te klikken.

   >[!NOTE]
   >
   >Als u meerdere mobiele toepassingen beheert, moeten alle velden die door al uw toepassingen worden gebruikt, worden vermeld. Met de iOS- of Android-oproep voor verzamelen van PII&#39;s wordt gedefinieerd welke velden door elke toepassing worden vastgelegd.

   ![](assets/in_app_personal_data.png)

1. Voeg een **[!UICONTROL Label]** en een **[!UICONTROL ID]** veld toe aan het nieuwe veld. Selecteer de velden **[!UICONTROL Type]**.

   ![](assets/schema_extension_uc9.png)

1. In de **[!UICONTROL Link to profiles]** categorie configureert u de afstemmingssleutel die wordt gebruikt om de profielen van de Adobe Campaign-database te koppelen aan de abonnees van uw toepassingen, zoals de e-mail.

   Voor uw In-App-berichten kunt u slechts één afstemmingssleutel definiëren voor al uw mobiele toepassingen.

   ![](assets/in_app_personal_data_3.png)

1. **[!UICONTROL Save]** en publiceert u uw aangepaste bron. Raadpleeg deze [pagina](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource)voor meer informatie over de publicatie van aangepaste bronnen.

