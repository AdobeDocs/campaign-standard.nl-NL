---
title: De integratie van Campaign-Experience Manager configureren
description: Met de Adobe Experience Manager-integratie kunt u inhoud rechtstreeks in AEM maken en later in Adobe Campaign gebruiken.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: f56f5a19-6283-4eef-8127-c69a16a42a37
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 3%

---

# De integratie van Campaign-Experience Manager configureren {#configuration-aem}

Dankzij deze integratie tussen Adobe Campaign Standard en Adobe Experience Manager kunt u inhoud die in Adobe Experience Manager is gemaakt, gebruiken in uw Adobe Campaign-e-mails.

Met dit gebruiksgeval leert u hoe u e-mailinhoud maakt en beheert in Adobe Experience Manager en deze vervolgens voor uw marketingcampagnes gebruikt door deze inhoud in uw e-mails naar Adobe Campaign Standard te importeren.

## Vereisten {#prerequisites}

Zorg ervoor dat u de volgende elementen vooraf hebt:

* An Adobe Experience Manager **ontwerpen** instance
* An Adobe Experience Manager **publiceren** instance
* Een Adobe Campaign-instantie

## Configuratie in Adobe Campaign Standard {#config-acs}

Om deze twee oplossingen samen te gebruiken, moet u hen vormen om met elkaar te verbinden.
Adobe Campaign configureren:

1. U moet eerst het **[!UICONTROL Adobe Experience Manager instance]** externe rekening onder **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL External accounts menu]**.

1. De externe Adobe Experience Manager-account configureren met uw **[!UICONTROL Server]** URL, **[!UICONTROL Account]** en **[!UICONTROL Password]**.

   ![](assets/aem_1.png)

1. Controleer of de **[!UICONTROL AEMResourceTypeFilter]** is correct geconfigureerd. Toegang krijgen tot de **[!UICONTROL Options]** menu onder **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]** -menu.

1. In de **[!UICONTROL Value (text)]** -veld, controleer of de volgende syntaxis correct is:

   ```
   mcm/campaign/components/newsletter,mcm/campaign/components/campaign_newsletterpage,mcm/neolane/components/newsletter
   ```

   ![](assets/aem_2.png)

1. Kies vervolgens in het menu Geavanceerd onder **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]** dupliceer een van de bestaande sjablonen om een e-mailsjabloon te maken die specifiek is voor Adobe Experience Manager.

   ![](assets/aem_3.png)

1. Klik op de knop **[!UICONTROL Edit properties]** pictogram.

   ![](assets/aem_4.png)

1. Onder de **[!UICONTROL Content]** vervolgkeuzelijst, selecteert u **[!UICONTROL Adobe Experience Manager]** in de **[!UICONTROL Content source]** veld en uw eerder gemaakte externe account in het dialoogvenster **[!UICONTROL Adobe Experience Manager account]**.

U moet nu de integratie configureren in Adobe Experience Manager.

## Configuratie in Adobe Experience Manager {#config-aem}

Voer de volgende stappen uit om Adobe Experience Manager te configureren met Adobe Campaign Standard:

1. Eerst moet u de replicatie tussen de Adobe Experience Manager-instanties voor schrijven en publiceren configureren. Zie dit [sectie](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignstandard.html?lang=nl-NL#configuring-adobe-experience-manager).

1. Sluit vervolgens Adobe Experience Manager aan op Adobe Campaign door een speciale toepassing te configureren **[!UICONTROL Cloud Service]**. Zie dit [sectie](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignstandard.html?lang=nl-NL#connecting-aem-to-adobe-campaign).

1. U moet nu de externalizer in Adobe Experience Manager op uw auteurinstantie vormen. Zie dit [sectie](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignstandard.html?lang=nl-NL#configuring-the-externalizer).
