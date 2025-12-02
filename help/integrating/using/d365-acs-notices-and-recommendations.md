---
title: Campagne en Microsoft Dynamics 365-gegevensbeheer
description: Leer hoe Campaign Standard en Microsoft Dynamics 365 gemeenschappelijke gegevens beheren
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
feature: Microsoft CRM Integration
old-role: Data Architect
role: Developer
level: Experienced
exl-id: aab6f005-f3da-4c0b-b856-da8504e611dc
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '2523'
ht-degree: 0%

---

# Best practices en beperkingen {#acs-msdyn-best-practices}

## Gegevens beheren {#acs-msdyn-manage-data}

Voor contact en de synchronisatie van de douaneentiteit, behandelt deze integratie **Microsoft Dynamics 365 als bron van waarheid**.  Wijzigingen in gesynchroniseerde kenmerken moeten worden doorgevoerd in Dynamics 365 en niet in Adobe Campaign Standard).  Als er wijzigingen worden aangebracht in Campagne, kunnen deze tijdens de synchronisatie worden overschreven in Campagne, omdat de synchronisatie in één richting plaatsvindt.

De integratie kan naar keuze worden gevormd om profiel uit te geven schrapt vraag aan Campagne wanneer een contact in Dynamica 365 wordt geschrapt helpen gegevensintegriteit handhaven. Een profielverwijdering is echter anders dan een privacyverwijdering. Als u een privacyverwijdering uitvoert in Campagne, worden de record met het Campagneprofiel en de bijbehorende logbestandvermeldingen verwijderd. Als u een profiel regelmatig verwijdert, wordt alleen de record met het Campagneprofiel verwijderd, maar blijven de resterende items achter in Campagnerogboeken. Als de functie voor het verwijderen van profielen is ingeschakeld in de integratie, moeten aanvullende stappen worden uitgevoerd om privacyverzoeken van betrokkenen op de juiste wijze te verwerken. Verwijs naar de stappen in de [&#x200B; sectie van de Privacy hieronder &#x200B;](#manage-privacy-requests).

## Privacy{#acs-msdyn-manage-privacy}

Deze integratie is ontworpen om gegevens van eindgebruikers over te dragen tussen Microsoft Dynamics 365 en Adobe Campaign Standard. Dit gegeven omvat persoonlijke informatie als het in uw eind - gebruikersgegevens bevat.  Uw bedrijf is verantwoordelijk voor het naleven van de privacywetten en -regels die van toepassing zijn op het verzamelen en gebruiken van persoonsgegevens.

Deze integratie is bedoeld om gegevens van eindgebruikers (inclusief, maar niet beperkt tot, persoonlijke gegevens, als deze in uw gegevens voor eindgebruikers staan) tussen Microsoft Dynamics 365 en Adobe Campaign Standard over te brengen. Uw bedrijf is verantwoordelijk voor het naleven van de privacywetten en -regels die van toepassing zijn op het verzamelen en gebruiken van persoonsgegevens.

De integratie geeft geen privacy van de betrokkene weer (bv. GDPR) en schrapt of behandelt geen andere privacyverzoeken (met uitzondering van opt-out). Wanneer u privacyverzoeken verwerkt, moet u dit onafhankelijk doen in zowel Microsoft Dynamics 365 als Campagne (via de Adobe Experience Platform Privacy Service).

Als u de integratie hebt gevormd om regelmatige profiel uit te geven schrapt vraag aan Campagne wanneer een contact in Dynamiek 365 wordt geschrapt, zouden de stappen hieronder moeten worden gevolgd. Zorg ervoor dat de record in kwestie tijdens dit proces niet wordt bijgewerkt.

1. De privacyschrappingsverzoek van de kwestie aan [&#x200B; Adobe Experience Platform Privacy Service &#x200B;](https://developer.adobe.com/experience-platform-apis/references/privacy-service)

1. Verzoek van de monitor tot het met succes is voltooid

1. Controleren of de record niet meer in uw Campagne-instantie staat

1. (Kort daarna) Verwijder de privacy van problemen in Dynamics 365

1. Controleren of de record van beide systemen is verwijderd


>[!IMPORTANT]
>
>Als om het even welk dossier van het Bron van de Campagne van het douanemiddel persoonlijke informatie bevat, van toepassing op het gebruik van een klant van Campagne, zou zulk verslag aan een overeenkomstig het profielverslag van de Campagne (of direct of door een andere douanemiddel) moeten worden verbonden zodat een privacy-verwante schrapping in het profielverslag het verbonden douanemiddelverslag met persoonlijke informatie kan ook schrappen; de verbinding en schrappingsopties tussen de entiteiten moeten worden gevormd om deze cascade gewijze verwijdering van de verbonden verslagen toe te laten. Persoonlijke gegevens moeten niet worden ingevoerd in een aangepaste bron die niet aan het profiel is gekoppeld.

## Uitschakelen {#opt-out}

Vanwege de verschillen in de opt-outkenmerken tussen Microsoft Dynamics 365 en Campagne en vanwege de verschillen in de zakelijke vereisten van elke klant, is de opt-out-toewijzing aan de klant overgelaten.  Het is belangrijk ervoor te zorgen dat de optie-outs correct tussen systemen worden toegewezen, zodat de voorkeuren voor de optie-uit voor eindgebruikers behouden blijven en dat gebruikers geen communicatie ontvangen via een kanaal waarvan ze hebben afgezien.

Houd er rekening mee dat alleen de volgende opties kunnen worden gebruikt in toewijzingen voor niet-deelname:

* Campagneringkenmerken met het voorvoegsel &#39;Geen contact meer maken door&#39; (bijvoorbeeld Geen contact meer via e-mail), of

* het specifieke kenmerk voor de CCPA

Meer informatie betreffende de entiteitgebieden van het Profiel kan [&#x200B; hier &#x200B;](../../developing/using/datamodel-profile.md) worden gevonden.

In Dynamiek 365, hebben de meeste opt-outgebieden het &quot;niet&quot;prefix, echter, kunt u andere attributen voor opt-outdoeleinden ook gebruiken als de gegevens-types compatibel zijn.

Wanneer levering van de integratie, zult u de kans hebben om te specificeren welke opt-out configuratie u voor uw zaken vereist:

* **Unidirectioneel (Microsoft Dynamics 365 aan Campagne)**: De dynamiek 365 is bron van waarheid voor opt-outs. De opt-outkenmerken worden in één richting gesynchroniseerd, van Dynamics 365 tot Campaign Standard
* **Unidirectioneel (Campagne aan Microsoft Dynamics 365)**: Campaign Standard is de bron van waarheid voor opt-outs. Kenmerken voor Uitschakelen worden in één richting gesynchroniseerd van Campaign Standard naar Dynamics 365
* **Bidirectional**: Dynamiek 365 EN Campaign Standard zijn beide bronnen van waarheid. Opt-out-kenmerken worden bidirectioneel gesynchroniseerd tussen Campaign Standard en Dynamics 365

Als u een afzonderlijk proces hebt voor het beheren van de synchronisatie met de optie om te weigeren tussen de systemen, kan de gegevensstroom van de integratie worden uitgeschakeld.

De bidirectionele opt-out configuratie gebruikt logica om te bepalen welke waarde aan beide systemen moet schrijven. De logica vergelijkt timestamps tussen de twee systemen (verandering op recordniveau in Dynamiek 365, attribuut-vlakke verandering in Campagne) om te bepalen welk systeem prevaleert. Als Campagne de recentere timestamp bevat, dan heeft de waarde van de Campagne voorrang. Als Dynamics 365 de recentere timestamp bevat of als zij gelijk zijn, dan zal opt-out=TRUE winnen (veronderstellend één van de waarden is WAAR).

Leer hoe te om opt-in/uit opties in [&#x200B; te selecteren deze sectie &#x200B;](../../integrating/using/d365-acs-self-service-app-data-sync.md#opt-in-out-wf).

>[!NOTE]
>
>Controleer de standaard- en specifieke typologieregels in Adobe Campaign en werk deze zo nodig bij voordat u wijzigingen aanbrengt om ervoor te zorgen dat deze wijzigingen correct worden toegepast op alle uitgaande communicatie. Zorg er bijvoorbeeld voor dat in toewijzingen voor voorkeuren voor niet-deelname de intent-/communicatiekeuzen van de ontvanger nauwkeurig worden weergegeven en dat de levering van relatie- of transactieberichten, zoals bevestigingen van de klantenorder, niet per ongeluk wordt stopgezet.

Als u de **Bidirectionele** of **Unidirectionele (Campagne aan Microsoft Dynamics 365)** opt-out configuratie selecteerde, zullen de optiegegevens van de Campagne periodiek via werkschema naar uw het opslaggebied van SFTP van de Campagne worden uitgevoerd (zie &quot;Gebruik SFTP van de Campagne hieronder&quot;). Als de workflows voor het uitschakelen van de campagne niet meer actief zijn, moet u de software zo snel mogelijk handmatig opnieuw opstarten om de kans op een ontbrekende uitschakelsynchronisatie te verkleinen.

>[!IMPORTANT]
>
>Als u de **Bidirectionele** of **Unidirectionele (Campagne aan Microsoft Dynamics 365)** opt-out configuratie vereist, zult u het verzoek aan uw technische contact van Adobe voor de opt-out werkschema&#39;s moeten indienen om opstelling op uw instantie van de Campagne te zijn

## Gebruik van campagne-SFTP

De integratie in de onderstaande gebruiksgevallen zal uw opslag van de Campagne SFTP moeten gebruiken.  U moet ervoor zorgen dat uw SFTP-account over voldoende opslagcapaciteit beschikt om deze gebruiksgevallen op te vangen. Het overschrijden van de gelicentieerde SFTP-opslagcapaciteit kan het functionele gebruik van Campagne, de integratie en/of de SFTP-account ernstig belemmeren.

| Gebruiksscenario | Beschrijving |
|---|---|
| Bidirectioneel en gericht (campagne naar Microsoft Dynamics 365) | Bidirectionele en unidirectionele (Campagne aan Microsoft Dynamics 365) gegevens uit opt-out zullen de opslag van SFTP van de Campagne gebruiken. Een campagneworkflow exporteert incrementele wijzigingen naar de SFTP-map. Vanaf dat moment zal de integratie de records en het proces oppakken. |
| Logboeken uitschakelen | Logboeken van de output van de schakelaar zullen nuttig zijn wanneer het oplossen van problemen de integratie. Uitvoerlogboeken kunnen in- en uitgeschakeld worden. |


>[!IMPORTANT]
>
>U bent verantwoordelijk voor de informatie die u opent en downloadt van de omslagen SFTP. Als de informatie persoonlijke gegevens bevat, moet u zich aan de toepasselijke privacywetten en -regels houden. [Meer informatie](#acs-msdyn-manage-privacy).

## Data management

### Bestaande Campagnegegevens

Deze integratie zal contacten en douaneentiteiten van Microsoft Dynamics 365 aan Campagne synchroniseren. Campagnerecords die buiten de integratie worden gemaakt (d.w.z. die niet door de synchronisatietaak worden gemaakt), worden niet door de integratie gewijzigd, inclusief Campagne-records die op het moment van de integratieconfiguratie bestaan.

Omdat in deze integratie het veld **[!UICONTROL externalId]** in Campagne wordt gebruikt om Campagne-profielrecords te synchroniseren met de contactrecords van Dynamics 365, moet dit Campagne-veld ( **[!UICONTROL externalId]** ) worden gevuld met de Microsoft Dynamics 365 **[!UICONTROL contactId]** voor de records die u wilt synchroniseren vanuit Microsoft Dynamics 365.  Aangepaste entiteiten worden ook gesynchroniseerd met een unieke Microsoft Dynamics 365-id. De aangepaste entiteit Campagne moet dit id-kenmerk opnemen als tabelkolom. De kolom externalId kan worden gebruikt om deze attributenwaarde op te slaan, maar het wordt niet vereist voor de douane van de Campagne entiteiten.

Houd in mening, dat Microsoft Dynamics 365 nog de bron van waarheid is, en dat de het profielgegevens van de Campagne kunnen worden beschreven aangezien de integratie updates aan de Dynamica 365 kant ontdekt.  Afhankelijk van uw bestaande implementatie kunnen er ook andere stappen vereist zijn om de integratie mogelijk te maken. Daarom wordt u aangeraden nauw samen te werken met uw technische Adobe-contactpersoon.

>[!NOTE]
>
>Vanwege de complexiteit van bestaande implementaties van klanten wordt u aangeraden om samen met uw Adobe technische contactpersoon te werken bij het plannen en instellen van de integratie.

### Frequentie gegevenssynchronisatie

De integratie maakt gebruik van een architectuur waarmee updates kunnen worden gedetecteerd en aan de verwerkingswachtrij kunnen worden toegevoegd kort nadat ze in Microsoft Dynamics 365 voorkomen (dat wil zeggen, streaming, geen batchverwerking). Om deze reden, is er geen behoefte om de uitvoerfrequenties of programma&#39;s van de gegevensstroom te specificeren.

De uitzondering op dit is de bidirectionele en Campagne aan Dynamiek 365 uit gegevensstromen. Voor deze opt-out configuraties, worden de bijgewerkte verslagen van de Campagne uitgevoerd naar SFTP via een werkschema van de Campagne eens per dag, waarna het integratiehulpmiddel het dossier leest en het verslag verwerkt.

### Gegevensgebruiksovereenkomst

Als u in EMEA- of APAC-regio&#39;s bent gevestigd, zullen sommige gegevens in het kader van deze integratie in de VS worden verwerkt. Raadpleeg [deze sectie](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement) voor meer informatie.

## Afvoerkanalen en beperkingen

>[!IMPORTANT]
>
>Bepaalde handelingen van uw kant (bijvoorbeeld eerste opname van records, opnieuw afspelen van recordgegevens, enz.) kunnen ertoe leiden dat een grote hoeveelheid records van Microsoft Dynamics 365 naar uw Adobe Campaign-exemplaar wordt ingeslikt. Om het risico van prestatieskwesties te verminderen, adviseert u alle processen van de Campagne (b.v., geen marketing activiteit, geen looppas van werkschema&#39;s, enz.) tot na de grote lading verslagen in Campaign is opgenomen.

### Aangepaste entiteiten

De [&#x200B; integratie 365-Adobe Campaign Standard van Microsoft Dynamics &#x200B;](../../integrating/using/d365-acs-get-started.md) steunt douaneentiteiten, toelatend douaneentiteiten in Dynamiek 365 om aan overeenkomstige douanemiddelen in Campagne worden gesynchroniseerd.

De integratie ondersteunt zowel gekoppelde als niet-gekoppelde tabellen.

Wanneer het vormen van de gegevensstromen van de douaneentiteit, is het belangrijk om zich van het volgende bewust te zijn:

* Het creëren van en het wijzigen van de douanemiddelen van de Campagne zijn gevoelige verrichtingen die door deskundige slechts gebruikers moeten worden uitgevoerd.
* Voor de stromen van de gegevens van de douaneentiteit, verandering het volgen binnen Dynamiek 365 voor gesynchroniseerde douaneentiteiten moet worden toegelaten.
* Als een ouder en verbonden kindverslag dicht bij de zelfde tijd in Dynamiek 365, wegens de parallelle verwerking van de integratie worden gecreeerd, is er een lichte kans dat een nieuw kindverslag aan Campaign vóór zijn ouderverslag zou kunnen worden geschreven.

* Als de ouder en het kind op de kant van de Campagne gebruikend de **1 cardinaliteit eenvoudige verbinding** optie verbonden zijn, zal het kindverslag verborgen en ontoegankelijk (via UI of API) blijven tot het ouderverslag in Campagne aankomt.

* (Veronderstellend **1 kardinaliteit eenvoudige verbinding** in Campagne) als het kindverslag in Dynamiek 365 wordt bijgewerkt of geschrapt, en die verandering wordt geschreven aan Campagne alvorens het ouderverslag in Campagne (niet waarschijnlijk, maar een verre mogelijkheid) toont, zal die update of schrapping niet in Campagne worden verwerkt en een fout zal worden geworpen. In het geval van een update moet de betreffende record opnieuw worden bijgewerkt in Dynamics 365 om de bijgewerkte record te synchroniseren. In geval van schrapping moet de betrokken record afzonderlijk aan de campagnezijde worden vermeld, aangezien er geen record meer is in Dynamics 365 om te verwijderen of bij te werken.

* Als u in een situatie loopt waar u denkt u kindverslagen en geen manier hebt om tot hen toegang te hebben, kunt u het type van de kardinaalverbinding in **0 of 1 kardinaliteit eenvoudige verbinding** tijdelijk veranderen om tot die verslagen toegang te hebben.

Een uitvoeriger overzicht van de douanemiddelen van de Campagne kan [&#x200B; in deze sectie &#x200B;](../../developing/using/key-steps-to-add-a-resource.md) worden gevonden.

### Integratiehandleidingen

Bij de planning van het gebruik van deze integratie moet rekening worden gehouden met de volgende instructies. Neem contact op met uw technische vertegenwoordiger van Adobe als u denkt dat u deze instructies overschrijdt.

* U zult het juiste pakket van de Campagne moeten vergunning geven om het volume van de motorvraag te steunen dat door de integratie wordt geproduceerd. Het overschrijden van het gelicentieerde aanroepvolume van de motor kan een verslechtering van de campagneprestaties veroorzaken.

  Gebruik het volgende om te helpen het volume van de motorvraag van de integratie schatten:

   * Record invoegen (d.w.z. nieuwe record): 1 motoraanroep
   * Record verwijdert: 1 motoraanroep
   * Recordupdates: 2 motoraanroepen (slechts 1 aanroep als de doelrecord identiek is aan de bronrecord - dat wil zeggen, als er geen wijziging is in de campagnerecord)

  Bij het schatten van het totale volume van de de vraagvraag van de motor van de Campagne, is het belangrijk om in andere bronnen van motorvraag, met inbegrip van het landen van pagina&#39;s, WebApps, JSSP, APIs, mobiele toepassingsregistraties, enz. rekening te houden.

  Bekijk hier het pakketinformatie van Adobe Campaign Standard: [&#x200B; https://helpx.adobe.com/nl/legal/product-descriptions/campaign-standard.html](https://helpx.adobe.com/nl/legal/product-descriptions/campaign-standard.html)

* De integratie steunt een maximum van 15 miljoen totale verslagen voor de aanvankelijke synchronisatie aan middelen in Campagne. Incrementele synchronisatie wordt beperkt door het Adobe Campaign Standard-pakket.

* De standaard integratie biedt ondersteuning voor maximaal twintig aangepaste entiteiten, elk met een maximale grootte van 50 kolommen.

* U moet uw aangepaste bronnen maken en publiceren voordat u de integratie kunt implementeren.

* De maximale tabeldiepte bij het koppelen van tabellen is twee (tabel1->table2->table3)

* De integratie steunt tot 5 verbonden kolommen per douanemiddel. Het koppelen van meerdere kolommen tussen aangepaste bronnen kan dramatische gevolgen hebben voor de prestaties. **0 of 1 kardinaliteit de eenvoudige verbinding** heeft de voorkeur over **1 kardinaliteit eenvoudige verbinding**.

* De integratie ondersteunt transformatie tussen primitieve Microsoft Dynamics 365-gegevenstypen (Boolean, Integer, Decimaal, Double, String, DateTime, Date) en Adobe Campaign Standard-gegevenstypen (integer, boolean, float, double, date, datetime, string). Geavanceerde gegevenstypen worden geïnterpreteerd als tekenreeksen en worden ongewijzigd gesynchroniseerd.

* Het kan nodig zijn om tussen Adobe en de klant onderhoudsvensters aan boord te hebben.

* Houd er rekening mee dat aanzienlijke stijgingen of &quot;pieken&quot; in het gebruik van de integratie (bijvoorbeeld een sterke toename van nieuwe of bijgewerkte records) kunnen leiden tot een vertraging van de gegevenssynchronisatie.

* Als onderdeel van de integratie wordt verwacht dat u de configuratiestappen voor de integratie in Microsoft Azure en Dynamics 365 uitvoert. Zie de configuratiestappen [&#x200B; op deze pagina &#x200B;](../../integrating/using/d365-acs-configure-d365.md)

* Verwacht wordt dat u uw Dynamica 365 en de gegevensmodellen van de Campagne aan de integratie zult brengen en hen zult handhaven.

### Integratiegrenzen

De integratie was bedoeld om het algemene gebruik van gemeenschappelijke gegevensbewegingen tussen Microsoft Dynamics 365 en Campagne op te lossen, maar is niet bedoeld om elk gebruiksgeval te behandelen specifiek voor elke klant:

* De integratie heeft geen betrekking op het verwijderen van privacy (bijvoorbeeld GDPR). De verantwoordelijkheid voor het voldoen aan de privacyverzoeken van eindgebruikers ligt bij de klant; dergelijke verzoeken moeten onafhankelijk van elkaar worden gedaan in zowel de campagne (via de Adobe Experience Platform Privacy Service) als in Dynamics 365. De integratie kan regelmatige schrappingen uitgeven om met gegevenssynchronisatie te helpen, indien gewenst.   Herzie [&#x200B; de sectie van de Privacy &#x200B;](#manage-privacy-requests) voor meer informatie.

* Geen profiel of douaneentiteitsgegevens zullen van Campagne aan Dynamica 365, met uitzondering van opt-out informatie (als gevormd door de klant) worden gesynchroniseerd.

* Abonnementsbeheer voor campagnes (d.w.z. abonnees/unsubscribes) wordt niet native ondersteund.

* Het samenstellen en activeren van campagne-e-mailcampagnes vanuit Dynamics 365 wordt niet ondersteund.

* De integratie steunt **niet** het remodeling van gegevens tussen Dynamiek 365 en de gegevensmodellen van Campaign Standard. Verwacht wordt dat de integratie één Dynamics 365-tabel synchroniseert met één campagneretabel.
