---
title: Informatie over sms-berichten
description: Ontdek de belangrijkste specifieke kenmerken van het SMS-kanaal in Adobe Campaign.
audience: channels
content-type: reference
topic-tags: sms-messages
delivercontext-tags: deliveryCreation,wizard;delivery,smsContent,back
feature: SMS
role: User
level: Beginner
exl-id: a7f22d92-dbf9-4c2b-8fc1-1e31d1e5e79c
source-git-commit: b5e98c07ee55cab0b6a628a97162ccd64711501a
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 21%

---

# Informatie over sms-berichten{#about-sms-messages}

Met Adobe Campaign kunt u SMS-berichten (Short Message Service) verzenden.

>[!NOTE]
>
>SMS-kanaal is een invoegtoepassing. Controleer hiervoor uw licentieovereenkomst.

Voor SMS-berichten kunt u alleen in tekstindeling berichten maken, wijzigen en personaliseren. Je kunt ook een voorbeeld van je SMS-berichten bekijken voordat ze worden verzonden.

De lengte van een SMS-bericht is beperkt tot 160 tekens als het in GSM-codering is en slechts 70 tekens als het in Unicode is. Bepaalde speciale tekens kunnen echter de lengte van het bericht beïnvloeden. Raadpleeg voor meer informatie de [SMS-codering](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration) sectie.

SMS-berichten kunnen worden gemaakt op basis van de **[!UICONTROL Marketing activities]** vanuit een campagne, of in een workflow, zie [Een SMS-bericht maken](../../channels/using/creating-an-sms-message.md).

Als u SMS-berichten naar een mobiele telefoon wilt verzenden, hebt u het volgende nodig:

* Een extern **[!UICONTROL Routing]**-account dat geconfigureerd is op het kanaal **[!UICONTROL Mobile (SMS)]** met de modus **[!UICONTROL Bulk delivery]**. Raadpleeg de sectie [Routering](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing) voor meer informatie.
* Een leveringssjabloon die correct aan dit externe account is gekoppeld.

**Verwante onderwerpen:**

* [Sjablonen beheren](../../start/using/marketing-activity-templates.md)
* [SMS-configuratie](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing)
* [Sms-rapport](../../reporting/using/sms-report.md)
* [Campaign Standard - gids voor mobiel gebruik](../../channels/using/get-started-communication-channels.md)

## Sjabloon voor verzending via SMS {#sms-delivery-template}

Adobe Campaign biedt een leveringssjabloon voor mobiele apparaten. Deze sjabloon moet correct zijn gekoppeld aan de externe account die wordt gebruikt voor de **[!UICONTROL Mobile (SMS)]** kanaal. Om tot het toegang te hebben en het te wijzigen:

1. Selecteren **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]** in het geavanceerde menu.
1. Houd de aanwijzer boven de **[!UICONTROL Send via SMS]** sjabloon met de muis en selecteer de **Element dupliceren** -optie.
1. Selecteer de nieuwe sjabloon.
1. Klik op de knop **[!UICONTROL Edit properties]**.
1. In de **[!UICONTROL Advanced parameters]** van de sjablooneigenschappen, zorg er dan voor dat de sjabloon is gekoppeld aan de externe account die moet worden gebruikt voor het verzenden van SMS.

   ![](assets/sms_template.png)

**Verwante onderwerpen:**

* [Sjablonen beheren](../../start/using/marketing-activity-templates.md)
