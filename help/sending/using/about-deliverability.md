---
title: Informatie over leverbaarbaarheid in Adobe Campaign Standard
description: Leer meer over de concepten en beste praktijken met betrekking tot leverbaarheid evenals de hulpmiddelen die door Adobe Campaign Standard worden aangeboden om het verzenden van uw leveringen te optimaliseren.
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: Deliverability
role: User
level: Intermediate
exl-id: 5e523519-7192-4031-9d96-559af23074d9
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '744'
ht-degree: 7%

---

# Wat is afleverbaarheid?{#about-deliverability}

De levering staat toe om het succes van uw campagnes te meten die uw ontvangers&#39; inbox bereiken zonder te stuiteren, of als spam worden gemerkt. [Meer weten waarom het van belang is om te leveren](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/deliverability-strategy-and-definition.html#why-deliverability-matters).

Meer bepaald, verwijst de e-maillevering naar de reeks eigenschappen die de capaciteit van een bericht bepalen om zijn bestemming, via een persoonlijk e-mailadres, binnen een korte tijd, en met de verwachte kwaliteit in termen van inhoud en formaat te bereiken. <!--These characteristics fall into four main categories: data quality, message and content, sending infrastructure, and reputation. Together, they form the foundation of a successful email deliverability program.-->

Voor een diepgaander inzicht in wat de te leveren prestaties zijn en meer te leren over zeer belangrijke leverbaarheidsvoorwaarden, concepten, en benaderingen, verwijs naar [Adobe Handleiding voor beste praktijken voor aflevering](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=nl).

## Hoe te om leverbaarheid te verbeteren {#deliverability-key-points}

De leveringsproblemen houden gewoonlijk verband met maatregelen van bescherming tegen spam die door Internet dienstverleners en de beheerders van de postserver worden uitgevoerd.

* Voor algemene aanbevelingen over het ontwerpen van succesvolle e-mailmarketingcampagnes raadpleegt u [Leverbaarheidsstrategie en definitie](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/deliverability-strategy-and-definition.html).

* Voor specifiekere aanbevelingen voor het optimaliseren van de leverbaarbaarheid van je Adobe Campaign-e-mails raden we u aan de beste praktijken in deze sectie te gebruiken.

>[!NOTE]
>
>Omdat ISPs verplicht is voortdurend nieuwe verfijnde het filtreren technieken te ontwikkelen om hun klanten tegen spammers te beschermen, wordt de e-maillevering gekenmerkt door voortdurend veranderende criteria en regels. Zorg ervoor dat u naar de [Adobe Handleiding voor beste praktijken voor aflevering](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html) die regelmatig wordt bijgewerkt.

### Leverbaarheidsgraad

Het leverbaarheidstarief is het aantal berichten die de ontvangers&#39; in dozen vergeleken bij het aantal berichten raakten die werden geleverd. Om de leverbaarheid te verbeteren, kunt u aan verhoging dit tarief werken.

Bij Adobe Campaign hangt het leverbrengingscijfer af van een groot aantal factoren, met name:

