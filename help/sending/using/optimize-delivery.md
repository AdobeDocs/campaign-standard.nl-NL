---
title: Berichtlevering optimaliseren
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: true
description: Leer hoe u het verzendproces upstream kunt beveiligen en optimaliseren.
feature: Deliverability
role: User
level: Intermediate
exl-id: 28b0cf6d-c1f1-4d55-b9bc-0d6bfb063471
source-git-commit: ac925ec5f59f1bb57b56b430fd175a27b08c3bfe
workflow-type: tm+mt
source-wordcount: '727'
ht-degree: 0%

---

# Levering optimaliseren {#optimize-delivery}

Voordat u zelfs begint met het maken van leveringen, kunt u verschillende acties uitvoeren om het verzendingsproces te beveiligen en te optimaliseren.

In de volgende sectie worden aanbevolen procedures en aanbevolen procedures voor de optimale configuratie van Adobe Campaign beschreven. Als u deze praktijken volgt, worden de problemen die u later tegenkomt, tot een minimum beperkt.

## Platformprestaties

Verschillende factoren kunnen de serverprestaties rechtstreeks beïnvloeden en het platform vertragen:

* Het aantal en het type van verpersoonlijkingselementen: de verpersoonlijking in e-mail trekt gegevens uit het gegevensbestand voor elke ontvanger. Als er vele verpersoonlijkingselementen zijn, verhoogt dat de hoeveelheid gegevens nodig om de levering voor te bereiden.  Leer meer over e-mailverpersoonlijking in [&#x200B; deze sectie &#x200B;](../../designing/using/personalization.md)

* De server wordt geladen: wanneer tijdens de campagne veel verschillende taken tegelijk worden uitgevoerd, kunnen de prestaties afnemen. De server moet alle inkomende en uitgaande gegevens voor alle leveringen coördineren om ervoor te zorgen dat de gegevens correct en op tijd zijn.

  **TIP** - om dit te vermijden, coördineer het plannen van leveringen met de andere leden van uw team om de beste prestaties te verzekeren.

* De [&#x200B; werkschemauitvoering &#x200B;](../../automating/using/about-workflow-execution.md): het controleren van uw werkschema is essentieel om de kwesties van de platformprestaties te vermijden. Volg de vermelde richtlijnen [&#x200B; in deze pagina &#x200B;](../../automating/using/monitoring-workflow-execution.md). Leer meer in de [&#x200B; werkschema beste praktijken &#x200B;](../../automating/using/best-practices-workflows.md) sectie.

* U kunt hefboomwerking &lbrace;de mogelijkheden van het Controlebord van de Campagne [&#x200B; om uw platform te controleren, gebruikend &#x200B;](https://experienceleague.adobe.com/docs/control-panel/using/discover-control-panel/key-features.html) prestaties controlerende [&#x200B; functies.](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/about-performance-monitoring.html)

## Netwerkconfiguratie controleren {#network-config}

Om levering te optimaliseren wanneer het behandelen van e-mails in grote volumes en vermijd wordt verward voor spammer, zorg ervoor dat u een wettige netwerkconfiguratie hebt die niet probeert om de identiteit van de server te verbergen.

**Uiteinde**: Gebruik een transparant afzenderadres dat aan de website van uw merk beantwoordt. Het bedrijf TravelAgency beheert bijvoorbeeld de hotelketen Valentino. Zijn bezit het valentino.com domein voor zijn website. Om het hotel Valentino in Parijs te promoten, gebruikt het subdomein paris.valentino.com. Daarom kan een relevant afzenderadres hotel@paris.valentino.com zijn.

## Leverbaarheidsbeheer {#deliverability-management}

Om uw ontvangers&#39; te bereiken inbox zonder te stuiteren of als spam worden gemerkt, moet u het leverbaarheidstarief van uw berichten verbeteren.

* Wat is leverbaarheid?

   * Het verwijst naar de factoren van een e-mail die zijn capaciteit bepalen om door de server van een ontvanger te worden goedgekeurd. ISPs (de Dienstverleners van Internet) filter uit e-mails die zij als SPAM identificeren, of zij blokkeren beelden van het downloaden. Als ze vaststellen dat een bepaald domein te veel e-mails verzendt, stellen ze een limiet in voor het aantal e-mails dat ze van die afzender accepteren.

   * Wanneer u uw e-mail controleert op leverbaarheid, wilt u zich op vier hoofdcategorieën concentreren: gegevenskwaliteit, bericht en inhoud, verzendende infrastructuur, en reputatie. Voor een diepere duik op dit onderwerp, verwijs naar [&#x200B; deze sectie &#x200B;](../../sending/using/about-deliverability.md).

* Wanneer het beginnen van een nieuw platform, pas de aanbevelingen toe die op [&#x200B; worden gedetailleerd deze pagina &#x200B;](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/switching-email-platforms.html#transition-process).

* Neem contact op met uw Adobe-vertegenwoordiger voor hulp.

## Quarantainebeheer {#quarantine-management}

Het is in uw belang om goede processen van het quarantainebeheer te handhaven.

Wanneer u e-mailberichten op een nieuw platform gaat verzenden, kunt u een lijst met adressen gebruiken die niet volledig zijn gekwalificeerd. Als u naar ongeldige adressen of naar honeypot-adressen (brievenbussen slechts die aan truc spammers worden gecreeerd) verzendt, zal dit de reputatie van uw platform beginnen te verminderen. Goede quarantainebeheerprocessen helpen: de adreskwaliteit handhaven, lijst van gewezen personen door internettoegangsproviders vermijden, en uw foutenpercentage verminderen, leveringen en productie versnellen.

**Uiteinden**

* De ontvangers de waarvan adressen in quarantined zijn uitgesloten door gebrek tijdens de leveringsanalyse: zij worden niet gericht. Dit zal leveranties versnellen, aangezien het foutenpercentage een significant effect op leveringssnelheid heeft. Een e-mailadres kan in quarantaine worden geplaatst bijvoorbeeld wanneer inbox volledig is of als het adres niet bestaat. [&#x200B; Leer meer &#x200B;](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses)

* Adobe Campaign beheert onjuiste adressen op basis van het type geretourneerde fout. Voor meer op dit, verwijs naar [&#x200B; deze sectie &#x200B;](../../sending/using/understanding-quarantine-management.md).

* Sommige internetproviders beschouwen e-mails automatisch als spam als de snelheid van ongeldige adressen te hoog is. Met quarantaine kunt u dus voorkomen dat deze providers aan de lijst van gewezen personen worden toegevoegd.

* Het beheer van quarantaines zal ook de verzendkosten van SMS helpen verminderen door onjuiste telefoonnummers uit te sluiten van leveringen.

## Dubbele opt-in-regeling {#double-opt-in}

Om te voorkomen dat berichten naar ongeldige adressen worden verzonden, onjuiste communicatie wordt beperkt en de reputatie van de afzender wordt verbeterd, raadt Adobe aan een dubbele aanmeldingsprocedure voor bevestiging na abonnement in te voeren. Zo weet u zeker dat een ontvanger met opzet is geabonneerd.

De details voor het uitvoeren van dit mechanisme worden geschetst in [&#x200B; deze sectie &#x200B;](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md).

Leer meer in [&#x200B; worden begonnen met profielen en publiek &#x200B;](../../audiences/using/get-started-profiles-and-audiences.md).
