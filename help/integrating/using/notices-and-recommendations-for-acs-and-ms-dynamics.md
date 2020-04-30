---
title: Over de integratie van Microsoft Dynamics 365
description: Leer berichten en aanbevelingen voor hoe te met de Norm van de Campagne en de Dynamica 365 van Microsoft te werken
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 277663c4cf0e810f691eeebfade17bf8dd73698e

---


# Over de integratie van Microsoft Dynamics 365

## Ondersteuning voor regio

Deze integratie is beschikbaar in de regio&#39;s Noord-Amerika, EMEA en APAC.

Als u in EMEA- of APAC-regio&#39;s bent gevestigd, zullen sommige gegevens in het kader van deze integratie in de VS worden verwerkt. For more information, refer to [this section](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

## Bron van waarheid voor one-way contact sync

Voor de synchronisatie van het Contact en van de douaneentiteit, behandelt deze integratie Dynamiek 365 als bron van waarheid. Wijzigingen in gesynchroniseerde kenmerken moeten worden doorgevoerd in Microsoft Dynamics 365, niet in Adobe Campaign Standard. Als er wijzigingen worden aangebracht in Campagne, kunnen deze tijdens de synchronisatie worden overschreven in Campagne, omdat de synchronisatie in één richting plaatsvindt.  Bovendien wordt de Synchronisatie van Contacten ontworpen om alle verslagen van het Contact te trekken, of zij als actief of inactief in de Dynamica 365 van Microsoft worden gemerkt.

## Privacyverzoeken beheren

Deze integratie is ontworpen voor de overdracht van gegevens van eindgebruikers (inclusief, maar niet beperkt tot, persoonlijke informatie, als deze in uw gegevens voor eindgebruikers is opgenomen) tussen Microsoft Dynamics 365 en Adobe Campaign Standard.  Uw bedrijf is verantwoordelijk voor het naleven van de privacywetten en -regels die van toepassing zijn op het verzamelen en gebruiken van persoonsgegevens.

Voor deze integratie, moet u elk verzoek van gegevenssubject in elk systeem onafhankelijk verwerken om de verandering in beide gegevensbestanden wordt weerspiegeld. De wijziging moet eerst worden uitgevoerd in Microsoft Dynamics 365 en vervolgens in Adobe Campaign Standard. De enige uitzondering hierop is dat een privacygerelateerd verwijderingsverzoek wordt toegevoegd aan de wachtrij Privacy Tools in Campagnestandaard wanneer een contactpersoon wordt verwijderd in Dynamics 365.

Hieronder vindt u koppelingen die u helpen bij het implementeren van verzoeken om toegang tot en/of het verwijderen van privacygerelateerde verzoeken in elk systeem:

