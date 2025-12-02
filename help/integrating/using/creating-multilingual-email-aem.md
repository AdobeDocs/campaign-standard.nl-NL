---
title: Een meertalige e-mail maken met de Adobe Experience Manager-integratie.
description: Met de Adobe Experience Manager-integratie kunt u inhoud rechtstreeks in AEM maken en later in Adobe Campaign gebruiken.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 0f66fe2b-22b1-49d7-a080-29b00941a2cc
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '616'
ht-degree: 3%

---

# Een meertalige e-mail maken met de integratie van Adobe Experience Manager {#creating-multilingual-email-aem}

Met dit document leert u hoe u een meertalige e-mail kunt maken met Adobe Experience Manager-inhoud en -taalkopieën.

De voorwaarden zijn:

* Toegang tot een AEM-instantie die is geconfigureerd voor integratie.
* Toegang tot een Adobe Campaign-instantie die is geconfigureerd voor integratie.
* Een Adobe Campaign-sjabloon voor meertalige e-mail die is geconfigureerd om AEM-inhoud te ontvangen.

## Nieuwe e-mailinhoud maken in Adobe Experience Manager {#creating-email-content-aem}

1. Selecteer **[!UICONTROL Site]** op de startpagina van Adobe Experience Manager.

   ![](assets/aem_acs_1.png)

1. Selecteer in welke map u de pagina wilt maken en klik op **[!UICONTROL Create]** en **[!UICONTROL Page]** . Hier maken we onze pagina in de map en_us, onze standaardtaal.

   ![](assets/aem_acs_2.png)

1. Selecteer de sjabloon **[!UICONTROL Adobe Campaign Email (ACS)]** .

1. Vul de eigenschappen van uw e-mail in en klik op **[!UICONTROL Create]** .

   ![](assets/aem_acs_3.png)

1. Open uw nieuwe e-mailinhoud en pas deze indien nodig aan. Raadpleeg [deze pagina](../../integrating/using/creating-email-experience-manager.md#editing-email-aem) voor meer informatie.

   ![](assets/aem_acs_4.png)

1. Selecteer op het tabblad **[!UICONTROL Workflow]** de **[!UICONTROL Approve for Adobe Campaign]** -validatieworkflow. U kunt geen e-mail verzenden in Adobe Campaign als er inhoud wordt gebruikt die niet is goedgekeurd.

   ![](assets/aem_acs_7.png)

1. Klik **[!UICONTROL Complete]** dan **[!UICONTROL Newsletter review]** van het **[!UICONTROL Complete work item]** venster.

1. Klik op **[!UICONTROL Complete]** en vervolgens op **[!UICONTROL Newsletter approval]** . Zodra de parameters voor inhoud en verzending zijn gedefinieerd, kunt u doorgaan met het goedkeuren, voorbereiden en verzenden van de e-mail in Adobe Campaign Standard.

   ![](assets/aem_acs_8.png)

## Taalkopieën maken {#creating-language-copies}

Nadat u uw e-mailinhoud hebt ontworpen, moet u nu uw taalkopieën maken die gesynchroniseerd worden met Adobe Campaign Standard als varianten.

1. Selecteer de eerder gemaakte pagina en klik op **[!UICONTROL Create]** en **[!UICONTROL Language Copy]** .

   ![](assets/aem_acs_5.png)

1. Selecteer de eerder gemaakte e-mailinhoud die in de gekozen talen wordt vertaald en klik op **[!UICONTROL Next]** .

   ![](assets/aem_acs_6.png)

1. Selecteer in de vervolgkeuzelijst **[!UICONTROL Target language(s)]** in welke taal uw inhoud wordt vertaald en klik op **[!UICONTROL Next]** .

   ![](assets/aem_acs_9.png)

1. Klik op **[!UICONTROL Create]**.

Uw taalexemplaren worden nu gecreeerd, kunt u uw inhoud nu uitgeven afhankelijk van de gekozen taal.

>[!CAUTION]
>
>Elke taalkopie moet worden goedgekeurd via de validatieworkflow van **[!UICONTROL Approve for Adobe Campaign]** . U kunt geen e-mail verzenden in Adobe Campaign als er inhoud wordt gebruikt die niet is goedgekeurd.

![](assets/aem_acs_11.png)

## Meertalige inhoud maken in Adobe Campaign Standard {#multilingual-acs}

1. Klik op de startpagina van Adobe Campaign Standard op **[!UICONTROL Create an email]** .

   ![](assets/aem_acs_12.png)

1. Selecteer uw Adobe Campaign-sjabloon voor meertalige e-mail die is geconfigureerd om Adobe Experience Manager-inhoud te ontvangen. Meer leren op hoe te om een malplaatje tot stand te brengen verbonden aan uw instantie van Adobe Experience Manager, verwijs naar deze [ pagina ](../../integrating/using/configure-experience-manager.md#config-acs).

   >[!NOTE]
   >
   >In dit geval moet u de ingebouwde sjabloon **[!UICONTROL Multilingual email (mailMultiLang)]** dupliceren om uw meertalige e-mail te kunnen verzenden.

   ![](assets/aem_acs_13.png)

1. Vul de **[!UICONTROL Properties]** en **[!UICONTROL Audience]** van uw e-mail in en klik op **[!UICONTROL Create]** .

1. Controleer in **[!UICONTROL Edit properties]** of uw Adobe Experience Manager-account correct is ingesteld in de vervolgkeuzelijst **[!UICONTROL Content]** .

   ![](assets/aem_acs_20.png)

1. Klik op **[!UICONTROL Language copy creation]**.

   ![](assets/aem_acs_16.png)

1. Selecteer de eerder gemaakte Adobe Experience Manager-inhoud en klik op **[!UICONTROL Confirm]** . De Adobe Experience Manager-inhoud die hier wordt weergegeven, is alleen gevalideerde inhoud en kan op de bijbehorende **[!UICONTROL Label]** en **[!UICONTROL Path]** worden gefilterd.

   >[!NOTE]
   >
   >De gekozen taalkopie wordt ingesteld als standaard. U kunt deze kopie later wijzigen in het blok **[!UICONTROL Content variant]** .

   ![](assets/aem_acs_17.png)

1. Klik op **[!UICONTROL Create variants]** om uw meertalige inhoud te koppelen. Adobe Campaign Standard zal dan automatisch de andere taalexemplaren aan deze inhoud verbinden. De gemaakte varianten hebben dezelfde label- en codetaal als die welke in Adobe Experience Manager is gekozen.

   ![](assets/aem_acs_18.png)

1. Klik indien nodig op het blok **[!UICONTROL Content variant]** om de standaardvariant te wijzigen en klik op **[!UICONTROL Confirm]** .

   ![](assets/aem_acs_19.png)

1. Als uw inhoud of varianten in Adobe Experience Manager worden bijgewerkt, kunt u deze rechtstreeks in Adobe Campaign Standard synchroniseren met de knop **[!UICONTROL Refresh AEM contents]** .

1. Uw e-mail kan nu worden verzonden. Voor meer informatie over dit, verwijs naar deze [ pagina ](../../sending/using/get-started-sending-messages.md).

   >[!NOTE]
   >
   >U kunt geen e-mail verzenden in Adobe Campaign als er AEM-inhoud wordt gebruikt die niet is goedgekeurd.

Uw doelgroep ontvangt uw e-mail afhankelijk van de set **[!UICONTROL Preferred languages]** in de **[!UICONTROL Profiles]** . Meer leren op hoe te om profielen en aangewezen talen uit te geven, verwijs naar deze [ pagina ](../../audiences/using/editing-profiles.md).
