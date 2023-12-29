---
title: Formulierdata voor landingspagina beheren
description: Leer hoe u formulierdata voor de landingspagina beheert.
audience: channels
content-type: reference
topic-tags: landing-pages
context-tags: landingPage,main
feature: Landing Pages
role: User
level: Intermediate
exl-id: 7083447c-4cac-41cb-8453-369819e0c7c1
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '835'
ht-degree: 12%

---

# Formulierdata voor landingspagina beheren{#managing-landing-page-form-data}

In de inhoud van de bestemmingspagina worden de inputgebieden gebruikt om gegevens van het gegevensbestand van de Campagne op te slaan of bij te werken.

Hiertoe moeten deze velden worden toegewezen aan databasevelden.

U kunt hun toewijzing definiëren en beheren via de **[!UICONTROL Form data]** in het linkerpalet.

![](assets/lp_form-data.png)

## Formuliervelden toewijzen {#mapping-form-fields}

Als u de Campagne-database naar wens wilt bijwerken, koppelt u relevante databasevelden aan invoerzone, keuzerondje of keuzelijstblokken van de landingspagina.

Hiervoor voert u de volgende stappen uit:

1. Selecteer een blok in de inhoud van de bestemmingspagina.

   >[!NOTE]
   >
   >De standaardvelden van de ingebouwde landingspagina&#39;s zijn vooraf geconfigureerd. U kunt deze desgewenst wijzigen.

1. Toegang krijgen tot de **[!UICONTROL Form data]** in het linkerpalet.

