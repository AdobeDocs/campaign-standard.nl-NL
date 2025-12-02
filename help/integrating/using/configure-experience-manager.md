---
title: De integratie van Campaign-Experience Manager configureren
description: Met de Adobe Experience Manager-integratie kunt u inhoud rechtstreeks in AEM maken en later in Adobe Campaign gebruiken.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: f56f5a19-6283-4eef-8127-c69a16a42a37
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 3%

---

# De integratie van Campaign-Experience Manager configureren {#configuration-aem}

Dankzij deze integratie tussen Adobe Campaign Standard en Adobe Experience Manager kunt u inhoud die in Adobe Experience Manager is gemaakt, gebruiken in uw Adobe Campaign-e-mails.

Met dit gebruiksgeval leert u hoe u e-mailinhoud maakt en beheert in Adobe Experience Manager en deze vervolgens voor uw marketingcampagnes gebruikt door deze inhoud in uw e-mails naar Adobe Campaign Standard te importeren.

## Vereisten {#prerequisites}

Zorg ervoor dat u de volgende elementen vooraf hebt:

* Een Adobe Experience Manager **auteursende** instantie
* Een Adobe Experience Manager **het publiceren** instantie
* Een Adobe Campaign-instantie

## Configuratie in Adobe Campaign Standard {#config-acs}

Om deze twee oplossingen samen te gebruiken, moet u hen vormen om met elkaar te verbinden.
Adobe Campaign configureren:

1. U moet eerst de **[!UICONTROL Adobe Experience Manager instance]** externe account configureren onder **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL External accounts menu]** .

1. Configureer het externe Adobe Experience Manager-account met uw **[!UICONTROL Server]** URL, **[!UICONTROL Account]** en **[!UICONTROL Password]** .

   ![](assets/aem_1.png)

1. Controleer of de optie **[!UICONTROL AEMResourceTypeFilter]** correct is geconfigureerd. Open het menu **[!UICONTROL Options]** via **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]** menu.

1. Controleer in het veld **[!UICONTROL Value (text)]** of de volgende syntaxis correct is:

   ```
   mcm/campaign/components/newsletter,mcm/campaign/components/campaign_newsletterpage,mcm/neolane/components/newsletter
   ```

   ![](assets/aem_2.png)

1. Vervolgens dupliceert u in het geavanceerde menu onder **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]** een van de bestaande sjablonen om een specifieke e-mailsjabloon voor Adobe Experience Manager te maken.

   ![](assets/aem_3.png)

1. Klik op het pictogram **[!UICONTROL Edit properties]** .

   ![](assets/aem_4.png)

1. Selecteer onder de vervolgkeuzelijst **[!UICONTROL Content]** in het veld **[!UICONTROL Adobe Experience Manager]** **[!UICONTROL Content source]** de externe account die u eerder hebt gemaakt in de vervolgkeuzelijst **[!UICONTROL Adobe Experience Manager account]** .

U moet nu de integratie configureren in Adobe Experience Manager.

## Configuratie in Adobe Experience Manager {#config-aem}

Voer de volgende stappen uit om Adobe Experience Manager te configureren met Adobe Campaign Standard:

1. Eerst moet u de replicatie tussen de Adobe Experience Manager-instanties voor schrijven en publiceren configureren. Verwijs naar deze [&#x200B; sectie &#x200B;](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignstandard.html?lang=nl-NL#configuring-adobe-experience-manager).

1. Sluit vervolgens Adobe Experience Manager aan op Adobe Campaign door een toegewezen **[!UICONTROL Cloud Service]** te configureren. Verwijs naar deze [&#x200B; sectie &#x200B;](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignstandard.html?lang=nl-NL#connecting-aem-to-adobe-campaign).

1. U moet nu de externalizer in Adobe Experience Manager op uw auteurinstantie vormen. Verwijs naar deze [&#x200B; sectie &#x200B;](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignstandard.html?lang=nl-NL#configuring-the-externalizer).
