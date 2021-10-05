---
title: Veelgestelde vragen In-App
description: Veelgestelde vragen over In-App-berichten
audience: channels
content-type: reference
topic-tags: in-app-messaging
context-tags: delivery,triggers,back
feature: In App
role: User
exl-id: 986646b1-42d5-4169-ac38-d8e612a9a6d3
source-git-commit: b5e98c07ee55cab0b6a628a97162ccd64711501a
workflow-type: tm+mt
source-wordcount: '668'
ht-degree: 2%

---


# Veelgestelde vragen In-App {#in-app-faq}

## Wat zouden enkele nuttige hulpbronnenaanbevelingen zijn om meer te weten te komen over het In-App-kanaal in Adobe Campaign Standard? {#resources-inapp}

Ontdek de onderstaande bronnen:

* [Videotutorials](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/communication-channels/mobile/in-app/in-app-message-overview.html)
* [Blogbericht](https://theblog.adobe.com/get-more-out-of-the-new-in-app-message-channel-from-adobe-campaign/)
* [Community-pagina](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-standard/ct-p/adobe-campaign-standard-community)

## Wat is het doel van API&#39;s setLinkageField en resetLinkageField voor Campagneextensies? {#extensions-apis}

Aangezien de berichten in-app door SDK van Campagne worden getrokken, willen wij een veilig mechanisme verstrekken om ervoor te zorgen dat de Berichten in-app die PII gegevens bevatten niet in kwaadwillige handen vallen. Als dusdanig, hebben wij het volgende mechanisme op zijn plaats om de veilige levering van berichten aan het apparaat te verzekeren:

* Klanten markeren velden voor mobiele profielen (appSubscriberRcp-tabel) als Persoonlijk en Gevoelig als ze ervoor willen zorgen dat deze specifieke gegevens veilig worden geleverd.
* Als zodanig gemarkeerde velden kunnen alleen worden gebruikt in de profielsjabloon (niet in de appSubscriber-sjabloon of de Broadcast-sjabloon) waarvoor een extra beveiligingsmechanisme is ingebouwd.
* Berichten die zijn gemaakt met de profielsjabloon kunnen alleen worden gediend wanneer de gebruiker zich heeft aangemeld bij de app.
* Om deze veilige handshake te vergemakkelijken, moeten ontwikkelaars van mobiele apps aanvullende verificatiegegevens doorgeven met de setLinkageField-API. Let op: het koppelingsveld is het veld dat wordt geïdentificeerd als de koppeling tussen Mobiel profiel en CRM-profiel tijdens het uitbreiden van de tabel appSubscriberRcp.
* Ze moeten de in-app-berichten die op het apparaat zijn opgeslagen en resetLinkagefields verwijderen wanneer de gebruiker zich afmeldt bij de App met resetLinkageField. Dit zorgt ervoor dat als een andere gebruiker zich aanmeldt bij de app, deze de berichten die voor de vorige gebruiker worden bedoeld, niet ziet.
* Raadpleeg [Mobiele SDK API&#39;s](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference) om dit beveiligingsmechanisme te implementeren op de client.

## Wat moet ik doen om In-App rapportering in Campaign toe te laten? {#enable-inapp-reporting}

U moet in-app het volgen postback vormen. Instructies vindt u [hier](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback).

Als u het bijhouden van lokale meldingen wilt implementeren, raadpleegt u deze [pagina](../../administration/using/local-tracking.md).

## Welke rapporten zijn beschikbaar voor het kanaal In-App? {#report-inapp}

Een out-of-the-box rapport is beschikbaar in Adobe Campaign for In-App channel. Raadpleeg deze [documentatie](../../reporting/using/in-app-report.md).

Zie deze [pagina](../../reporting/using/indicator-calculation.md#in-app-delivery) om te begrijpen hoe elke metriek in-app wordt berekend.

## Biedt u ondersteuning voor meertalige inhoudvarianten voor In-App, vergelijkbaar met Push? {#multilingual-inapp}

Er zijn nu geen meertalige sjablonen beschikbaar voor In-App-berichten.

Als het echter de bedoeling is een bericht in de app in een andere taal dan Engels te verzenden, kan de inhoud rechtstreeks in de beschikbare tekstvakken worden geplakt.

![](assets/faq_inapp.png)

## Kunnen de gebieden van de Aanpassing van de Campagne aan Aangepast HTML worden toegevoegd? {#custom-html-inapp}

Nee, dit wordt nog niet ondersteund.

## Ik heb een waakzaam bericht gevormd maar het toont niet op het apparaat. {#alert-message}

Voor waarschuwingsberichten is ten minste één afwijzingsknop vereist (primaire of secundaire knop moet actie afwijzen). Anders, is het mogelijk om het bericht te bewaren maar het zal niet worden ontvangen.

## Als aangepaste iOS-geluiden voor lokale meldingen niet worden afgespeeld; wordt het standaardgeluid afgespeeld? {#local-notification-sound}

Voor aangepast geluid op iOS moet u een bestandsnaam met extensie opgeven wanneer u een lokale melding maakt (bijvoorbeeld sound.caf). Als deze extensie niet is opgegeven, wordt het standaardgeluid gebruikt.

## Worden de diepte gesteund in in-app berichten? {#inapp-deeplinks}

Ja, deplinks worden ondersteund in In-App-berichten. Deeplinks moeten omvatten:

* de taal die verklaart dat levering het volgen moet worden onbruikbaar gemaakt om de diepte te werken.
* Appsflyer met Tak als partners die het zuiveren volgen kunnen doen. Voor meer informatie over de integratie van de Tak en van Adobe Campaign Standard, verwijs naar deze [pagina](https://help.branch.io/using-branch/docs/adobe-campaign-standard-1).

## Kan een bericht in de app worden geactiveerd wanneer de gebruiker de app start via een pushmelding? {#inapp-push-trigger}

Ja, deze berichten worden ook bedoeld als de berichten van de madeliefketen. Volg het onderstaande proces:

1. Maak een bericht in de app.

1. Definieer een aangepaste gebeurtenis en selecteer deze als een gebeurtenisactivering voor deze IAM, bijvoorbeeld &quot;Trigger from fall preview Push&quot;.

1. Wanneer u uw pushbericht ontwerpt, definieert u een aangepaste variabele waarvan de waarde kan worden ingesteld als een gebeurtenis die IAM activeert, bijvoorbeeld Key = &quot;inappkey&quot; en value = &quot;Trigger from fall preview Push&quot;.

1. Implementeer gebeurtenistrigger in de mobiele toepassingscode als volgt:

   ![](assets/faq_inapp_2.png)
