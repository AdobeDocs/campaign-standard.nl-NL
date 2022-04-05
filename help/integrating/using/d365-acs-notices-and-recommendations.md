---
title: Campagne en Microsoft Dynamics 365 - gegevensbeheer
description: Leer hoe Campaign Standard en Microsoft Dynamics 365 gemeenschappelijke gegevens beheren
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: aab6f005-f3da-4c0b-b856-da8504e611dc
source-git-commit: 4b0c4fb13cc11c06e2487e531ca96574e49b6beb
workflow-type: tm+mt
source-wordcount: '2507'
ht-degree: 1%

---

# Best practices en beperkingen {#acs-msdyn-best-practices}

## Gegevens beheren {#acs-msdyn-manage-data}

Voor contact en aangepaste entiteitssynchronisatie, behandelt deze integratie **Microsoft Dynamics 365 als bron van de waarheid**.  Wijzigingen in gesynchroniseerde kenmerken moeten worden doorgevoerd in Dynamics 365 en niet in Adobe Campaign Standard).  Als er wijzigingen worden aangebracht in Campagne, kunnen deze tijdens de synchronisatie worden overschreven in Campagne, omdat de synchronisatie in één richting plaatsvindt.

De integratie kan naar keuze worden gevormd om profiel uit te geven schrapt vraag aan Campagne wanneer een contact in Dynamica 365 wordt geschrapt helpen gegevensintegriteit handhaven. Een profielverwijdering is echter anders dan een privacyverwijdering. Een privacyschrapping in Campagne zal het het profielverslag van de Campagne en bijbehorende logboekingangen verwijderen; overwegende dat een reguliere profielverwijdering alleen de Campagneprofielrecord verwijdert, zodat de resterende bestanden achter blijven in Campagnelogboeken. Als de functie voor het verwijderen van profielen is ingeschakeld in de integratie, moeten aanvullende stappen worden uitgevoerd om privacyverzoeken van betrokkenen correct te verwerken. Raadpleeg de stappen in het dialoogvenster [Sectie Privacy hieronder](#manage-privacy-requests).

## Privacy{#acs-msdyn-manage-privacy}

Deze integratie is ontworpen om gegevens van eindgebruikers over te dragen tussen Microsoft Dynamics 365 en Adobe Campaign Standard. Dit gegeven omvat persoonlijke informatie als het in uw eind - gebruikersgegevens bevat.  Uw bedrijf is verantwoordelijk voor het naleven van de privacywetten en -regels die van toepassing zijn op het verzamelen en gebruiken van persoonsgegevens.

Deze integratie is ontworpen om gegevens van eindgebruikers (inclusief, maar niet beperkt tot, persoonlijke informatie, als deze in uw gegevens voor eindgebruikers staat), over te brengen tussen Microsoft Dynamics 365 en Adobe Campaign Standard. Uw bedrijf is verantwoordelijk voor het naleven van de privacywetten en -regels die van toepassing zijn op het verzamelen en gebruiken van persoonsgegevens.

De integratie geeft geen privacy van de betrokkene weer (bv. GDPR) en schrapt of behandelt geen andere privacyverzoeken (met uitzondering van opt-out). Wanneer u privacyverzoeken verwerkt, moet u dit onafhankelijk doen in zowel Microsoft Dynamics 365 als Campagne (via de Adobe Experience Platform Privacy Service).

Als u de integratie hebt gevormd om regelmatige profiel uit te geven schrapt vraag aan Campagne wanneer een contact in Dynamiek 365 wordt geschrapt, zouden de stappen hieronder moeten worden gevolgd. Zorg ervoor dat de record in kwestie tijdens dit proces niet wordt bijgewerkt.

1. Aanvraag voor verwijderen van privacy van probleem aan [Adobe Experience Platform Privacy Service](https://developer.adobe.com/experience-platform-apis/references/privacy-service)

1. Verzoek van de monitor tot het met succes is voltooid

1. Controleren of de record niet meer in uw Campagne-instantie staat

1. (Kort daarna) Verwijder de privacy van problemen in Dynamics 365

1. Controleren of de record van beide systemen is verwijderd

Hieronder vindt u koppelingen die u helpen bij het implementeren van verzoeken om toegang tot en/of het verwijderen van privacygerelateerde verzoeken in elk systeem:

* [Microsoft Dynamics 365](https://docs.microsoft.com/en-us/dynamics365/get-started/gdpr/)

* [Adobe Campaign Standard](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html)

>[!IMPORTANT]
>
>Als om het even welk dossier van de Bron douane van de Campagne persoonlijke informatie bevat, toepasselijk op het gebruik van een klant van Campagne, zou zulk verslag aan een overeenkomstig het profielverslag van de Campagne (of direct of door een andere douanemiddel) moeten worden verbonden zodat een privacy verwante schrapping in het profielverslag het verbonden douanemiddelverslag met persoonlijke informatie kan ook schrappen; de koppelings- en verwijderingsopties tussen de entiteiten moeten zo zijn geconfigureerd dat deze trapsgewijze verwijdering van de gekoppelde records mogelijk is. Persoonlijke gegevens moeten niet worden ingevoerd in een aangepaste bron die niet aan het profiel is gekoppeld.

## Uitschakelen {#opt-out}

Wegens de verschillen in opt-outattributen tussen de Dynamica 365 van Microsoft en Campagne, en wegens de verschillen in bedrijfsvereisten van elke klant, is opt-out afbeelding verlaten als oefening voor de klant om te voltooien.  Het is belangrijk ervoor te zorgen dat de optie-outs correct tussen systemen worden toegewezen, zodat de voorkeuren voor de optie-uit voor eindgebruikers behouden blijven en dat gebruikers geen communicatie ontvangen via een kanaal waarvan ze hebben afgezien.

Houd er rekening mee dat alleen de volgende opties kunnen worden gebruikt in toewijzingen voor niet-deelname:

* Campagneringkenmerken met het voorvoegsel &#39;Geen contact meer maken door&#39; (bijvoorbeeld Geen contact meer via e-mail), of

* het specifieke kenmerk voor de CCPA

Meer informatie over de velden Profielentiteit is te vinden [hier](../../developing/using/datamodel-profile.md).

In Dynamiek 365, hebben de meeste opt-outgebieden het &quot;niet&quot;prefix, echter, kunt u andere attributen voor opt-outdoeleinden ook gebruiken als de gegevens-types compatibel zijn.

Wanneer levering van de integratie, zult u de kans hebben om te specificeren welke opt-out configuratie u voor uw zaken vereist:

* **Unidirectioneel (Microsoft Dynamics 365 to Campaign)**: Dynamics 365 is een bron van waarheid voor opt-outs. De opt-uit attributen zullen in één richting van Dynamiek 365 aan Campaign Standard worden gesynchroniseerd
* **Unidirectioneel (campagne voor Microsoft Dynamics 365)**: Campaign Standard is de bron van de waarheid voor opt-outs. De opt-uit attributen zullen in één richting van Campaign Standard aan Dynamica 365 worden gesynchroniseerd
* **Bidirectioneel**: Dynamics 365 EN Campaign Standard zijn beide bronnen van waarheid. De opt-uit attributen zullen bidirectioneel tussen Campaign Standard en Dynamiek 365 worden gesynchroniseerd

Als u een afzonderlijk proces hebt voor het beheren van de synchronisatie met de optie om te weigeren tussen de systemen, kan de gegevensstroom van de integratie worden uitgeschakeld.

De bidirectionele opt-out configuratie gebruikt logica om te bepalen welke waarde aan beide systemen moet schrijven. De logica vergelijkt timestamps tussen de twee systemen (verandering op recordniveau in Dynamiek 365, attribuut-vlakke verandering in Campagne) om te bepalen welk systeem prevaleert. Als Campagne de recentere timestamp bevat, dan heeft de waarde van de Campagne voorrang. Als Dynamics 365 de recentere timestamp bevat of als zij gelijk zijn, dan zal opt-out=TRUE winnen (veronderstellend één van de waarden is WAAR).

Leer hoe u opties voor in- en uitschakelen kunt selecteren in [deze sectie](../../integrating/using/d365-acs-self-service-app-data-sync.md#opt-in-out-wf).

>[!NOTE]
>
>Controleer de standaard- en specifieke typologieregels in Adobe Campaign en werk deze zo nodig bij voordat u wijzigingen aanbrengt om ervoor te zorgen dat deze wijzigingen correct worden toegepast op alle uitgaande communicatie. Zorg er bijvoorbeeld voor dat in toewijzingen voor voorkeuren voor niet-deelname de intent-/communicatiekeuzen van de ontvanger nauwkeurig worden weergegeven en dat de levering van relatie- of transactieberichten, zoals bevestigingen van de klantenorder, niet per ongeluk wordt stopgezet.

Als u **Bidirectioneel** of **Unidirectioneel (campagne voor Microsoft Dynamics 365)** configuratie om te weigeren, worden de gegevens van de campagne-opt-out periodiek geëxporteerd via workflow naar uw opslaggebied van Campagne SFTP (zie &quot;Gebruik SFTP-campagne hieronder&quot;). Als de workflows voor het uitschakelen van de campagne niet meer actief zijn, moet u de software zo snel mogelijk handmatig opnieuw opstarten om de kans op een ontbrekende uitschakelsynchronisatie te verkleinen.

>[!IMPORTANT]
>
>Als u **Bidirectioneel** of **Unidirectioneel (campagne voor Microsoft Dynamics 365)** de opt-out configuratie, zult u het verzoek aan uw technische contact van de Adobe voor de opt-out werkschema&#39;s moeten indienen om opstelling op uw instantie van de Campagne te zijn

## Gebruik van campagne-SFTP

De integratie in de onderstaande gebruiksgevallen zal uw opslag van de Campagne SFTP moeten gebruiken.  U moet ervoor zorgen dat uw SFTP-account over voldoende opslagcapaciteit beschikt om deze gebruiksgevallen op te vangen. Het overschrijden van de gelicentieerde SFTP-opslagcapaciteit kan het functionele gebruik van Campagne, de integratie en/of de SFTP-account ernstig belemmeren.

| Gebruiksscenario | Beschrijving |
|---|---|
| Bidirectioneel en unidirectioneel (campagne voor Microsoft Dynamics 365) | De bidirectionele en unidirectionele (Campagne aan de Dynamica 365 van Microsoft) uit gegevensstromen zullen de opslag van SFTP van de Campagne gebruiken. Een campagneworkflow exporteert incrementele wijzigingen naar de SFTP-map. Vanaf dat moment zal de integratie de records en het proces oppakken. |
| Logboeken uitschakelen | Logboeken van de output van de schakelaar zullen nuttig zijn wanneer het oplossen van problemen de integratie. Uitvoerlogboeken kunnen in- en uitgeschakeld worden. |


>[!IMPORTANT]
>
>U bent verantwoordelijk voor de informatie die u opent en downloadt van de omslagen SFTP. Als de informatie persoonlijke gegevens bevat, moet u zich aan de toepasselijke privacywetten en -regels houden. [Meer informatie](#acs-msdyn-manage-privacy).

## Data management

### Bestaande Campagnegegevens

Deze integratie zal contacten en douaneentiteiten van de Dynamica 365 van Microsoft aan Campagne synchroniseren. Campagnerecords die buiten de integratie worden gemaakt (d.w.z. die niet door de synchronisatietaak worden gemaakt), worden niet door de integratie gewijzigd, inclusief Campagne-records die op het moment van de integratieconfiguratie bestaan.

Omdat deze integratie gebruikmaakt van de **[!UICONTROL externalId]** veld in Campagne voor synchronisatie van Campagne-profielrecords met Dynamics 365 contactrecords, dit veld Campagne (**[!UICONTROL externalId]** ) moet worden gevuld met Microsoft Dynamics 365 **[!UICONTROL contactId]** voor de records die u wilt synchroniseren via Microsoft Dynamics 365.  Aangepaste entiteiten worden ook gesynchroniseerd met een unieke id voor Microsoft Dynamics 365. De aangepaste entiteit Campagne moet dit id-kenmerk opnemen als tabelkolom. De kolom externalId kan worden gebruikt om deze attributenwaarde op te slaan, maar het wordt niet vereist voor de douane van de Campagne entiteiten.

Houd in mening, dat de Dynamica 365 van Microsoft nog de bron van waarheid is, en dat de het profielgegevens van de Campagne kunnen worden beschreven aangezien de integratie updates aan de kant van Dynamica 365 ontdekt.  Afhankelijk van uw bestaande implementatie kunnen er ook andere stappen vereist zijn om de integratie in te schakelen. daarom wordt aanbevolen nauw samen te werken met uw technische Adobe-contactpersoon.

>[!NOTE]
>
>Vanwege de complexiteit van bestaande implementaties van klanten wordt u aangeraden met uw technische Adobe-contactpersoon te werken bij het plannen en instellen van de integratie.

### Frequentie gegevenssynchronisatie

De integratie maakt gebruik van een architectuur waarmee updates kunnen worden gedetecteerd en aan de verwerkingswachtrij kunnen worden toegevoegd kort nadat ze in Microsoft Dynamics 365 voorkomen (dat wil zeggen, streaming, geen batchverwerking). Om deze reden, is er geen behoefte om de uitvoerfrequenties of programma&#39;s van de gegevensstroom te specificeren.

De uitzondering op dit is de bidirectionele en Campagne aan Dynamiek 365 uit gegevensstromen. Voor deze opt-out configuraties, worden de bijgewerkte verslagen van de Campagne uitgevoerd naar SFTP via een werkschema van de Campagne eens per dag, waarna het integratiehulpmiddel het dossier leest en het verslag verwerkt.

### Gegevensgebruiksovereenkomst

Als u in EMEA- of APAC-regio&#39;s bent gevestigd, zullen sommige gegevens in het kader van deze integratie in de VS worden verwerkt. Raadpleeg [deze sectie](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement) voor meer informatie.

## Afvoerkanalen en beperkingen

>[!IMPORTANT]
>
>Bepaalde handelingen van uw kant (bijvoorbeeld eerste opname van records, opnieuw afspelen van recordgegevens, enz.) kan ertoe leiden dat een groot aantal records van Microsoft Dynamics 365 naar uw Adobe Campaign-instantie wordt getypt. Om het risico van prestatieskwesties te verminderen, adviseert u alle processen van de Campagne (b.v., geen marketing activiteit, geen looppas van werkschema&#39;s, enz.) totdat de grote hoeveelheid records in de campagne is opgenomen.

### Aangepaste entiteiten

De [Integratie van Microsoft Dynamics 365-Adobe Campaign Standard](../../integrating/using/d365-acs-get-started.md) steunt douaneentiteiten, toelatend douaneentiteiten in Dynamiek 365 om aan overeenkomstige douanemiddelen in Campagne worden gesynchroniseerd.

De integratie ondersteunt zowel gekoppelde als niet-gekoppelde tabellen.

Wanneer het vormen van de gegevensstromen van de douaneentiteit, is het belangrijk om zich van het volgende bewust te zijn:

* Het creëren van en het wijzigen van de douanemiddelen van de Campagne zijn gevoelige verrichtingen die door deskundige slechts gebruikers moeten worden uitgevoerd.
* Voor de stromen van de gegevens van de douaneentiteit, verandering het volgen binnen Dynamiek 365 voor gesynchroniseerde douaneentiteiten moet worden toegelaten.
* Als een ouder en verbonden kindverslag dicht bij de zelfde tijd in Dynamiek 365, wegens de parallelle verwerking van de integratie worden gecreeerd, is er een lichte kans dat een nieuw kindverslag aan Campaign vóór zijn ouderverslag zou kunnen worden geschreven.

* Als het bovenliggende element en het onderliggende element aan de zijde Campagne zijn gekoppeld, gebruikt u de optie **1 cardinaliteit eenvoudige link** de onderliggende record verborgen en ontoegankelijk blijft (via UI of API) totdat de bovenliggende record in Campaign wordt ontvangen.

* (aangenomen **1 cardinaliteit eenvoudige link** in Campagne) als het kindverslag in Dynamiek 365 wordt bijgewerkt of geschrapt, en die verandering wordt geschreven aan Campagne alvorens het ouderverslag in Campaign (niet waarschijnlijk, maar een verre mogelijkheid) verschijnt, zal die update of schrapping niet in Campagne worden verwerkt en een fout zal worden geworpen. In het geval van een update moet de betreffende record opnieuw worden bijgewerkt in Dynamics 365 om de bijgewerkte record te synchroniseren. In geval van schrapping moet de betrokken record afzonderlijk aan de campagnezijde worden vermeld, aangezien er geen record meer is in Dynamics 365 om te verwijderen of bij te werken.

* Als u in een situatie terechtkomt waarin u denkt dat u kinderrecords hebt verborgen en deze niet kunt openen, kunt u het type cardinaliteitskoppeling tijdelijk wijzigen in **0 of 1 cardinaliteit, eenvoudige koppeling** om toegang te krijgen tot die records.

Een uitgebreider overzicht van aangepaste campagnebronnen vindt u [in deze sectie](../../developing/using/key-steps-to-add-a-resource.md).

### Integratiehandleidingen

Bij het gebruik van deze integratie moet rekening worden gehouden met de volgende instructies. Neem contact op met uw Adobe technisch vertegenwoordiger als u denkt dat u deze instructies overschrijdt.

* U zult het juiste pakket van de Campagne moeten vergunning geven om het volume van de motorvraag te steunen dat door de integratie wordt geproduceerd. Het overschrijden van het gelicentieerde aanroepvolume van de motor kan een verslechtering van de campagneprestaties veroorzaken.

   Gebruik het volgende om te helpen het volume van de motorvraag van de integratie schatten:

   * Record wordt ingevoegd (d.w.z. nieuwe record): 1 motoraanroep
   * Opnemen verwijdert: 1 motoraanroep
   * Updates opnemen: 2 motoraanroepen (slechts 1 aanroep als de doelrecord identiek is aan de bronrecord, d.w.z. als er geen wijziging is in de campagnerecord)

   Bij het schatten van het totale volume van de de vraagvraag van de motor van de Campagne, is het belangrijk om in andere bronnen van motorvraag, met inbegrip van het landen van pagina&#39;s, WebApps, JSSP, APIs, mobiele toepassingsregistraties, enz. rekening te houden.

   Hier vindt u informatie over het Adobe Campaign Standard-pakket: [https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html](https://helpx.adobe.com/nl/legal/product-descriptions/campaign-standard.html)

* De integratie steunt een maximum van 15 miljoen totale verslagen voor de aanvankelijke synchronisatie aan middelen in Campagne. Incrementele synchronisatie wordt beperkt door het Adobe Campaign Standard-pakket.

* Het standaard integratieaanbod omvat ondersteuning voor maximaal twintig aangepaste entiteiten, elk met een maximale grootte van 50 kolommen.

* U moet uw aangepaste bronnen maken en publiceren voordat u de integratie kunt implementeren.

* De maximale tabeldiepte bij het koppelen van tabellen is twee (tabel1->table2->table3)

* De integratie steunt tot 5 verbonden kolommen per douanemiddel. Het koppelen van meerdere kolommen tussen aangepaste bronnen kan dramatische gevolgen hebben voor de prestaties. **0 of 1 cardinaliteit, eenvoudige koppeling** heeft de voorkeur boven **1 cardinaliteit eenvoudige link**.

* De integratie ondersteunt transformatie tussen primitieve gegevenstypen van Microsoft Dynamics 365 (Boolean, Integer, Decimaal, Double, String, DateTime, Date) en Adobe Campaign Standard (integer, boolean, float, double, date, datetime, string). Geavanceerde gegevenstypen worden geïnterpreteerd als tekenreeksen en worden ongewijzigd gesynchroniseerd.

* Onderhoudsvensters aan boord moeten mogelijk tussen Adobe en de klant worden vastgesteld.

* Houd er rekening mee dat aanzienlijke stijgingen of &quot;pieken&quot; in het gebruik van de integratie (bijvoorbeeld een sterke toename van nieuwe of bijgewerkte records) kunnen leiden tot een vertraging van de gegevenssynchronisatie.

* Als onderdeel van de integratie wordt verwacht dat u de configuratiestappen voor de integratie in Microsoft Azure en Dynamics 365 uitvoert. Zie de configuratiestappen [op deze pagina](../../integrating/using/d365-acs-configure-d365.md)

* Verwacht wordt dat u uw Dynamica 365 en de gegevensmodellen van de Campagne aan de integratie zult brengen en hen zult handhaven.

### Integratiegrenzen

De integratie was ontworpen om het algemene gebruik van gemeenschappelijke gegevensbewegingen tussen de Dynamica 365 van Microsoft en Campagne op te lossen, maar is niet bedoeld om elk gebruiksgeval te richten specifiek voor elke klant:

* De integratie heeft geen betrekking op het verwijderen van privacy (bijvoorbeeld GDPR). De verantwoordelijkheid voor het voldoen aan de privacyverzoeken van eindgebruikers berust bij de klant; dergelijke verzoeken moeten onafhankelijk van elkaar worden gedaan in de campagne (via de Adobe Experience Platform Privacy Service) en in Dynamics 365. De integratie kan regelmatige schrappingen uitgeven om met gegevenssynchronisatie te helpen, indien gewenst.   Controleren [de sectie Privacy](#manage-privacy-requests) voor meer informatie .

* Geen profiel of douaneentiteitsgegevens zullen van Campagne aan Dynamica 365, met uitzondering van opt-out informatie (als gevormd door de klant) worden gesynchroniseerd.

* Abonnementsbeheer voor campagnes (d.w.z. abonnees/unsubscribes) wordt niet native ondersteund.

* Het samenstellen en activeren van campagne-e-mailcampagnes vanuit Dynamics 365 wordt niet ondersteund.

* De integratie doet **niet** de remodeling van gegevens tussen Dynamica 365 en de gegevensmodellen van Campaign Standard steunen. Naar verwachting zal de integratie één Dynamics 365-tabel synchroniseren met één campagneretabel.
