---
title: E-mailcontent maken in Adobe Experience Manager.
description: Met de Adobe Experience Manager-integratie kunt u inhoud rechtstreeks in AEM maken en later in Adobe Campaign gebruiken.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 72b99864-d9d9-4cf4-be06-dc5719a2e4f2
source-git-commit: 579404ddc128e25cc7f8f93dfec30663c7cf754e
workflow-type: tm+mt
source-wordcount: '511'
ht-degree: 2%

---

# Adobe Experience Manager-inhoud importeren in een Adobe Campaign-e-mail {#creating-email-aem}

Met dit document leert u hoe u e-mailinhoud maakt en beheert in Adobe Experience Manager en deze vervolgens voor uw marketingcampagnes gebruikt door deze inhoud in uw e-mails naar Adobe Campaign Standard te importeren.

De voorwaarden zijn:

* Toegang tot een AEM die voor de integratie wordt gevormd.
* Toegang tot een Adobe Campaign-instantie die is geconfigureerd voor integratie.
* Een Adobe Campaign e-mailsjabloon geconfigureerd voor het ontvangen van AEM inhoud.

## E-mailberichten openen in Adobe Experience Manager {#email-content-aem}

Meld u aan bij de Adobe Experience Manager-ontwerpinstantie en blader door uw site naar de map met uw e-mailinhoud.

>[!VIDEO](https://video.tv.adobe.com/v/29996)

## Nieuwe e-mailinhoud maken in Adobe Experience Manager {#creating-email-content-aem}

Er zijn verschillende sjablonen beschikbaar die specifiek zijn voor Adobe Campaign. U moet een van deze sjablonen gebruiken omdat deze vooraf gedefinieerde componenten bevatten die door Adobe Campaign worden ondersteund.

Standaard kunt u met twee vooraf gedefinieerde sjablonen e-mailinhoud voor Adobe Campaign maken.

* **[!UICONTROL Adobe Campaign Email]**: deze sjabloon bevat een standaardinhoud die u kunt aanpassen. U kunt kiezen tussen Adobe Campaign-e-mail (AC6.1) en Adobe Campaign-mail (ACS).
* **[!UICONTROL Importer Page]**: met deze sjabloon kunt u een ZIP-bestand importeren dat een HTML-bestand bevat met inhoud die u vervolgens kunt aanpassen.

1. Maak in Adobe Experience Manager een nieuwe **[!UICONTROL Page]**.

1. Selecteer de **[!UICONTROL Adobe Campaign Email]** sjabloon. Raadpleeg de volgende video voor de gedetailleerde stappen.

   >[!VIDEO](https://video.tv.adobe.com/v/29997)

1. Open uw nieuwe e-mailinhoud.

1. In de **[!UICONTROL Page properties]**, set **[!UICONTROL Adobe Campaign]** als de **[!UICONTROL Cloud Service Configuration]**. Hierdoor wordt communicatie mogelijk tussen uw inhoud en uw Adobe Campaign-instantie.

   Bekijk de volgende video voor meer informatie:

   >[!VIDEO](https://video.tv.adobe.com/v/29999)

## Een e-mail bewerken en verzenden {#editing-email-aem}

U kunt de e-mailinhoud bewerken door componenten en elementen toe te voegen. De gebieden van de verpersoonlijking kunnen worden gebruikt om een relevanter bericht te leveren dat op de gegevens van de ontvangers in Adobe Campaign wordt gebaseerd.

Een e-mailinhoud maken in Adobe Experience Manager:

1. Bewerk het onderwerp en de **[!UICONTROL Plain text]** versie van uw e-mail door de **[!UICONTROL Page properties]** > **[!UICONTROL Email]** van de hulpwerkplaats.

1. Toevoegen **[!UICONTROL Personalization fields]** via de **[!UICONTROL Text & Personalization]** component. Elke component komt overeen met een specifiek gebruik: afbeeldingen invoegen, personalisatie toevoegen, enz.

   Bekijk de volgende video voor meer informatie:

   >[!VIDEO](https://video.tv.adobe.com/v/29998)

1. Van de **[!UICONTROL Workflow]** selecteert u de **[!UICONTROL Approve for Adobe Campaign]** validatieworkflow. U kunt geen e-mail verzenden in Adobe Campaign als er inhoud wordt gebruikt die niet is goedgekeurd.

Uw e-mail verzenden in Adobe Campaign Standard:

1. Als de parameters voor inhoud en verzending eenmaal zijn gedefinieerd, maakt u een e-mailbericht op basis van een AEM-specifieke e-mailsjabloon in Adobe Campaign Standard.

+++ Meer weten over AEM specifieke template?

   1. Via het geavanceerde menu hebt u toegang tot **[!UICONTROL Resources]** `>` **[!UICONTROL Templates]** `>` **[!UICONTROL Delivery templates]**.

      ![](assets/aem_templates_1.png)

   1. Dupliceer of selecteer een van de leveringssjablonen.

   1. Van de **[!UICONTROL Properties]** van uw sjabloon, in de **[!UICONTROL Content]** vervolgkeuzelijst, selecteert u **[!UICONTROL Adobe Experience Manager as Content mode]** dan uw Adobe Experience Manager-account.

      ![](assets/aem_templates_2.png)

+++

   ![](assets/aem_send_1.png)

1. Vul de eigenschappen van uw e-mail in en klik **[!UICONTROL Create]** om uw AEM inhoud te kunnen selecteren.

1. Toegang krijgen tot de **[!UICONTROL Content]** blokkeren.

   ![](assets/aem_send_2.png)

1. Van de **[!UICONTROL Use Adobe Experience Manager content]** menu, klikt u op **[!UICONTROL Link AEM content]**.

   Selecteer vervolgens de inhoud die u in uw e-mail wilt gebruiken.

   ![](assets/aem_send_3.png)

1. Pas uw e-mail verder aan door extra parameters zoals doelpubliek en uitvoeringsprogramma door het dashboard te specificeren. Zodra gevormd, kunt u de e-maillevering nu verzenden. [Meer informatie](../../sending/using/confirming-the-send.md)

