---
title: Technische aanbevelingen voor de aflevering van Adobe Campagne Standard
description: Lees meer over enkele technische aanbevelingen om de prestaties te verbeteren met Adobe Campagne Standard.
page-status-flag: never-activated
uuid: 286fceee-65a9-4cb9-b205-9ce5d024675c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: sheduling-messages
discoiquuid: 9c7fd670-bba9-4f3c-8cb1-87397a1acd27
context-tags: delivery,schedule,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 44049443f8028ed26089ee0d49944ebac6a62111

---


# Technische aanbevelingen{#technical-recommendations}

Hieronder vindt u een overzicht van verschillende technieken, configuraties en gereedschappen die u kunt gebruiken om de prestaties te verbeteren.

Hier volgen enkele definities van de belangrijkste technische termen.

**De omgekeerde DNS** Campagne van Adobe controleert of omgekeerde DNS voor een IP adres wordt gegeven en dat dit correct naar IP wijst.

**De MX regels** MX regels worden gebruikt om de snelheid te controleren waarbij de Campagne MTA (de Agent van de Overdracht van het Bericht) e-mail naar elk individueel e-maildomein of ISP (b.v. hotmail.com, comcast.net) verzendt. Deze regels zijn typisch gebaseerd op grenzen die door ISPs worden gepubliceerd (bijvoorbeeld omvatten niet meer dan 20 berichten per elke verbinding SMTP).

**TLS** TLS (Transport Layer Security) is een versleutelingsprotocol dat kan worden gebruikt om de verbinding tussen twee e-mailservers te beveiligen en de inhoud van een e-mailbericht te beschermen tegen lezen door andere personen dan de beoogde ontvangers.

**SPF** SPF (het Kader van het Beleid van de Afzender) is een norm van de e-mailauthentificatie die de eigenaar van een domein toestaat om te specificeren welke e-mailservers e-mail namens dat domein mogen verzenden. Deze standaard gebruikt het domein in de &quot;terugkeer-Weg&quot;kopbal van e-mail (die ook als &quot;Omhulsel van&quot;adres wordt bedoeld).

**DKIM** DKIM (Domein Keys Identified Mail) authentificatie is een opvolger van SPF en gebruikt publiek-zeer belangrijke cryptografie die de ontvangende e-mailserver toestaat om te verifiëren dat een bericht in feite werd verzonden door de persoon of de entiteit het beweert werd verzonden door, en of de berichtinhoud werd veranderd binnen tussen de tijd het oorspronkelijk werd verzonden (en DKIM &quot;ondertekend&quot;) en de tijd het werd ontvangen. Deze standaard gebruikt doorgaans het domein in de kop &quot;Van&quot; of &quot;Afzender&quot;.

**DMARC** DMARC (Op domein gebaseerde Authentificatie, Rapportering en Conformiteit van het Bericht) is de meest recente vorm van e-mailauthentificatie, en het baseert zich op zowel SPF als authentificatie DKIM om te bepalen of een e-mail overgaat of ontbreekt. DMARC is uniek en krachtig op twee zeer belangrijke manieren:
* Conformiteit - het staat de afzender toe om ISPs te instrueren over wat met om het even welk bericht te doen dat er niet in slaagt voor authentiek te verklaren (b.v. keurt het niet goed).
* Het melden - het verstrekt de afzender van een gedetailleerd rapport dat alle berichten toont die authentificatie DMARC, samen met het &quot;Van&quot;domein en IP adres ontbrak dat voor elk wordt gebruikt. Dit staat een bedrijf toe om wettige e-mail te identificeren die authentificatie ontbreekt en één of ander type van &quot;moeilijke situatie&quot;(b.v. het toevoegen van IP adressen aan hun SPF verslag), evenals de bronnen en de prevalentie van phishingpogingen op hun e-maildomeinen vereist.

DMARC kan de rapporten gebruiken die door 250ok worden geproduceerd.

**SMTP** SMTP (Simple Mail Transfer Protocol) is een internetstandaard voor e-mailverzending.

**Speciale IP&#39;s** Adobe biedt een toegewijde IP-strategie voor elke klant met een IP-bestand voor het maken van een upgrade om een reputatie op te bouwen en de prestaties van de levering te optimaliseren.
