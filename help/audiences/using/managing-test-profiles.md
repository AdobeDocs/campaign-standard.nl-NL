---
title: Testprofielen beheren
description: Leer hoe u testprofielen beheert.
page-status-flag: never-activated
uuid: eb4d893b-3724-4b15-9312-1ec74784368d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
discoiquuid: 37320ec5-196c-4260-8156-98932da3e4a5
context-tags: seedMember,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 767d4233236019213003961aae1abb317198e581

---


# Testprofielen beheren {#managing-test-profiles}

## Testprofielen {#about-test-profiles}

Met de testprofielen kunt u zich richten op extra ontvangers die niet voldoen aan de gedefinieerde doelcriteria. Ze worden toegevoegd aan het publiek van een bericht om frauduleus gebruik van de database van de ontvanger op te sporen of om ervoor te zorgen dat de e-mails in de postvakken aankomen.

U kunt uw testprofielen beheren via het menu Geavanceerd **[!UICONTROL Profiles & audiences > Test profiles]**.

Een testprofiel bevat fictieve contactinformatie, of contactinformatie die door de afzender wordt gecontroleerd, die dan in een bericht in de volgende context kan worden gebruikt:

* Voor het verzenden van **proefdrukken**: Het Bewijs is een specifiek bericht dat wordt gebruikt om het bericht te controleren alvorens de definitieve levering naar ontvangers te verzenden. Een proeftestprofiel is verantwoordelijk voor de controle van de aflevering met betrekking tot de inhoud en de vorm ervan. Zie Proefdrukken [verzenden](../../sending/using/sending-proofs.md).
* Voor **e-mailrendering**: Het testprofiel voor e-mail renderen wordt gebruikt om te controleren hoe een bericht wordt weergegeven volgens het bericht in het postvak dat het bericht ontvangt. Webmail, berichtservice, mobiel, enzovoort. Zie [E-mailrendering](../../sending/using/email-rendering.md).

   Het gebruik van de rendering **via e-mail** is alleen-lezen. Testprofielen voor dit gebruik zijn alleen offline beschikbaar in Adobe Campagne.

* Als **overvulling**: Het bericht wordt naar het testprofiel verzonden enkel aangezien het naar het belangrijkste doel wordt verzonden. Zie [Overvullen](../../sending/using/using-traps.md)gebruiken.
* Aan **Voorproef** berichten: U kunt een testprofiel selecteren wanneer u een voorbeeld weergeeft van een bericht om de personalisatie-elementen te testen. Zie [Berichten](/help/sending/using/previewing-messages.md)voorvertonen.

![](assets/test_profile.png)

## Testprofielen maken {#creating-test-profiles}

1. Kies in het menu Geavanceerd via het logo van Adobe Campagne de optie **Profielen en publiek > Testprofielen** om de lijst met testprofielen te openen.

   ![](assets/test_profile_creation_1.png)

1. Klik in het **[!UICONTROL Test profiles]** dashboard op **Maken**.

   ![](assets/test_profile_creation_2.png)

1. Voer de gegevens voor dit profiel in.

   ![](assets/test_profile_creation_3.png)

1. Selecteer het gewenste gebruik voor het testprofiel.

   ![](assets/test_profile_creation_4.png)

1. Voer zo nodig de contactkanalen **[!UICONTROL Email, Telephone, Mobile, Mobile app]** en het adres van het testprofiel in.

   >[!NOTE]
   >
   >U kunt een e-mailindeling van uw voorkeur definiëren: **[!UICONTROL Text]** of **[!UICONTROL HTML]**.

1. Geef een gebeurtenistype en de gegevens voor deze gebeurtenis op als u dit testprofiel wilt gebruiken om de personalisatie van een transactiemelding te testen.
1. Klik **[!UICONTROL Create]** om het testprofiel op te slaan.

Het testprofiel wordt vervolgens toegevoegd aan de lijst met profielen.

**Verwant onderwerp:**

[Video over het maken van een testprofiel](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/test-profiles.html)

## Testprofielen bewerken {#editing-test-profiles}

U kunt als volgt een testprofiel bewerken en de bijbehorende gegevens raadplegen of het profiel wijzigen:

1. Selecteer het testprofiel dat u wilt bewerken door op de afbeelding te klikken.
1. Raadpleeg of wijzig de velden.

   ![](assets/test_profile_edit.png)

1. Klik **[!UICONTROL Save]** als u de wijzigingen hebt ingevoerd of selecteer de naam van het testprofiel en ga vervolgens **[!UICONTROL Test profiles]** in de sectie boven aan het scherm terug naar het dashboard voor testprofielen.
