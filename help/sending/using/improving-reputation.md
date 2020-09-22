---
title: Je reputatie verbeteren met Adobe Campaign Standard
description: Leer hoe u uw reputatie met Adobe Campaign Standard kunt verbeteren door dubbele e-mailadressen en quarantines te beheren.
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
source-git-commit: 1b1fb4a0dc0f7881e24e10f8ac171feab2ac8cba
workflow-type: tm+mt
source-wordcount: '458'
ht-degree: 2%

---


# Uw reputatie verbeteren{#improving-reputation}

Verwijder dubbele e-mailadressen van uw doel om te voorkomen dat de ontvangers uitputten. Deze stap beschermt uw verzendende reputatie en verzekert goed quarantainebeheer. Adobe Campaign biedt de noodzakelijke hulpmiddelen aan om deze aanbevelingen uit te voeren en het risico te vermijden om aan de lijst van afgewezen personen door ISPs worden toegevoegd.

Hieronder vindt u meer informatie over duplicaat- en quarantainebeheer.

## Duplicaten {#duplicates}

Het hebben van dubbele e-mailadressen kan veelvoudige gevolgen hebben:
* Hetzelfde bericht wordt meerdere keren verzonden. Zelfs als Campagne standaard een deduplicatieprocedure uitvoert voordat het wordt verzonden, is er niets om te voorkomen dat hetzelfde bericht wordt verzonden door verschillende handelingen met dezelfde inhoud wanneer een doel wordt gesplitst.
* Abonnementsverzoeken worden niet geaccepteerd. Als een ontvanger zich afmeldt na het ontvangen van een bericht, zal zijn dubbel profiel nog verkiesbaar voor toekomstige berichten zijn.

Naast deze zijstap van opt-in procedures, zal deze situatie gebruikers waarschijnlijk leiden om de berichten als spam te beschouwen en een procedure van de lijst van afgewezen personen bij ISP teweeg te brengen.

U moet bijzonder voorzichtig zijn wanneer het uitvoeren van verrichtingen op het gegevensbestand. Om dubbel werk zoveel mogelijk te voorkomen, moeten de volgende acties worden uitgevoerd:
* **De invoer moet zorgvuldig worden gevormd.** Dit is met name van belang bij het kiezen van de verzoeningssleutel.
* **Let op bij het wijzigen van e-mailadressen.** Gewijzigde e-mailadressen kunnen ook een bron van duplicaten zijn. Met name, kunnen twee adressen met verschillende domeinen aan de zelfde brievenbus worden verpletterd, bijvoorbeeld in het geval van een bedrijf dat naam heeft veranderd en het vroegere domein voor een bepaalde periode heeft gehandhaafd: joe.doe@amce-co.com en joe.doe@acme-rebranded.com.
* **Let op bij automatisch importeren.** Of het nu gaat om lijsten of andere databases, het zijn elementen waarmee rekening moet worden gehouden bij het beheren van profielen. Wat gebeurt er als u een profiel verwijdert of verplaatst in een andere partitie? Het kan opnieuw worden gemaakt in de eerste partitie door een automatische importbewerking, bijvoorbeeld wanneer een inkooporder wordt geplaatst.
* **Profielen moeten in verschillende mappen worden gesorteerd.**

Er zijn echter gevallen waarin duplicaten tussen de verschillende partities normaal zijn. Bij het verzenden van documenten voor derden of voor verschillende bedrijfsentiteiten is het bijvoorbeeld logisch dat dezelfde persoon om verschillende redenen een ontvanger is. Het is echter zelden normaal om duplicaten binnen dezelfde partitie te zoeken.

## Quarantines {#quarantines}

Adobe Campaign beheert een lijst met in quarantaine geplaatste adressen. De ontvangers de waarvan adressen quarantined zijn uitgesloten door gebrek tijdens de leveringsanalyse: zij zijn niet gericht .

Het quarantainebeheer wordt beschreven in [deze sectie](../../sending/using/understanding-quarantine-management.md).

Een e-mailadres kan in quarantaine worden geplaatst bijvoorbeeld wanneer inbox volledig is of als het adres niet bestaat. In alle gevallen, beantwoordt quarantining aan de specifieke regels die in [deze sectie](../../sending/using/understanding-quarantine-management.md#conditions-for-sending-an-address-to-quarantine)worden voorgesteld.
