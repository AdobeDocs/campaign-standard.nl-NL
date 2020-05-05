---
title: Ga aan de slag met het beheer Campagne Standard
description: Adobe Campaign biedt u een volledige set beheergereedschappen. Leer hoe u uw gebruikers beheert en uw kanalen configureert.
page-status-flag: never-activated
uuid: 64c34729-5c98-4db0-9131-af6dd0e78fb4
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: about-administrating-adobe-campaign
discoiquuid: 5587530a-2308-4be1-9f56-19eeb7a924d5
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 40bb454d13de14658bfc30a6454a1a896bf3ad70

---


# Ga aan de slag met het beheer Campagne Standard {#about-administrating-adobe-campaign}

<table>
<tr><td><img src="assets/do-not-localize/icon_menu.svg" width="60px"><p><a href="#administration-menu">Menu Beheer</a></p></td>
<td><img src="assets/do-not-localize/icon_users.svg" width="60px"><p><a href="#users-security">Gebruikers en beveiliging</a></p></td>
<td><img src="assets/do-not-localize/icon_channels.svg" width="60px"><p><a href="#channels-configuration">Kanaalconfiguratie</a></p></td>
<td><img src="assets/do-not-localize/icon_settings.svg" width="60px"><p><a href="#application-settings">Toepassingsinstellingen</a></p></td></tr>
</table>

Als cloudgebaseerde oplossing biedt Adobe Campaign beheerders verschillende manieren om de toepassing te configureren. Hoewel de infrastructuurconfiguratie door Adobe wordt uitgevoerd, kunnen functionele beheerders verschillende configuratiebewerkingen uitvoeren die hieronder worden beschreven.

>[!NOTE]
>
>Als u vragen of verzoeken hebt over implementatie en configuratie, neemt u contact op met de manager van uw Adobe-account.

## Menu Beheer {#administration-menu}

<img src="assets/do-not-localize/icon_menu.svg" width="60px">

De verschillende Adobe Campagne-beheerbewerkingen worden uitgevoerd via het **[!UICONTROL Administration]** menu dat toegankelijk is wanneer u in de linkerbovenhoek op het Adobe Campagne-logo klikt. Dit deel van de interface is alleen toegankelijk voor functionele beheerders van het platform.

De verschillende beschikbare menu&#39;s zijn:

