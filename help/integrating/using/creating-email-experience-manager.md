---
title: Een e-mailinhoud maken in Adobe Experience Manager.
description: Met de integratie met Adobe Experience Manager kunt u inhoud rechtstreeks in AEM maken en deze later gebruiken in Adobe Campaign.
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 9efce905cd767013a22afb2a4d642e42b6616ef1

---


# Een Adobe Experience Manager-inhoud importeren in een e-mailbericht voor een Adobe-campagne {#creating-email-aem}

Met dit document leert u hoe u e-mailinhoud maakt en beheert in Adobe Experience Manager en deze vervolgens gebruikt voor uw marketingcampagnes door deze inhoud in uw e-mails te importeren in Adobe Campaign Standard.

De voorwaarden zijn:

* Toegang tot een instantie AEM die voor de integratie wordt gevormd.
* Toegang tot een Adobe Campagne-instantie die is geconfigureerd voor de integratie.
* Een e-mailsjabloon voor Adobe Campagne die is geconfigureerd voor het ontvangen van AEM-inhoud.

## E-mailberichten openen in Adobe Experience Manager {#email-content-aem}

Meld u aan bij de ontwerpinstantie van Adobe Experience Manager en blader door uw site naar de map met uw e-mailinhoud.

>[!VIDEO](https://video.tv.adobe.com/v/29996)

## Nieuwe e-mailinhoud maken in Adobe Experience Manager {#creating-email-content-aem}

Er zijn verschillende sjablonen beschikbaar die specifiek zijn voor Adobe Campaign. U moet een van deze sjablonen gebruiken omdat deze vooraf gedefinieerde componenten bevatten die door Adobe Campaign worden ondersteund.

Standaard kunt u met twee vooraf gedefinieerde sjablonen e-mailinhoud maken voor Adobe Campagne.

* **[!UICONTROL Adobe Campaign Email]**: Deze sjabloon bevat een standaardinhoud die u kunt aanpassen. U kunt kiezen tussen Adobe Campagne-e-mail (AC6.1) en Adobe Campagne-e-mail (ACS).
* **[!UICONTROL Importer Page]**: Met deze sjabloon kunt u een ZIP-bestand importeren dat een HTML-bestand bevat met inhoud die u vervolgens kunt aanpassen.

1. Maak een nieuwe versie in Adobe Experience Manager **[!UICONTROL Page]**.

1. Selecteer de **[!UICONTROL Adobe Campaign Email]** sjabloon. Raadpleeg de volgende video voor de gedetailleerde stappen.
   >[!VIDEO](https://video.tv.adobe.com/v/29997)

1. Open uw nieuwe e-mailinhoud.

1. In de **[!UICONTROL Page properties]**, plaats **[!UICONTROL Adobe Campaign]** als **[!UICONTROL Cloud Service Configuration]**. Hierdoor wordt communicatie mogelijk tussen uw inhoud en uw Adobe Campagne-instantie.

   Bekijk de volgende video voor meer informatie:

   >[!VIDEO](https://video.tv.adobe.com/v/29999)

## Een e-mail bewerken en verzenden {#editing-email-aem}

U kunt de e-mailinhoud bewerken door componenten en elementen toe te voegen. U kunt velden voor aanpassen gebruiken om een relevanter bericht weer te geven op basis van de gegevens van de ontvangers in Adobe Campaign.

Een e-mailinhoud maken in Adobe Experience Manager:

1. Bewerk het onderwerp en de **[!UICONTROL Plain text]** versie van uw e-mail door vanuit de assistent het tabblad **[!UICONTROL Page properties]** > **[!UICONTROL Email]** te openen.

1. Voeg toe **[!UICONTROL Personalization fields]** door de **[!UICONTROL Text & Personalization]** component. Elke component komt overeen met een specifiek gebruik: afbeeldingen invoegen, personalisatie toevoegen, enz.

   Bekijk de volgende video voor meer informatie:
   >[!VIDEO](https://video.tv.adobe.com/v/29998)

1. Selecteer op het **[!UICONTROL Workflow]** tabblad de **[!UICONTROL Approve for Adobe Campaign]** validatieworkflow. U kunt geen e-mail verzenden in Adobe Campagne als het inhoud gebruikt die niet is goedgekeurd.

1. Zodra de parameters voor inhoud en verzending zijn gedefinieerd, kunt u doorgaan met het goedkeuren, voorbereiden en verzenden van de e-mail in Adobe Campagne Standard.

   Bekijk de volgende video voor meer informatie:

   >[!VIDEO](https://video.tv.adobe.com/v/23721)