* [Microsoft Dynamics 365](https://docs.microsoft.com/en-us/microsoft-365/compliance/gdpr-dsr-dynamics365?toc=/microsoft-365/enterprise/toc.json)

* [Adobe Campagne Standard](https://www.adobe.io/apis/experiencecloud/gdpr/docs.html)

## Contactverwijdering

Aangezien Dynamics 365 de bron van waarheid is, zullen de schrappingen van het Contact in Dynamiek 365 in Campagne worden weerspiegeld.

Wanneer een Contact in Dynamiek 365 wordt geschrapt, vormt de integratie een rij omhoog een privacy verwante schrappingsverzoek in het verzoek/het hulpmiddelscherm van de Privacy van de Campagne.  Als u het proces van twee stappen voor privacygerelateerde verwijderingsverzoeken hebt uitgeschakeld, zorgt Campagne voor de verwijdering voor u.

Nochtans, als het proces in twee stappen wordt toegelaten, zult u in het verzoek van de Privacy/het hulpmiddelscherm moeten gaan, nadat de technische werkschema&#39;s van de privacy in werking zijn gesteld, en bevestigen of zijn de verslagen ok om te worden geschrapt.  Alleen dan zal Campaign zorgen voor de verwijdering.

Raadpleeg [How to execute privacy related delete request in Adobe Campaign Standard voor meer informatie](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/privacy/execute-privacy-requests.html)

>[!CAUTION]
>
>Als u het proces in twee stappen voor privacyverzoeken in Campagne wordt toegelaten, uw schrappingen in Dynamiek 365 zullen niet automatisch in Campagne worden weerspiegeld.  U moet het aanvraagscherm Campagne Privacy openen om de verwijderingen te bevestigen.

>[!NOTE]
>
>Deze integratie leidt tot een verzoek gebruikend Externe identiteitskaart (d.w.z., Dynamica 365 identiteitskaart van het Contact) als verslag/profiel herkenningsteken.

## Uitschakelen

Wegens de verschillen in opt-outattributen tussen Dynamiek 365 en Campagne, en wegens de verschillen in bedrijfsvereisten van elke klant, is de opt-out afbeelding verlaten als oefening voor de klant om te voltooien. Het is belangrijk ervoor te zorgen dat de optie-outs correct tussen systemen worden toegewezen, zodat de voorkeuren voor de optie-out voor eindgebruikers behouden blijven en er geen communicatie plaatsvindt via een kanaal dat ze hebben opgegeven.

Houd er rekening mee dat alleen Campagnekenmerken met het voorvoegsel &quot;blackList&quot; (bijvoorbeeld blackListEmail) of het specifieke kenmerk voor de optie om te weigeren in toewijzingen voor niet-aanmelding kunnen worden gebruikt.  In Dynamiek 365, hebben de meeste opt-outgebieden het &quot;doNot&quot;prefix; echter, kunt u douanekenmerken ook gebruiken u voor opt-outdoeleinden hebt gecreeerd als de gegevens-types compatibel zijn.

Wanneer levering van de integratie, zult u de kans hebben om te specificeren welke opt-out configuratie u voor uw zaken vereist:

* Dynamics 365 is een bron van waarheid voor opt-outs: de optieattributen zullen in één richting van Dynamiek 365 aan de Norm van de Campagne worden gesynchroniseerd
* Campagnestandaard is de bron van de waarheid voor opt-outs: de optieattributen zullen in één richting van de Norm van de Campagne aan Dynamica 365 worden gesynchroniseerd
* Dynamics 365 AND Campaign Standard are both sources of Waar: de opt-outattributen zullen bidirectioneel tussen de Norm van de Campagne en Dynamiek 365 worden gesynchroniseerd

Volg de instructies na levering in de [Unifi-gebruikershandleiding](https://drive.google.com/drive/folders/16seHF45e6bFxHX15zWLqFLEXymCuA_wn) om deze waarden correct toe te wijzen.

De bidirectionele opt-out configuratie gebruikt logica bepaalt welke waarde aan beide systemen moet schrijven.  De logica vergelijkt timestamps tussen de twee systemen (verandering op recordniveau in Dynamiek 365, attribuut-vlakke verandering in Campagne) om te bepalen welk systeem prevaleert.  Als Campagne de recentere timestamp bevat, dan heeft de waarde van de Campagne voorrang.  Als Dynamics 365 de recentere timestamp bevat of als zij gelijk zijn, dan zal opt-out=TRUE winnen (veronderstellend één van de waarden is WAAR).

**Uitschakelen op grond van de California Consumer Protection Act (CCPA) en soortgelijke wetgeving.**

De bidirectionele &quot;opt-out&quot;-configuratiefunctie biedt momenteel geen ondersteuning voor de naleving van bepaalde wettelijke vereisten in het kader van de CCPA en/of andere wetten inzake de privacy van gegevens. Klanten die moeten voldoen aan de CCPA of soortgelijke wettelijke vereisten met betrekking tot opt-outs zijn verantwoordelijk voor de implementatie van hun eigen oplossing van derden om bidirectionele synthesen uit te voeren.

>[!NOTE]
>
>Als uw bedrijf geen tweerichtingsondersteuning voor de optie Weigeren nodig heeft, kunt u het beste een optie voor één richting selecteren.

>[!NOTE]
>
>Controleer de standaard- en specifieke typologieregels in Adobe Campaign en werk deze zo nodig bij voordat u hier wijzigingen aanbrengt om ervoor te zorgen dat dergelijke wijzigingen correct worden toegepast op alle uitgaande communicatie. Zorg er bijvoorbeeld voor dat in toewijzingen voor voorkeuren voor niet-deelname de intent-/communicatiekeuzen van de ontvanger nauwkeurig worden weergegeven en dat de levering van relatie- of transactieberichten, zoals bevestigingen van de klantenorder, niet per ongeluk wordt stopgezet.

## Bestaande Campagnegegevens

Deze integratie zal Contacten en douaneentiteiten van Dynamiek 365 aan Campagne synchroniseren. Campagne-records die buiten de integratie zijn gemaakt (d.w.z. niet zijn gemaakt door de synchronisatietaak), worden niet beïnvloed door de integratie, inclusief Campagne-records die bestaan op het moment van de integratieconfiguratie.

Omdat deze integratie het **[!UICONTROL externalId]** gebied in de Norm van de Campagne gebruikt om het profielverslagen van de Campagne met Dynamiek 365 verslagen van het Contact te synchroniseren, moet dit gebied van de Campagne (**[!UICONTROL externalId]** ) met Dynamiek 365 **[!UICONTROL contactId]** voor de verslagen worden bevolkt u van Dynamiek 365 wenst te worden gesynchroniseerd.  Aangepaste entiteiten moeten dit veld ook hebben en correct hebben ingevuld om de synchronisatie te kunnen behouden.  Houd er echter rekening mee dat Dynamics 365 nog steeds de bron van de waarheid is en dat de Campagneprofielgegevens kunnen worden overschreven wanneer de integratie updates aan de zijde Dynamics 365 detecteert.  Afhankelijk van uw bestaande implementatie kunnen er ook andere stappen vereist zijn om de integratie in te schakelen. Daarom wordt u aangeraden nauw samen te werken met uw technische contactpersoon van Adobe.

>[!NOTE]
>
>Vanwege de complexiteit van bestaande implementaties van klanten wordt u aangeraden met uw technische contactpersoon van Adobe te werken bij het plannen en instellen van de integratie.
