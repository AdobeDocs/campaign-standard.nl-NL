---
title: Campagne en het gegevensbeheer van de Dynamica 365 van Microsoft
description: Leer hoe Campaign Standard en de Dynamica 365 van Microsoft gemeenschappelijke gegevens beheren
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2ef169d9bf76856bb687af88358e0452953313a0
workflow-type: tm+mt
source-wordcount: '1448'
ht-degree: 0%

---


# Gegevens beheren tussen Campagne en de Dynamica 365 van Microsoft

## Bron van waarheid voor eenrichtingssynchronisatie

Voor contact en de synchronisatie van de douaneentiteit, behandelt deze integratie Dynamiek 365 als bron van waarheid.  Om het even welke veranderingen in gesynchroniseerde attributen zouden in Dynamiek 365, niet Campagne moeten worden gedaan.  Als er wijzigingen worden aangebracht in Campagne, kunnen deze tijdens de synchronisatie worden overschreven in Campagne, omdat de synchronisatie in één richting plaatsvindt.

## Contactverwijdering

Indien gewenst, kan de integratie worden gevormd om profiel uit te geven schrapt vraag aan Campagne wanneer een contact in Dynamiek 365 wordt geschrapt, helpen gegevensintegriteit handhaven.

Een profielverwijdering is echter anders dan een privacyverwijdering. Een privacyschrapping in Campagne zal het het profielverslag van de Campagne en bijbehorende logboekingangen verwijderen; overwegende dat een regelmatige profielschrapping slechts het ACS profielverslag zal schrappen, verlatend resten in de logboeken van de Campagne.

