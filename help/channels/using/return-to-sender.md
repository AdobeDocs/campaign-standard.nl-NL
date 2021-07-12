---
solution: Campaign Standard
product: campaign
title: Terug naar afzender
description: Leer hoe te om van een onjuist adres op de hoogte te worden gebracht en het van toekomstige mededelingen uit te sluiten.
audience: channels
content-type: reference
topic-tags: direct-mail
feature: Direct mail
role: User
level: Intermediate
exl-id: 6783aa68-7fd7-4f53-86bf-853c0fea5899
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 3%

---

# Terug naar afzender{#return-to-sender}

Platte bestandsuitwisselingen met Direct Mail-providers die informatie over terugsturen bevatten, worden ondersteund. Hierdoor kunnen de overeenkomstige postadressen van toekomstige mededelingen worden uitgesloten. Op deze manier kunt u ook op de hoogte worden gesteld van een onjuist adres en contact opnemen met de klant via andere kanalen of u kunt hem aanmoedigen zijn postadres bij te werken.

Een contactpersoon is bijvoorbeeld naar een nieuwe plaats verhuisd en heeft je geen nieuw postadres verschaft. De leverancier wint de lijst van onjuiste adressen terug en verzendt deze informatie naar Adobe Campaign die automatisch de onjuiste adressen voegt op lijst van gewenste personen.

Opdat deze functionaliteit werkt, omvat het direct-mail standaardleveringsmalplaatje, in de inhoud, identiteitskaart van het leveringslogboek. Zo kan Adobe Campaign het profiel en de leveringsgegevens synchroniseren met de informatie die door de provider wordt geretourneerd.

![](assets/direct_mail_return_sender_1.png)

Een importsjabloon is beschikbaar onder **[!UICONTROL Adobe Campaign > Resources > Templates > Import templates > Update Direct Mail quarantines and delivery logs]**. Dupliceer deze sjabloon om uw eigen sjabloon te maken. Raadpleeg [Importsjablonen gebruiken](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates) voor meer informatie over het gebruik van importsjablonen.

![](assets/direct_mail_return_sender_2.png)

Wanneer het importeren is voltooid, voert Adobe Campaign automatisch de volgende handelingen uit:

* Onjuiste adressen worden toegevoegd aan lijst van gewezen personen op het profielniveau
* De belangrijkste leveringsindicatoren (KPI&#39;s) worden bijgewerkt
* De leveringslogs worden bijgewerkt
