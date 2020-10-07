---
title: De integratie van Microsoft Dynamics 365 gebruiken
description: Leer hoe te om de Dynamica 365 van Microsoft met de integratie van Campaign Standard te gebruiken
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '1186'
ht-degree: 0%

---


# De integratie van Microsoft Dynamics 365 gebruiken

Deze integratie biedt verschillende functies:

* **Ingress**:

   * Breng in **contacten** van Dynamiek 365 in Campagne

   * **Aangepaste entiteiten**: Breng douanetabellen van Dynamiek 365 aan Campagne in. Meer informatie [in deze sectie](../../integrating/using/map-campaign-custom-resources-and-dynamics-365-custom-entities.md).

* **Bol**: Maak e-mailmarketinggebeurtenissen van ACS naar D365 (e-mail verzenden, openen, klikken, stuiteren)

* **Uitschakelen**: De status Weigeren via bidirectionele synchronisatie (bijvoorbeeld lijst van afgewezen personen)

Meer informatie over de gegevensstromen vindt u [in deze sectie](#data-flows).

## Adobe Campaign Standard-gebruikerservaring

Wanneer een contact wordt gecreeerd of (of geschrapt, als toegelaten) in Dynamiek 365 wordt veranderd, zal het over naar Campagne worden verzonden.  Deze contacten zullen in het scherm van Profielen in Campagne zichtbaar zijn en kunnen in marketing campagnes worden gericht.  Zie het scherm Profielen hieronder.

![](assets/MSdynamicsACS-usage1.png)

Wanneer een opt-out attribuut in Campagne wordt gewijzigd, zal het in Dynamiek 365 worden weerspiegeld als u de campagne-aan-Dynamiek 365 of bidirectionele opt-out configuratie hebt geselecteerd, en als u die bepaalde die eigenschap correct in kaart gebracht hebt.

## Gebruikerservaring voor Microsoft Dynamics 365

Voor egress worden de volgende e-mailmarketinggebeurtenissen verzonden van Campagne naar Dynamics 365 en weergegeven in de tijdlijnweergave van Dynamics 365 als aangepaste activiteiten:

* Adobe Campaign E-mail verzenden

* Adobe Campaign-e-mail geopend

* Adobe Campaign-e-mailURL klikken

* Adobe Campaign-e-mailstempel

Om de Chronologie van een contact te bekijken, navigeer aan uw contactenlijst door op de Hub van de Verkoop van de Dynamiek 365 drop-down menu te klikken.  Klik vervolgens op Contactpersonen op de linkermenubalk en selecteer een contactpersoon.

>[!NOTE]
>
>De app Adobe Campaign for Dynamics 365 in AppSource moet zijn geïnstalleerd in uw instantie Dynamics 365 om deze gebeurtenissen te kunnen bekijken.

Hieronder ziet u een momentopname van het scherm van het Contact voor &quot;Gebruiker van de Dynamiek&quot;.  In de mening van de Chronologie, zult u merken dat de Gebruiker van de Dynamiek een e-mail werd verzonden verbonden aan de Naam van de Campagne &quot;2019LoyaltyCamp&quot;en de Naam van de Levering &quot;DM190&quot;.  Dynamics User opende het e-mailbericht en klikte ook een URL in e-mail; beide acties hebben gebeurtenissen gemaakt die ook hieronder worden weergegeven .  Als u naar de rechterhoek kijkt, ziet u de RA-kaart (Relationship Assistant). bevat momenteel een taak die moet worden opgevolgd op de aangeklikte URL.

![](assets/do-not-localize/MSdynamicsACS-usage4.png)

Zie hieronder voor een close-up van de mening van de Chronologie voor de Gebruiker van de Dynamiek.

![](assets/do-not-localize/MSdynamicsACS-usage5.png)

Hieronder volgt een close-up van de Relationship Assistant-kaart (RA).  De app AppSource bevat een workflow die zoekt naar een klikgebeurtenis via e-mail van de Adobe.  Wanneer deze gebeurtenis zich voordoet, wordt een taak gemaakt en wordt een vervaldatum ingesteld.  Hierdoor kan de taak worden weergegeven in de RA-kaart, waardoor deze meer zichtbaar wordt.  Er is een vergelijkbare workflow voor Adobe-e-mailstuitergebeurtenissen, waarbij een taak wordt toegevoegd om het ongeldige e-mailadres te combineren.  Deze workflows kunnen in de oplossing worden uitgeschakeld.

![](assets/do-not-localize/MSdynamicsACS-usage6.png)

Als u klikt op het onderwerp van de verzendgebeurtenis, ziet u een formulier dat lijkt op het hieronder weergegeven formulier.  De formulieren voor open en bounce-gebeurtenissen zijn vergelijkbaar.

![](assets/do-not-localize/mirror_page_url_send.png)

Het formulier voor URL-klikgebeurtenissen voor e-mail voegt een extra kenmerk toe voor de URL waarop is geklikt:

![](assets/do-not-localize/mirror_page_url_click.png)

Hieronder volgt een lijst met kenmerken en een beschrijving:

* Betreft: onderwerp van het evenement; die bestaat uit de campagne-id en de bezorgings-id van de e-maillevering

* Eigenaar: De gebruiker van de toepassing die in de post-levering stappen wordt gecreeerd

* Betreffende: De naam van de contactpersoon

* Naam campagne: De campagne-id in Campaign Standard

* Naam van levering: De leverings-id in Campaign Standard

* Datum van verzending/openen/klikken/teruglopen: Datum/tijd waarop de gebeurtenis is gemaakt

* URL bijhouden: URL waarop is geklikt

* URL spiegel: De URL naar de spiegelpagina van het e-mailbericht dat is verzonden/geopend/geklikt/teruggestuurd

>[!NOTE]
>
>De vervalperiode van de pagina van de e-mailspiegel kan in het configuratiescherm van de overeenkomstige activiteit van het e-mailkanaal van de Campagne worden gewijzigd (zie de parameters [van de](../../administration/using/configuring-email-channel.md#validity-period-parameters)Geldigheidsperiode).

>[!NOTE]
>
>Voor opt-out, wanneer een opt-out attribuut in Dynamiek 365 wordt gewijzigd, zal het in Campagne worden weerspiegeld als u de Dynamiek 365-aan-Campagne of bidirectionele opt-out configuratie hebt geselecteerd, en als u die bepaalde eigenschap correct in kaart gebracht hebt.

## Gegevensstromen {#data-flows}

### Contact- en aangepaste entiteitsingress

Nieuwe en bijgewerkte (en verwijderde, als toegelaten) verslagen worden verzonden van de het contactlijst van de Dynamiek 365 naar de de profiellijst van de Campagne.

De afbeeldingen van de lijst kunnen worden gevormd om Dynamiek 365 lijstattributen aan de lijstattributen van de Campagne in kaart te brengen. De tabeltoewijzingen kunnen zo nodig worden gewijzigd om kenmerken toe te voegen of te verwijderen.

De eerste run van de gegevensstroom is ontworpen om alle toegewezen records over te brengen, met inbegrip van de records die als &quot;inactief&quot; zijn gemarkeerd; vervolgens zal de integratie alleen incrementele updates verwerken . De uitzondering op dit is als een filter wordt gevormd; basis, op attribuut-gebaseerde, het filtreren regels kunnen worden gevormd om te bepalen welke verslagen aan synchronisatie aan Campagne.

De basis vervangingsregels kunnen worden gevormd om een attributenwaarde met een verschillende waarde (b.v., &quot;groen&quot;voor &quot;#00FF00&quot;, &quot;F&quot;voor 1, enz.) te vervangen.

Afhankelijk van het volume van verslagen, kan uw opslag van de Campagne SFTP voor de aanvankelijke gegevensoverdracht moeten worden gebruikt.  Zie de sectie over &quot;Eerste gegevensoverdracht&quot;.

Het attribuut externalId van de de profiellijst van de Campagne moet met de Dynamica 365 contactattributen contactId worden bevolkt om contacttoegang te werken. De aangepaste entiteiten van de campagne moeten ook worden gevuld met het attribuut &#39;Dynamics 365 unique ID&#39;; dit kenmerk kan echter worden opgeslagen in elk kenmerk van een aangepaste entiteit voor campagne (het hoeft dus niet om externalId te gaan).

>[!NOTE]
>
>Voor ingangen van de douaneentiteit, veranderings het volgen binnen Dynamiek 365 voor gesynchroniseerde douaneentiteiten moet worden toegelaten.

### E-mailmarketinggebeurtenisstroom

E-mailmarketinggebeurtenissen worden vanuit Campagne verzonden naar Dynamics 365 en worden weergegeven in de tijdlijnweergave.

Ondersteunde typen marketinggebeurtenissen:
* Verzenden - e-mail verzonden naar ontvanger
* Openen - e-mail geopend door ontvanger
* Klik - URL binnen e-mail die door ontvanger wordt geklikt
* Stuiteren - e-mail naar ontvanger heeft een harde stuit ondergaan

De volgende gebeurteniskenmerken worden weergegeven in D365:
* Naam van marketingcampagne
* Naam e-mailbezorging
* Tijdstempel
* URL van spiegel e-mailen
* URL geklikt (alleen klikgebeurtenissen)

E-mailmarketinggebeurtenissen kunnen via het type worden in-/uitgeschakeld (verzenden, openen, klikken, stuiteren), zodat alleen de gebeurtenistypen die u selecteert, worden doorgegeven aan Dynamics 365.

### Stroom uitschakelen

De waarden voor &quot;Opt-out&quot; (bv. lijst van afgewezen personen) worden gesynchroniseerd tussen systemen; u kunt uit de volgende opties kiezen wanneer u aan boord gaat:
* Dynamics 365 is een bron van waarheid voor opt-outs: de optieattributen zullen in één richting van Dynamiek 365 aan Campaign Standard worden gesynchroniseerd
* Campaign Standard is de bron van de waarheid voor opt-outs: de opt-outkenmerken worden in één richting gesynchroniseerd, van Campaign Standard tot Dynamics 365
* Dynamics 365 EN Campaign Standard zijn beide bronnen van waarheid: de opt-outattributen zullen bidirectioneel tussen Campaign Standard en Dynamiek 365 worden gesynchroniseerd

Als u een afzonderlijk proces hebt voor het beheren van de synchronisatie met de optie om te weigeren tussen de systemen, kan de gegevensstroom van de integratie worden uitgeschakeld.

De klant moet aangeven dat de toewijzing van de &quot;opt-out&quot;-stroom moet plaatsvinden, aangezien de zakelijke vereisten per onderneming kunnen verschillen.  Aan de kant van de Campagne, slechts kunnen de OOTB opt-out attributen worden gebruikt voor opt-out afbeelding:
* lijst van afgewezen personen
* denyListEmail
* denyListFax
* denyListMobile
* denyListPhone
* denyListPostalMail
* denyListPushnotification
* ccpaOptOut

In Dynamiek 365, hebben de meeste opt-outgebieden het &quot;donot&quot;prefix; u kunt echter ook andere kenmerken voor opt-outdoeleinden gebruiken als de gegevenstypen compatibel zijn.

### Eerste gegevensoverdracht

Dynamics 365 tables over 500k verslagen zullen naar uw opslag van de Campagne SFTP moeten worden uitgevoerd om via het werkschema van de Campagne te worden ingevoerd.

De eerste gegevensoverdracht is een eenmalige, op bestanden gebaseerde gegevensoverdracht. Na de gegevensoverdracht, zal de integratie APIs voor de stijgende updates gebruiken.
