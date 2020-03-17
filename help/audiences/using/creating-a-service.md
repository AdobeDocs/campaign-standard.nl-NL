---
title: Een service maken
description: Leer hoe u uw eerste service maakt en configureert om e-mailbevestigingen naar uw abonnees te verzenden.
page-status-flag: never-activated
uuid: 0d95d852-0f22-4b7b-b301-8fb4844c3ca2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-subscriptions
discoiquuid: 6b7788fe-fa6c-472a-97db-765595ce1589
context-tags: service,wizard;service,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a8ee3b864b6916871711c6bd2e2d3b794bc706f8

---


# Een service maken{#creating-a-service}

Om abonnementen te kunnen beheren, moet u eerst een dienst tot stand brengen en het vormen. Als u een nieuwe service configureert, kunt u de e-mailbevestigingen opgeven die de profielen ontvangen wanneer zij zich op de service abonneren of zich niet meer bij de service abonneren. U definieert ook de bestemmingspagina&#39;s voor abonnementen en abonnementen die aan de service zijn gekoppeld. Een servicesabonnementkoppeling die bijvoorbeeld in een e-mail wordt ingevoegd, leidt het profiel automatisch naar de bestemmingspagina van het abonnement die in de service is opgegeven.

Om de dienst te vormen:

1. Voeg een nieuwe service toe in het menu Geavanceerd **[!UICONTROL Profiles & audiences]** > **[!UICONTROL Services]** via het logo van de Adobe-campagne of selecteer een bestaande service. Als u een nieuwe dienst creeert, volg eenvoudig de stappen die op het scherm worden getoond.

   Er is een standaardservicesjabloon beschikbaar. Deze sjabloon is vooraf geconfigureerd met standaard bestemmingspagina&#39;s en bevestigingse-mails. U kunt andere sjablonen maken om specifieke configuraties te definiëren. Raadpleeg voor meer informatie de sectie [Sjablonen](../../start/using/marketing-activity-templates.md) beheren.

1. In de **[!UICONTROL Service properties]** sectie, die via de ![](assets/edit_darkgrey-24px.png) knoop in het de dienstdashboard wordt betreden, vorm de bevestigingsberichten voor abonnementen en ophoudingen.

   ![](assets/lp_service_parameters.png)

1. Selecteer de **[!UICONTROL Subscriptions with an expiration date]** optie om een geldigheidsperiode voor het abonnement in te stellen.

   ![](assets/lp_service_expiration.png)

   U kunt de vervaldatum in een activiteit van de Segmentatie aan doelprofielen gebruiken die aan de dienst worden geabonneerd die niet is verlopen.

1. Vul het **[!UICONTROL Service label]** veld in. Het servicelabel is verplicht wanneer u een aangepast bevestigingsbericht gebruikt.

1. Selecteer een sjabloon voor het bevestigingsbericht voor abonnementen en abonnementen. Er zijn drie modi beschikbaar:

   * **[!UICONTROL No message]**: in deze modus kunt u een service maken zonder een bevestigingsbericht.
   * **[!UICONTROL Default message]**: in deze modus wordt het standaardbericht voor het bevestigen van abonnementen of voor het opzeggen van abonnementen gebruikt. De standaardbevestigingsberichten zijn generisch en zullen het zelfde voor alle diensten zijn die de standaardwijze gebruiken.

      >[!NOTE]
      >
      >U kunt een standaardbericht wijzigen door op het label ervan in de **[!UICONTROL Service properties]** sectie te klikken of door het te selecteren in de transactielijst van de Campagne van Adobe, nadat u het **[!UICONTROL Show internal transactional messages]** selectievakje hebt ingeschakeld.

   * **[!UICONTROL Custom message]**: in deze modus kunt u specifieke aangepaste bevestigingsberichten voor elke service afhandelen. Vervolgens selecteert u de sjabloon **[!UICONTROL Custom subscription event configuration]** die aan een specifieke [transactiemplate](../../channels/using/about-transactional-messaging.md) is gekoppeld. Zie Abonnement op een service [](../../audiences/using/confirming-subscription-to-a-service.md)bevestigen voor meer informatie hierover.

1. Sla de service op. Het is nu klaar om te worden gebruikt.

Zodra de dienst is gecreeerd, kunt u beginnen het te bevorderen.

**Verwante onderwerpen:**

* [Een service- en abonnementvideo](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/services-and-subscriptions.html) beheren
* [Een service promoten](../../audiences/using/promoting-a-service.md)
* [Een publiek maken van abonnees](../../audiences/using/creating-audiences.md#creating-list-audiences)
* [Een openingspagina koppelen aan een service](../../channels/using/configuring-landing-page.md#linking-a-landing-page-to-a-service)
