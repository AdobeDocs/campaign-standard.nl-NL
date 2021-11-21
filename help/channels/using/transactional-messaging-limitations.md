---
title: Beperkingen voor transactionele berichten
description: Meer informatie over de belangrijkste aanbevelingen en beperkingen met betrekking tot transactieberichten in Adobe Campaign Standard.
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: Transactional Messaging
role: User
level: Intermediate
exl-id: d6aaec6e-c718-46a2-88e8-7402970def1a
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '742'
ht-degree: 68%

---

# Beste praktijken en beperkingen van het Transactionele overseinen {#transactional-messaging-limitations}

<img src="assets/do-not-localize/icon_concepts.svg" width="60px">

Deze sectie maakt een lijst van de beste praktijken en de beperkingen u zich van bewust zou moeten zijn alvorens transactionele berichten te beginnen creëren.

<!--For more on transactional messages, including on how to configure and create them, see [Getting started with transactional messaging](../../channels/using/getting-started-with-transactional-msg.md).-->

## Machtigingen {#permissions}

Alleen gebruikers met de [Beheer](../../administration/using/users-management.md#functional-administrators) de rol kan transactionele gebeurtenissen vormen en tot transactionele berichten toegang hebben.

## Configuratie en publicatie van gebeurtenissen {#design-and-publication}

Terwijl u transactionele gebeurtenissen configureert en publiceert, kunnen sommige stappen die u moet uitvoeren niet worden teruggezet. U dient op de hoogte te zijn van de volgende beperkingen:

* De beschikbare kanalen voor transactieoverseinen zijn: **[!UICONTROL Email]**, **[!UICONTROL Mobile (SMS)]** en **[!UICONTROL Push notification]**.
* Voor elke gebeurtenisconfiguratie kan slechts één kanaal worden gebruikt. Zie [Een gebeurtenis maken](../../channels/using/configuring-transactional-event.md#creating-an-event).
* Nadat de gebeurtenis is gemaakt, kunt u het kanaal niet meer wijzigen. Als een bericht niet succesvol wordt verzonden, moet u een mechanisme ontwerpen waardoor het bericht door middel van een workflow via een ander kanaal wordt verzonden. Zie [Workflowdata en processen](../../automating/using/get-started-workflows.md).
* U kunt de doeldimensie (**[!UICONTROL Real-time event]** of **[!UICONTROL Profile]**) niet wijzigen nadat de gebeurtenis is gemaakt. Zie [Een gebeurtenis maken](../../channels/using/configuring-transactional-event.md#creating-an-event).
* U kunt een publicatie niet terugdraaien, maar u kunt de publicatie van een gebeurtenis wel ongedaan maken, zodat de gebeurtenis en het bijbehorende transactiebericht ontoegankelijk worden. Zie [Publicatie van een gebeurtenis ongedaan maken](../../channels/using/publishing-transactional-event.md#unpublishing-an-event).
* Het enige transactiebericht dat met een gebeurtenis kan worden geassocieerd, is het bericht dat automatisch wordt gemaakt tijdens het publiceren van die gebeurtenis. Zie [Een voorvertoning weergeven en de gebeurtenis publiceren](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event).

## Aantal transactieberichten {#transactional-message-number}

Het aantal gepubliceerde transactieberichten kan een significante invloed op uw platform hebben. Voor optimale prestaties, zou het aantal gepubliceerde transactieberichten onder 100 moeten blijven. Om dit te verzekeren, unpublish of schrap om het even welke ongebruikte transactieberichten. Zie [Het publiceren van een transactiemelding opheffen](../../channels/using/publishing-transactional-message.md#unpublishing-a-transactional-message) en [Transactiebericht verwijderen](../../channels/using/publishing-transactional-message.md#deleting-a-transactional-message).

Voor de beste prestaties kunt u ook het publiceren ongedaan maken of verwijderen van ongebruikte gebeurtenissen. Als u een gebeurtenis verwijdert of publiceert, worden de desbetreffende transactiemeldingen en de verzendings- en trackinglogboeken van die gebeurtenis ook verwijderd of gepubliceerd. Zie [Publicatie van een gebeurtenis ongedaan maken](../../channels/using/publishing-transactional-event.md#unpublishing-an-event) en [Een gebeurtenis verwijderen](../../channels/using/publishing-transactional-event.md#deleting-an-event).

## Personalisatie {#personalization}

De manier waarop u berichtcontent kunt personaliseren hangt af van het type transactiebericht. Specifieke informatie staat hieronder.

### Transactieberichten op basis van gebeurtenissen

* De persoonlijke informatie komt uit data van de gebeurtenis zelf. Zie [Transactieberichtconfiguratie op basis van gebeurtenissen](../../channels/using/configuring-transactional-event.md#event-based-transactional-messages).
* U **kan** gebruiken **[!UICONTROL Unsubscription link]** inhoud blokkeert in een bericht over een gebeurtenistransactie.
* Het gebeurtenistransactiebericht wordt verondersteld om alleen de data in de verzendgebeurtenis zelf te gebruiken bij het bepalen van de ontvanger en de personalisatie van de berichtcontent. U kunt de content van het transactiebericht echter wel verrijken met data uit de Adobe Campaign-database. Zie [Een gebeurtenis verrijken](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content) en [Een transactiebericht aanpassen](../../channels/using/editing-transactional-message.md#personalizing-a-transactional-message).
* Aangezien de transactieberichten voor gebeurtenissen geen profielinformatie bevatten, zijn ze niet compatibel met &#39;moeheidsregels&#39;, zelfs in het geval van een verrijking met profielen.

### Transactieberichten op basis van profiel

* De personalisatiegegevens kunnen afkomstig zijn van de data in de gebeurtenis of van de afgestemde profielrecord. Zie [Configuratie van op profielen gebaseerde transactieberichten](../../channels/using/configuring-transactional-event.md#profile-based-transactional-messages) en [Specifieke kenmerken van op profielen gebaseerde transactiemeldingen](../../channels/using/editing-transactional-message.md#profile-transactional-message-specificities).
* U **kan** gebruiken **[!UICONTROL Unsubscription link]** in een bericht voor een profieltransactie. Zie [Een contentblok](../../designing/using/personalization.md#adding-a-content-block) toevoegen.
* De moeheidsregels zijn compatibel met transactieberichten voor profielen. Zie [Moeheidsregels](../../sending/using/fatigue-rules.md).

### Productaanbiedingen

Merk op dat productaanbiedingen beschikbaar zijn in transactie **e-mailberichten** alleen. Zie [Productaanbiedingen gebruiken in een transactiebericht](../../designing/using/using-product-listings.md).

## Branding {#permissions-and-branding}

Wanneer het om het beheer van [branding](../../administration/using/branding.md) gaat, biedt transactionele messaging minder flexibiliteit dan standaard messaging. Adobe raadt u aan alle merken die in transactieberichten worden gebruikt, te koppelen aan de **[!UICONTROL All]** organisatorische eenheid[](../../administration/using/organizational-units.md). Lees de gedetailleerde uitleg hieronder voor meer informatie.

Wanneer u een transactiebericht bewerkt, kunt u het aan een merk koppelen en automatisch bepaalde parameters toepassen, zoals de merknaam of het logo. De optie **[!UICONTROL Default brand]** is standaard geselecteerd in de eigenschappen van het transactiebericht.

![](assets/message-center_branding.png)

Alle objecten (inclusief branding) die in een transactiebericht worden gebruikt, moeten zichtbaar zijn vanuit de **[!UICONTROL Message Center]**-organisatie-eenheid, wat betekent dat deze objecten zich in de organisatie-eenheden **[!UICONTROL Message Center]** of **[!UICONTROL All]** moeten bevinden.

Als het geselecteerde merk in de berichteigenschappen wordt gekoppeld aan een organisatie-eenheid die anders is dan **[!UICONTROL Message Center]** of **[!UICONTROL All]**, wordt een fout veroorzaakt en kunt u het transactiebericht niet verzenden.

Als u multi-branding daarom binnen de context van transactieberichten wilt gebruiken, moet u alle merken ofwel koppelen aan de organisatie-eenheid **[!UICONTROL Message Center]** of aan **[!UICONTROL All]**.

## Transactieberichten exporteren en importeren {#exporting-and-importing-transactional-messages}

* Als u een transactiebericht wilt exporteren, moet u de bijbehorende gebeurtenisconfiguratie opnemen wanneer u [het pakket voor exporteren maakt](../../automating/using/managing-packages.md#creating-a-package).
* Als het transactiebericht eenmaal via een pakket [is geïmporteerd](../../automating/using/managing-packages.md#importing-a-package), wordt het niet weergegeven in de lijst met transactieberichten. U moet de gebeurtenisconfiguratie [publiceren](../../channels/using/publishing-transactional-event.md) om het bijbehorende transactiebericht beschikbaar te maken.
