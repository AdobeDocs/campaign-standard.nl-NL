---
title: Abonnement op een service bevestigen
description: Voer de volgende stappen uit om een bevestigingsbericht in te stellen voor profielen die zich abonneren op een service in Adobe Campaign.
page-status-flag: never-activated
uuid: 23e6c4c2-e2c7-472f-b616-36a95225ac1d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-subscriptions
discoiquuid: 1a24504e-7f9d-4297-b39e-c5f085b0f388
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 95e01eb33097fc76caac3f4dd5f5591461b887cf

---


# Abonnement op een service bevestigen{#confirming-subscription-to-a-service}

## Abonnementsbevestiging verzenden {#sending-subscription-confirmation}

In deze sectie wordt beschreven hoe u een automatisch aangepast bevestigingsbericht verzendt naar de profielen die zich op een specifieke service abonneren.

Wanneer u een bevestigingsbericht voor een abonnement (of unsubscription) aan de dienst wilt verzenden, kunt u het standaardbericht of een douanebericht gebruiken. De stappen voor het selecteren van een bevestigingsbericht worden voorgesteld in het [Creëren van een de dienstsectie](../../audiences/using/creating-a-service.md) .

Als u het standaardbericht wilt gebruiken, kunt u de inhoud van het bericht op de volgende manieren bewerken:
* U kunt de inhoud van het bericht alleen aanpassen met beperkte velden uit de context van de gebeurtenis.
* Dit bericht zal het zelfde voor alle diensten zijn die de standaardwijze gebruiken.

