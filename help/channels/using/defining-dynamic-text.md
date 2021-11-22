---
title: Dynamische tekst definiëren
description: Leer hoe u verschillende teksten dynamisch aan de gebruiker kunt weergeven volgens de voorwaarden die in Adobe Campaign zijn gedefinieerd.
audience: designing
content-type: reference
topic-tags: defining-conditional-content
feature: SMS
role: User
level: Beginner
exl-id: 649e3428-a3bf-470f-923c-04d9a57a208f
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '213'
ht-degree: 3%

---

# Dynamische tekst definiëren{#defining-dynamic-text}

Dynamische tekst wordt op dezelfde manier gedefinieerd als dynamische inhoud. Zie de [Dynamische inhoud definiëren](../../designing/using/personalization.md#defining-dynamic-content-in-an-email) sectie.

>[!NOTE]
>
>Voor SMS en push kunt u alleen dynamische tekst definiëren. U kunt zowel dynamische inhoud als tekst op een openingspagina definiëren. Als u dynamische tekst wilt definiëren met de [E-mailontwerper](../../designing/using/designing-content-in-adobe-campaign.md), zie [Dynamische inhoud in een e-mail definiëren](../../designing/using/personalization.md#defining-dynamic-content-in-an-email).

Note that surrogate pairs, characters not included in the Basic Multilingual Plane of the Unicode character set, cannot be stored in 2 bytes (16bits) and need to get encoded into 2 UTF-16 characters. Deze tekens zijn enkele CJK-ideografieën, de meeste emojis en sommige talen.
<br>These characters can cause some incompatibility issues in dynamic text. You need to perform strong tests before sending your messages.


The example below shows how to define dynamic text in an SMS message.

1. Select text in the body of your message or landing page.
1. Klik op **[!UICONTROL Enable dynamic text]**.

   ![](assets/dynamic_text_sms_1.png)

   De **[!UICONTROL Dynamic text]** wordt weergegeven in het palet. Het wordt gevormd op de zelfde manier zoals dynamische inhoud.

1. Selecteer een variant.

   ![](assets/dynamic_text_sms_2.png)

1. Definieer een voorwaarde voor deze variant.

   ![](assets/dynamic_text_sms_4.png)

Wanneer voor ten minste één variant een voorwaarde is gedefinieerd, wordt een paarse kader rond de dynamische tekst weergegeven.

![](assets/dynamic_text_sms_3.png)