* [Gebruikers en beveiliging](../../administration/using/about-access-management.md): Met dit menu kunt u de toegang tot het platform (gebruikers, rollen, beveiligingsgroepen, eenheden) beheren.
* [Kanalen](../../administration/using/about-channel-configuration.md): In dit menu worden de technische parameters gegroepeerd die zijn gekoppeld aan de verschillende platformkanalen (e-mail, SMS) en het typologie- en quarantainebeheer.
* [Toepassingsinstellingen](../../administration/using/external-accounts.md): Met dit menu kunt u verschillende toepassingselementen configureren (externe accounts, opties, technische workflows).
* [Ontwikkeling](../../developing/using/data-model-concepts.md): Met dit menu kunt u uw aangepaste bronnen beheren en toegang krijgen tot diagnostische gereedschappen.
* [Instellingen](../../administration/using/branding.md)voor instanties: In dit menu definieert u de verschillende merken en configureert u de instellingen (logo, beheer, bijhouden, URL-domein voor toegang tot de bestemmingspagina&#39;s, enz.).
* [Implementatie](../../automating/using/managing-packages.md): In dit menu worden de import- en exportopties voor het pakket opnieuw gegroepeerd.
* [Klantcijfers](../../audiences/using/active-profiles.md): Adobe Campaign biedt een rapport waarin het aantal actieve profielen wordt weergegeven. Dit rapport is slechts informatief, het heeft geen directe invloed op het factureren.
* [Privacygereedschappen](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_GDPR.html): Met dit menu kunt u GDPR-toegang maken, aanvragen verwijderen en de evolutie ervan volgen.

## Gebruikers en beveiliging {#users-security}

<img src="assets/do-not-localize/icon_users.svg"  width="60px">

Nodig gebruikers uit om tot de toepassing toegang te hebben en **veiligheidsgroepen** te beheren, die reeksen gebruikers zijn die de zelfde rollen en de rechten binnen uw organisatie delen. Standaard biedt Adobe Campagne een set **rollen** waarmee u eenheidmachtigingen kunt definiëren die zijn toegewezen aan gebruikers en gebruikersgroepen. In combinatie met **organisatorische eenheden** geven rollen gebruikers een gefilterde weergave van de interface en definiëren ze hun toegang tot de verschillende functies.

De standaard van de campagne staat u ook toe om op veiligheid betrekking hebbende informatie te controleren. U kunt informatie over gegevensexport ophalen die door gebruikers via het **[!UICONTROL Export audits]** scherm wordt uitgevoerd, en het **[!UICONTROL Licenses]** scherm gebruiken om alle geïnstalleerde Campagnelicenties binnen uw organisatie te controleren, en andere informatie zoals het nummer van de build, de releaseversie en de voorwaarden van overeenkomst.

Meer informatie:

* [Gebruikersbeheer](../../administration/using/users-management.md)
* [Organisatorische eenheden](../../administration/using/organizational-units.md)
* [Lijst met rollen](../../administration/using/list-of-roles.md)
* [Groepen en gebruikers beheren](../../administration/using/managing-groups-and-users.md)
* [Logbestanden voor exporteren controleren](../../administration/using/auditing-export-logs.md)
* [Licenties](../../administration/using/licenses.md)

## Kanaalconfiguratie {#channels-configuration}

<img src="assets/do-not-localize/icon_channels.svg" width="60px">

Alle communicatiekanalen in Adobe Campaign moeten op de juiste wijze zijn geconfigureerd om berichten te verzenden. In het **[!UICONTROL Channel]** menu kunt u de technische parameters beheren die aan de verschillende kanalen zijn gekoppeld.

Verschillende parameters voor **e-mail** configureren: verwerkingsregels voor stuit, quarantines, e-maileigenschappen en routeparameters, typoly-regels. Bepaal het verpletteren van configuraties en eigenschappen voor het kanaal van **SMS** , evenals het coderen van SMS en formaten.

Stel **mobiele toepassingen** in om in-app berichten en pushmeldingen te kunnen verzenden met behulp van Adobe Experience Platform SDK&#39;s en configureer **transactiemeldingen** door gebeurtenissen te maken en in te stellen.

Meer informatie:

* [Kanaalconfiguratie](../../administration/using/about-channel-configuration.md)
* [E-mailkanaal configureren](../../administration/using/configuring-email-channel.md)
* [SMS-kanaal configureren](../../administration/using/configuring-sms-channel.md)
* [Een mobiele toepassing configureren](../../administration/using/configuring-a-mobile-application.md)
* [Transactieberichten configureren](../../administration/using/configuring-transactional-messaging.md)

## Toepassingsinstellingen {#application-settings}

<img src="assets/do-not-localize/icon_settings.svg" width="60px">

De standaard van de campagne komt met verschillende toepassingselementen die kunnen worden gevormd om aan uw behoeften te passen.

Stel **externe accounts** in waarmee u Adobe Campagne kunt verbinden met externe servers. Toegang tot standaarddoeltoewijzingen voor campagnes en controle uw platform met behulp van **technische workflows**.

Definieer een of meerdere **merken** voor uw organisatie en configureer de verzending van **realtime meldingen** binnen de toepassing in het geval van belangrijke systeemactiviteiten.

Meer informatie:

* [Informatie over standaardinstellingen voor campagnes](../../administration/using/about-campaign-standard-settings.md)
* [Externe rekeningen](../../administration/using/external-accounts.md)
* [Doeltoewijzingen in campagne](../../administration/using/target-mappings-in-campaign.md)
* [Technische workflows](../../administration/using/technical-workflows.md)
* [Branding](../../administration/using/branding.md)
* [Interne meldingen verzenden](../../administration/using/sending-internal-notifications.md)

## Aanvullende bronnen

* [Toegangsrechten van gebruikers beheren (video)](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/administrating/managing-user-access-rights.html)
* [Documentatie van het regelpaneel](https://docs.adobe.com/content/help/en/control-panel/using/control-panel-home.html)
