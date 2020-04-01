---
title: Werken met de Standaard van de Campagne en Dynamica 365 van Microsoft
description: Leer hoe te met de Norm van de Campagne en Dynamica 365 van Microsoft te werken
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 74cc176a1b93a7983629ccccb1fea00628241952

---


# Werken met de Standaard van de Campagne en Dynamica 365 van Microsoft

Activeer uw CRM-gegevens voor kanaalcommunicatie: Leer hoe te om contacten van de Dynamica 365 van Microsoft aan de Campagne van Adobe over te brengen, en de gegevens van campagneprestaties (verzendt, opent, klikt, en stuit) terug van de Campagne van Adobe aan de Dynamica 365 van Microsoft te delen.

>[!NOTE]
>
>De integratie van Microsoft Dynamics 365 / Adobe Campaign Standard biedt alleen ondersteuning voor de **verkoopapp** Microsoft Dynamics 365.

## Voordelen en gebruiksgevallen

### Beginselen

De integratie van de Campagne van Adobe en van de Dynamica 365 van Microsoft laat synchronisatie van alle beschikbare gegevens van het Contact in het systeem van CRM toe, die alle relevante gegevens van het Contact ter beschikking stellen voor campagneactiviteiten.

Omgekeerd, omdat profielen in Adobe Campaign communiceren met berichten, deze gegevens (bijvoorbeeld: verzendt, opent, klikt, en de grenzen) stromen automatisch in de Dynamiek 365 van Microsoft om de verslagen van het Contact met marketing activiteit eveneens te houden volledig.

De recentste versie van de integratie voegt ook steun voor douaneentiteiten toe, toelatend douaneentiteiten in Dynamiek 365 om aan overeenkomstige douaneentiteiten in Campagne worden gesynchroniseerd.

Deze integratie is ontworpen om drie hoofdgebruiksituaties te ondersteunen:

1. Het synchroniseren van Contacten van Dynamiek 365 aan Campagne zodat kunnen zij in marketing campagnes worden gericht
1. Het verzenden van e-mail marketing gebeurtenissen (verzendt, opent, klikt, stuit) van Campagne aan Dynamica 365 om aan verkoopbewaarplaats in de interface van de Dynamiek 365 te tonen
1. Het synchroniseren van douaneentiteiten van Dynamiek 365 aan Campagne zodat kunnen zij voor segmentatie en verpersoonlijking worden gebruikt

Bekijk [hier](https://helpx.adobe.com/campaign/kt/acs/using/acs-ms-dynamics-crm-connector-tutorial.html)de video van de 365-Campagne Standaard integratie.

### Belangrijkste voordelen

* Consistente communicatie tussen verkoop en marketing

De integratie van de Campagne van Adobe en van de Dynamica 365 van Microsoft verleent zowel systeemtoegang tot het inzicht van de klant als de geschiedenis van de e-mailmarketing die alle berichten aan de klant toestaat om het zelfde verenigbare overseinen te delen.

* Holistische mening van alle vooruitzichten en klantengegevens

Door de Campagne van Adobe met Dynamica 365 te integreren, is het mogelijk om e-mailmarketing geschiedenis op elke Contact van binnen het systeem van CRM te delen en toegang te hebben.

* Dynamiek 365 gegevens op om het even welk kanaal activeren

Als contactgegevens zijn gesynchroniseerd met Adobe Campaign, kunnen communicatie via elk online of offline kanaal worden verzonden met Campagne, zoals mobiele push, in-app, e-mail of direct mail. Ongeacht het voorkeurkanaal van elke Contactpersoon, heeft de Campagne u behandeld.

>[!CAUTION]
>
>Voor de synchronisatie van Contacten, beschouwt deze integratie Dynamiek 365 als bron van waarheid.  Om het even welke veranderingen in gesynchroniseerde contactattributen zouden in Dynamiek 365, niet in Campagne moeten worden gedaan.  Als er wijzigingen worden aangebracht in Campagne, kunnen deze tijdens de synchronisatie worden overschreven.

