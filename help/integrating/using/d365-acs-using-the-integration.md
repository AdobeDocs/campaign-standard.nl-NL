---
title: De integratie van Microsoft Dynamics 365 gebruiken
description: Leer hoe u Microsoft Dynamics 365 kunt gebruiken met Campaign Standard-integratie
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: fb464183-13bf-4b47-ac27-4b785bafef37
source-git-commit: e7fdaa4b1d77afdae8004a88bbe41bbbe75a3f3c
workflow-type: tm+mt
source-wordcount: '1607'
ht-degree: 0%

---

# De Microsoft Dynamics 365-integratie gebruiken

Er zijn verscheidene gegevensstromen die de Integratie van Adobe Campaign Standard met de Dynamica 365 van Microsoft uitvoert. Deze stromen worden in detail beschreven in [deze pagina](../../integrating/using/d365-acs-self-service-app-workflows.md).

Meer informatie over de gegevensstromen vindt u verderop in dit document in de [Gegevensstromen](#data-flows)  sectie.

## Adobe Campaign Standard-gebruikerservaring

Wanneer een contact wordt gecreeerd, gewijzigd, of geschrapt (als geschrapt wordt toegelaten) in de Dynamiek 365 van Microsoft, zal het naar Campaign Standard worden verzonden. Deze contacten zullen in het scherm van Profielen in Campagne zichtbaar zijn en kunnen in marketing campagnes worden gericht. Zie het scherm Profielen hieronder.

![](assets/MSdynamicsACS-usage1.png)

Wanneer een opt-out-kenmerk wordt gewijzigd in Campagne, wordt dit weerspiegeld in Dynamics 365 als u de optie **Unidirectioneel (campagne voor Microsoft Dynamics 365)** of **Bidirectioneel** de opt-out configuratie, en als u dat bepaalde attribuut correct in kaart gebracht hebt.

## Microsoft Dynamics 365 gebruikerservaring

Voor egress worden de volgende e-mailmarketinggebeurtenissen verzonden van Campagne naar Dynamics 365 en in de tijdlijnweergave van Microsoft Dynamics 365 weergegeven als aangepaste activiteiten:

* Adobe Campaign E-mail verzenden

* Adobe Campaign-e-mail geopend

* Adobe Campaign-e-mailURL klikken

* Adobe Campaign-e-mailstempel

Om de Chronologie van een contact te bekijken, navigeer aan uw contactenlijst door op de Hub van de Verkoop van de Dynamiek 365 drop-down menu te klikken. Klik vervolgens op Contactpersonen op de linkermenubalk en selecteer een contactpersoon.

>[!NOTE]
>
>De **Adobe Campaign for Microsoft Dynamics 365** app in AppSource moet zijn geïnstalleerd in uw Microsoft Dynamics 365-exemplaar om deze gebeurtenissen te kunnen weergeven. [Meer informatie](../../integrating/using/d365-acs-configure-d365.md#install-appsource-app).

Hieronder ziet u een momentopname van het scherm van het Contact voor &quot;Gebruiker van de Dynamiek&quot;. In de mening van de Chronologie, zult u merken dat de Gebruiker van de Dynamiek een e-mail werd verzonden verbonden aan de Naam van de Campagne &quot;2019LoyaltyCamp&quot;en de Naam van de Levering &quot;DM190&quot;. Dynamics User opende het e-mailbericht en klikte ook een URL in e-mail; beide acties hebben gebeurtenissen gemaakt die ook hieronder worden weergegeven . Als u naar de rechterhoek kijkt, ziet u de RA-kaart (Relationship Assistant). bevat momenteel een taak die moet worden opgevolgd op de aangeklikte URL.

![](assets/do-not-localize/MSdynamicsACS-usage4.png)

Zie hieronder voor een close-up van de mening van de Chronologie voor de Gebruiker van de Dynamiek.

![](assets/do-not-localize/MSdynamicsACS-usage5.png)

Hieronder volgt een close-up van de Relationship Assistant-kaart (RA). De app AppSource bevat een workflow die zoekt naar een klikgebeurtenis via e-mail van de Adobe. Wanneer deze gebeurtenis zich voordoet, wordt een taak gemaakt en wordt een vervaldatum ingesteld. Hierdoor kan de taak worden weergegeven in de RA-kaart, waardoor deze meer zichtbaar wordt. Er is een vergelijkbare workflow voor Adobe-e-mailstuitergebeurtenissen, waarbij een taak wordt toegevoegd om het ongeldige e-mailadres te combineren. Deze workflows kunnen in de oplossing worden uitgeschakeld.

![](assets/do-not-localize/MSdynamicsACS-usage6.png)

Als u klikt op het onderwerp van de verzendgebeurtenis, ziet u een formulier dat lijkt op het hieronder weergegeven formulier. De formulieren voor open en bounce-gebeurtenissen zijn vergelijkbaar.

![](assets/do-not-localize/mirror_page_url_send.png)

Het formulier voor URL-klikgebeurtenissen voor e-mail voegt een extra kenmerk toe voor de URL waarop is geklikt:

![](assets/do-not-localize/mirror_page_url_click.png)

Hieronder volgt een lijst met kenmerken en een beschrijving:

* **Onderwerp**: onderwerp van het evenement; die bestaat uit de campagne-id en de bezorgings-id van de e-maillevering

* **Eigenaar**: De gebruiker van de toepassing die in de post-levering stappen wordt gecreeerd

* **Betreffende**: De naam van de contactpersoon

* **Campagnenaam**: De campagne-id in Campaign Standard

* **Leveringsnaam**: De leverings-id in Campaign Standard

* **Datum van verzending/openen/klikken/Afmelden**: Datum/tijd waarop de gebeurtenis is gemaakt

* **URL bijhouden**: URL waarop is geklikt

* **URL van pagina spiegelen**: De URL naar de spiegelpagina van het e-mailbericht dat is verzonden, geopend, geklikt of teruggestuurd. De vervalperiode van de pagina van de e-mailspiegel kan in het configuratiescherm van de overeenkomstige activiteit van het e-mailkanaal van de Campagne worden gewijzigd. [Meer informatie](../../administration/using/configuring-email-channel.md#validity-period-parameters).

>[!NOTE]
>
>Als u de optie Weigeren hebt ingeschakeld en een kenmerk Weigeren is gewijzigd in Microsoft Dynamics 365, wordt dit kenmerk weerspiegeld in Campagne als u de optie **Unidirectioneel (campagne voor Microsoft Dynamics 365)** of **Bidirectioneel** de opt-out configuratie, en als u dat bepaalde attribuut correct in kaart gebracht hebt.

## Gegevensstromen {#data-flows}

### Contact- en aangepaste entiteitsvermeldingen

Nieuwe, bijgewerkte en verwijderde records (Opmerking: verwijderde moet zijn ingeschakeld) worden vanuit de contacttabel Microsoft Dynamics 365 verzonden naar de tabel met cameraprofielen.

De afbeeldingen van de lijst kunnen in de integratietoepassing UI worden gevormd om de lijstattributen van de Dynamiek 365 van Microsoft aan de lijstattributen van de Campagne in kaart te brengen. De tabeltoewijzingen kunnen zo nodig worden gewijzigd om kenmerken toe te voegen of te verwijderen.

De eerste run van de gegevensstroom is ontworpen om alle toegewezen records over te brengen, met inbegrip van de records die als &quot;inactief&quot; zijn gemarkeerd; vervolgens zal de integratie alleen incrementele updates verwerken . De uitzondering op dit is als het gegeven wordt herhaald of als een filter wordt gevormd; basis, op attribuut-gebaseerde, het filtreren regels kunnen worden gevormd om te bepalen welke verslagen aan synchronisatie aan Campagne.

De basis vervangingsregels kunnen in de integratietoepassing UI worden gevormd om een attributenwaarde met een verschillende waarde (b.v., &quot;groen&quot;voor &quot;#00FF00&quot;, &quot;F&quot;voor 1, enz.) te vervangen.

Afhankelijk van het volume van verslagen, kan uw opslag van de Campagne SFTP voor de aanvankelijke gegevensoverdracht moeten worden gebruikt. [Meer informatie](#initial-data-transfer).

Het attribuut externalId van de de profiellijst van de Campagne moet met de Dynamica 365 contactattributen contactId worden bevolkt om contacttoegang te werken. De aangepaste entiteiten van de campagne moeten ook worden gevuld met het attribuut &#39;Dynamics 365 unique ID&#39;; dit kenmerk kan echter worden opgeslagen in elk kenmerk van een aangepaste entiteit voor campagne (het hoeft dus niet om externalId te gaan).

>[!NOTE]
>
>Voor ingangen van de douaneentiteit, veranderings het volgen binnen Dynamiek 365 voor gesynchroniseerde douaneentiteiten moet worden toegelaten.

#### Aangepaste entiteiten

De [Integratie van Microsoft Dynamics 365-Adobe Campaign Standard](../../integrating/using/d365-acs-get-started.md) steunt douaneentiteiten, toelatend douaneentiteiten in Dynamiek 365 om aan overeenkomstige douanemiddelen in Campagne worden gesynchroniseerd.

De nieuwe gegevens in de douanemiddelen kunnen voor verscheidene doeleinden, met inbegrip van segmentatie en verpersoonlijking worden gebruikt.

De integratie ondersteunt zowel gekoppelde als niet-gekoppelde tabellen. Koppeling wordt ondersteund tot drie niveaus (niveau1->niveau2->niveau3).

>[!IMPORTANT]
>
>Als om het even welk dossier van het middel van de Campagne persoonlijke informatie bevat, zijn de specifieke aanbevelingen van toepassing. Meer informatie [in deze sectie](../../integrating/using/d365-acs-notices-and-recommendations.md#acs-msdyn-manage-data).

Wanneer het vormen van de gegevensstromen van de douaneentiteit, is het belangrijk om zich van het volgende bewust te zijn:

* Het creëren van en het wijzigen van de douanemiddelen van de Campagne zijn gevoelige verrichtingen die door deskundige slechts gebruikers moeten worden uitgevoerd.
* Voor de stromen van de gegevens van de douaneentiteit, verandering het volgen binnen Dynamiek 365 voor gesynchroniseerde douaneentiteiten moet worden toegelaten.
* Als een ouder en verbonden kindverslag dicht bij de zelfde tijd in Dynamiek 365, wegens de parallelle verwerking van de integratie worden gecreeerd, is er een lichte kans dat een nieuw kindverslag aan Campaign vóór zijn ouderverslag zou kunnen worden geschreven.

* Als het bovenliggende element en het onderliggende element aan de zijde Campagne zijn gekoppeld, gebruikt u de optie **1 cardinaliteit eenvoudige link** de onderliggende record verborgen en ontoegankelijk blijft (via UI of API) totdat de bovenliggende record in Campaign wordt ontvangen.

* (aangenomen **1 cardinaliteit eenvoudige link** in Campagne) als het kindverslag in Dynamiek 365 wordt bijgewerkt of geschrapt, en die verandering wordt geschreven aan Campagne alvorens het ouderverslag in Campaign (niet waarschijnlijk, maar een verre mogelijkheid) verschijnt, zal die update of schrapping niet in Campagne worden verwerkt en een fout zal worden geworpen. In het geval van een update moet de betreffende record opnieuw worden bijgewerkt in Dynamics 365 om de bijgewerkte record te synchroniseren. In geval van schrapping moet de betrokken record afzonderlijk aan de campagnezijde worden vermeld, aangezien er geen record meer is in Dynamics 365 om te verwijderen of bij te werken.

* Als u in een situatie terechtkomt waarin u denkt dat u kinderrecords hebt verborgen en deze niet kunt openen, kunt u het type cardinaliteitskoppeling tijdelijk wijzigen in **0 of 1 cardinaliteit, eenvoudige koppeling** om toegang te krijgen tot die records.

Een uitgebreider overzicht van aangepaste campagnebronnen vindt u [in deze sectie](../../developing/using/key-steps-to-add-a-resource.md).

### Gebeurtenisstroom voor e-mailmarketing{#email-marketing-event-flow}

E-mailmarketinggebeurtenissen worden vanuit Campagne verzonden naar Microsoft Dynamics 365 en worden weergegeven in de tijdlijnweergave.

Ondersteunde typen marketinggebeurtenissen:
* Verzenden - e-mail verzonden naar ontvanger
* Openen - e-mail geopend door ontvanger
* Klik - URL binnen e-mail die door ontvanger wordt geklikt
* Stuiteren - e-mail naar ontvanger heeft een harde stuit ondergaan

De volgende gebeurtenisattributen worden getoond binnen Dynamiek 365:
* Naam van marketingcampagne
* Naam e-mailbezorging
* Tijdstempel
* URL van spiegel e-mailen
* URL geklikt (alleen klikgebeurtenissen)

E-mailmarketinggebeurtenissen kunnen via het type worden in-/uitgeschakeld (verzenden, openen, klikken, stuiteren), zodat alleen de gebeurtenistypen die u selecteert, worden doorgegeven aan Dynamics 365.

### Stroom uitschakelen {#opt-out-flow}

De waarden voor &quot;Opt-out&quot; (bv. lijst van gewezen personen) worden gesynchroniseerd tussen systemen; u kunt uit de volgende opties kiezen wanneer u aan boord gaat:

* **Unidirectioneel (Microsoft Dynamics 365 to Campaign)**: Dynamics 365 is een bron van waarheid voor opt-outs. De opt-uit attributen zullen in één richting van Dynamiek 365 aan Campaign Standard worden gesynchroniseerd&quot;
* **Unidirectioneel (campagne voor Microsoft Dynamics 365)**: Campaign Standard is de bron van de waarheid voor opt-outs. De opt-uit attributen zullen in één richting van Campaign Standard aan Dynamica 365 worden gesynchroniseerd
* **Bidirectioneel**: Dynamics 365 EN Campaign Standard zijn beide bronnen van waarheid. De opt-uit attributen zullen bidirectioneel tussen Campaign Standard en Dynamiek 365 worden gesynchroniseerd

Als u een afzonderlijk proces hebt voor het beheren van de synchronisatie met de optie om te weigeren tussen de systemen, kan de gegevensstroom van de integratie worden uitgeschakeld.

>[!NOTE]
>
>In de UI van de integratietoepassing, **Unidirectioneel (Microsoft Dynamics 365 to Campaign)** en de **Bidirectioneel** De gevallen van het opt-out-gebruik worden geconfigureerd in een afzonderlijke opt-out-workflow. [Meer informatie](../../integrating/using/d365-acs-self-service-app-data-sync.md#opt-in-out-wf).
>
>De **Unidirectioneel (campagne voor Microsoft Dynamics 365)** het geval van opt-out is een uitzondering; wordt geconfigureerd binnen de workflow voor toegang (Contactpersoon voor profiel).

De klant moet aangeven dat de toewijzing van de &quot;opt-out&quot;-stroom moet plaatsvinden, aangezien de zakelijke vereisten per onderneming kunnen verschillen. Aan de kant van de Campagne, slechts kunnen de OOTB opt-out attributen worden gebruikt voor opt-out afbeelding:

* lijst van gewezen personen
* denyListEmail
* denyListFax
* denyListMobile
* denyListPhone
* denyListPostalMail
* denyListPushnotification
* ccpaOptOut

In Dynamiek 365, hebben de meeste opt-outgebieden het &quot;donot&quot;prefix; u kunt echter ook andere kenmerken voor opt-outdoeleinden gebruiken als de gegevenstypen compatibel zijn.

### Eerste gegevensoverdracht {#initial-data-transfer}

De eerste gegevensoverdracht kan enige tijd duren, afhankelijk van het aantal records dat u hebt ingevoerd bij Microsoft Dynamics 365. Na de eerste gegevensoverdracht neemt de integratie de incrementele updates op.
