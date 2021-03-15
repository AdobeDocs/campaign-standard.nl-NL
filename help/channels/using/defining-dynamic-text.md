---
solution: Campaign Standard
product: campaign
title: Dynamische tekst definiëren
description: Leer hoe u verschillende teksten dynamisch aan de gebruiker kunt weergeven volgens de voorwaarden die in Adobe Campaign zijn gedefinieerd.
audience: designing
content-type: reference
topic-tags: defining-conditional-content
feature: Sms
role: Zakelijke praktiserer
level: Begin
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 3%

---


# Dynamische tekst definiëren{#defining-dynamic-text}

Dynamische tekst wordt op dezelfde manier gedefinieerd als dynamische inhoud. Raadpleeg de sectie [Dynamische inhoud definiëren](../../designing/using/personalization.md#defining-dynamic-content-in-an-email).

>[!NOTE]
>
>Voor SMS en push kunt u alleen dynamische tekst definiëren. U kunt zowel dynamische inhoud als tekst op een openingspagina definiëren. Zie [Dynamische inhoud definiëren in een e-mail](../../designing/using/personalization.md#defining-dynamic-content-in-an-email) als u dynamische tekst wilt definiëren met de [e-mailontwerper](../../designing/using/designing-content-in-adobe-campaign.md).

Vervangende paren, tekens die niet in het meertalig basisvlak van de Unicode-tekenset staan, kunnen niet in 2 bytes (16 bits) worden opgeslagen en moeten in 2 UTF-16-tekens worden gecodeerd. Deze tekens zijn enkele CJK-ideografieën, de meeste emojis en sommige talen.
<br>Deze tekens kunnen onverenigbaarheidsproblemen veroorzaken in dynamische tekst. U moet sterke tests uitvoeren alvorens uw berichten te verzenden.


In het onderstaande voorbeeld ziet u hoe u dynamische tekst in een SMS-bericht definieert.

1. Selecteer tekst in de tekst van het bericht of de landingspagina.
1. Klik op **[!UICONTROL Enable dynamic text]**.

   ![](assets/dynamic_text_sms_1.png)

   De optie **[!UICONTROL Dynamic text]** wordt weergegeven in het palet. Het wordt gevormd op de zelfde manier zoals dynamische inhoud.

1. Selecteer een variant.

   ![](assets/dynamic_text_sms_2.png)

1. Definieer een voorwaarde voor deze variant.

   ![](assets/dynamic_text_sms_4.png)

Wanneer voor ten minste één variant een voorwaarde is gedefinieerd, wordt een paarse kader rond de dynamische tekst weergegeven.

![](assets/dynamic_text_sms_3.png)
