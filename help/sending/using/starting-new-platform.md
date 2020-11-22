---
solution: Campaign Standard
product: campaign
title: Een nieuw platform starten met Adobe Campaign Standard
description: Leer hoe te opstelling een nieuw platform terwijl het handhaven van uw domein en IP adresreputatie met Adobe Campaign Standard.
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '444'
ht-degree: 2%

---


# Een nieuw platform starten{#starting-new-platform}

Het handhaven van uw domein en IP adresreputatie is essentieel. Hier volgt een advies voor het opzetten van een nieuw platform.

Het beginnen om e-mails op een nieuw platform te verzenden is een gevoelige stap omdat het platform geen geschiedenis van gebruik en geen reputatie heeft (wanneer de verzendende IPs nooit voor dit doel zijn gebruikt). ISPs is natuurlijk verdacht van IP adressen die nooit zijn gebruikt om e-mail te verzenden en die plotseling beginnen grote volumes van e-mailverkeer te verzenden. In feite, gebruiken spammers over het algemeen &quot;onbekende&quot;IP adressen (adressen die nooit aan de lijst van afgewezen personen zijn toegevoegd) om het grootste mogelijke aantal berichten vóór opsporing te verzenden.

Je kunt niet verwachten dat je aan het begin van de productiefase een operationele snelheid bereikt in termen van productie. Bovendien zou u niet moeten proberen om berichten aan dit tarief te verzenden aangezien het ISPs zou kunnen leiden om de verzendende adressen te blokkeren en de rest van de aanloopfase ernstig te compromitteren.

Het beginnen van een platform gebeurt vaak wanneer het gebruiken van een lijst van adressen voor het eerst en die niet volledig gekwalificeerd kunnen zijn. Als u naar ongeldige adressen verzendt of naar honeypot-adressen, zal dit bijdragen aan het verminderen van de reputatie van het platform.
* Als u een lijst van ongeldige adressen hebt, is het in uw beste belang om het in de quarantainetabel (**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Quarantines]** > **[!UICONTROL Addresses]**) in te voeren alvorens voor het eerst te verzenden. Zie [deze sectie](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses-for-the-entire-platform) voor meer informatie.
* Als, allen het zelfde, u wenst om de ongeldige adressen opnieuw te kwalificeren, is het verreweg verkieslijk om dit te doen zodra de reputatie van het platform en beetje door beetje wordt gevestigd om het gebruik van slechte adressen in tijd &quot;te &quot;verwateren&quot;.

Een overzicht geven van de beginselen die bij het opstarten moeten worden gevolgd:
* **Vorm specifieke subdomain** om met Campagne te werken die voor e-mailcampagnes specifiek is die van Adobe worden verzonden.
* **Importeer ongeldige/inactieve adressen in de quarantainetabel** (als u deze informatie hebt).
* **Beperk het tarief van de leveringsproductie** (technische het plaatsen: beperking van het aantal tapijten).
* **De verzonden** volumes progressief verhogen: richt niet het volledige gegevensbestand vanaf zeer begin, maar voegt eerder een extra fractie van de lijst toe telkens als u verzendt. Dit zou u moeten toelaten om het volume bij elke stap te verhogen terwijl het verminderen van het algemene tarief van ongeldige adressen.
* **Verzend regelmatig** berichten: tot op zekere hoogte is het beter regelmatig kleine opnamen te sturen in plaats van sporadisch grote campagnes .
* **De leveringsrapporten** nauwlettend volgen: hoge foutenindicatoren kunnen betekenen een technische instelling slecht gevormd is.
