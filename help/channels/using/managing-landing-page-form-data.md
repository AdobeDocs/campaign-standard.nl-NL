---
solution: Campaign Standard
product: campaign
title: Formulierdata voor landingspagina beheren
description: Leer hoe u formulierdata voor de landingspagina beheert.
audience: channels
content-type: reference
topic-tags: landing-pages
context-tags: landingPage,main
feature: Landingspagina's
role: User
level: Intermediate
exl-id: 7083447c-4cac-41cb-8453-369819e0c7c1
source-git-commit: c56d0e0ab4496ae769dc504107f677ef6ea74068
workflow-type: tm+mt
source-wordcount: '837'
ht-degree: 15%

---

# Formulierdata voor landingspagina beheren{#managing-landing-page-form-data}

In de inhoud van de bestemmingspagina worden de inputgebieden gebruikt om gegevens van het gegevensbestand van de Campagne op te slaan of bij te werken.

Hiertoe moeten deze velden worden toegewezen aan databasevelden.

U kunt de toewijzing ervan definiëren en beheren via de sectie **[!UICONTROL Form data]** in het linkerpalet.

![](assets/lp_form-data.png)

## Formuliervelden toewijzen {#mapping-form-fields}

Als u de Campagne-database naar wens wilt bijwerken, koppelt u relevante databasevelden aan invoerzone, keuzerondje of keuzelijstblokken van de landingspagina.

Volg de onderstaande stappen om dit te doen:

1. Selecteer een blok in de inhoud van de bestemmingspagina.

   >[!NOTE]
   >
   >De standaardvelden van de ingebouwde landingspagina&#39;s zijn vooraf geconfigureerd. U kunt deze desgewenst wijzigen.

1. Open de sectie **[!UICONTROL Form data]** in het linkerpalet.