Als u voor een bepaalde service een specifieke e-mailbevestiging wilt verzenden, kunt u een aangepast bericht maken waarin u ook personalisatievelden uit andere bronnen kunt gebruiken. Om dit te doen, moet u een transactiebericht creëren en vormen. Naar dit bericht kan worden verwezen:
* Van de dienst zelf. Voor meer op dit, zie het [Vormen bevestigingsbericht van de dienst](#configuring-confirmation-message-from-service).
* Vanaf een bestemmingspagina met een abonnement. Voor meer op dit, zie het [Vormen bevestigingsbericht van een het landen pagina](#configuring-confirmation-message-from-landing-page).

## Bevestigingsbericht van een service configureren {#configuring-confirmation-message-from-service}

U wilt bijvoorbeeld automatisch een bevestigingsbericht sturen naar de bezoekers van uw website wanneer zij zich abonneren op uw nieuwsbrief.

U moet een transactie-e-mail vormen en dat bericht van de gewenste dienst (abonnement aan uw merknieuwsbrief in dit geval) van verwijzingen voorzien. Als u het transactiebericht wilt verrijken met servicegegevens, kunt u een afstemming definiëren wanneer u de gebeurtenis maakt.

Wanneer het vormen van het van de dienst, zal het bericht van de bevestigingstransactie slechts de eerste keer worden verzonden elke bezoeker aan die dienst intekent. Als een profiel al is geabonneerd, wordt er geen bevestigingsbericht meer naar dat profiel verzonden.

### Stap 1: Het bevestigingsbericht maken {#step-1--create-the-confirmation-email-1}

Er wordt automatisch een bevestigingsbericht verzonden naar elk profiel dat zich abonneert op de nieuwsbrief (via een landingspagina of op een andere manier). Het abonnement wordt beschouwd als een gebeurtenis en het e-mailbericht is een [transactiebericht](../../channels/using/about-transactional-messaging.md) dat zich richt op elk profiel dat zich op de service abonneert.

De stappen voor het maken van het bevestigingsbericht worden hieronder beschreven. Aangezien het transactionele bericht in de dienst van verwijzingen zal worden voorzien, moet u het eerst tot stand brengen.

#### De gebeurtenis maken {#create-the-event-1}

Het bevestigingsbericht is een transactiemelding wanneer het op een gebeurtenis reageert: het abonnement op een service. Dit bericht wordt verzonden ter bevestiging van uw abonnement op uw nieuwsbrief.

1. Maak een gebeurtenis via het menu **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]** , die u kunt openen via het logo van de Adobe-campagne.
1. Voer een label in, selecteer een doeldimensie en klik op **[!UICONTROL Create]**.

   De configuratiestappen worden voorgesteld in de het [Vormen sectie van het transactiemelding](../../administration/using/configuring-transactional-messaging.md) .

1. Klik in de **[!UICONTROL Fields]** sectie op de gegevensstructuur **[!UICONTROL Create element]** en voeg deze toe **[!UICONTROL publicLabel]** om de afstemming mogelijk te maken.

   ![](assets/confirmation_publicLabel-field.png)

   >[!NOTE]
   >
   >Het **[!UICONTROL publicLabel]** veld is verplicht. Als u deze niet toevoegt aan de gegevensstructuur van de gebeurtenis, kan Adobe Campaign geen verbinding maken met de service. Wanneer u zich abonneert op een service, wordt dit veld ingevuld met de naam **[!UICONTROL Service label]** van de bijbehorende service.

1. Klik in de **[!UICONTROL Enrichment]** sectie op de **[!UICONTROL Create element]** doelbron **[!UICONTROL Service]** en selecteer deze.

   ![](assets/confirmation_enrichment-service.png)

1. Wijs in de **[!UICONTROL Join definition]** sectie het **[!UICONTROL publicLabel]** veld van de **[!UICONTROL Service]** bron toe aan het **[!UICONTROL publicLabel]** veld van de gebeurtenisconfiguratie.

   ![](assets/confirmation_publicLabel-join.png)

   >[!NOTE]
   >
   >Dit zal u toelaten om verpersoonlijkingsgebieden van het **[!UICONTROL Service]** middel in het transactionele bericht te gebruiken.

1. Sla de gebeurtenisconfiguratie op en klik **[!UICONTROL Publish]** om de gebeurtenis te publiceren.

De gebeurtenis is gereed. U kunt nu het transactie-e-mailbericht ontwerpen.

#### Het bevestigingsbericht ontwerpen {#design-the-confirmation-message-1}

Het bevestigingsbericht is een transactiemelding op basis van de gebeurtenis die u net hebt gepubliceerd.

1. Selecteer **[!UICONTROL Marketing plans]** > in het Adobe Campagne-logo **[!UICONTROL Transactional messages]** en klik op **[!UICONTROL Transactional messages]**.
1. Selecteer de transactie-e-mail die overeenkomt met de gebeurtenis die u net hebt gepubliceerd.

1. Klik op de **[!UICONTROL Content]** sectie en selecteer een e-mailsjabloon. Zie Transactieberichten voor [gebeurtenissen](../../channels/using/event-transactional-messages.md)voor meer informatie over het bewerken van de inhoud van een transactiebericht.
1. Aangezien u directe toegang tot alle gebieden van het **[!UICONTROL Service]** middel hebt, kunt u om het even welk gebied van **[!UICONTROL Context]** > **[!UICONTROL Real-time event (rtEvent)]** > **[!UICONTROL Event context (ctx)]** >**[!UICONTROL Service]** knoop selecteren om uw inhoud aan te passen.

   ![](assets/confirmation_personalization-service.png)

   Voor meer bij het personaliseren van een transactiebericht, zie [deze sectie](../../channels/using/event-transactional-messages.md#personalizing-a-transactional-message).

1. Geef een voorvertoning van uw bericht weer met een testprofiel. Zie Een testprofiel [definiëren in een transactiebericht](../../channels/using/event-transactional-messages.md#defining-a-test-profile-in-a-transactional-message)voor meer informatie hierover.

1. Klik **[!UICONTROL Save & close]** om de inhoud op te slaan.
1. Publiceer het transactiebericht. Zie [Transactiebericht](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message)publiceren.

### Stap 2: De service maken en configureren {#step-2--create-and-configure-the-service-1}

1. Maak een service via het geavanceerde menu **Profielen en publiek** > **Services** via het Adobe Campagne-logo.
1. Ga naar de **[!UICONTROL Service properties]** sectie, die via de ![](assets/edit_darkgrey-24px.png) knoop in het de dienstdashboard wordt betreden.
1. Vul het **[!UICONTROL Service label]** veld in.

   ![](assets/confirmation_service-label.png)

   >[!NOTE]
   >
   >U moet dit veld invullen om afstemming met het transactiebericht mogelijk te maken.

1. Selecteer in de **[!UICONTROL Confirmation messages]** sectie **[!UICONTROL Custom message]**: in deze modus kunt u verwijzen naar een specifiek bevestigingsbericht voor profielen die zijn geabonneerd op uw service.
1. Selecteer het **[!UICONTROL Custom subscription event configuration]** bericht dat u hebt gemaakt.

   ![](assets/confirmation_service-confirmation-message.png)

1. Klik op de service **[!UICONTROL Confirm]** en sla deze op.

Nu telkens wanneer een profiel aan deze dienst intekent, ontvangt hij het transactiebericht dat u, met gepersonaliseerde gebieden in kaart bracht aan de geselecteerde dienst.

>[!NOTE]
>
>Er wordt alleen een bericht verzonden wanneer de gebruiker zich voor de eerste keer abonneert.

## Bevestigingsbericht configureren van een bestemmingspagina {#configuring-confirmation-message-from-landing-page}

U kunt ook naar het bevestigingsbericht van een bestemmingspagina van het abonnement verwijzen door de **[!UICONTROL Start sending messages]** optie van de **[!UICONTROL Job]** sectie van de landingspagina te gebruiken.

Wanneer wordt verwezen naar het bevestigingsbericht van de landingspagina, zal een bericht worden verzonden telkens als de landingspagina wordt voorgelegd (zelfs als het profiel reeds wordt geabonneerd).

### Stap 1: Het bevestigingsbericht maken {#step-1--create-the-confirmation-email-2}

Er wordt automatisch een bevestigingsbericht verzonden naar elk profiel dat zich abonneert op de nieuwsbrief via een bestemmingspagina. Het abonnement wordt beschouwd als een gebeurtenis en het e-mailbericht is een [transactiebericht](../../channels/using/about-transactional-messaging.md) dat zich richt op elk profiel dat zich op de service abonneert.

De stappen voor het maken van deze elementen worden hieronder beschreven. Aangezien het transactionele bericht in de het landen pagina van verwijzingen zal worden voorzien, moet u het eerst tot stand brengen.

#### De gebeurtenis maken {#create-the-event-2}

Het bevestigingsbericht is een [transactiebericht](../../channels/using/about-transactional-messaging.md) als reactie op een gebeurtenis: het abonnement op een service. Dit bericht wordt verzonden ter bevestiging van uw abonnement op uw nieuwsbrief.

1. Maak een gebeurtenis via het menu **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]** , die u kunt openen via het logo van de Adobe-campagne.
1. Voer een label in, selecteer een doeldimensie en klik op **[!UICONTROL Create]**.

   De configuratiestappen worden voorgesteld in de het [Vormen sectie van het transactieoverseinen](../../administration/using/configuring-transactional-messaging.md) .

1. Klik in de **[!UICONTROL Fields]** sectie op de gegevensstructuur **[!UICONTROL Create element]** en voeg deze toe **[!UICONTROL serviceName]** om de afstemming mogelijk te maken.

   ![](assets/confirmation_serviceName-field.png)

   >[!NOTE]
   >
   >Het **[!UICONTROL serviceName]** veld is verplicht. Als u deze niet toevoegt aan de gegevensstructuur van de gebeurtenis, kan Adobe Campagne geen afstemming met de geabonneerde service uitvoeren.

1. Klik in de **[!UICONTROL Enrichment]** sectie op de **[!UICONTROL Create element]** doelbron **[!UICONTROL Service]** en selecteer deze.
1. Wijs in de **[!UICONTROL Join definition]** sectie het **[!UICONTROL serviceName]** veld van de **[!UICONTROL Service]** bron toe aan het **[!UICONTROL name]** veld van de gebeurtenisconfiguratie.

   ![](assets/confirmation_serviceName-join.png)

   >[!NOTE]
   >
   >Dit zal u toelaten om verpersoonlijkingsgebieden van het [!UICONTROL Service] middel in het transactionele bericht te gebruiken.

#### Het bevestigingsbericht ontwerpen {#design-the-confirmation-message-2}

De stappen voor het ontwerpen van het transactiemelding worden voorgesteld in deze [sectie](#design-the-confirmation-message-1).

### Stap 2: De service maken en configureren {#step-2--create-and-configure-the-service-2}

1. Maak een service via het geavanceerde menu **[!UICONTROL Profiles & audiences]** > **[!UICONTROL Services]** via het Adobe Campagne-logo.
1. Ga naar de **[!UICONTROL Service properties]** sectie, die via de ![](assets/edit_darkgrey-24px.png) knoop in het de dienstdashboard wordt betreden.
1. Vul het **[!UICONTROL Service label]** veld in. Dit label wordt weergegeven in het bevestigingsbericht en op de bestemmingspagina van het abonnement.
1. Klik op de service **[!UICONTROL Confirm]** en sla deze op.

### Stap 3: De bestemmingspagina maken en configureren {#step-3--create-and-configure-the-landing-page}

Maak een bestemmingspagina voor abonnementen die op uw website wordt gepubliceerd.

Volg onderstaande stappen om deze bestemmingspagina te maken en te configureren:

1. Ontwerp een [nieuwe landingspagina](../../channels/using/getting-started-with-landing-pages.md) op basis van de **[!UICONTROL Subscription]** sjabloon.
1. Bewerk de eigenschappen van de openingspagina. Selecteer in de sectie **[!UICONTROL Job]** > **[!UICONTROL Specific actions]** de **[!UICONTROL Specific service]** optie en kies de service die u zojuist hebt gemaakt in de vervolgkeuzelijst.

   ![](assets/confirmation_lp-specific-service.png)

1. Selecteer de **[!UICONTROL Start sending message]** optie en kies het transactiemelding dat u net van de drop-down lijst creeerde.

   ![](assets/confirmation_lp-start-sending-message.png)

1. Pas de inhoud van de openingspagina aan.

1. [Test en publiceer](../../channels/using/testing-publishing-landing-page.md) de openingspagina.

Telkens wanneer een profiel zich abonneert op uw nieuwsbrief door de landingspagina te verzenden, ontvangt hij het bevestigingsbericht dat u met gepersonaliseerde gebieden bepaalde die aan de dienst in kaart worden gebracht.

>[!NOTE]
>
>Elke keer dat de landingspagina wordt verzonden, wordt een bericht verzonden, zelfs als het profiel al is geabonneerd.
