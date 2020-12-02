---
solution: Campaign Standard
product: campaign
title: Aan de slag met Campaign Standard-beheer
description: Ontdek gebruikers en toestemmingenbeheer, controlerichtlijnen, kanaal-specifieke configuraties en toepassingsmontagerichtlijnen.
audience: administration
content-type: reference
topic-tags: about-administrating-adobe-campaign
translation-type: tm+mt
source-git-commit: a0ad969c86a5047f3f967a21fdc2d6040d7d939f
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Aan de slag met Campaign Standard-beheer {#about-administrating-adobe-campaign}

<table>
<tr><td><img src="assets/do-not-localize/icon_menu.svg" width="60px"><p><a href="#administration-menu">Menu Beheer</a></p></td>
<td><img src="assets/do-not-localize/icon_users.svg" width="60px"><p><a href="#users-security">Gebruikers en beveiliging</a></p></td>
<td><img src="assets/do-not-localize/icon_channels.svg" width="60px"><p><a href="#channels-configuration">Kanaalconfiguratie</a></p></td>
<td><img src="assets/do-not-localize/icon_settings.svg" width="60px"><p><a href="#application-settings">Applicatie-instellingen</a></p></td></tr>
</table>

Als cloudgebaseerde oplossing biedt Adobe Campaign beheerders verschillende manieren om de toepassing te configureren. Hoewel de infrastructuurconfiguratie door Adobe wordt uitgevoerd, kunnen de functionele beheerders diverse configuratiehandelingen uitvoeren die hieronder worden beschreven.

>[!NOTE]
>
>Als u vragen of verzoeken over implementatie en configuratiekwesties hebt, contacteer uw Adobe rekeningsmanager.

Houd er rekening mee dat als uw instantie wordt gehost op AWS, Admin-gebruikers ook het Configuratiescherm kunnen gebruiken voor het beheren van instellingen en het bijhouden van gebruik voor elk van uw instanties. Raadpleeg de [desbetreffende documentatie](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html) voor meer informatie.

## Menu Beheer {#administration-menu}

<img src="assets/do-not-localize/icon_menu.svg" width="60px">

De verschillende Adobe Campaign-beheerbewerkingen worden uitgevoerd via het menu **[!UICONTROL Administration]** dat toegankelijk is wanneer u in de linkerbovenhoek op het Adobe Campaign-logo klikt. Dit deel van de interface is alleen toegankelijk voor functionele beheerders van het platform.

De verschillende beschikbare menu&#39;s zijn:

* [Gebruikers en beveiliging](../../administration/using/about-access-management.md): Met dit menu kunt u de toegang tot het platform (gebruikers, rollen, beveiligingsgroepen, eenheden) beheren.
* [Kanalen](../../administration/using/about-channel-configuration.md): In dit menu worden de technische parameters gegroepeerd die zijn gekoppeld aan de verschillende platformkanalen (e-mail, mobiel) en het typologie- en quarantainebeheer.
* [Toepassingsinstellingen](../../administration/using/external-accounts.md): Met dit menu kunt u verschillende toepassingselementen configureren (externe accounts, opties, technische workflows).
* [Ontwikkeling](../../developing/using/data-model-concepts.md): Met dit menu kunt u uw aangepaste bronnen beheren en toegang krijgen tot diagnostische gereedschappen.
* [Instellingen](../../administration/using/branding.md) voor instanties: In dit menu definieert u de verschillende merken en configureert u de instellingen (logo, beheer, bijhouden, URL-domein voor toegang tot de bestemmingspagina&#39;s, enz.).
* [Implementatie](../../automating/using/managing-packages.md): In dit menu worden de import- en exportopties voor het pakket opnieuw gegroepeerd.
* [Klantcijfers](../../audiences/using/active-profiles.md): Adobe Campaign geeft een rapport weer waarin het aantal actieve profielen wordt weergegeven. Dit rapport is slechts informatief, het heeft geen directe invloed op het factureren.
* [Privacygereedschappen](../../start/using/privacy-management.md): Met dit menu kunt u GDPR-toegang maken, aanvragen verwijderen en de evolutie ervan volgen.

## Gebruikers en beveiliging {#users-security}

<img src="assets/do-not-localize/icon_users.svg"  width="60px">

Nodig gebruikers uit om tot de toepassing toegang te hebben en **veiligheidsgroepen** te beheren, die reeksen gebruikers zijn die de zelfde rollen en de rechten binnen uw organisatie delen. Adobe Campaign biedt standaard een set rollen **rollen**, waarmee u eenheidsmachtigingen kunt definiëren die zijn toegewezen aan gebruikers en gebruikersgroepen. Gecombineerd met **organisatorische eenheden**, geven de rollen gebruikers een gefilterde mening van de interface en bepalen hun toegang tot de verschillende eigenschappen.

De standaard van de campagne staat u ook toe om op veiligheid betrekking hebbende informatie te controleren. U kunt informatie over gegevensexport ophalen die door gebruikers via het **[!UICONTROL Export audits]** scherm wordt uitgevoerd, en het **[!UICONTROL Licenses]** scherm gebruiken om alle geïnstalleerde campagnelicenties binnen uw organisatie te controleren, evenals andere informatie zoals het buildnummer, de releaseversie en de voorwaarden van overeenkomst.

Meer informatie:

* [Gebruikersbeheer](../../administration/using/users-management.md)
* [Organisatorische eenheden](../../administration/using/organizational-units.md)
* [Lijst met rollen](../../administration/using/list-of-roles.md)
* [Groepen en gebruikers beheren](../../administration/using/managing-groups-and-users.md)
* [Audits uitvoeren op exportlogboeken](../../administration/using/auditing-export-logs.md)
* [Licenties](../../administration/using/licenses.md)

## Configuratie van kanalen {#channels-configuration}

<img src="assets/do-not-localize/icon_channels.svg" width="60px">

Alle communicatiekanalen in Adobe Campaign moeten correct zijn geconfigureerd om berichten effectief te kunnen verzenden. In het menu **[!UICONTROL Channel]** kunt u de technische parameters beheren die aan de verschillende kanalen zijn gekoppeld.

Configureer verschillende **e-mailparameters**: verwerkingsregels voor stuit, quarantines, e-maileigenschappen en routeparameters, typoly-regels. Bepaal het verpletteren van configuraties en eigenschappen voor het **SMS** kanaal, evenals het coderen van SMS en formaten.

Stel **mobiele toepassingen** in om berichten in de app en pushmeldingen te kunnen verzenden met behulp van Adobe Experience Platform SDK&#39;s en configureer **transactioneel messaging** door gebeurtenissen te maken en in te stellen.

Meer informatie:

* [Informatie over kanaalconfiguratie](../../administration/using/about-channel-configuration.md)
* [E-mailkanaal configureren](../../administration/using/configuring-email-channel.md)
* [Een sms-kanaal configureren](../../administration/using/configuring-sms-channel.md)
* [Een mobiele applicatie configureren](../../administration/using/configuring-a-mobile-application.md)
* [Transactionele berichten configureren](../../administration/using/configuring-transactional-messaging.md)

## Applicatie-instellingen {#application-settings}

<img src="assets/do-not-localize/icon_settings.svg" width="60px">

Campaign Standard wordt geleverd met verschillende toepassingselementen die kunnen worden geconfigureerd om aan uw behoeften te voldoen.

Stel **externe accounts** in die worden gebruikt om Adobe Campaign aan te sluiten op externe servers. Open Campaign Standard-doeltoewijzingen en controleer uw platform met behulp van **technische workflows**.

Definieer een of meerdere **brands** voor uw organisatie en configureer de verzending van **real-time meldingen** binnen de toepassing in het geval van belangrijke systeemactiviteiten.

Meer informatie:

* [Informatie over Campaign Standard-instellingen](../../administration/using/about-campaign-standard-settings.md)
* [Externe accounts](../../administration/using/external-accounts.md)
* [Doeltoewijzingen in Campaign](../../administration/using/target-mappings-in-campaign.md)
* [Technische workflows](../../administration/using/technical-workflows.md)
* [Merkpositionering](../../administration/using/branding.md)
* [Interne meldingen verzenden](../../administration/using/sending-internal-notifications.md)
