---
title: Terug naar afzender
description: Leer hoe te om van een onjuist adres op de hoogte te worden gebracht en het van toekomstige mededelingen uit te sluiten.
page-status-flag: never-activated
uuid: 11981c2f-0b7f-4166-9daa-ec6a6b4d5367
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: direct-mail
discoiquuid: 5f20ff3f-8242-4735-8c60-c57610edff52
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 9c812b0b622b82ba7aa382f04edb7a2a3f717cd4
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 2%

---


# Terug naar afzender{#return-to-sender}

Platte bestandsuitwisselingen met Direct Mail-providers die informatie over terugsturen bevatten, worden ondersteund. Hierdoor kunnen de overeenkomstige postadressen van toekomstige mededelingen worden uitgesloten. Op deze manier kunt u ook op de hoogte worden gesteld van een onjuist adres en contact opnemen met de klant via andere kanalen of u kunt hem aanmoedigen zijn postadres bij te werken.

Een contactpersoon is bijvoorbeeld naar een nieuwe plaats verhuisd en heeft je geen nieuw postadres verschaft. De leverancier wint de lijst van onjuiste adressen terug en verzendt deze informatie naar Adobe Campaign die automatisch de onjuiste adressen toe_voegt op lijst van gewenste personen.

Opdat deze functionaliteit werkt, omvat het direct-mail standaardleveringsmalplaatje, in de inhoud, identiteitskaart van het leveringslogboek. Zo kan Adobe Campaign het profiel en de leveringsgegevens synchroniseren met de informatie die door de provider wordt geretourneerd.

![](assets/direct_mail_return_sender_1.png)

Een importsjabloon is beschikbaar onder **[!UICONTROL Adobe Campaign > Resources > Templates > Import templates > Update Direct Mail quarantines and delivery logs]**. Dupliceer deze sjabloon om uw eigen sjabloon te maken. Raadpleeg Importsjablonen [gebruiken voor meer informatie over het gebruik van importsjablonen](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates).

![](assets/direct_mail_return_sender_2.png)

Wanneer het importeren is voltooid, voert Adobe Campaign automatisch de volgende handelingen uit:

* Onjuiste adressen worden toegevoegd aan lijst van afgewezen personen op het profielniveau
* De belangrijkste leveringsindicatoren (KPI&#39;s) worden bijgewerkt
* De leveringslogs worden bijgewerkt
