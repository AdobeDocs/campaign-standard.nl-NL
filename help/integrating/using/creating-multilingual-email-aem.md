---
solution: Campaign Standard
product: campaign
title: Een meertalige e-mail maken met de Adobe Experience Manager-integratie.
description: Met de Adobe Experience Manager-integratie kunt u inhoud rechtstreeks in AEM maken en later in Adobe Campaign gebruiken.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
translation-type: tm+mt
source-git-commit: 3672f0bc4ebc551c4eb34660a3a55d44fa726f1a
workflow-type: tm+mt
source-wordcount: '594'
ht-degree: 5%

---


# Een meertalige e-mail maken met de Adobe Experience Manager-integratie {#creating-multilingual-email-aem}

Met dit document leert u hoe u een meertalige e-mail kunt maken met Adobe Experience Manager-inhoud en -taalkopieën.

De voorwaarden zijn:

* Toegang tot een AEM die voor de integratie wordt gevormd.
* Toegang tot een Adobe Campaign-instantie die is geconfigureerd voor integratie.
* Een Adobe Campaign-sjabloon voor meertalige e-mail die is geconfigureerd voor het ontvangen van AEM inhoud.

## Nieuwe e-mailinhoud maken in Adobe Experience Manager {#creating-email-content-aem}

1. Selecteer **[!UICONTROL Site]** op de startpagina van Adobe Experience Manager.

   ![](assets/aem_acs_1.png)

1. Selecteer in welke map u de pagina wilt maken en klik op **[!UICONTROL Create]** en **[!UICONTROL Page]**. Hier maken we onze pagina in de map en_us, onze standaardtaal.

   ![](assets/aem_acs_2.png)

1. Selecteer de sjabloon **[!UICONTROL Adobe Campaign Email (ACS)]**.

1. Vul de eigenschappen van uw e-mail in en klik **[!UICONTROL Create]**.

   ![](assets/aem_acs_3.png)

1. Open uw nieuwe e-mailinhoud en pas deze indien nodig aan. Raadpleeg [deze pagina](../../integrating/using/creating-email-experience-manager.md#editing-email-aem) voor meer informatie.

   ![](assets/aem_acs_4.png)

1. Selecteer op het tabblad **[!UICONTROL Workflow]** de validatieworkflow **[!UICONTROL Approve for Adobe Campaign]**. U kunt geen e-mail verzenden in Adobe Campaign als er inhoud wordt gebruikt die niet is goedgekeurd.

   ![](assets/aem_acs_7.png)

1. Klik **[!UICONTROL Complete]** dan **[!UICONTROL Newsletter review]** van **[!UICONTROL Complete work item]** venster.

1. Klik op **[!UICONTROL Complete]** en vervolgens op **[!UICONTROL Newsletter approval]**. Zodra de parameters voor inhoud en verzending zijn gedefinieerd, kunt u doorgaan met het goedkeuren, voorbereiden en verzenden van de e-mail in Adobe Campaign Standard.

   ![](assets/aem_acs_8.png)

## Taalkopieën maken {#creating-language-copies}

Na het ontwerpen van uw e-mailinhoud moet u nu uw taalkopieën maken die gesynchroniseerd zijn met Adobe Campaign Standard als varianten.

1. Selecteer de eerder gemaakte pagina en klik op **[!UICONTROL Create]** en **[!UICONTROL Language Copy]**.

   ![](assets/aem_acs_5.png)

1. Selecteer de eerder gemaakte e-mailinhoud die in de gekozen talen wordt vertaald en klik op **[!UICONTROL Next]**.

   ![](assets/aem_acs_6.png)

1. Selecteer in de vervolgkeuzelijst **[!UICONTROL Target language(s)]** in welke taal uw inhoud wordt vertaald en klik op **[!UICONTROL Next]**.

   ![](assets/aem_acs_9.png)

1. Klik op **[!UICONTROL Create]**.

Uw taalexemplaren worden nu gecreeerd, kunt u uw inhoud nu uitgeven afhankelijk van de gekozen taal.

>[!CAUTION]
>
>Elke taalkopie moet worden goedgekeurd via de validatieworkflow **[!UICONTROL Approve for Adobe Campaign]**. U kunt geen e-mail verzenden in Adobe Campaign als er inhoud wordt gebruikt die niet is goedgekeurd.

![](assets/aem_acs_11.png)

## Meertalige inhoud maken in Adobe Campaign Standard {#multilingual-acs}

1. Klik op **[!UICONTROL Create an email]** vanaf de startpagina van Adobe Campaign Standard.

   ![](assets/aem_acs_12.png)

1. Selecteer uw Adobe Campaign-sjabloon voor meertalige e-mail die is geconfigureerd om Adobe Experience Manager-inhoud te ontvangen. Als u meer wilt weten over het maken van een sjabloon die is gekoppeld aan uw Adobe Experience Manager-instantie, raadpleegt u deze [pagina](../../integrating/using/configure-experience-manager.md#config-acs).

   >[!NOTE]
   >
   >In dit geval moet u de ingebouwde sjabloon **[!UICONTROL Multilingual email (mailMultiLang)]** dupliceren om uw meertalige e-mail te kunnen verzenden.

   ![](assets/aem_acs_13.png)

1. Vul **[!UICONTROL Properties]** en **[!UICONTROL Audience]** van uw e-mail in en klik **[!UICONTROL Create]**.

1. Controleer in de **[!UICONTROL Edit properties]** of uw Adobe Experience Manager-account correct is ingesteld in de vervolgkeuzelijst **[!UICONTROL Content]**.

   ![](assets/aem_acs_20.png)

1. Klik op **[!UICONTROL Language copy creation]**.

   ![](assets/aem_acs_16.png)

1. Selecteer de eerder gemaakte Adobe Experience Manager-inhoud en klik op **[!UICONTROL Confirm]**. De Adobe Experience Manager-inhoud die hier wordt weergegeven, is alleen gevalideerde inhoud en kan op **[!UICONTROL Label]** en **[!UICONTROL Path]** worden gefilterd.

   >[!NOTE]
   >
   >De gekozen taalkopie wordt ingesteld als standaard, u kunt deze later wijzigen in het blok **[!UICONTROL Content variant]**.

   ![](assets/aem_acs_17.png)

1. Klik op **[!UICONTROL Create variants]** om uw meertalige inhoud te koppelen. Adobe Campaign Standard zal dan automatisch de andere taalexemplaren aan deze inhoud verbinden. De gemaakte varianten hebben dezelfde label- en codetaal als die welke in Adobe Experience Manager is gekozen.

   ![](assets/aem_acs_18.png)

1. Klik op het blok **[!UICONTROL Content variant]** om uw standaardvariant indien nodig te wijzigen en klik **[!UICONTROL Confirm]**.

   ![](assets/aem_acs_19.png)

1. Als uw inhoud of varianten in Adobe Experience Manager worden bijgewerkt, kunt u deze in Adobe Campaign Standard rechtstreeks synchroniseren met de knop **[!UICONTROL Refresh AEM contents]**.

1. Uw e-mail kan nu worden verzonden. Raadpleeg deze [pagina](../../sending/using/get-started-sending-messages.md) voor meer informatie hierover.

Uw publiek ontvangt uw e-mail afhankelijk van **[!UICONTROL Preferred languages]** die in **[!UICONTROL Profiles]** wordt geplaatst. Raadpleeg deze [pagina](../../audiences/using/editing-profiles.md) voor meer informatie over het bewerken van profielen en voorkeurstalen.
