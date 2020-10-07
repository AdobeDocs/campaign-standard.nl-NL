---
title: De integratie van Campaign en Experience Manager configureren
description: Met de Adobe Experience Manager-integratie kunt u inhoud rechtstreeks in AEM maken en later in Adobe Campaign gebruiken.
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 3%

---


# De integratie van Campaign en Experience Manager configureren {#configuration-aem}

Dankzij deze integratie tussen Adobe Campaign Standard en Adobe Experience Manager kunt u inhoud die in Adobe Experience Manager is gemaakt, gebruiken in uw Adobe Campaign-e-mails.

Met dit gebruiksgeval leert u hoe u e-mailinhoud maakt en beheert in Adobe Experience Manager en deze vervolgens voor uw marketingcampagnes gebruikt door deze inhoud in uw e-mails naar Adobe Campaign Standard te importeren.

## Vereisten {#prerequisites}

Zorg ervoor dat u de volgende elementen vooraf hebt:

* Een Adobe Experience Manager- **ontwerpinstantie**
* Een Adobe Experience Manager- **publicatie** -instantie
* Een Adobe Campaign-instantie

## Configuratie in Adobe Campaign Standard {#config-acs}

Om deze twee oplossingen samen te gebruiken, moet u hen vormen om met elkaar te verbinden.
Adobe Campaign configureren:

1. U moet eerst de **[!UICONTROL Adobe Experience Manager instance]** externe account configureren onder **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL External accounts menu]**.

1. Configureer het externe Adobe Experience Manager-account met uw **[!UICONTROL Server]** URL **[!UICONTROL Account]** en **[!UICONTROL Password]**.

   ![](assets/aem_1.png)

1. Controleer of de **[!UICONTROL AEMResourceTypeFilter]** optie correct is geconfigureerd. Open het **[!UICONTROL Options]** menu via **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]** .

1. Controleer in het **[!UICONTROL Value (text)]** veld of de volgende syntaxis correct is:

   ```
   mcm/campaign/components/newsletter,mcm/campaign/components/campaign_newsletterpage,mcm/neolane/components/newsletter
   ```

   ![](assets/aem_2.png)

1. Vervolgens dupliceert u in het menu Geavanceerd onder **[!UICONTROL Resources]** > **[!UICONTROL Templates]** **[!UICONTROL Delivery templates]**> een van de bestaande sjabloon om een e-mailsjabloon te maken die specifiek is voor Adobe Experience Manager.

   ![](assets/aem_3.png)

1. Klik op het **[!UICONTROL Edit properties]** pictogram.

   ![](assets/aem_4.png)

1. Selecteer onder de **[!UICONTROL Content]** vervolgkeuzelijst **[!UICONTROL Adobe Experience Manager]** in het **[!UICONTROL Content source]** veld uw eerder gemaakte externe account in de **[!UICONTROL Adobe Experience Manager account]**.

U moet nu de integratie configureren in Adobe Experience Manager.

## Configuratie in Adobe Experience Manager {#config-aem}

Voer de volgende stappen uit om Adobe Experience Manager te configureren met Adobe Campaign Standard:

1. Eerst moet u de replicatie tussen de Adobe Experience Manager-instanties voor schrijven en publiceren configureren. Refer to this [section](https://docs.adobe.com/content/help/en/experience-manager-65/administering/integration/campaignstandard.html#configuring-adobe-experience-manager).

1. Sluit vervolgens Adobe Experience Manager aan op Adobe Campaign door een speciale **[!UICONTROL Cloud Service]** configuratie te configureren. Refer to this [section](https://docs.adobe.com/content/help/en/experience-manager-65/administering/integration/campaignstandard.html#connecting-aem-to-adobe-campaign).

1. U moet nu de externalizer in Adobe Experience Manager op uw auteurinstantie vormen. Refer to this [section](https://docs.adobe.com/content/help/en/experience-manager-65/administering/integration/campaignstandard.html#configuring-the-externalizer).