1. Als u het veldtype wilt wijzigen, selecteert u een waarde in de vervolgkeuzelijst **[!UICONTROL HTML type of the field]**.

   ![](assets/lp_html-field-type.png)

   >[!NOTE]
   >
   >Voor meer bij het gebruiken van het checkbox type in een het landen pagina, zie [veelvoudige de dienstabonnementen ](#multiple-subscriptions) en [checkbox van de Overeenkomst](#agreement-checkbox) secties bijwerken.

1. Als u een veldtype selecteert dat niet compatibel is met het databaseveld dat momenteel is geselecteerd in de zone **[!UICONTROL Field]**, wordt een waarschuwingsbericht weergegeven. Selecteer een geschikte waarde voor optimale toewijzing.

   ![](assets/lp_field-type-warning.png)

1. Gebruik de zone **[!UICONTROL Field]** om een databaseveld te selecteren dat wordt gekoppeld aan het formulierveld.

   ![](assets/lp_select-database-field.png)

   >[!NOTE]
   >
   >Landingspagina&#39;s kunnen alleen worden toegewezen met de **[!UICONTROL Profiles]**- of **[!UICONTROL Service]**-bronnen.

   In dit voorbeeld wijst u het veld **Naam** van de landingspagina toe aan het veld **[!UICONTROL Last name]** van de bron **[!UICONTROL Profiles]**.

   ![](assets/lp_database-field-example.png)

1. Schakel indien nodig de optie **[!UICONTROL Mandatory]** in. In dat geval kan de landingspagina alleen worden verzonden als de gebruiker dit veld heeft ingevuld.

   ![](assets/lp_mandatory-option.png)

   Als een verplicht veld niet is ingevuld, wordt een foutbericht weergegeven wanneer de gebruiker de pagina verzendt.

1. Klik **[!UICONTROL Confirm]** om uw veranderingen te bewaren.

<!--If you choose a mandatory **[!UICONTROL Checkbox]**, make sure that it is of **[!UICONTROL Field]** type.-->

## Dataopslag en afstemming{#data-storage-and-reconciliation}

Met de parameters voor data-afstemming definieert u hoe de data die zijn ingevoerd op de landingspagina, worden beheerd nadat ze door de gebruiker zijn verzonden.

Dit doet u als volgt:

1. Bewerk de eigenschappen van de landingspagina die u via het pictogram ![](assets/edit_darkgrey-24px.png) in het dashboard van de landingspagina opent en geef de parameters voor **[!UICONTROL Job]** weer.

   ![](assets/lp_parameters_job.png)

1. Selecteer **[!UICONTROL Reconciliation key]**: dit databaseveld wordt gebruikt om te bepalen of de bezoeker een profiel heeft dat al bekend is in de Adobe Campaign-database. Het kan bijvoorbeeld e-mail, voornaam, achternaam zijn. Met de reconciliatietoets kunt u een profiel bijwerken of maken, volgens de parameter **[!UICONTROL Update strategy]** die hieronder wordt gedefinieerd.

1. Definieer **[!UICONTROL Form parameter mapping]**: in deze sectie kunt u de veldparameters van de landingspagina toewijzen, net als de parameters die in de afstemmingssleutel worden gebruikt.

1. Selecteer **[!UICONTROL Update strategy]**: als met de afstemmingssleutel een bestaand databaseprofiel wordt hersteld, kunt u ervoor kiezen dat dit profiel wordt bijgewerkt met de gegevens die in het formulier zijn ingevoerd, of in plaats daarvan deze update voorkomen.

   ![](assets/lp_parameters_update-strategy.png)

## Meerdere abonnementen op services {#multiple-subscriptions}

U kunt verschillende selectievakjes gebruiken op één bestemmingspagina om gebruikers toe te staan zich van de veelvoudige diensten te abonneren of af te melden.

Volg de onderstaande stappen om dit te doen:

1. Bij het ontwerpen van de bestemmingspagina:

   * Selecteer een blok, en van **[!UICONTROL Form data]** sectie, kies **[!UICONTROL Checkbox]** als gebiedstype.

      ![](assets/lp_field-type-checkbox.png)

   * Als u bekend bent met HTML, kunt u ook handmatig een selectievakje invoegen met de knop **[!UICONTROL Show source]**.

      ![](assets/lp_show_source.png)

      Op deze manier kunt u het selectievakje op de gewenste plaats op de pagina invoegen.

      ![](assets/lp_manual-checkbox.png)

1. Controleer of het selectievakje is ingeschakeld in de inhoud. De vervolgkeuzelijst **[!UICONTROL Type]** wordt weergegeven in de sectie **[!UICONTROL Form data]** van het linkerpalet. Selecteer **[!UICONTROL Service and subscription]** in de lijst.

   ![](assets/lp_service-and-subscription.png)

1. Kies een optie in de vervolgkeuzelijst **[!UICONTROL Behavior]**.

   ![](assets/lp_checkbox-behavior.png)

1. Selecteer een [service](../../audiences/using/creating-a-service.md) in de corresponderende lijst.

   ![](assets/lp_checkbox-service.png)

1. Controleer of de optie **[!UICONTROL Mandatory]** is uitgeschakeld. Anders hebben uw gebruikers geen keuze.

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

   * Selecteer een blok, en van **[!UICONTROL Form data]** sectie, kies **[!UICONTROL Checkbox]** als gebiedstype.

      ![](assets/lp_field-type-checkbox.png)

   * Als u bekend bent met HTML, kunt u ook handmatig een selectievakje invoegen met de knop **[!UICONTROL Show source]**.

      ![](assets/lp_show_source.png)

      <!--Manually insert a checkbox, such as in the example below:

      <!--Click **[!UICONTROL Hide source]**.-->

1. Controleer of het selectievakje is ingeschakeld.

   ![](assets/lp_select_checkbox.png)

1. De vervolgkeuzelijst **[!UICONTROL Type]** wordt weergegeven in de sectie **[!UICONTROL Form data]** van het linkerpalet. Selecteer **[!UICONTROL Agreement]** in de lijst.

   ![](assets/lp_form_data_drop-down.png)

   >[!NOTE]
   >
   >Het **[!UICONTROL Agreement]** element wordt niet in kaart gebracht aan een gebied van het gegevensbestand van de Campagne.

1. Klik op het pictogram ![](assets/lp-properties-icon.png) naast **[!UICONTROL Form data]** om de geavanceerde eigenschappen van het selectievakje te openen.

1. U kunt het bericht indien nodig bewerken.

   ![](assets/lp_agreement_message.png)

   Deze tekst wordt weergegeven als een waarschuwing als de gebruiker het selectievakje niet inschakelt voordat het formulier wordt verzonden.

   >[!NOTE]
   >
   >Deze handeling is standaard verplicht en kan niet worden gewijzigd.

1. Klik op **[!UICONTROL Confirm]**.

Elke keer dat de landingspagina wordt weergegeven, moet de gebruiker dit selectievakje inschakelen voordat het formulier wordt verzonden. Als dat niet het geval is, wordt de waarschuwing weergegeven en kan de gebruiker het formulier pas verzenden als het selectievakje is geactiveerd.