---
title: Een nieuw platform starten met Adobe Campagne Standard
description: Leer hoe u een nieuw platform instelt met behoud van uw domein- en IP-adresreputatie met Adobe Campagne Standard.
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
source-git-commit: 89965d859986b9176de6b6bf96df1fbbb89b5b8f

---


# Een nieuw platform starten{#starting-new-platform}

Het handhaven van uw domein en IP adresreputatie is essentieel. Hier volgt een advies voor het opzetten van een nieuw platform.

Het beginnen om e-mails op een nieuw platform te verzenden is een gevoelige stap omdat het platform geen geschiedenis van gebruik en geen reputatie heeft (wanneer de verzendende IPs nooit voor dit doel zijn gebruikt). ISPs is natuurlijk verdacht van IP adressen die nooit zijn gebruikt om e-mail te verzenden en die plotseling beginnen grote volumes van e-mailverkeer te verzenden. In feite, gebruiken spammers over het algemeen &quot;onbekende&quot;IP adressen (d.w.z. adressen die nooit op de zwarte lijst zijn gezet) om het grootste mogelijke aantal berichten vóór opsporing te verzenden.

Je kunt niet verwachten dat je aan het begin van de productiefase een operationele snelheid bereikt in termen van productie. Bovendien zou u niet moeten proberen om berichten aan dit tarief te verzenden aangezien het ISPs zou kunnen leiden om de verzendende adressen te blokkeren en de rest van de aanloopfase ernstig te compromitteren.

Het beginnen van een platform gebeurt vaak wanneer het gebruiken van een lijst van adressen voor het eerst en die niet volledig gekwalificeerd kunnen zijn. Als u naar ongeldige adressen verzendt of naar honeypot-adressen, zal dit bijdragen aan het verminderen van de reputatie van het platform. Als u een lijst van ongeldige adressen hebt, is het in uw beste belang om het in de quarantainetabel (**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Quarantines]** > **[!UICONTROL Addresses]**) in te voeren alvorens voor het eerst te verzenden. Als, allen het zelfde, u wenst om de ongeldige adressen opnieuw te kwalificeren, is het verreweg verkieslijk om dit te doen zodra de reputatie van het platform en beetje door beetje wordt gevestigd om het gebruik van slechte adressen in tijd &quot;te &quot;verwateren&quot;.

Een overzicht geven van de beginselen die bij het opstarten moeten worden gevolgd:
* **Een specifiek subdomein** delegeren aan Adobe dat specifiek is voor e-mailcampagnes die van Adobe worden verzonden
* **Ongeldige/inactieve adressen importeren in de quarantainetabel** (als u deze informatie hebt)
* **Beperk het tarief van de leveringsproductie** (technische het plaatsen: beperking van het aantal tapijten)
* **De verzonden** volumes progressief verhogen: niet de gehele database vanaf het begin als doel instellen, maar telkens wanneer u de gegevens verzendt, een extra gedeelte van de lijst toevoegen; dit zou u moeten toelaten om het volume bij elke stap te verhogen terwijl het verminderen van het algemene tarief van ongeldige adressen
* **Verzend regelmatig** berichten: In zekere zin is het beter om regelmatig kleine opnamen te sturen in plaats van sporadisch grote campagnes
* **De leveringsrapporten** nauwlettend volgen: hoge foutenindicatoren kunnen betekenen een technische instelling slecht gevormd is.