* Correcte configuratie van uw instanties: Neem contact op met uw Adobe-vertegenwoordiger voor hulp.
* Legitieme netwerkconfiguratie: zie [deze sectie](../../sending/using/optimize-delivery.md#network-config) en [Instellen en strategie van domeinen](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#domain-setup-and-strategy).
* Uw IP adresreputatie: zie [IP-strategie](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#ip-strategy).
* Kwaliteit van de beoogde adressen: zie [Quarantainebeheer](../../sending/using/optimize-delivery.md#quarantine-management).
* Laag [klachten](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/complaints.html) en [harde stoot](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html#hard-bounces) tarieven.
* Uw berichtinhoud: zie [E-mailinhoud beheren](../../sending/using/control-email-content.md).
* Berichtverificatie (SPF, DKIM, DMARC): zie [deze sectie](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#authentication).
* Afkorting van afzender: om te leren hoe belangrijkste ISPs een afzenderreputatie evalueert, zie [deze sectie](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/internet-service-provider-specifics/overview.html).

## Hulpprogramma&#39;s voor het leveren van campagnes {#deliverability-tools}

Adobe Campaign biedt een aantal tools om de prestaties van uw platform te volgen en te verbeteren. Op deze pagina worden ook de belangrijkste beginselen gemarkeerd die u in gedachten moet houden om de prestaties te optimaliseren wanneer u campagne gebruikt.

### Uw bericht zorgvuldig samenstellen

Wanneer het vormen van, het ontwerpen van en het testen van uw bericht, zorg ervoor u de beste praktijken volgt die in de hieronder vermelde secties worden vermeld. Door gebruik te maken van alle functies die Adobe Campaign biedt, kunt u de leverbaarheid verbeteren.

* [Best practices voor verzending](../../sending/using/delivery-best-practices.md)
* [E-mailcontent controleren](../../sending/using/control-email-content.md)
* [Berichten voorvertonen](../../sending/using/previewing-messages.md)
* [Proeven verzenden](../../sending/using/sending-proofs.md)

### Verifieer toestemming door dubbele opt-in {#double-opt-in}

Om het verzenden van berichten naar ongeldige adressen te vermijden, onjuiste mededelingen te beperken en afzenderreputatie te verbeteren, adviseert Adobe het uitvoeren van een dubbel opt-in mechanisme. Op deze manier kunt u ervoor zorgen dat de ontvangers zich bewust hebben geabonneerd.

Zie voor meer informatie [Over opt-in en opt-out in campagne](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md).

Raadpleeg voor meer informatie over aanbevolen procedures bij het verzamelen van gegevens van uw klanten de [Adobe Handleiding voor beste praktijken voor aflevering](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/first-impressions/address-collection-and-list-growth.html#data-quality-and-hygiene).

### Gebruik quarantainebeheer

Adobe Campaign beheert een lijst met spamklachten, harde stuitingen en zachte stuitingen die consistent voorkomen.

Om uw leverbaarheid te beschermen, worden de ontvangers van wie adressen op die lijst zijn uitgesloten door gebrek van alle toekomstige leveringen, omdat het verzenden naar deze contacten uw verzendende reputatie zou kunnen schaden.

Sommige internetproviders beschouwen e-mails automatisch als spam als het aantal ongeldige adressen te hoog is. Met quarantaine kunt u dus voorkomen dat u door deze providers aan de lijst van gewezen personen wordt toegevoegd.

Raadpleeg de volgende secties voor meer informatie hierover:

* [Leveringsfouten begrijpen](../../sending/using/understanding-delivery-failures.md)
* [Werken met quarantainebeheer](../../sending/using/understanding-quarantine-management.md)
* [Quarantine versus lijst van gewezen personen](../../sending/using/understanding-quarantine-management.md#quarantine-vs-denylist)

### Gereedschappen voor bewaking en rapportage gebruiken

Gebruik de functies die Adobe Campaign biedt om de prestaties te controleren.

Met Adobe Campaign kunt u controleren hoe uw leveringen presteren aan de hand van een set ingebouwde realtime-indicatoren. <!--For example, you can check the number of messages that are successfully executed, sent and delivered. You can also verify the number of messages that have been opened and the number of messages/links that have been clicked.-->U kunt ook volledig aanpasbare en real-time rapporten maken voor een beter inzicht in uw leveringen.

Raadpleeg de volgende secties voor meer informatie hierover:

* [Leverbaarheid controleren](../../sending/using/monitor-deliverability.md)

   <!--[Monitoring a delivery](../../sending/using/monitoring-a-delivery.md)-->
* [Waarschuwingen ontvangen wanneer fouten optreden](../../sending/using/receiving-alerts-when-failures-happen.md)
* [Dynamische rapporten](../../reporting/using/about-dynamic-reports.md)

<!--## General recommendations

NOT SURE TO KEEP

Here are a few additional recommendations when it comes to deliverability.

### Send to valid addresses {#valid-addresses}

Spammers often use address generators based on lists of frequent names and first names; in addition, they rarely process technical notifications sent back by mail servers. A high rate of invalid addresses is often interpreted as a sign of spam.

Double opt-in mechanisms and effective handling of technical bounce messages make it possible to avoid this.

### Reduce complaint rate {#reduce-complaint-rate}

ISPs usually have a prominent means of reporting a received message as spam. This makes it possible to identify unreliable sources. By rapidly honoring opt-out requests, making regular use of a given list, verifying consent through a double opt-in system, and implementing feedback loops, you can reduce complaint rates.

<!--Sending to honeypot addresses {#honeypot-addresses}
ISPs and other organizations (refer to https://www.projecthoneypot.org/) make use of mailboxes that do not correspond to physical persons but are created simply to trick spammers. These so-called "honey pot" addresses are published on the Web in order to be collected by spambots and thus catch illegitimate senders. The use of a double opt-in mechanism precludes this sort of address being added to a list. When using a third-party list, you must be sure of the methods employed by its maintainer.-->

<!--## Sending on a regular basis {#regular-deliveries}

Spammers make programmed deliveries to maintain their reputation over time. They sometimes need to adapt their marketing plan to meet the best practices imposed by the ISPs and so, after a peak in reputation (ramp-up), they configure regular deliveries.-->
