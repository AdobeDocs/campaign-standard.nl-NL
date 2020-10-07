---
title: Berichtlevering optimaliseren
seo-title: Berichtlevering optimaliseren
page-status-flag: never-activated
uuid: a540efc7-105d-4c7f-a2ee-ade4d22b3445
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
discoiquuid: 0cbc4e92-482f-4dac-a1fb-b738e7127938
index: y
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '735'
ht-degree: 6%

---


# Levering optimaliseren {#optimize-delivery}

Voordat u zelfs begint met het maken van leveringen, kunt u verschillende acties uitvoeren om het verzendingsproces te beveiligen en te optimaliseren.

In de volgende sectie worden aanbevolen procedures en aanbevolen procedures voor de optimale configuratie van Adobe Campaign beschreven. Als u deze praktijken volgt, worden de problemen die u later tegenkomt, tot een minimum beperkt.

## Prestaties van Platforms

Verschillende factoren kunnen de serverprestaties rechtstreeks beïnvloeden en het platform vertragen:

* Het aantal en het type van verpersoonlijkingselementen: personalisatie in e-mailberichten haalt gegevens uit de database voor elke ontvanger. Als er vele verpersoonlijkingselementen zijn, verhoogt dat de hoeveelheid gegevens nodig om de levering voor te bereiden.  Meer informatie over e-mailpersonalisatie vindt u in [deze sectie](../../designing/using/personalization.md)

* De server wordt geladen: als Campagne vele verschillende taken tezelfdertijd behandelt, kan het prestaties vertragen. De server moet alle inkomende en uitgaande gegevens voor alle leveringen coördineren om ervoor te zorgen dat de gegevens correct en op tijd zijn.

   **TIP** - om dit te vermijden, coördineert het plannen van leveringen met de andere leden van uw team om de beste prestaties te verzekeren.

* De [workflowuitvoering](../../automating/using/about-workflow-execution.md): het controleren van uw workflows is essentieel om problemen met de prestaties van het platform te voorkomen. Volg de richtlijnen [op deze pagina](../../automating/using/monitoring-workflow-execution.md). Meer informatie vindt u in het gedeelte over aanbevolen [werkwijzen](../../automating/using/best-practices-workflows.md) in de workflow.

* U kunt de mogelijkheden [van het deelvenster](https://docs.adobe.com/content/help/en/control-panel/using/discover-control-panel/key-features.html) Campagne Control gebruiken om uw platform te bewaken met behulp van de functies voor [prestatiebewaking](https://docs.adobe.com/content/help/en/control-panel/using/performance-monitoring/about-performance-monitoring.html) .

## Netwerkconfiguratie controleren {#network-config}

Om levering te optimaliseren wanneer het behandelen van e-mails in grote volumes en vermijd wordt verward voor spammer, zorg ervoor dat u een wettige netwerkconfiguratie hebt die niet probeert om de identiteit van de server te verbergen.

**Tip**:  Gebruik een transparant verzendadres dat overeenkomt met de website van uw merk. Het bedrijf TravelAgency beheert bijvoorbeeld de hotelketen Valentino. Zijn bezit het domein valentino.com voor zijn website. Om het hotel Valentino in Parijs te promoten, gebruikt het subdomein paris.valentino.com. Daarom kan een relevant afzenderadres hotel@paris.valentino.com zijn.

## Leverbaarheidsbeheer {#deliverability-management}

Om uw ontvangers&#39; te bereiken inbox zonder te stuiteren of als spam worden gemerkt, moet u het leverbaarheidstarief van uw berichten verbeteren.

* Wat is leverbaarheid?

   * Het verwijst naar de factoren van een e-mail die zijn capaciteit bepalen om door de server van een ontvanger worden goedgekeurd. ISPs (de Dienstverleners van Internet) filter uit e-mails die zij als SPAM identificeren, of zij blokkeren beelden van het downloaden. Als ze vaststellen dat een bepaald domein te veel e-mails verzendt, stellen ze een limiet in voor het aantal e-mails dat ze van die afzender accepteren.

   * Wanneer u uw e-mail controleert op leverbaarheid, wilt u zich op vier hoofdcategorieën concentreren: gegevenskwaliteit, bericht en inhoud, verzendende infrastructuur, en reputatie. Raadpleeg [deze sectie](../../sending/using/about-deliverability.md)voor een dieper overzicht van dit onderwerp.

* Pas bij het starten van een nieuw platform de aanbevelingen toe die [in deze pagina](../../sending/using/starting-new-platform.md)worden beschreven.

* Neem contact op met uw Adobe-vertegenwoordiger voor hulp.

## Quarantainebeheer {#quarantine-management}

Het is in uw belang om goede processen van het quarantainebeheer te handhaven.

Wanneer u e-mailberichten op een nieuw platform gaat verzenden, kunt u een lijst met adressen gebruiken die niet volledig zijn gekwalificeerd. Als u naar ongeldige adressen of naar honeypot-adressen (brievenbussen slechts die aan truc spammers worden gecreeerd) verzendt, zal dit de reputatie van uw platform beginnen te verminderen. Goede quarantainebeheerprocessen helpen: Houd de adreskwaliteit in stand, vermijd lijst van afgewezen personen door internettoegangsproviders en verlaag uw foutenpercentage, versnelt de levering en doorvoer.

**Tips**

* De ontvangers de waarvan adressen quarantined zijn uitgesloten door gebrek tijdens de leveringsanalyse: zij zijn niet gericht . Hierdoor wordt de levering versneld, omdat het foutenpercentage een belangrijk effect heeft op de leveringssnelheid. Een e-mailadres kan in quarantaine worden geplaatst bijvoorbeeld wanneer inbox volledig is of als het adres niet bestaat. [Meer informatie](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses)

* Adobe Campaign beheert onjuiste adressen op basis van het type geretourneerde fout. Raadpleeg [deze sectie](../../sending/using/understanding-quarantine-management.md) voor meer informatie.

* Sommige internetproviders beschouwen e-mails automatisch als spam als het aantal ongeldige adressen te hoog is. Met quarantaine kunt u dus voorkomen dat u door deze providers aan de lijst van afgewezen personen wordt toegevoegd.

* Het beheer van quarantaines zal ook de verzendkosten van SMS helpen verminderen door onjuiste telefoonnummers uit te sluiten van leveringen.

## Dubbele opt-in-regeling {#double-opt-in}

Om te voorkomen dat berichten naar ongeldige adressen worden verzonden, onjuiste communicatie wordt beperkt en de reputatie van de afzender wordt verbeterd, raadt Adobe aan een dubbele opt-in-mechanisme in te voeren voor bevestiging na abonnement. Zo weet u zeker dat een ontvanger met opzet is geabonneerd.

De details voor de implementatie van dit mechanisme worden beschreven in [deze sectie](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md).

Meer informatie in Aan de [slag met profielen en publiek](../../audiences/using/get-started-profiles-and-audiences.md).
