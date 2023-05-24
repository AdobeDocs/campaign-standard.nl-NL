---
title: Een Campaign-formulier maken in Experience Manager
description: Met de Adobe Experience Manager-integratie kunt u rechtstreeks in AEM formulieren maken om profielen te maken en bij te werken of abonnementen te beheren.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 61683639-3f71-4652-a138-acfc0e91e868
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '181'
ht-degree: 12%

---

# Een Campaign-formulier maken in Experience Manager {#creating-a-campaign-form-in-experience-manager}

U kunt &quot;formulieren&quot; maken op uw AEM en de velden in een formulier toewijzen aan de velden in de Adobe Campaign-database. Zo kunt u profielen maken en bijwerken of de abonnementen op een service beheren.

Een Adobe Campaign-formulier maken op uw AEM-site:

1. Maak in uw AEM-site een nieuwe pagina op basis van de **Adobe Campaign-profiel** sjabloon.

   ![](assets/aem_content_forms.png)

1. Selecteer in de pagina-eigenschappen de optie **[!UICONTROL Cloud Service]** komt overeen met uw Adobe Campaign-exemplaar.

   ![](assets/aem_content_forms_2.png)

1. Selecteer het formuliertype in het menu **[!UICONTROL Form Start]** component:

   * **Adobe Campaign: Profiel opslaan**
   * **Adobe Campaign: Abonneren op services**
   * **Adobe Campaign: Abonnement op services opzeggen**

1. Bewerk de inhoud van het formulier door verschillende velden en componenten toe te voegen die u kunt toewijzen aan de Adobe Campaign-databasevelden.
1. Test en publiceer het formulier om het toegankelijk te maken op uw AEM.

Raadpleeg de [gedetailleerde documentatie](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/aem-adobe-campaign/adobe-campaign-forms.html) voor meer informatie.
