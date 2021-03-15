---
solution: Campaign Standard
product: campaign
title: De integratie van Campaign en Experience Manager configureren
description: Met de Adobe Experience Manager-integratie kunt u inhoud rechtstreeks in AEM maken en later in Adobe Campaign gebruiken.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
role: Gegevensarchitect
level: Intermediair
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '345'
ht-degree: 3%

---


# De integratie van Campaign en Experience Manager configureren {#configuration-aem}

Dankzij deze integratie tussen Adobe Campaign Standard en Adobe Experience Manager kunt u inhoud die in Adobe Experience Manager is gemaakt, gebruiken in uw Adobe Campaign-e-mails.

Met dit gebruiksgeval leert u hoe u e-mailinhoud maakt en beheert in Adobe Experience Manager en deze vervolgens voor uw marketingcampagnes gebruikt door deze inhoud in uw e-mails naar Adobe Campaign Standard te importeren.

## Vereisten {#prerequisites}

Zorg ervoor dat u de volgende elementen vooraf hebt:

* Een Adobe Experience Manager **authoring**-instantie
* Een Adobe Experience Manager **publishing**-instantie
* Een Adobe Campaign-instantie

## Configuratie in Adobe Campaign Standard {#config-acs}

Om deze twee oplossingen samen te gebruiken, moet u hen vormen om met elkaar te verbinden.
Adobe Campaign configureren:

1. U moet eerst de **[!UICONTROL Adobe Experience Manager instance]** externe account configureren onder **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL External accounts menu]**.

1. Configureer de externe Adobe Experience Manager-account met uw **[!UICONTROL Server]** URL, **[!UICONTROL Account]** en **[!UICONTROL Password]**.

   ![](assets/aem_1.png)

1. Controleer of de optie **[!UICONTROL AEMResourceTypeFilter]** correct is geconfigureerd. Open het menu **[!UICONTROL Options]** onder **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]** menu.

1. Controleer in het veld **[!UICONTROL Value (text)]** of de volgende syntaxis correct is:

   ```
   mcm/campaign/components/newsletter,mcm/campaign/components/campaign_newsletterpage,mcm/neolane/components/newsletter
   ```

   ![](assets/aem_2.png)

1. Vervolgens dupliceert u in het geavanceerde menu onder **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]** een van de bestaande sjablonen om een specifieke e-mailsjabloon voor Adobe Experience Manager te maken.

   ![](assets/aem_3.png)

1. Klik op het pictogram **[!UICONTROL Edit properties]**.

   ![](assets/aem_4.png)

1. Selecteer **[!UICONTROL Adobe Experience Manager]** in het veld **[!UICONTROL Content source]** onder de vervolgkeuzelijst **[!UICONTROL Content]** en selecteer vervolgens uw eerder gemaakte externe account in **[!UICONTROL Adobe Experience Manager account]**.

U moet nu de integratie configureren in Adobe Experience Manager.

## Configuratie in Adobe Experience Manager {#config-aem}

Voer de volgende stappen uit om Adobe Experience Manager te configureren met Adobe Campaign Standard:

1. Eerst moet u de replicatie tussen de Adobe Experience Manager-instanties voor schrijven en publiceren configureren. Zie deze [sectie](https://docs.adobe.com/content/help/en/experience-manager-65/administering/integration/campaignstandard.html#configuring-adobe-experience-manager).

1. Sluit vervolgens Adobe Experience Manager aan op Adobe Campaign door een speciale **[!UICONTROL Cloud Service]** te configureren. Zie deze [sectie](https://docs.adobe.com/content/help/en/experience-manager-65/administering/integration/campaignstandard.html#connecting-aem-to-adobe-campaign).

1. U moet nu de externalizer in Adobe Experience Manager op uw auteurinstantie vormen. Zie deze [sectie](https://docs.adobe.com/content/help/en/experience-manager-65/administering/integration/campaignstandard.html#configuring-the-externalizer).

