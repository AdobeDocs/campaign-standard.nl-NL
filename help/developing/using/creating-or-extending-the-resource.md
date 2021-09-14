---
title: De bron maken of uitbreiden
description: Ontdek hoe u een geheel nieuwe bron definieert.
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
feature: Data Model
role: Developer
level: Experienced
exl-id: b8731088-a675-4070-9036-bf2b5254e4e8
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '153'
ht-degree: 11%

---

# De bron maken of uitbreiden{#creating-or-extending-the-resource}

Beheerders kunnen een geheel nieuwe bron maken of een uitbreiding van een bestaande bron maken als u gegevens nodig hebt die geen deel uitmaken van het ingebouwde gegevensmodel.

Alleen de volgende ingebouwde bronnen kunnen worden uitgebreid:

* **[!UICONTROL Campaign (campaign)]**
* **[!UICONTROL Deliveries (delivery)]**
* **[!UICONTROL Landing page (Landingpage)]**
* **[!UICONTROL Profiles (profile)]**
* **[!UICONTROL Program (program)]**
* **[!UICONTROL Service (service)]**
* **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]**
* **[!UICONTROL Test profiles (seedMember)]**
* **[!UICONTROL Workflow (workflow)]**

Een bron maken of uitbreiden:

1. Klik **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom Resources]** op de knop **[!UICONTROL Create]**.
1. Kies de handeling die u wilt uitvoeren:

   * **[!UICONTROL Create a new resource]**: Voer de  **[!UICONTROL Label]** en de  **[!UICONTROL ID]** velden in. Het veld **[!UICONTROL ID]** is verplicht. Als u het veld Label leeg laat, wordt dit automatisch ingevuld met de id.

      ![](assets/schema_extension_2.png)

      >[!NOTE]
      >
      >Gebruik maximaal 30 tekens.

   * **[!UICONTROL Extend an existing resource]**: Selecteer de bron die u wilt uitbreiden.

      ![](assets/schema_extension_10.png)

1. Klik **[!UICONTROL Create]** om de bron te maken, die dan de status **[!UICONTROL Draft]** krijgt in het geval van een nieuwe bron of de status **[!UICONTROL Editing]** in het geval van een extensie.

Het nieuwe middel wordt gecreeerd en kan nu worden gevormd. Voor meer op middelconfiguratie, verwijs naar [Vormend de de gegevensstructuur van het middel](../../developing/using/configuring-the-resource-s-data-structure.md).
