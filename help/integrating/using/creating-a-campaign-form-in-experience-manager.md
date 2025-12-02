---
title: Een Campaign-formulier maken in Experience Manager
description: Met de Adobe Experience Manager-integratie kunt u rechtstreeks in AEM formulieren maken om profielen te maken en bij te werken of abonnementen te beheren.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 61683639-3f71-4652-a138-acfc0e91e868
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 12%

---

# Een Campaign-formulier maken in Experience Manager {#creating-a-campaign-form-in-experience-manager}

U kunt &quot;formulieren&quot; maken op uw AEM-sites en de velden in een formulier toewijzen aan de velden in de Adobe Campaign-database. Zo kunt u profielen maken en bijwerken of de abonnementen op een service beheren.

Een Adobe Campaign-formulier maken op uw AEM-site:

1. In uw plaats van AEM, creeer een nieuwe pagina die op het **1&rbrace; malplaatje van het Profiel van Adobe Campaign wordt gebaseerd.**

   ![](assets/aem_content_forms.png)

1. Selecteer in de pagina-eigenschappen de **[!UICONTROL Cloud Service]** die overeenkomt met uw Adobe Campaign-instantie.

   ![](assets/aem_content_forms_2.png)

1. Selecteer het formuliertype in de component **[!UICONTROL Form Start]** :

   * **Adobe Campaign: Sparen profiel**
   * **Adobe Campaign: Abonneren aan de Diensten**
   * **Adobe Campaign: Unsubscribe van de Diensten**

1. Bewerk de inhoud van het formulier door verschillende velden en componenten toe te voegen die u kunt toewijzen aan de Adobe Campaign-databasevelden.
1. Test en publiceer het formulier om het toegankelijk te maken op uw AEM-site.

Raadpleeg de [gedetailleerde documentatie](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/aem-adobe-campaign/adobe-campaign-forms.html) voor meer informatie.
