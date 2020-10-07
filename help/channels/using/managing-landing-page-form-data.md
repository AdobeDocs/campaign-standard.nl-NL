---
title: Formulierdata voor landingspagina beheren
description: Leer hoe u formulierdata voor de landingspagina beheert.
page-status-flag: never-activated
uuid: 5b222ea2-6628-457f-a618-bfc0e5eb93dd
contentOwner: lemaitre
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: landing-pages
discoiquuid: 899c7152-f415-4df9-b4b4-5ff3470a4e32
context-tags: landingPage,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '394'
ht-degree: 100%

---


# Formulierdata voor landingspagina beheren{#managing-landing-page-form-data}

## De eigenschappen wijzigen van formulierdata voor de landingspagina{#changing-a-landing-page-form-data-properties}

U kunt databasevelden koppelen aan blokken voor invoerzones, keuzerondjes of selectievakjes. Selecteer het blok en voer de **[!UICONTROL Form data]** in het palet in.

![](assets/delivery_content_9.png)

* In de invoerzone **Field** (Veld) selecteert u het databaseveld dat u wilt koppelen aan het formulierveld.
* Met de optie **Mandatory** (Verplicht) kunt u de verzending van de pagina alleen toestaan als de gebruiker het veld heeft ingevuld. Als een verplicht veld niet is ingevuld, wordt een foutbericht weergegeven.

## Formuliervelden toewijzen {#mapping-form-fields}

Invoervelden worden gebruikt om data in de Campaign-database op te slaan of bij te werken. Hiervoor moet u databasevelden koppelen aan blokken voor invoerzones, keuzerondjes of selectievakjes. Dit doet u als volgt:

1. Selecteer een blok op de landingspagina.
1. Vul het onderdeel **[!UICONTROL Form data]** in het palet in.

   ![](assets/editing_lp_content_4.png)

1. Kies een databaseveld dat u wilt koppelen aan het formulierveld in de **[!UICONTROL Field]**-selectiezone. Landingspagina&#39;s kunnen alleen worden toegewezen aan **profielen**.

1. Schakel indien nodig de optie **[!UICONTROL Mandatory]** in. De pagina kan alleen worden verzonden als de gebruiker dit veld heeft ingevuld. Als een verplicht veld niet is ingevuld, verschijnt een foutbericht wanneer de gebruiker de pagina valideert.

1. Definieer het veldtype door bijvoorbeeld **[!UICONTROL Text]**, **[!UICONTROL Number]** of **[!UICONTROL Date]** te kiezen in het selectiegebied van **[!UICONTROL HTML type of the field]**.
Als u een verplichte optie kiest voor **[!UICONTROL Checkbox]**, moet u controleren of deze van het type **[!UICONTROL Field]** is.

>[!NOTE]
>
>De standaardvelden van de ingebouwde landingspagina&#39;s zijn vooraf geconfigureerd. U kunt deze desgewenst wijzigen.

## Dataopslag en afstemming{#data-storage-and-reconciliation}

Met de parameters voor data-afstemming definieert u hoe de data die zijn ingevoerd op de landingspagina, worden beheerd nadat ze door de gebruiker zijn verzonden.

Dit doet u als volgt:

1. Bewerk de eigenschappen van de landingspagina die u via het pictogram ![](assets/edit_darkgrey-24px.png) in het dashboard van de landingspagina opent en geef de parameters voor **[!UICONTROL Job]** weer.

   ![](assets/lp_parameters_4.png)

1. Selecteer **[!UICONTROL Reconciliation key]**: deze databasevelden (bijvoorbeeld: e-mail, voornaam, achternaam) worden gebruikt om te bepalen of de bezoeker een profiel heeft dat al bekend is in de Adobe Campaign-database. Zo kunt u een profiel bijwerken of maken volgens de gedefinieerde parameters voor de updatestrategie.
1. Definieer **[!UICONTROL Form parameter mapping]**: in deze sectie kunt u de veldparameters van de landingspagina toewijzen, net als de parameters die in de afstemmingssleutel worden gebruikt.
1. Selecteer **[!UICONTROL Update strategy]**: als een bestaand databaseprofiel wordt hersteld met de afstemmingssleutel, kunt u dit profiel bijwerken met de data die in het formulier zijn ingevoerd, of juist voorkomen dat het profiel wordt bijgewerkt.
