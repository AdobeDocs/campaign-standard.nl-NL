---
title: Een openingspagina delen
description: Leer hoe u een openingspagina test en publiceert in Adobe Campaign.
page-status-flag: never-activated
uuid: fb7b087a-3292-496c-bc41-2e3012bacf59
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: landing-pages
discoiquuid: f7d4bb71-f957-4f86-97c7-8ac0a0030026
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 54612511de07edc3e6f3eea34ef095c26b35f4af

---


# Een bestemmingspagina testen en publiceren{#testing-publishing--landing-page}

## Publicatie van bestemmingspagina {#about-landing-page-publication}

Voordat u een bestemmingspagina publiceert, moet u tests uitvoeren: valideer de uitvoering, configureer de toegang en stel het einde van de levensduur van de bestemmingspagina in. Deze stappen zijn voorwaarden en moeten met voorzichtigheid worden uitgevoerd.

## De bestemmingspagina testen {#testing-the-landing-page-}

Aangezien de landingspagina uw platform en gegevens zal beïnvloeden, moet u zorgvuldig testen zijn uitvoering. Dit doet u als volgt:

1. Klik op de **[!UICONTROL Test]** knop op de actiebalk van de bestemmingspagina.
1. Selecteer in het testscherm een testprofiel en een testservice als de landingspagina abonnementen moet beheren.

   ![](assets/lp_test_2.png)

1. Voer gegevens in de velden in en selecteer opties.
1. Verzend de bestemmingspagina en controleer updates in het gegevensbestand.

   >[!IMPORTANT]
   >
   >Wanneer het formulier wordt verzonden, worden de service en het gebruikte profiel bijgewerkt.

1. Herhaal dit met verschillende profielen en gegevens.

   U kunt ook de miniatuur van de openingspagina genereren op basis van dit scherm.

>[!NOTE]
>
>Als u de voorvertoning van de bestemmingspagina wilt weergeven in de gebruikersinterface van Campagne, moet de URL van de toepassingsserver veilig zijn. In dat geval gebruikt u https:// in plaats van http:// om deze URL in te stellen bij het [configureren van uw merk](../../administration/using/branding.md#configuring-and-using-brands).

## Geldigheidsparameters instellen {#setting-up-validity-parameters}

Voordat u gaat publiceren, raden we u uit veiligheidsoverwegingen en om prestaties van het platform aan een vervaldatum in te stellen in de eigenschappen van de bestemmingspagina. Op de geselecteerde datum wordt de bestemmingspagina automatisch niet gepubliceerd. Dit doet u als volgt:

1. Bewerk de eigenschappen van de bestemmingspagina die via de ![](assets/edit_darkgrey-24px.png) knop in het dashboard van de bestemmingspagina worden benaderd.

   ![](assets/lp_edit_properties_button.png)

1. Vervaldatum en -tijd instellen in de **[!UICONTROL Publication]** sectie: de landingspagina wordt automatisch gepubliceerd op de opgegeven datum en is daarom niet langer beschikbaar.

   U kunt de tijdzone selecteren waarmee u rekening wilt houden voor deze datum en tijd.

1. Definieer een URL voor omleiding om bezoekers om te leiden wanneer ze proberen een niet-actieve bestemmingspagina te openen.

   ![](assets/lp_settings_general.png)

>[!IMPORTANT]
>
>U kunt ook een implementatiedatum en -tijd definiëren: de landingspagina wordt dan automatisch gepubliceerd op de opgegeven datum.

## Een openingspagina publiceren {#publishing-a-landing-page}

Wanneer u een landingspagina publiceert, wordt deze live weergegeven en kan deze worden geopend door uw bezoekers.

U kunt de publicatie of update van de bestemmingspagina op elk gewenst moment ongedaan maken en opnieuw publiceren via de **[!UICONTROL Publish]** knop. Als het opnieuw publiceren mislukt en u de bestemmingspagina nog niet hebt gepubliceerd, blijft de eerste versie online.
