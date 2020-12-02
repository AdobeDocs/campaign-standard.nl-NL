---
solution: Campaign Standard
product: campaign
title: Beperkingen voor transactionele berichten
description: Meer informatie over de belangrijkste beperkingen en aanbevelingen met betrekking tot transactieberichten in Adobe Campaign Standard.
audience: channels
content-type: reference
topic-tags: landing-pages
context-tags: landingPage,wizard;landingPage,overview;landingPage,main
translation-type: tm+mt
source-git-commit: 840795064021688e25f8c9ae3c7150bcc1f085b1
workflow-type: tm+mt
source-wordcount: '637'
ht-degree: 79%

---


# Aanbevolen werkwijzen en beperkingen {#transactional-messaging-limitations} voor transactiemeldingen

<img src="assets/do-not-localize/icon_concepts.svg" width="60px">

In de onderstaande sectie worden de aanbevolen procedures en beperkingen weergegeven die u moet kennen voordat u transactiemeldingen gaat maken.

<!--For more on transactional messages, including on how to configure and create them, see [Getting started with transactional messaging](../../channels/using/getting-started-with-transactional-msg.md).-->

>[!IMPORTANT]
>
>Om tot transactieberichten toegang te hebben, moet u [beleid](../../administration/using/users-management.md#functional-administrators) rechten hebben.

## Configuratie en publicatie van gebeurtenissen {#design-and-publication}

Terwijl u transactionele gebeurtenissen configureert en publiceert, kunnen sommige stappen die u moet uitvoeren niet worden teruggezet. U dient op de hoogte te zijn van de volgende beperkingen:

* Voor elke gebeurtenisconfiguratie kan slechts één kanaal worden gebruikt. Zie [Een gebeurtenis maken](../../channels/using/configuring-transactional-event.md#creating-an-event).
* Nadat de gebeurtenis is gemaakt, kunt u het kanaal niet meer wijzigen. Als een bericht niet succesvol wordt verzonden, moet u een mechanisme ontwerpen waardoor het bericht door middel van een workflow via een ander kanaal wordt verzonden. Zie [Workflowdata en processen](../../automating/using/get-started-workflows.md).
* U kunt de doeldimensie (**[!UICONTROL Real-time event]** of **[!UICONTROL Profile]**) niet wijzigen nadat de gebeurtenis is gemaakt. Zie [Een gebeurtenis maken](../../channels/using/configuring-transactional-event.md#creating-an-event).
* U kunt een publicatie niet terugdraaien, maar u kunt de publicatie van een gebeurtenis wel ongedaan maken, zodat de gebeurtenis en het bijbehorende transactiebericht ontoegankelijk worden. Zie [Publicatie van een gebeurtenis ongedaan maken](../../channels/using/publishing-transactional-event.md#unpublishing-an-event).
* Het enige transactiebericht dat met een gebeurtenis kan worden geassocieerd, is het bericht dat automatisch wordt gemaakt tijdens het publiceren van die gebeurtenis. Zie [Een voorvertoning weergeven en de gebeurtenis publiceren](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event).

## Personalisatie {#personalization}

De manier waarop u berichtcontent kunt personaliseren hangt af van het type transactiebericht. Specifieke informatie staat hieronder.

### Transactieberichten op basis van gebeurtenissen

* De persoonlijke informatie komt uit data van de gebeurtenis zelf. Zie [Transactieberichtconfiguratie op basis van gebeurtenissen](../../channels/using/configuring-transactional-event.md#event-based-transactional-messages).
* U **kunt niet** gebruiken **[!UICONTROL Unsubscription link]** inhoudsblokken in een bericht van de gebeurtenistransactie.
* Het gebeurtenistransactiebericht wordt verondersteld om alleen de data in de verzendgebeurtenis zelf te gebruiken bij het bepalen van de ontvanger en de personalisatie van de berichtcontent. U kunt de content van het transactiebericht echter wel verrijken met data uit de Adobe Campaign-database. Zie [Een gebeurtenis verrijken](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content) en [Een transactiebericht aanpassen](../../channels/using/editing-transactional-message.md#personalizing-a-transactional-message).
* Aangezien de transactieberichten voor gebeurtenissen geen profielinformatie bevatten, zijn ze niet compatibel met &#39;moeheidsregels&#39;, zelfs in het geval van een verrijking met profielen.

### Transactieberichten op basis van profiel

* De personalisatiegegevens kunnen afkomstig zijn van de data in de gebeurtenis of van de afgestemde profielrecord. Zie [Transactieberichtconfiguratie op basis van profiel](../../channels/using/configuring-transactional-event.md#profile-based-transactional-messages) en [Specificaties van op profiel gebaseerde transactiemeldingen](../../channels/using/editing-transactional-message.md#profile-transactional-message-specificities).
* U **kan** gebruiken **[!UICONTROL Unsubscription link]** inhoudsblokken in een bericht van de profieltransactie. Zie [Een contentblok](../../designing/using/personalization.md#adding-a-content-block) toevoegen.
* De moeheidsregels zijn compatibel met transactieberichten voor profielen. Zie [Moeheidsregels](../../sending/using/fatigue-rules.md).

### Productaanbiedingen

Merk op dat de productaanbiedingen in transactie **e-mailberichten** slechts beschikbaar zijn. Zie [Productaanbiedingen gebruiken in een transactiebericht](../../channels/using/editing-transactional-message.md#using-product-listings-in-a-transactional-message).

## Toestemmingen en branding{#permissions-and-branding}

Wanneer het om het beheer van [branding](../../administration/using/branding.md) gaat, biedt transactionele messaging minder flexibiliteit dan standaard messaging. Adobe raadt u aan alle merken die in transactieberichten worden gebruikt, te koppelen aan de **[!UICONTROL All]** organisatorische eenheid[](../../administration/using/organizational-units.md). Lees de gedetailleerde uitleg hieronder voor meer informatie.

Wanneer u een transactiebericht bewerkt, kunt u het aan een merk koppelen en automatisch bepaalde parameters toepassen, zoals de merknaam of het logo. De optie **[!UICONTROL Default brand]** is standaard geselecteerd in de eigenschappen van het transactiebericht.

![](assets/message-center_branding.png)

Alle objecten (inclusief branding) die in een transactiebericht worden gebruikt, moeten zichtbaar zijn vanuit de **[!UICONTROL Message Center]**-organisatie-eenheid, wat betekent dat deze objecten zich in de organisatie-eenheden **[!UICONTROL Message Center]** of **[!UICONTROL All]** moeten bevinden.

Als het geselecteerde merk in de berichteigenschappen wordt gekoppeld aan een organisatie-eenheid die anders is dan **[!UICONTROL Message Center]** of **[!UICONTROL All]**, wordt een fout veroorzaakt en kunt u het transactiebericht niet verzenden.

Als u multi-branding daarom binnen de context van transactieberichten wilt gebruiken, moet u alle merken ofwel koppelen aan de organisatie-eenheid **[!UICONTROL Message Center]** of aan **[!UICONTROL All]**.

## Transactieberichten exporteren en importeren {#exporting-and-importing-transactional-messages}

* Als u een transactiebericht wilt exporteren, moet u de bijbehorende gebeurtenisconfiguratie opnemen wanneer u [het pakket voor exporteren maakt](../../automating/using/managing-packages.md#creating-a-package).
* Als het transactiebericht eenmaal via een pakket [is geïmporteerd](../../automating/using/managing-packages.md#importing-a-package), wordt het niet weergegeven in de lijst met transactieberichten. U moet de gebeurtenisconfiguratie [publiceren](../../channels/using/publishing-transactional-event.md) om het bijbehorende transactiebericht beschikbaar te maken.