1. Als u het veldtype wilt wijzigen, selecteert u een waarde in het menu **[!UICONTROL HTML type of the field]** vervolgkeuzelijst.

   ![](assets/lp_html-field-type.png)

   >[!NOTE]
   >
   >Zie voor meer informatie over het gebruik van het type selectievakje op een bestemmingspagina de optie [Meerdere abonnementen op services bijwerken](#multiple-subscriptions) en [Selectievakje voor overeenkomst](#agreement-checkbox) secties.

1. Als u een veldtype selecteert dat niet compatibel is met het databaseveld dat momenteel is geselecteerd in het dialoogvenster **[!UICONTROL Field]** zone, zal een waarschuwingsbericht tonen. Selecteer een geschikte waarde voor optimale toewijzing.

   ![](assets/lp_field-type-warning.png)

1. Gebruik de **[!UICONTROL Field]** zone om een databaseveld te selecteren dat wordt gekoppeld aan het formulierveld.

   ![](assets/lp_select-database-field.png)

   >[!NOTE]
   >
   >Landingspagina&#39;s kunnen alleen worden toegewezen aan de **[!UICONTROL Profiles]** of **[!UICONTROL Service]** middelen.

   Wijs in dit voorbeeld de **Naam** veld van de landingspagina naar de **[!UICONTROL Last name]** van het **[!UICONTROL Profiles]** resource.

   ![](assets/lp_database-field-example.png)

1. Schakel indien nodig de optie **[!UICONTROL Mandatory]** in. In dat geval kan de landingspagina alleen worden verzonden als de gebruiker dit veld heeft ingevuld.

   ![](assets/lp_mandatory-option.png)

   Als een verplicht veld niet is ingevuld, wordt een foutbericht weergegeven wanneer de gebruiker de pagina verzendt.

1. Klikken **[!UICONTROL Confirm]** om uw wijzigingen op te slaan.

<!--If you choose a mandatory **[!UICONTROL Checkbox]**, make sure that it is of **[!UICONTROL Field]** type.-->

## Gegevensopslag en afstemming{#data-storage-and-reconciliation}

Met de parameters voor data-afstemming definieert u hoe de data die zijn ingevoerd op de landingspagina, worden beheerd nadat ze door de gebruiker zijn verzonden.

Dit doet u als volgt:

1. Bewerk de eigenschappen van de landingspagina die u via het pictogram ![](assets/edit_darkgrey-24px.png) in het dashboard van de landingspagina opent en geef de parameters voor **[!UICONTROL Job]** weer.

   ![](assets/lp_parameters_job.png)

1. Selecteer de **[!UICONTROL Reconciliation key]**: dit databaseveld wordt gebruikt om te bepalen of de bezoeker een profiel heeft dat al bekend is in de Adobe Campaign-database. Het kan bijvoorbeeld e-mail, voornaam, achternaam zijn. Met de afstemmingssleutel kunt u een profiel bijwerken of maken, afhankelijk van de **[!UICONTROL Update strategy]** hieronder gedefinieerde parameter.

1. Definieer **[!UICONTROL Form parameter mapping]**: in deze sectie kunt u de veldparameters van de landingspagina toewijzen, net als de parameters die in de afstemmingssleutel worden gebruikt.

1. Selecteer de **[!UICONTROL Update strategy]**: als met de afstemmingssleutel een bestaand databaseprofiel wordt hersteld, kunt u ervoor kiezen dat dit profiel wordt bijgewerkt met de gegevens die in het formulier zijn ingevoerd, of deze update voorkomen.

   ![](assets/lp_parameters_update-strategy.png)

## Meerdere abonnementen op services {#multiple-subscriptions}

U kunt verschillende selectievakjes gebruiken op één bestemmingspagina om gebruikers toe te staan zich van de veelvoudige diensten te abonneren of af te melden.

Hiervoor voert u de volgende stappen uit:

1. Bij het ontwerpen van de bestemmingspagina:

   * Selecteer een blok in het menu **[!UICONTROL Form data]** sectie, kiest u **[!UICONTROL Checkbox]** als het veldtype.

     ![](assets/lp_field-type-checkbox.png)

   * Als u bekend bent met HTML, kunt u ook handmatig een selectievakje invoegen met de opdracht **[!UICONTROL Show source]** knop.

     ![](assets/lp_show_source.png)

     Op deze manier kunt u het selectievakje op de gewenste plaats op de pagina invoegen.

     ![](assets/lp_manual-checkbox.png)

1. Controleer of het selectievakje is ingeschakeld in de inhoud. De **[!UICONTROL Type]** vervolgkeuzelijst wordt weergegeven in het dialoogvenster **[!UICONTROL Form data]** in het linkerpalet. Selecteren **[!UICONTROL Service and subscription]** in de lijst.

   ![](assets/lp_service-and-subscription.png)

1. Kies een optie in het menu **[!UICONTROL Behavior]** vervolgkeuzelijst.

   ![](assets/lp_checkbox-behavior.png)

1. Selecteer een [service](../../audiences/using/creating-a-service.md) in de overeenkomstige lijst.

   ![](assets/lp_checkbox-service.png)

1. Zorg ervoor dat de **[!UICONTROL Mandatory]** is uitgeschakeld. Anders hebben uw gebruikers geen keuze.

   ![](assets/lp_uncheck-mandatory.png)

1. Als u meer selectievakjes wilt toevoegen waarmee u zich kunt abonneren op andere services, herhaalt u de bovenstaande stappen zo vaak als nodig is.

   ![](assets/lp_multiple-checkboxes.png)

Nadat de bestemmingspagina is gepubliceerd, kunnen de gebruikers meerdere selectievakjes selecteren om zich te abonneren op meerdere nieuwsbrieven van dezelfde pagina.

## Selectievakje voor overeenkomst {#agreement-checkbox}

U kunt een selectievakje toevoegen waarmee het profiel moet worden gecontroleerd voordat de bestemmingspagina wordt verzonden.

Zo kunt u bijvoorbeeld vragen dat gebruikers hun toestemming geven voor het privacybeleid, of ze uw voorwaarden laten accepteren voordat ze het formulier verzenden.

>[!IMPORTANT]
>
>Dit selectievakje is verplicht voor uw gebruikers. Als deze optie niet is geselecteerd, kunnen ze de bestemmingspagina niet indienen.

Voer de volgende handelingen uit om dit selectievakje in te voegen en te configureren:

1. Bij het ontwerpen van de bestemmingspagina:

   * Selecteer een blok in het menu **[!UICONTROL Form data]** sectie, kiest u **[!UICONTROL Checkbox]** als het veldtype.

     ![](assets/lp_field-type-checkbox.png)

   * Als u bekend bent met HTML, kunt u ook handmatig een selectievakje invoegen met de opdracht **[!UICONTROL Show source]** knop.

     ![](assets/lp_show_source.png)

     <!--Manually insert a checkbox, such as in the example below:

      <!--Click **[!UICONTROL Hide source]**.-->

1. Controleer of het selectievakje is ingeschakeld.

   ![](assets/lp_select_checkbox.png)

1. De **[!UICONTROL Type]** vervolgkeuzelijst wordt weergegeven in het dialoogvenster **[!UICONTROL Form data]** in het linkerpalet. Selecteren **[!UICONTROL Agreement]** in de lijst.

   ![](assets/lp_form_data_drop-down.png)

   >[!NOTE]
   >
   >De **[!UICONTROL Agreement]** element wordt niet toegewezen aan een gebied van het gegevensbestand van de Campagne.

1. Klik op de knop ![](assets/lp-properties-icon.png) pictogram naast **[!UICONTROL Form data]** om toegang te krijgen tot geavanceerde eigenschappen van het selectievakje.

1. U kunt het bericht indien nodig bewerken.

   ![](assets/lp_agreement_message.png)

   Deze tekst wordt weergegeven als een waarschuwing als de gebruiker het selectievakje niet inschakelt voordat het formulier wordt verzonden.

   >[!NOTE]
   >
   >Deze handeling is standaard verplicht en kan niet worden gewijzigd.

1. Klik op **[!UICONTROL Confirm]**.

Elke keer dat de landingspagina wordt weergegeven, moet de gebruiker dit selectievakje inschakelen voordat het formulier wordt verzonden. Als dat niet het geval is, wordt de waarschuwing weergegeven en kan de gebruiker het formulier pas verzenden als het selectievakje is geactiveerd.