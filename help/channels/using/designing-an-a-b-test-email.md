---
title: Een e-mail met A/B-testfunctie ontwerpen
description: Ontdek de A/B-testfunctionaliteit en voer de volgende stappen uit om een e-mail op te stellen op basis van een A/B-testsjabloon in Adobe Campaign.
page-status-flag: never-activated
uuid: 104f6973-68a7-4692-a90a-a5570a980ec7
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: email-messages
discoiquuid: e249ba70-90d0-43f2-868c-ce9fdc7e642d
context-tags: delivery,abTesting,back;deliveryCreation,wizard;delivery,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '832'
ht-degree: 100%

---


# Een e-mail met A/B-testfunctie ontwerpen{#designing-an-a-b-test-email}

Met de A/B-testfunctionaliteit in Adobe Campaign kunt u twee tot drie e-mailvarianten definiëren. Elke variant wordt naar populatiesamples verzonden om te bepalen welke variant het beste resultaat oplevert. Zodra dit is bepaald, wordt de winnende variant naar de resterende populatie verzonden.

U kunt de content, het onderwerp of de afzender van de e-mail variëren.

>[!NOTE]
>
>A/B-tests op e-mails die zijn gemaakt in Adobe Experience Manager zijn niet mogelijk.

## Een e-mail met A/B-testfunctie maken {#creating-an-a-b-test-email}

U kunt een A/B-test maken met de wizard voor het maken van standaard-e-mails waaraan een stap voor de A/B-testconfiguratie is toegevoegd. Het maken van een standaard-e-mail wordt beschreven in de sectie [Een e-mail maken](../../channels/using/creating-an-email.md).

In de specifieke context van een A/B-test gaat dit als volgt:

1. Maak een nieuwe e-mail op basis van een van de drie A/B-testsjablonen, afhankelijk van het element dat u wilt variëren:

   * A/B-test op verzender
   * A/B-test op content
   * A/B-test op onderwerp

   ![](assets/create_ab_testing.png)

   >[!NOTE]
   >
   >Follow-up- en A/B-testsjablonen zijn standaard verborgen. Schakel het vakje voor A/B-testen aan de linkerkant (het zijpaneel **[!UICONTROL Filter]**) in om deze weer te geven.

1. Definieer de algemene eigenschappen en de doelgroep van de e-mail, net als voor een standaard-e-mail. Raadpleeg de sectie [Doelgroepen maken](../../audiences/using/creating-audiences.md).
1. Bij de vierde stap in de wizard Creation definieert u de A/B-testparameters:

   * **[!UICONTROL Number of variants]**: U kunt kiezen of u twee of drie varianten wilt gebruiken. Als u drie varianten kiest, kunt u deze keuze later niet wijzigen nadat deze stap is bevestigd in de wizard.
   * **[!UICONTROL Winning strategy]**: Selecteer het criterium dat moet worden gebruikt om de winnende variant te bepalen.
   * **[!UICONTROL Target breakdown]**: Kies welk percentage van de doelgroep elke variant zal ontvangen. Het resterende percentage ontvangt de winnende variant zodra deze is bepaald. De doelprofielen worden willekeurig geselecteerd.
   * **[!UICONTROL Winner sending method]**: Kies of u wilt dat de winnende variant automatisch wordt verzonden zodra deze is bepaald of dat u het verzenden naar de resterende populatie handmatig wilt bevestigen.
   * **[!UICONTROL Test duration]**: Geef de duur van de test op. De winnende variant wordt automatisch bepaald na deze duur. U kunt de winnende variant vóór het einde van de test handmatig kiezen in het e-maildashboard.

      De test moet ten minste één uur duren zodat alle trackingdata kunnen worden verzameld en correct in overweging kunnen worden genomen voor het selecteren van de winnende variant.
   ![](assets/ab_parameters.png)

1. Nadat de A/B-testparameters zijn gedefinieerd, gaat u naar de volgende stap in de wizard en definieert u de e-mailcontent. Afhankelijk van de sjabloon die u hebt gekozen, kunt u verschillende onderwerpen, verschillende namen van afzenders of verschillende content definiëren. Gebruik de carrousel om tussen de verschillende varianten van het element te navigeren. Raadpleeg de sectie [Contenteditor](../../designing/using/designing-content-in-adobe-campaign.md) voor meer informatie.

   ![](assets/create_ab_testing2.png)

1. Bevestig het maken van de e-mail. Het e-maildashboard wordt nu weergegeven.
1. Plan de verzending. De gedefinieerde datum geeft het begin van de A/B-test aan.
1. Controleer de A/B-testparameters die in het blok **[!UICONTROL A/B test parameters]** worden weergegeven. U kunt ze wijzigen totdat u het verzenden van de test bevestigt (stap 9) door het blok te selecteren.

   ![](assets/create_ab_testing3.png)

1. Bereid de verzending van de e-mail voor om het doel en het aantal berichten dat moet worden verzonden te analyseren. Raadpleeg de sectie [De verzending voorbereiden](../../sending/using/preparing-the-send.md).
1. Controleer voordat u de A/B-test verzendt, uw e-mail door proeven te verzenden.
1. Zodra de voorbereiding is voltooid, bevestigt u de verzending van de test. Na bevestiging kunnen de A/B-testparameters niet meer worden gewijzigd.

   De A/B-test begint op de datum die bij **[!UICONTROL Schedule]** is gedefinieerd. U kunt de voortgang ervan volgen met de blokken **[!UICONTROL A/B test]** en **[!UICONTROL Deployment]**.

   U kunt de winnende variant op elk gewenst moment handmatig selecteren als u de testduur wilt verkorten.

   Nadat het testen is voltooid, wordt een overzichtstabel weergegeven in het blok **[!UICONTROL A/B Test]**. Op deze manier kunt u de verschillende indicatoren bekijken voor de verschillende geteste varianten.

1. Als u **[!UICONTROL Send after confirmation]** als verzendingsmethode hebt geselecteerd, moet u de winnende variant handmatig selecteren om te beginnen met de verzending ervan naar de resterende populatie. Als u **[!UICONTROL Automatic]** hebt geselecteerd, wordt de winnende variant automatisch naar de resterende populatie verzonden zodra deze door het systeem is bepaald.

   >[!NOTE]
   >
   >Als er meerdere varianten in aanmerking komen, moet de winnende variant handmatig worden geselecteerd. U kunt de personen die de e-mail maken en wijzigen ervan op de hoogte brengen dat een variant is gekozen of moet worden geselecteerd. Zie [Adobe Campaign-meldingen](../../administration/using/sending-internal-notifications.md).

Uw e-mail is nu gedefinieerd en verzonden. U kunt de logboeken en rapporten van de e-mail openen om het succes van uw campagne te meten.

**Verwant onderwerp**:

Video over [Een e-mail maken](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/getting-started/create-email-from-homepage.html)

## Informatie over A/B-testindicatoren {#about-a-b-test-indicators}

In het e-maildashboard zijn verschillende indicatoren beschikbaar waarmee u uw A/B-test kunt meten: het aantal keer dat op een e-mail is geklikt, het aantal keer dat een e-mail is geopend, het aantal keer dat een e-mail niet is bezorgd, enzovoort.

Merk op dat de indicator **[!UICONTROL Estimated recipient reactivity]** een percentage is dat het aantal ontvangers dat op de e-mail heeft geklikt, vergelijkt met het aantal ontvangers dat de e-mail heeft geopend. Als bijvoorbeeld 10 ontvangers de e-mail hebben geopend en 5 ontvangers erop hebben geklikt, dan is de reactiviteitsgraad 50%.