Als de functie voor het verwijderen van profielen is ingeschakeld in de integratie, moeten aanvullende stappen worden uitgevoerd om privacyverzoeken van betrokkenen correct te verwerken. Raadpleeg de stappen in de [onderstaande](#manage-privacy-requests)sectie.

## Privacy

### Privacyverzoeken beheren {#manage-privacy-requests}

Deze integratie wordt ontworpen om eindgebruikersgegevens (met inbegrip van, maar niet beperkt tot, persoonlijke informatie, als het in uw eindgebruikergegevens), tussen de Dynamica 365 van Microsoft en Adobe Campaign Standard wordt bevat over te brengen. Uw bedrijf is verantwoordelijk voor het naleven van de privacywetten en -regels die van toepassing zijn op het verzamelen en gebruiken van persoonsgegevens.

De integratie geeft geen privacy van de betrokkene weer (bv. GDPR) en schrapt of behandelt geen andere privacyverzoeken (met uitzondering van opt-out). Wanneer u privacyverzoeken verwerkt, moet u dit onafhankelijk doen in zowel Dynamics 365 als Campagne (via de Adobe Experience Platform Privacy Service).

Als u de integratie hebt gevormd om regelmatige profiel uit te geven schrapt vraag aan Campagne wanneer een contact in Dynamiek 365 wordt geschrapt, zouden de stappen hieronder moeten worden gevolgd. Zorg ervoor dat de record in kwestie tijdens dit proces niet wordt bijgewerkt.

1. Aanvraag voor privacyverwijdering aan [Adobe Experience Platform Privacy Service afgeven](https://www.adobe.io/apis/experiencecloud/gdpr.html)

1. Verzoek van de monitor tot het met succes is voltooid

1. Controleren of de record niet meer in uw Campagne-instantie staat

1. (Kort daarna) Verwijder de privacy van problemen in Dynamics 365

1. Controleren of de record van beide systemen is verwijderd

Hieronder vindt u koppelingen die u helpen bij het implementeren van verzoeken om toegang tot en/of het verwijderen van privacygerelateerde verzoeken in elk systeem:

* [Microsoft Dynamics 365](https://docs.microsoft.com/en-us/microsoft-365/compliance/gdpr-dsr-dynamics365?toc=/microsoft-365/enterprise/toc.json)

* [Adobe Campaign Standard](https://www.adobe.io/apis/experiencecloud/gdpr/docs.html)


### Privacy en gekoppelde bronnen {#privacy-linked-resources}

Als om het even welk dossier van de Bron douane van de Campagne persoonlijke informatie bevat, toepasselijk op het gebruik van een klant van Campagne, zou zulk verslag aan een overeenkomstig het profielverslag van de Campagne (of direct of door een andere douanemiddel) moeten worden verbonden zodat een privacy verwante schrapping in het profielverslag het verbonden douanemiddelverslag met persoonlijke informatie kan ook schrappen; de koppelings- en verwijderingsopties tussen de entiteiten moeten zo zijn geconfigureerd dat deze trapsgewijze verwijdering van de gekoppelde records mogelijk is. Persoonlijke gegevens moeten niet worden ingevoerd in een aangepaste bron die niet aan het profiel is gekoppeld.

Leer hoe u campagnebronnen en Dynamics 365-entiteiten [in deze sectie](../../integrating/using/map-campaign-custom-resources-and-dynamics-365-custom-entities.md)in kaart brengt.

## Uitschakelen

Wegens de verschillen in opt-outattributen tussen Dynamiek 365 en Campagne, en wegens de verschillen in bedrijfsvereisten van elke klant, is de opt-out afbeelding verlaten als oefening voor de klant om te voltooien.  Het is belangrijk ervoor te zorgen dat de optie-outs correct tussen systemen worden toegewezen, zodat de voorkeuren voor de optie-uit voor eindgebruikers behouden blijven en dat gebruikers geen communicatie ontvangen via een kanaal waarvan ze hebben afgezien.

Houd er rekening mee dat alleen campagnerekenmerken met het voorvoegsel &#39;Geen contact meer door&#39; (bijvoorbeeld Geen contact meer via e-mail) of het specifieke kenmerk voor de optie CCPA-optie om te weigeren kunnen worden gebruikt in toewijzingen voor niet-deelname. [Meer informatie](../../developing/using/datamodel-profile.md).
In Dynamiek 365, hebben de meeste opt-outgebieden het &quot;donot&quot;prefix; u kunt echter ook andere kenmerken voor opt-outdoeleinden gebruiken als de gegevenstypen compatibel zijn.

Wanneer levering van de integratie, zult u de kans hebben om te specificeren welke opt-out configuratie u voor uw zaken vereist:

* Dynamics 365 is een bron van waarheid voor opt-outs: de optieattributen zullen in één richting van Dynamiek 365 aan Campagne worden gesynchroniseerd
* Campagne is de bron van de waarheid voor opt-outs: de opt-outkenmerken worden in één richting gesynchroniseerd, van Campagne tot Dynamics 365
* Dynamics 365 EN Campaign zijn beide bronnen van waarheid: de opt-outkenmerken worden bidirectioneel gesynchroniseerd tussen Campagne en Dynamics 365

Als u een afzonderlijk proces hebt voor het beheren van de synchronisatie met de optie om te weigeren tussen de systemen, kan de gegevensstroom van de integratie worden uitgeschakeld.

De bidirectionele opt-out configuratie gebruikt logica om te bepalen welke waarde aan beide systemen moet schrijven. De logica vergelijkt timestamps tussen de twee systemen (verandering op recordniveau in Dynamiek 365, attribuut-vlakke verandering in Campagne) om te bepalen welk systeem prevaleert. Als Campagne de recentere timestamp bevat, dan heeft de waarde van de Campagne voorrang. Als Dynamics 365 de recentere timestamp bevat of als zij gelijk zijn, dan zal opt-out=TRUE winnen (veronderstellend één van de waarden is WAAR).

>[!NOTE]
>
>Controleer de standaard- en specifieke typologieregels in Adobe Campaign en werk deze zo nodig bij voordat u wijzigingen aanbrengt om ervoor te zorgen dat deze wijzigingen correct worden toegepast op alle uitgaande communicatie. Zorg er bijvoorbeeld voor dat in toewijzingen voor voorkeuren voor niet-deelname de intent-/communicatiekeuzen van de ontvanger nauwkeurig worden weergegeven en dat de levering van relatie- of transactieberichten, zoals bevestigingen van de klantenorder, niet per ongeluk wordt stopgezet.

Als uw uitgezocht bidirectionele of Campagne aan Dynamiek 365 opt-out configuratie, zullen de opting-outgegevens van de Campagne periodiek via werkschema naar uw het opslaggebied van SFTP van de Campagne worden uitgevoerd (zie &quot;Gebruik SFTP van de Campagne hieronder&quot;). Als de workflows voor het uitschakelen van de campagne niet meer actief zijn, moet u de software zo snel mogelijk handmatig opnieuw opstarten om de kans op een ontbrekende uitschakelsynchronisatie te verkleinen.

## Gebruik van campagne-SFTP

De integratie in de onderstaande gebruiksgevallen zal uw opslag van de Campagne SFTP moeten gebruiken.  U moet ervoor zorgen dat uw SFTP-account over voldoende opslagcapaciteit beschikt om deze gebruiksgevallen op te vangen.  Het overschrijden van de gelicentieerde SFTP-opslagcapaciteit kan het functionele gebruik van Campagne, de integratie en/of de SFTP-account ernstig belemmeren.

| Gebruiksscenario | Beschrijving |
|---|---|
| Oorspronkelijke gegevensbelasting | Dynamics 365 tables over 500k verslagen zullen naar de opslag van SFTP van de Campagne moeten worden uitgevoerd om via werkschema worden ingevoerd. Vanaf dat moment gebruikt de integratie API&#39;s voor incrementele updates. |
| Bidirectionele opt-out en Campagne voor dynamiek 365 uni-directionele opt-out | De bidirectionele opt-out en de Campagne aan Dynamiek 365 uni-directionele opt-out gegevensstromen zullen de opslag van SFTP van de Campagne gebruiken. Een werkschema ACS zal stijgende veranderingen in de omslag SFTP uitvoeren. Vanaf dat moment zal de integratie de records en het proces oppakken. |
| Noodherstel | In het onwaarschijnlijke geval van een systeemramp, zal de &quot;Aanvankelijke het gebruikscase van de Lading van Gegevens&quot;worden gevolgd om de stijgende updates aan Campagne te voeren die werden gemist. |

## Bestaande Campagnegegevens

Deze integratie zal contacten en douaneentiteiten van Dynamiek 365 aan Campagne synchroniseren. Campagnerecords die buiten de integratie worden gemaakt (d.w.z. die niet door de synchronisatietaak worden gemaakt), worden niet door de integratie gewijzigd, inclusief Campagne-records die op het moment van de integratieconfiguratie bestaan.

Omdat deze integratie het **[!UICONTROL externalId]** gebied in Campagne gebruikt om het profielverslagen van de Campagne met Dynamiek 365 contactverslagen te synchroniseren, moet dit gebied van de Campagne (**[!UICONTROL externalId]** ) met Dynamiek 365 **[!UICONTROL contactId]** voor de verslagen worden bevolkt u van Dynamiek 365 wenst te worden gesynchroniseerd.  De entiteiten van de douane worden ook gesynchroniseerd gebruikend een Dynamica 365 unieke identiteitskaart. De aangepaste entiteit Campagne moet dit id-kenmerk opnemen als tabelkolom. De kolom externalId kan worden gebruikt om deze attributenwaarde op te slaan, maar het wordt niet vereist voor de douane van de Campagne entiteiten.

Onthoud, dat de Dynamiek 365 nog de bron van waarheid is, en dat de het profielgegevens van de Campagne kunnen worden beschreven aangezien de integratie updates aan de Dynamica 365 kant ontdekt.  Afhankelijk van uw bestaande implementatie kunnen er ook andere stappen vereist zijn om de integratie in te schakelen. daarom wordt aanbevolen nauw samen te werken met uw technische Adobe-contactpersoon.

>[!NOTE]
>
>Vanwege de complexiteit van bestaande implementaties van klanten wordt u aangeraden met uw technische Adobe-contactpersoon te werken bij het plannen en instellen van de integratie.

## Frequentie gegevenssynchronisatie

De integratie gebruikt een architectuur die updates om toelaat worden ontdekt en aan de verwerking &quot;rij&quot;worden toegevoegd kort nadat zij in Dynamiek 365 voorkomen (d.w.z., het stromen, niet partijverwerking). Om deze reden, is er geen behoefte om de uitvoerfrequenties of programma&#39;s van de gegevensstroom te specificeren.

De uitzondering hierop is de bidirectionele en Campagne aan Dynamica 365 opt-out gegevensstromen. Voor deze opt-out configuraties, worden de bijgewerkte ACS- verslagen uitgevoerd naar SFTP via ACS werkschema eens per dag, waarna het integratiehulpmiddel het dossier leest en het verslag verwerkt.

## Gegevensgebruiksovereenkomst

Als u in EMEA- of APAC-regio&#39;s bent gevestigd, zullen sommige gegevens in het kader van deze integratie in de VS worden verwerkt. Raadpleeg [deze sectie](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement) voor meer informatie.
