---
title: Informatie over SMS-berichten
description: Ontdek de belangrijkste specifieke kenmerken van het SMS-kanaal in Adobe Campaign.
page-status-flag: never-activated
uuid: 14dc7434-8171-4ad1-9540-52ca637659a9
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: sms-messages
discoiquuid: 6134fe72-77de-4fd0-b794-4d966effaccf
delivercontext-tags: deliveryCreation,wizard;delivery,smsContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 501ba6f97a86076116d4d84f43df674536e12f6a

---


# Informatie over SMS-berichten{#about-sms-messages}

Met Adobe Campaign kunt u SMS-berichten (Short Message Service) verzenden.

>[!NOTE]
>
>SMS-kanaal is een invoegtoepassing. Controleer uw licentieovereenkomst.

Voor SMS-berichten kunt u alleen in tekstindeling berichten maken, wijzigen en personaliseren. Je kunt ook een voorbeeld van je SMS-berichten bekijken voordat ze worden verzonden.

De lengte van een SMS-bericht is beperkt tot 160 tekens als het in GSM-codering is en slechts 70 tekens als het in Unicode is. Bepaalde speciale tekens kunnen echter de lengte van het bericht beïnvloeden. Raadpleeg het gedeelte [SMS-codering](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration) voor meer informatie hierover.

SMS-berichten kunnen worden gemaakt via het **[!UICONTROL Marketing activities]** menu, een campagne of een workflow. Zie [Een SMS-bericht](../../channels/using/creating-an-sms-message.md)maken.

Als u SMS-berichten naar een mobiele telefoon wilt verzenden, hebt u het volgende nodig:

* Een **[!UICONTROL Routing]** externe account die in de **[!UICONTROL Mobile (SMS)]** modus op het **[!UICONTROL Bulk delivery]** kanaal is geconfigureerd. Voor meer op dit, verwijs naar de [Verpletterende](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing) sectie.
* Een leveringssjabloon die correct is gekoppeld aan deze externe account.

**Verwante onderwerpen:**

* [Sjablonen beheren](../../start/using/marketing-activity-templates.md)
* [SMS-configuratie](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing)
* [SMS-rapport](../../reporting/using/sms-report.md)
* [Gids Standaard voor mobiele campagne](https://helpx.adobe.com/campaign/kb/acs-mobile.html)

## Sjabloon voor verzending via SMS {#sms-delivery-template}

Adobe Campaign biedt een leveringssjabloon voor mobiele apparaten. Deze sjabloon moet correct zijn gekoppeld aan de externe account die voor het **[!UICONTROL Mobile (SMS)]** kanaal wordt gebruikt. Om tot het toegang te hebben en het te wijzigen:

1. Kies **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]** in het menu Geavanceerd.
1. Houd de muisaanwijzer boven de **[!UICONTROL Send via SMS]** sjabloon en selecteer de optie **Element** dupliceren.
1. Selecteer de nieuwe sjabloon.
1. Klik op de **[!UICONTROL Edit properties]** knop.
1. Controleer in het **[!UICONTROL Advanced parameters]** gedeelte van de sjablooneigenschappen of de sjabloon is gekoppeld aan de externe account die moet worden gebruikt voor het verzenden van SMS.

   ![](assets/sms_template.png)

**Verwante onderwerpen:**

* [Sjablonen beheren](../../start/using/marketing-activity-templates.md)
