---
title: Een service maken
description: Leer hoe u uw eerste service maakt en deze configureert om e-mailbevestigingen naar uw abonnees te verzenden.
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
translation-type: ht
source-git-commit: a8ee3b864b6916871711c6bd2e2d3b794bc706f8
workflow-type: ht
source-wordcount: '420'
ht-degree: 100%

---


# Een service maken{#creating-a-service}

Om abonnementen te kunnen beheren, moet u eerst een service maken en configureren. Als u een nieuwe service configureert, kunt u de e-mailbevestigingen opgeven die de profielen ontvangen wanneer zij zich voor de service in- of uitschrijven. U definieert ook de landingspagina&#39;s voor in- en uitschrijven, die aan de service zijn gekoppeld. Een koppeling voor service-inschrijving die in een e-mail is ingevoegd, leidt het profiel bijvoorbeeld automatisch naar de landingspagina voor inschrijving die in de service is opgegeven.

Een service configureren:

1. Voeg een nieuwe service toe vanuit het geavanceerde menu **[!UICONTROL Profiles & audiences]** > **[!UICONTROL Services]** via het logo van Adobe Campaign of selecteer een bestaande service. Als u een nieuwe service maakt, volgt u eenvoudig de stappen die op het scherm worden getoond.

   Er is een standaardservicesjabloon beschikbaar. Deze sjabloon is vooraf geconfigureerd met standaardlandingspagina&#39;s en bevestigingse-mails. U kunt andere sjablonen maken om specifieke configuraties te definiëren. Raadpleeg de sectie [Sjablonen beheren](../../start/using/marketing-activity-templates.md) voor meer informatie.

1. Configureer de bevestigingsberichten voor in- en uitschrijving in de sectie **[!UICONTROL Service properties]**, die via de knop ![](assets/edit_darkgrey-24px.png) in het servicedashboard toegankelijk is.

   ![](assets/lp_service_parameters.png)

1. Selecteer de optie **[!UICONTROL Subscriptions with an expiration date]** om een geldigheidsperiode voor het abonnement in te stellen.

   ![](assets/lp_service_expiration.png)

   U kunt de vervaldatum in een Segmentation-activiteit gebruiken om u te richten op profielen die zijn ingeschreven voor een service die niet verlopen is.

1. Vul het veld **[!UICONTROL Service label]** in. Het servicelabel is verplicht wanneer u een aangepast bevestigingsbericht gebruikt.

1. Selecteer een sjabloon voor het bevestigingsbericht voor in- en uitschrijving. Er zijn drie modi beschikbaar:

   * **[!UICONTROL No message]**: in deze modus kunt u een service maken zonder een bevestigingsbericht.
   * **[!UICONTROL Default message]**: In deze modus wordt het standaardtransactiebericht voor bevestiging van in- en uitschrijving gebruikt. De standaardbevestigingsberichten zijn generiek en zijn hetzelfde voor alle services die de standaardmodus gebruiken.

      >[!NOTE]
      >
      >U kunt een standaardbericht wijzigen door op het betreffende label in de sectie **[!UICONTROL Service properties]** te klikken of door het te selecteren in de lijst met transactieberichten van Adobe Campaign, nadat u het selectievakje **[!UICONTROL Show internal transactional messages]** hebt ingeschakeld.

   * **[!UICONTROL Custom message]**: In deze modus kunt u specifieke aangepaste bevestigingsberichten voor elke service afhandelen. Vervolgens selecteert u de sjabloon **[!UICONTROL Custom subscription event configuration]** die aan een specifieke [transactiebericht](../../channels/using/about-transactional-messaging.md)-sjabloon is gekoppeld. Zie [Een abonnement op een service bevestigen](../../audiences/using/confirming-subscription-to-a-service.md) voor meer informatie hierover.

1. Sla de service op. De service is nu klaar om te worden gebruikt.

Zodra de service is gemaakt, kunt u deze gaan promoten.

**Verwante onderwerpen:**

* Video [Een service en abonnementen beheren](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/services-and-subscriptions.html)
* [Een service promoten](../../audiences/using/promoting-a-service.md)
* [Een doelgroep van abonnees maken](../../audiences/using/creating-audiences.md#creating-list-audiences)
* [Een landingspagina koppelen aan een service](../../channels/using/configuring-landing-page.md#linking-a-landing-page-to-a-service)
