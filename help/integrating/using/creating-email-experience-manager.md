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
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '414'
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

* **[!UICONTROL Adobe Campaign Email]**: Deze sjabloon bevat een standaardinhoud die u kunt aanpassen. U kunt kiezen tussen Adobe Campaign-e-mail (AC6.1) en Adobe Campaign-e-mail (ACS).
* **[!UICONTROL Importer Page]**: Met deze sjabloon kunt u een ZIP-bestand importeren dat een HTML-bestand bevat met inhoud die u vervolgens kunt aanpassen.

1. Maak in Adobe Experience Manager een nieuwe **[!UICONTROL Page]**.

1. Selecteer de sjabloon **[!UICONTROL Adobe Campaign Email]**. Raadpleeg de volgende video voor de gedetailleerde stappen.
   >[!VIDEO](https://video.tv.adobe.com/v/29997)

1. Open uw nieuwe e-mailinhoud.

1. In **[!UICONTROL Page properties]**, plaats **[!UICONTROL Adobe Campaign]** als **[!UICONTROL Cloud Service Configuration]**. Hierdoor wordt communicatie mogelijk tussen uw inhoud en uw Adobe Campaign-instantie.

   Bekijk de volgende video voor meer informatie:

   >[!VIDEO](https://video.tv.adobe.com/v/29999)

## Een e-mail bewerken en verzenden {#editing-email-aem}

U kunt de e-mailinhoud bewerken door componenten en elementen toe te voegen. De gebieden van de verpersoonlijking kunnen worden gebruikt om een relevanter bericht te leveren dat op de gegevens van de ontvangers in Adobe Campaign wordt gebaseerd.

Een e-mailinhoud maken in Adobe Experience Manager:

1. Bewerk het onderwerp en de **[!UICONTROL Plain text]**-versie van uw e-mail door het tabblad **[!UICONTROL Page properties]** > **[!UICONTROL Email]** van het secundaire bureaublad te openen.

1. Voeg **[!UICONTROL Personalization fields]** door de **[!UICONTROL Text & Personalization]** component toe. Elke component komt overeen met een specifiek gebruik: afbeeldingen invoegen, personalisatie toevoegen, enz.

   Bekijk de volgende video voor meer informatie:
   >[!VIDEO](https://video.tv.adobe.com/v/29998)

1. Selecteer op het tabblad **[!UICONTROL Workflow]** de validatieworkflow **[!UICONTROL Approve for Adobe Campaign]**. U kunt geen e-mail verzenden in Adobe Campaign als er inhoud wordt gebruikt die niet is goedgekeurd.

1. Zodra de parameters voor inhoud en verzending zijn gedefinieerd, kunt u doorgaan met het goedkeuren, voorbereiden en verzenden van de e-mail in Adobe Campaign Standard.

   Bekijk de volgende video voor meer informatie:

   >[!VIDEO](https://video.tv.adobe.com/v/23721)
