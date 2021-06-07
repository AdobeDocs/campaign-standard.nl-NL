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
role: Business Practitioner
level: Intermediate
exl-id: 7083447c-4cac-41cb-8453-369819e0c7c1
source-git-commit: d84a11d4064938792a2e2c365b6085c263f55648
workflow-type: tm+mt
source-wordcount: '613'
ht-degree: 62%

---

# Formulierdata voor landingspagina beheren{#managing-landing-page-form-data}

## De eigenschappen wijzigen van formulierdata voor de landingspagina{#changing-a-landing-page-form-data-properties}

U kunt databasevelden koppelen aan blokken voor invoerzones, keuzerondjes of selectievakjes. U doet dit door het blok te selecteren en toegang te krijgen tot **[!UICONTROL Form data]** in het palet.

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

## Selectievakje voor overeenkomst {#agreement-checkbox}

U kunt een selectievakje toevoegen waarmee het profiel moet worden gecontroleerd voordat de bestemmingspagina wordt verzonden.

Zo kunt u bijvoorbeeld vragen dat gebruikers hun toestemming geven voor het privacybeleid, of ze uw voorwaarden laten accepteren voordat ze het formulier verzenden.

<!--This is particularly useful in the following case:

When a profile opens the landing page from an Outlook.com mailbox, Outlook checks whether the links on the landing page are suspicious. However, this Outlook security feature (called safelinks) has an unwanted effect: it automatically activates the buttons included on the landing page. Consequently, profiles are automatically subscribed or unsubscribed without confirmation when the landing page is displayed after clicking the email link, even if they do not submit the form.

![](assets/lp_submit_button.png)

To avoid this, Adobe recommends you always add to your landing page a checkbox which enables the profile to agree before proceeding with subscription or unsubscription.-->

>[!IMPORTANT]
>
>Dit selectievakje is verplicht voor uw gebruikers. Als deze optie niet is geselecteerd, kunnen ze de bestemmingspagina niet indienen.

Voer de volgende handelingen uit om dit selectievakje in te voegen en te configureren:

1. Klik bij het ontwerpen van de bestemmingspagina op **[!UICONTROL Show source]**.

   ![](assets/lp_show_source.png)

1. Voeg handmatig een selectievakje in, zoals in het onderstaande voorbeeld:

   ![](assets/lp_checkbox_code.png)

   <!--
   <div id="HtmlPage_htmlPage.line3" data-nl-format="datetime"><input type="checkbox" class="nl-dce-todo" data-nl-bindto="agreement" data-nl-agreementmsg="You must agree with the terms and conditions before proceeding" />I agree with the terms and conditions</div>
   -->

1. Klik op **[!UICONTROL Hide source]**.

1. Het nieuwe selectievakje wordt weergegeven. Selecteer het.

   ![](assets/lp_select_checkbox.png)

1. De corresponderende vervolgkeuzelijst wordt weergegeven in de sectie **[!UICONTROL Form data]** van het palet. Selecteer **[!UICONTROL Agreement]** in de lijst.

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