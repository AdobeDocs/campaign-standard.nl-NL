---
title: Informatie over leverbaarbaarheid in Adobe Campaign Standard
description: Leer meer over de concepten en beste praktijken met betrekking tot leverbaarheid evenals de hulpmiddelen die door Adobe Campaign Standard worden aangeboden om het verzenden van uw leveringen te optimaliseren.
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
source-git-commit: df70a2165c5d3a4b553565d9a91ec3f8da1b44aa
workflow-type: tm+mt
source-wordcount: '662'
ht-degree: 6%

---


# Leverbaarheid{#about-deliverability}

De levering staat toe om het succes van uw campagnes te meten die uw ontvangers&#39; inbox bereiken zonder te stuiteren, of als spam worden gemerkt.

Het percentage te leveren producten hangt af van een groot aantal factoren, met name:

* Correcte configuratie van uw instanties
* Uw IP adresreputatie
* Kwaliteit van de beoogde adressen
* Lage klachten en harde stuitcijfers
* Uw berichtinhoud
* Berichtverificatie (SPF, DKIM, DMARC)
* Afzender

## Belangrijkste punten om te controleren {#deliverability-key-points}

We raden u aan de onderstaande aanbevolen procedures te gebruiken om de leverbaarheid van je Adobe Campaign-e-mails te optimaliseren. De leveringsproblemen houden over het algemeen verband met maatregelen ter bescherming tegen spam die worden uitgevoerd door internetserviceproviders en postserverbeheerders.

De e-mailleverbaarheid verwijst naar de reeks kenmerken die bepalen of een bericht zijn bestemming, via een persoonlijk e-mailadres, binnen een korte tijd, en met de verwachte kwaliteit in termen van inhoud en formaat kan bereiken. Deze kenmerken vallen in vier hoofdcategorieën: gegevenskwaliteit, bericht en inhoud, verzendende infrastructuur, en reputatie. Samen vormen ze de basis voor een succesvol e-mailprogramma.

Het percentage te leveren items is het aantal verzonden e-mailberichten dat is bezorgd aan de ontvangers.
Hier volgt een lijst met de belangrijkste punten die moeten worden gecontroleerd om te zorgen voor goede prestaties.

## Leveringsgereedschappen {#deliverability-tools}

Eerst raadpleegt u de documentatie over de leverbare gereedschappen die bij Campaign Standard worden geleverd:
* [Best practices voor levering](https://helpx.adobe.com/nl/campaign/kb/delivery-best-practices.html)
* [De naam van de afzender aanpassen](../../designing/using/personalization.md#personalizing-the-sender)
* [De onderwerpregel van een e-mail testen](../../sending/using/testing-subject-line-email.md)
* [De verzendtijd optimaliseren](../../sending/using/optimizing-the-sending-time.md)
* [Berichten voorvertonen](../../sending/using/previewing-messages.md)
* [E-mailweergave](../../sending/using/email-rendering.md)
* [Een levering controleren](../../sending/using/monitoring-a-delivery.md)
* [Waarschuwingen ontvangen wanneer fouten optreden](../../sending/using/receiving-alerts-when-failures-happen.md)
* [Leveringsfouten begrijpen](../../sending/using/understanding-delivery-failures.md)
* [Quarantainebeheer begrijpen](../../sending/using/understanding-quarantine-management.md)
* [Quarantine versus lijst van afgewezen personen](../../sending/using/understanding-quarantine-management.md#quarantine-vs-denylist)
* [Dynamische rapporten](../../reporting/using/about-dynamic-reports.md)

## Netwerkconfiguratie controleren {#network-configuration}

Spammers proberen hun echte identiteit te verhullen en maken hun servers daardoor moeilijk te identificeren. Een wettige netwerkconfiguratie die niet probeert om de identiteit van de server te verbergen is essentieel voor het verzenden van e-mails in grote volumes.

## Verzenden naar geldige adressen {#valid-addresses}

Spammers gebruiken vaak adresgeneratoren op basis van lijsten met frequente namen en voornamen; bovendien verwerken zij zelden technische kennisgevingen die door mailservers worden teruggestuurd . Een hoog tarief van ongeldige adressen wordt vaak geïnterpreteerd als teken van spam. Dubbele &quot;opt-in&quot;-mechanismen en een effectieve verwerking van technische &quot;bounce&quot;-berichten maken het mogelijk dit te voorkomen.

## Het klachtenpercentage verlagen {#reduce-complaint-rate}

ISPs heeft gewoonlijk een duidelijk middel om een ontvangen bericht als spam te melden. Hierdoor kunnen onbetrouwbare bronnen worden geïdentificeerd. Door opt-outverzoeken snel na te leven, regelmatig gebruik te maken van een bepaalde lijst, toestemming te controleren via een systeem met dubbele opt-in en terugkoppelingsmogelijkheden te implementeren, kunt u de klachtentarieven verlagen.

## Verzenden naar honingpotadressen {#honeypot-addresses}

ISPs en andere organisaties (verwijs naar https://www.projecthoneypot.org/) maken gebruik van brievenbussen die niet aan fysieke personen beantwoorden maar eenvoudig worden gecreeerd om spammers te bedriegen. Deze zogenaamde &quot;honingpot&quot;-adressen worden op het web gepubliceerd om door spambots te worden verzameld en aldus illegale afzenders te vangen. Het gebruik van een dubbele opt-in-mechanisme sluit het toevoegen van dit adres aan een lijst uit. Wanneer u een lijst van derden gebruikt, moet u zeker zijn van de methoden die door de onderhoudsleider worden gebruikt.

## Berichtinhoud aanpassen {#adapt-message-content}

In mindere mate kan de inhoud van bepaalde berichten ertoe leiden dat bepaalde filters de inhoud als spam detecteren. Het gebruik van bepaalde woorden, het gebruik van uitroeptekens in de onderwerpregel en in de berichten worden gelezen als verklikkersignalen van spam. Spammers kunnen ook tekst vervangen door afbeeldingen om te voorkomen dat onregelmatige tekst automatisch wordt geanalyseerd door anti-spamfilters. Als reactie hierop kan een bericht (in HTML-indeling) met een groot aantal afbeeldingen of afbeeldingen als bijlagen worden geblokkeerd.

## Regelmatig verzenden {#regular-deliveries}

Spammers maken geprogrammeerde leveringen om hun reputatie in de loop der tijd te behouden. Soms moeten zij hun marketing plan aanpassen om aan de beste praktijken te voldoen die door ISPs worden opgelegd en zo, na een piek in reputatie (oprijving), vormen zij regelmatige leveringen.
