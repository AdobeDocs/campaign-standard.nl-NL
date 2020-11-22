---
solution: Campaign Standard
product: campaign
title: Informatie over sms-berichten
description: Ontdek de belangrijkste specifieke kenmerken van het SMS-kanaal in Adobe Campaign.
audience: channels
content-type: reference
topic-tags: sms-messages
delivercontext-tags: deliveryCreation,wizard;delivery,smsContent,back
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 23%

---


# Informatie over sms-berichten{#about-sms-messages}

Met Adobe Campaign kunt u SMS-berichten (Short Message Service) verzenden.

>[!NOTE]
>
>SMS-kanaal is een invoegtoepassing. Controleer hiervoor uw licentieovereenkomst.

Voor SMS-berichten kunt u alleen in tekstindeling berichten maken, wijzigen en personaliseren. Je kunt ook een voorbeeld van je SMS-berichten bekijken voordat ze worden verzonden.

De lengte van een SMS-bericht is beperkt tot 160 tekens als het in GSM-codering is en slechts 70 tekens als het in Unicode is. Bepaalde speciale tekens kunnen echter de lengte van het bericht beïnvloeden. For more on this, refer to the [SMS encoding](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration) section.

SMS-berichten kunnen worden gemaakt via het **[!UICONTROL Marketing activities]** menu, een campagne of een workflow. Zie [Een SMS-bericht](../../channels/using/creating-an-sms-message.md)maken.

Als u SMS-berichten naar een mobiele telefoon wilt verzenden, hebt u het volgende nodig:

* Een extern **[!UICONTROL Routing]**-account dat geconfigureerd is op het kanaal **[!UICONTROL Mobile (SMS)]** met de modus **[!UICONTROL Bulk delivery]**. Raadpleeg de sectie [Routering](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing) voor meer informatie.
* Een leveringssjabloon die correct aan dit externe account is gekoppeld.

**Verwante onderwerpen:**

* [Sjablonen beheren](../../start/using/marketing-activity-templates.md)
* [SMS-configuratie](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing)
* [Sms-rapport](../../reporting/using/sms-report.md)
* [Campaign Standard - gids voor mobiel gebruik](https://helpx.adobe.com/nl/campaign/kb/acs-mobile.html)

## Sjabloon voor verzending via SMS {#sms-delivery-template}

Adobe Campaign biedt een leveringssjabloon voor mobiele apparaten. Deze sjabloon moet correct zijn gekoppeld aan de externe account die voor het **[!UICONTROL Mobile (SMS)]** kanaal wordt gebruikt. Om tot het toegang te hebben en het te wijzigen:

1. Kies **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]** in het menu Geavanceerd.
1. Houd de muisaanwijzer boven de **[!UICONTROL Send via SMS]** sjabloon en selecteer de optie **Element** dupliceren.
1. Selecteer de nieuwe sjabloon.
1. Klik op de knop **[!UICONTROL Edit properties]**.
1. Controleer in het **[!UICONTROL Advanced parameters]** gedeelte van de sjablooneigenschappen of de sjabloon is gekoppeld aan de externe account die moet worden gebruikt voor het verzenden van SMS.

   ![](assets/sms_template.png)

**Verwante onderwerpen:**

* [Sjablonen beheren](../../start/using/marketing-activity-templates.md)
