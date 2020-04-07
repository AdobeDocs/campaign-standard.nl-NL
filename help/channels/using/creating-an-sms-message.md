---
title: Een SMS-bericht maken
description: Ga als volgt te werk om een SMS-bericht voor één verzending te maken in Adobe Campaign.
page-status-flag: never-activated
uuid: 591ae97e-2d19-4f93-be4b-d8d20f1d2d12
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: sms-messages
discoiquuid: b27381a9-19e5-4b65-b194-c72f475ba54d
delivercontext-tags: deliveryCreation,wizard
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 155ed7e50e207e4c4dc0569e5e96b24e712e4be8

---


# Een SMS-bericht maken{#creating-an-sms-message}

Het maken van een SMS-verzending lijkt sterk op het maken van een gewone e-mail. In de volgende stappen wordt de configuratie beschreven die specifiek is voor dit kanaal. Zie Een e-mail [](../../channels/using/creating-an-email.md) maken voor meer informatie over andere opties.

De geavanceerde parameters van SMS worden gedetailleerd in de de configuratiesectie [van](../../administration/using/configuring-sms-channel.md) SMS.

Als u SMS-berichten wilt maken en verzenden naar een mobiele telefoon, hebt u het volgende nodig:

* Een **[!UICONTROL Routing]** externe account die in de **[!UICONTROL Mobile (SMS)]** modus op het **[!UICONTROL Bulk delivery]** kanaal is geconfigureerd. Voor meer op dit, verwijs naar de [Verpletterende](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing) sectie.
* Een leveringssjabloon die correct is gekoppeld aan deze externe account.

1. Maak een SMS-verzending. U kunt dit doen vanaf de [startpagina](../../start/using/interface-description.md#home-page)van Adobe Campagne, in een [campagne](../../start/using/marketing-activities.md#creating-a-marketing-activity) of in de lijst met [](../../start/using/programs-and-campaigns.md#creating-a-campaign)marketingactiviteiten.

   U kunt ook een SMS-activiteit toevoegen aan een workflow. Raadpleeg de handleiding [Workflows](../../automating/using/sms-delivery.md) voor meer informatie.

   Wanneer het creëren van een bericht, wordt een tovenaar getoond om u door de belangrijkste stappen te lopen. Wat door de tovenaar wordt bepaald kan nog achteraf van het berichtdashboard worden uitgegeven.

1. Selecteer de sjabloon die u wilt gebruiken. U kunt of uit-van-de-doos malplaatje van SMS of één van uw eigen malplaatjes kiezen.

   ![](assets/sms_creation_1.png)

   Om aan een mobiele telefoon te leveren, moet het leveringsmalplaatje correct met SMS verbonden zijn die externe rekening verpletteren.

1. Voer de algemene eigenschappen van het SMS in.

   ![](assets/sms_creation_2.png)

   Zowel verschijnen het activiteitenetiket als zijn identiteitskaart in de interface, maar zij zijn niet zichtbaar aan de berichtontvangers.

1. Geef het publiek op dat u als doel wilt instellen. U kunt een bestaand publiek selecteren of een populatie rechtstreeks als doel instellen door regels te definiëren en te combineren.

   ![](assets/sms_creation_3.png)

1. Voeg inhoud toe aan je SMS. U kunt de inhoud ook definiëren door te klikken op het **[!UICONTROL Content]** gedeelte van het leveringsdashboard, zodra het maken van SMS is voltooid. Zie [Informatie over het ontwerpen](../../channels/using/about-sms-and-push-content-design.md)van SMS-inhoud.

   Als u verpersoonlijkingsgebieden of voorwaardelijke tekst in de inhoud van uw SMS-bericht hebt opgenomen, kan de lengte van het bericht van de ene ontvanger tot de andere variëren. Deze factoren kunnen immers tekens bevatten die door de GSM-codering niet in aanmerking worden genomen. Daarom moet de berichtlengte worden geëvalueerd zodra de personalisatie is uitgevoerd. Zie [SMS-berichten](../../channels/using/personalizing-sms-messages.md)personaliseren.

   ![](assets/sms_creation_4.png)

1. Bevestig dat het bericht wordt gemaakt. Het dashboard wordt vervolgens weergegeven.
1. Plan de verzending. Het SMS kan manueel onmiddellijk na de berichtvoorbereiding of automatisch op een geplande datum worden verzonden. Zie [Berichten](../../sending/using/about-scheduling-messages.md)plannen.
1. Bereid het bericht voor om zijn geldigheid, verpersoonlijking en doel te analyseren.

   ![](assets/sms_creation_6.png)

   >[!NOTE]
   >
   >U kunt algemene regels voor vermoeidheid tussen kanalen instellen die overgevulde profielen automatisch uitsluiten van campagnes. Zie [Vermoeidheidsregels](../../sending/using/fatigue-rules.md).

1. Proefdrukken verzenden om uw bericht te controleren en te valideren en de weergave in de Postbus te controleren. Zie de sectie [Bewijs](../../sending/using/sending-proofs.md) verzenden.
1. Bevestig de verzending van het bericht. Het verzenden zal dienovereenkomstig aan het programma beginnen u hebt bepaald.

   ![](assets/sms_creation_7.png)

Het bericht wordt verzonden. U kunt zijn levering door het berichtdashboard en de logboeken controleren.

Zodra het verzenden wordt gebeëindigd, kunt u beginnen het effect van uw bericht met ingebouwde of aangepaste leveringsrapporten te meten.

**Verwante onderwerpen:**

* [Informatie over SMS en push-inhoud](../../channels/using/about-sms-and-push-content-design.md)
* [Sjablonen beheren](../../start/using/marketing-activity-templates.md)
* [Een video voor SMS-levering](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/communication-channels/mobile/sms/sms-delivery.html) maken

