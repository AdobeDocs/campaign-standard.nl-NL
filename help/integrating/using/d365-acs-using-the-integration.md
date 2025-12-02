---
title: De integratie van Microsoft Dynamics 365 gebruiken
description: Leer hoe u de Microsoft Dynamics 365 kunt gebruiken met Campaign Standard-integratie
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
feature: Microsoft CRM Integration
old-role: Data Architect
role: Developer
level: Experienced
exl-id: fb464183-13bf-4b47-ac27-4b785bafef37
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '1652'
ht-degree: 0%

---

# De Microsoft Dynamics 365-integratie gebruiken

Er zijn verscheidene gegevensstromen die de Integratie van Adobe Campaign Standard met Microsoft Dynamics 365 uitvoert. Deze stromen zijn gedetailleerd in [ deze pagina ](../../integrating/using/d365-acs-self-service-app-workflows.md).

Meer details over de gegevensstromen kunnen verder onderaan in dit document in de [ sectie van de Stromen van Gegevens ](#data-flows) worden gevonden.

## Adobe Campaign Standard-gebruikerservaring

Wanneer een contactpersoon wordt gemaakt, gewijzigd of verwijderd (als Verwijderen is ingeschakeld) in Microsoft Dynamics 365, wordt deze naar Campaign Standard verzonden. Deze contacten zullen in het scherm van Profielen in Campagne zichtbaar zijn en kunnen in marketing campagnes worden gericht. Zie het scherm Profielen hieronder.

![](assets/MSdynamicsACS-usage1.png)

Wanneer een opt-out attribuut in Campagne wordt gewijzigd, zal het in Dynamiek 365 worden weerspiegeld als u **Unidirectioneel (Campagne aan Microsoft Dynamics 365)** of **Bidirectionele** opt-out configuratie hebt geselecteerd, en als u die bepaalde die attributen correct in kaart gebracht hebt.

## Microsoft Dynamics 365-gebruikerservaring

Voor egress worden de volgende e-mailmarketinggebeurtenissen verzonden van Campagne naar Dynamics 365 en in de tijdlijnweergave van Microsoft Dynamics 365 weergegeven als aangepaste activiteiten:

* Adobe Campaign E-mail verzenden

* Adobe Campaign-e-mail geopend

* Adobe Campaign-e-mailURL klikken

* Adobe Campaign-e-mailstempel

Om de Chronologie van een contact te bekijken, navigeer aan uw contactenlijst door op de Hub van de Verkoop van de Dynamiek 365 drop-down menu te klikken. Klik vervolgens op Contactpersonen op de linkermenubalk en selecteer een contactpersoon.

>[!NOTE]
>
>**Adobe Campaign voor Microsoft Dynamics 365** app in AppSource zal in uw Microsoft Dynamics 365 instantie moeten worden geïnstalleerd om deze gebeurtenissen te bekijken. [Meer informatie](../../integrating/using/d365-acs-configure-d365.md#install-appsource-app).

Hieronder ziet u een momentopname van het scherm van het Contact voor &quot;Gebruiker van de Dynamiek&quot;. In de mening van de Chronologie, zult u merken dat de Gebruiker van de Dynamiek een e-mail werd verzonden verbonden aan de Naam van de Campagne &quot;2019LoyaltyCamp&quot;en de Naam van de Levering &quot;DM190&quot;. Dynamics User opende het e-mailbericht en klikte ook een URL in e-mail; allebei van deze acties creeerden gebeurtenissen die hieronder ook tonen. Als u naar de rechterhoek kijkt, ziet u de RA-kaart (Relationship Assistant). Deze kaart bevat momenteel een taak die u moet opvolgen op de aangeklikte URL.

![](assets/do-not-localize/MSdynamicsACS-usage4.png)

Zie hieronder voor een close-up van de mening van de Chronologie voor de Gebruiker van de Dynamiek.

![](assets/do-not-localize/MSdynamicsACS-usage5.png)

Hieronder volgt een close-up van de Relationship Assistant-kaart (RA). De app AppSource bevat een workflow die zoekt naar een Adobe-gebeurtenis Click URL. Wanneer deze gebeurtenis zich voordoet, wordt een taak gemaakt en wordt een vervaldatum ingesteld. Hierdoor kan de taak worden weergegeven in de RA-kaart, waardoor deze meer zichtbaar wordt. Er is een vergelijkbare workflow voor Adobe Email Bounce-gebeurtenissen, waarbij een taak wordt toegevoegd om het ongeldige e-mailadres te combineren. Deze workflows kunnen in de oplossing worden uitgeschakeld.

![](assets/do-not-localize/MSdynamicsACS-usage6.png)

Als u klikt op het onderwerp van de verzendgebeurtenis, ziet u een formulier dat lijkt op het hieronder weergegeven formulier. De formulieren voor open en bounce-gebeurtenissen zijn vergelijkbaar.

![](assets/do-not-localize/mirror_page_url_send.png)

Het formulier voor URL-klikgebeurtenissen voor e-mail voegt een extra kenmerk toe voor de URL waarop is geklikt:

![](assets/do-not-localize/mirror_page_url_click.png)

Hieronder volgt een lijst met kenmerken en een beschrijving:

* **Onderwerp**: Onderwerp van de gebeurtenis; samengesteld uit identiteitskaart van de Campagne en identiteitskaart van de Levering van de e-maillevering

* **Eigenaar**: De toepassingsgebruiker die in de post-provisioning stappen wordt gecreeerd

* **Betreffende**: De naam van het contact

* **Naam van de Campagne**: Identiteitskaart van de Campagne in Campaign Standard

* **Naam van de Levering**: Leverings identiteitskaart in Campaign Standard

* **Verzonden/Geopende Datum/Geklikt/Geëindigd**: Datum/tijd toen de gebeurtenis werd gecreeerd

* **Volgend URL**: URL die werd geklikt

* **de Pagina URL van het Spiegel**: URL aan de spiegelpagina van e-mail die werd verzonden/geopend/kliked/gebogen. De vervalperiode van de pagina van de e-mailspiegel kan in het configuratiescherm van de overeenkomstige activiteit van het e-mailkanaal van de Campagne worden gewijzigd. [Meer informatie](../../administration/using/configuring-email-channel.md#validity-period-parameters).

>[!NOTE]
>
>Voor opt-out, wanneer een opt-out attribuut in Microsoft Dynamics 365 wordt gewijzigd, zal het in Campagne worden weerspiegeld als u **Unidirectioneel (Campagne aan Microsoft Dynamics 365)** selecteerde of **bidirectionele** opt-out configuratie, en als u die bepaalde die eigenschap correct in kaart wordt gebracht hebt.

## Gegevensstromen {#data-flows}

### Contact- en aangepaste entiteitsvermeldingen

Nieuwe, bijgewerkte en verwijderde records (Opmerking: verwijderde bestanden moeten zijn ingeschakeld) worden vanuit de Microsoft Dynamics 365-tabel met contactpersonen verzonden naar de tabel met het campagneprofiel.

De afbeeldingen van de lijst kunnen in de integratietoepassing UI worden gevormd om Microsoft Dynamics 365 lijstattributen aan de lijstattributen van de Campagne in kaart te brengen. De tabeltoewijzingen kunnen zo nodig worden gewijzigd om kenmerken toe te voegen of te verwijderen.

De aanvankelijke looppas van de gegevensstroom wordt ontworpen om alle in kaart gebrachte verslagen, met inbegrip van die duidelijk als &quot;inactief&quot;over te brengen; later, zal de integratie slechts stijgende updates verwerken. De uitzondering aan dit is als het gegeven wordt herhaald of als een filter wordt gevormd; de basis, op attribuut-gebaseerde, het filtreren regels kunnen worden gevormd om te bepalen welke verslagen aan synchronisatie aan Campagne.

De basis vervangingsregels kunnen in de integratietoepassing UI worden gevormd om een attributenwaarde met een verschillende waarde (b.v., &quot;groen&quot;voor &quot;#00FF00&quot;, &quot;F&quot;voor 1, enz.) te vervangen.

Afhankelijk van het volume van verslagen, kan uw opslag van de Campagne SFTP voor de aanvankelijke gegevensoverdracht moeten worden gebruikt. [Meer informatie](#initial-data-transfer).

Het attribuut externalId van de de profiellijst van de Campagne moet met de Dynamica 365 contactattributen contactId worden bevolkt om contacttoegang te werken. Aangepaste entiteiten van de campagne moeten ook worden gevuld met een attribuut van de identiteitskaart van de Dynamiek 365 uniek; nochtans, kan dit attribuut in om het even welk attribuut van de de douaneentiteit van de Campagne worden opgeslagen (d.w.z., moet externalId niet zijn).

>[!NOTE]
>
>Voor ingangen van de douaneentiteit, veranderings het volgen binnen Dynamiek 365 voor gesynchroniseerde douaneentiteiten moet worden toegelaten.

#### Aangepaste entiteiten

De [ integratie 365-Adobe Campaign Standard van Microsoft Dynamics ](../../integrating/using/d365-acs-get-started.md) steunt douaneentiteiten, toelatend douaneentiteiten in Dynamiek 365 om aan overeenkomstige douanemiddelen in Campagne worden gesynchroniseerd.

De nieuwe gegevens in de douanemiddelen kunnen voor verscheidene doeleinden, met inbegrip van segmentatie en verpersoonlijking worden gebruikt.

De integratie ondersteunt zowel gekoppelde als niet-gekoppelde tabellen. Koppeling wordt ondersteund tot drie niveaus (d.w.z. niveau1->niveau2->niveau3).

>[!IMPORTANT]
>
>Als om het even welk dossier van het middel van de Campagne persoonlijke informatie bevat, zijn de specifieke aanbevelingen van toepassing. Leer meer [ in deze sectie ](../../integrating/using/d365-acs-notices-and-recommendations.md#acs-msdyn-manage-data).
>

Wanneer het vormen van de gegevensstromen van de douaneentiteit, is het belangrijk om zich van het volgende bewust te zijn:

* Het creëren van en het wijzigen van de douanemiddelen van de Campagne zijn gevoelige verrichtingen die door deskundige slechts gebruikers moeten worden uitgevoerd.
* Voor de stromen van de gegevens van de douaneentiteit, verandering het volgen binnen Dynamiek 365 voor gesynchroniseerde douaneentiteiten moet worden toegelaten.
* Als een ouder en verbonden kindverslag dicht bij de zelfde tijd in Dynamiek 365, wegens de parallelle verwerking van de integratie worden gecreeerd, is er een lichte kans dat een nieuw kindverslag aan Campaign vóór zijn ouderverslag zou kunnen worden geschreven.

* Als de ouder en het kind op de kant van de Campagne gebruikend de **1 cardinaliteit eenvoudige verbinding** optie verbonden zijn, zal het kindverslag verborgen en ontoegankelijk (via UI of API) blijven tot het ouderverslag in Campagne aankomt.

* (Veronderstellend **1 kardinaliteit eenvoudige verbinding** in Campagne) als het kindverslag in Dynamiek 365 wordt bijgewerkt of geschrapt, en die verandering wordt geschreven aan Campagne alvorens het ouderverslag in Campagne (niet waarschijnlijk, maar een verre mogelijkheid) toont, zal die update of schrapping niet in Campagne worden verwerkt en een fout zal worden geworpen. In het geval van een update moet de betreffende record opnieuw worden bijgewerkt in Dynamics 365 om de bijgewerkte record te synchroniseren. In geval van schrapping moet de betrokken record afzonderlijk aan de campagnezijde worden vermeld, aangezien er geen record meer is in Dynamics 365 om te verwijderen of bij te werken.

* Als u in een situatie loopt waar u denkt u kindverslagen en geen manier hebt om tot hen toegang te hebben, kunt u het type van de kardinaalverbinding in **0 of 1 kardinaliteit eenvoudige verbinding** tijdelijk veranderen om tot die verslagen toegang te hebben.

Een uitvoeriger overzicht van de douanemiddelen van de Campagne kan [ in deze sectie ](../../developing/using/key-steps-to-add-a-resource.md) worden gevonden.

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

Waarden voor uitschakelen (bijvoorbeeld lijst van gewezen personen) worden gesynchroniseerd tussen systemen. U kunt uit de volgende opties kiezen bij instapweigering:

* **Unidirectioneel (Microsoft Dynamics 365 aan Campagne)**: De dynamiek 365 is bron van waarheid voor opt-outs. De opt-outkenmerken worden in één richting gesynchroniseerd, van Dynamics 365 tot Campaign Standard.&quot;
* **Unidirectioneel (Campagne aan Microsoft Dynamics 365)**: Campaign Standard is de bron van waarheid voor opt-outs. Kenmerken voor Uitschakelen worden in één richting gesynchroniseerd van Campaign Standard naar Dynamics 365
* **Bidirectional**: Dynamiek 365 EN Campaign Standard zijn beide bronnen van waarheid. Opt-out-kenmerken worden bidirectioneel gesynchroniseerd tussen Campaign Standard en Dynamics 365

Als u een afzonderlijk proces hebt voor het beheren van de synchronisatie met de optie om te weigeren tussen de systemen, kan de gegevensstroom van de integratie worden uitgeschakeld.

>[!NOTE]
>
>In de integratietoepassing UI, worden de **Unidirectionele (Microsoft Dynamics 365 aan Campagne)** en **Bidirectionele** opt-out gebruiksgevallen gevormd in een afzonderlijke opt-out werkschema. [Meer informatie](../../integrating/using/d365-acs-self-service-app-data-sync.md#opt-in-out-wf).
>
>Het **Unidirectionele (Campagne aan Microsoft Dynamics 365)** opt-out gebruiksgeval is een uitzondering; het wordt gevormd binnen het ingangswerkschema (Contact aan Profiel).
>

De klant moet aangeven dat de toewijzing van de &quot;opt-out&quot;-stroom moet plaatsvinden, aangezien de zakelijke vereisten per onderneming kunnen verschillen. Aan de kant van de Campagne, slechts kunnen de OOTB opt-out attributen worden gebruikt voor opt-out afbeelding:

* lijst van gewezen personen
* denyListEmail
* denyListFax
* denyListMobile
* denyListPhone
* denyListPostalMail
* denyListPushnotification
* ccpaOptOut

In Dynamiek 365, hebben de meeste opt-outgebieden het &quot;niet&quot;prefix; nochtans, kunt u andere attributen voor opt-outdoeleinden ook gebruiken als de gegevens-types compatibel zijn.

### Eerste gegevensoverdracht {#initial-data-transfer}

De eerste gegevensoverdracht kan enige tijd duren, afhankelijk van het aantal records dat u van Microsoft Dynamics 365 gebruikt. Na de eerste gegevensoverdracht neemt de integratie de incrementele updates op.
