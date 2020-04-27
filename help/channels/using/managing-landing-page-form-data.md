---
title: Landingspaginaformuliergegevens beheren
description: Leer hoe u landingspagina-formuliergegevens beheert.
page-status-flag: never-activated
uuid: 5b222ea2-6628-457f-a618-bfc0e5eb93dd
contentOwner: lemaitre
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: landing-pages
discoiquuid: 899c7152-f415-4df9-b4b4-5ff3470a4e32
context-tags: landingPage,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 8c24e048c698f7ad699e83a753c114fcfd25f6a0

---


# Landingspaginaformuliergegevens beheren{#managing-landing-page-form-data}

## De eigenschappen van landingspaginaformuliergegevens wijzigen{#changing-a-landing-page-form-data-properties}

U kunt databasevelden koppelen aan invoerzone, keuzerondje of keuzelijstblokken. U doet dit door het blok te selecteren en het **[!UICONTROL Form data]** in het palet in te voeren.

![](assets/delivery_content_9.png)

* In de invoerzone **Veld** kunt u een databaseveld selecteren dat u wilt koppelen aan het formulierveld.
* Met de optie **Verplicht** kunt u de verzending van de pagina alleen toestaan als de gebruiker het veld heeft ingevuld. Als een verplicht veld niet is ingevuld, wordt een foutbericht weergegeven.

## Formuliervelden toewijzen {#mapping-form-fields}

Invoervelden worden gebruikt om gegevens op te slaan of bij te werken in de Campagne-database. Hiervoor moet u databasevelden koppelen aan invoerzone, keuzerondje of keuzelijstblokken. Dit doet u als volgt:

1. Selecteer een blok op de bestemmingspagina.
1. Vul het **[!UICONTROL Form data]** onderdeel in het palet in.

   ![](assets/editing_lp_content_4.png)

1. Kies een databaseveld dat u wilt koppelen aan het formulierveld in de **[!UICONTROL Field]** selectiezone. Openingspagina&#39;s kunnen alleen worden toegewezen met **profielen**.

1. Schakel indien nodig de **[!UICONTROL Mandatory]** optie in. De pagina kan alleen worden verzonden als de gebruiker dit veld heeft ingevuld. Als een verplicht veld niet wordt ingevuld, wordt een foutbericht weergegeven wanneer de gebruiker de pagina valideert.

1. Definieer het veldtype door bijvoorbeeld **[!UICONTROL Text]** of in **[!UICONTROL Number]** het **[!UICONTROL Date]** **[!UICONTROL HTML type of the field]** selectiegebied te kiezen.
Als u een verplichte optie kiest, moet u controleren of deze van het **[!UICONTROL Checkbox]****[!UICONTROL Field]** type is.

>[!NOTE]
>
>De standaardvelden van de ingebouwde bestemmingspagina&#39;s zijn vooraf geconfigureerd. U kunt deze desgewenst wijzigen.

## Gegevensopslag en afstemming{#data-storage-and-reconciliation}

Met de parameters voor het afstemmen van gegevens kunt u definiëren hoe de gegevens die op de landingspagina worden ingevoerd, worden beheerd nadat deze door een gebruiker zijn verzonden.

Dit doet u als volgt:

1. Bewerk de eigenschappen van de openingspagina die via het ![](assets/edit_darkgrey-24px.png) pictogram in het dashboard van de bestemmingspagina worden benaderd en geef de **[!UICONTROL Job]** parameters weer.

   ![](assets/lp_parameters_4.png)

1. Selecteer de **[!UICONTROL Reconciliation key]**: deze databasevelden (bijvoorbeeld: e-mail, voornaam, achternaam) worden gebruikt om te bepalen of de bezoeker een profiel heeft dat al bekend is in de Adobe Campagne-database. Zo kunt u een profiel bijwerken of maken volgens de gedefinieerde parameters voor de updatestrategie.
1. Definieer de **[!UICONTROL Form parameter mapping]**: in deze sectie kunt u de veldparameters van de bestemmingspagina en die van de afstemmingssleutel in kaart brengen.
1. Selecteer de **[!UICONTROL Update strategy]**: als met de afstemmingssleutel een bestaand databaseprofiel wordt hersteld, kunt u ervoor kiezen dat dit profiel wordt bijgewerkt met de gegevens die in het formulier zijn ingevoerd, of deze update voorkomen.
