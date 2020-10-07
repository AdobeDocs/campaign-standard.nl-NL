---
title: Aan de slag met de integratie van Microsoft Dynamics 365
description: Leer hoe u aan de slag kunt met de integratie van Microsoft Dynamics 365
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 10%

---


# Aan de slag met de integratie van Microsoft Dynamics 365

Activeer uw CRM-gegevens voor kanaalcommunicatie: Leer hoe te om contacten van de Dynamiek 365 van Microsoft aan Adobe Campaign over te gaan, en gegevens van campagneprestaties (verzendt, opent, klikt, en stuitingen) terug van Adobe Campaign naar de Dynamica 365 van Microsoft te delen.

Ondersteunde versies worden weergegeven [in deze sectie](#support-software-versions).

>[!CAUTION]
>
>Deze mogelijkheid is niet rechtstreeks beschikbaar als onderdeel van het product. Voor de implementatie moet Adobe Consulting worden ingeschakeld. Neem contact op met uw Adobe-vertegenwoordiger voor meer informatie.

## Beginselen

De integratie van de Dynamica 365 van Adobe Campaign en van Microsoft laat synchronisatie van alle beschikbare contactgegevens in het systeem van CRM toe, die alle relevante contactgegevens ter beschikking stellen voor campagneactiviteiten.

Omgekeerd, aangezien de profielen binnen Adobe Campaign met berichten in wisselwerking staan, die gegevens (b.v.: verzendt, opent, klikt, en stuitingen) stromen automatisch in de Dynamiek 365 van Microsoft om contactverslagen te houden volledig met marketing activiteit eveneens.

De integratie steunt ook douaneentiteiten, toelatend [douaneentiteiten](../../integrating/using/map-campaign-custom-resources-and-dynamics-365-custom-entities.md) in Dynamiek 365 om aan overeenkomstige douaneentiteiten in Campagne worden gesynchroniseerd.

Deze integratie is bedoeld ter ondersteuning van vier belangrijke gebruiksgevallen:

1. Het synchroniseren van contacten van Dynamiek 365 aan Campagne zodat kunnen zij in marketing campagnes worden gericht
1. Het synchroniseren van douaneentiteiten van Dynamiek 365 aan Campagne zodat kunnen zij voor segmentatie en verpersoonlijking worden gebruikt
1. Het verzenden van e-mail marketing gebeurtenissen (verzendt, opent, klikt, stuit) van Campagne aan Dynamica 365 om aan verkoopbewaarplaats in de interface van de Dynamiek 365 te tonen
1. Synchronizing opt-out (bijv., niet e-mail) status tussen Dynamics 365 en ACS om de voorkeur van de klantenprivacy te handhaven.

## Belangrijkste voordelen

* Consistente communicatie tussen verkoop en marketing

De integratie van de Dynamica 365 van Adobe Campaign en van Microsoft geeft zowel systeemtoegang tot klanteninzicht als e-mailmarketing geschiedenis die alle berichten aan de klant toestaan om het zelfde verenigbare overseinen te delen.

* Holistische mening van alle vooruitzichten en klantengegevens

Door Adobe Campaign met Dynamics 365 te integreren, is het mogelijk om e-mailmarketing geschiedenis op elk contact van binnen het systeem van CRM te delen en toegang te hebben.

* Dynamiek 365 gegevens op om het even welk kanaal activeren

Als contactgegevens zijn gesynchroniseerd met Adobe Campaign, kunnen communicatie via elk online of offline kanaal worden verzonden met Campagne, zoals mobiele push, in-app, e-mail of direct mail. Ongeacht het voorkeurkanaal van elke contactpersoon, heeft de Campagne u behandeld.

>[!CAUTION]
>
>Voor contact en de synchronisatie van de douaneentiteit, beschouwt deze integratie Dynamiek 365 als bron van waarheid.  Om het even welke veranderingen in gesynchroniseerde attributen zouden in Dynamiek 365, niet in Campagne moeten worden gedaan.  Als er wijzigingen worden aangebracht in Campagne, kunnen deze tijdens de synchronisatie worden overschreven.

## Softwareversies ondersteunen {#support-software-versions}

Voor deze integratie zijn de volgende softwareversies vereist:

* Microsoft Dynamics 365 for Sales Online, nieuwste versie

* Adobe Campaign Standard, nieuwste versie
