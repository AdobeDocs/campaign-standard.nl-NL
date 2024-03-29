---
title: Voorspellingsmogelijkheden voor gebruikersbetrokkenheid
description: Leer hoe u voorspellende verzendtijd en betrokkenheidsscores kunt gebruiken.
audience: sending
content-type: reference
topic-tags: ai-powered-emails
feature: Send Time Optimization
role: User
level: Intermediate
exl-id: e1cb04e6-eb38-4bcc-b071-321cc11ccc7e
source-git-commit: 75628ed8a2f9b21def23e5b257a3592e1a721536
workflow-type: tm+mt
source-wordcount: '1103'
ht-degree: 47%

---

# Voorspellingsmogelijkheden voor gebruikersbetrokkenheid {#journey-ai}

Met Campaign kunt u het ontwerp en de levering van klantjourneys optimaliseren om de betrokkenheidsvoorkeuren van elk individu te voorspellen. Dankzij AI en computerleren kunnen de Send-Time Optimization en de Predictive Engagement Scoring van Adobe Campaign open tarieven, optimale verzendtijden en waarschijnlijke prijs analyseren en voorspellen op basis van historische betrokkenheidsmetriek.

>[!IMPORTANT]
>
>Deze mogelijkheid is niet rechtstreeks beschikbaar als onderdeel van het product. Voor de implementatie moet Adobe Consulting worden ingeschakeld. Neem contact op met uw Adobe-vertegenwoordiger voor meer informatie.

Adobe Campaign biedt twee nieuwe modellen voor het leren van machines: **Optimalisatie van de verzendtijd** en **Progressieve scores voor betrokkenheid**. Deze twee modellen zijn machine-leert modellen die specifiek voor het ontwerpen en het leveren van betere klantenreizen zijn.

* **Optimalisatie van verzendtijd** Hiermee kunt u voorspellen welke de beste verzendtijd is voor elk ontvangend profiel voor e-mail wordt geopend of klikt en voor het openen van een pushbericht. Voor elk ontvangend profiel geven de scores aan wat de beste verzendtijd is op elke weekdag en welke weekdag het geschiktst is voor verzending om de beste resultaten te bereiken.

* **Predictieve betrokkenheidsscoring**: voorspelt de waarschijnlijkheid dat een ontvanger een bericht in dienst neemt evenals de waarschijnlijkheid om uit (het afmelden) te kiezen binnen de volgende 7 dagen na de volgende e-mail verzendt. De waarschijnlijkheid wordt verder verdeeld in emmers volgens het voorspelde niveau van betrokkenheid bij uw inhoud: hoog, gemiddeld of laag. Deze modellen bieden de klanten ook de percentiele positie van het niet-abonnementsrisico om te begrijpen waar de rang van een bepaalde klant ten opzichte van anderen is.

## Voorspellende optimalisatie van verzendtijd{#predictive-send-time}

De voorspellende voorspellingen van de Optimalisatie van de Send-Time die de beste verzendtijd voor elk ontvangend profiel voor e-mail opent of klikt en voor push-message opent. Voor elk ontvangend profiel geven de scores aan wat de beste verzendtijd is op elke weekdag en welke weekdag het geschiktst is voor verzending om de beste resultaten te bereiken.

Binnen het Predictive Send-Time Optimization model, zijn er twee submodellen:

* **Voorspeltijd voor open verzending** is de beste tijd een mededeling naar de klant moet worden verzonden om te maximaliseren opent

* **Tijdstip van voorspelbare verzending voor klikken** is de beste tijd een mededeling naar de klant moet worden verzonden om kliks te maximaliseren

**Modelinvoer**: leveringslogboeken, logbestanden bijhouden en profielkenmerken (niet-PII)

**Modeluitvoer**: beste tijd om een bericht te verzenden (voor openen en klikken)

Uitvoerdetails

* Berekent de beste tijd van de dag om een e-mail voor in de 7 dagen van de week met tussenpozen van 1 uur te verzenden (bijvoorbeeld: 9:00 uur, 10:00 uur, 11:00 uur)
* Het model geeft de beste dag in de week en het beste tijdstip op die dag aan
* Elke optimale tijd wordt twee keer berekend: één keer om de openingsfrequentie te maximaliseren en één keer om de klikfrequentie te maximaliseren
* Er worden 16 velden weergegeven (14 voor weekdagen en 2 voor de hele week):

* Beste tijd om een e-mail te verzenden om kliks voor Maandag te optimaliseren - waarden tussen 0 en 23

* De beste tijd voor het verzenden van een e-mail voor optimalisatie wordt geopend voor maandag - waarden tussen 0 en 23
* ...
* Beste tijd om een e-mail te verzenden om kliks voor Zondag te optimaliseren - waarden tussen 0 en 23
* De beste tijd voor het verzenden van een e-mail voor optimalisatie wordt geopend voor zondag - waarden tussen 0 en 23
* ...
* De beste dag om een e-mail voor optimalisatie te verzenden wordt geopend voor de hele week - van maandag tot en met zondag
* De beste tijd voor het verzenden van een e-mail voor optimalisatie wordt geopend voor de hele week - waarden tussen 0 en 23

>[!NOTE]
>
>Het model heeft minstens één maand aan data nodig om significante resultaten te produceren.
>
>Deze voorspellende mogelijkheden zijn alleen van toepassing op e-mail- en pushkanalen.

Zodra de mogelijkheden van machine learning zijn geïmplementeerd in Campaign, verrijken ze de profielgegevens met nieuwe tabbladen met de beste scores voor openen/klikken. De metriek worden berekend en in Campagne gebracht gebruikend technische werkschema&#39;s.

Voor toegang tot deze cijfers moet u het volgende doen:

1. Open een profiel en klik op de knop Edit.

1. Klik op het tabblad **Send Time Score By Click** of **Send Time Score By Open**.

De profielscores geven standaard het beste tijdstip van de dag voor elke dag van de week aan, en het beste algemene tijdstip voor de hele week.

![](assets/do-not-localize/SendTimeScore.png)

### Berichten verzenden op het beste moment{#use-predictive-send-time}

De e-mails kunnen alleen worden verzonden op het optimale tijdstip per profiel als de levering is gepland met de optie **[!UICONTROL Send at a custom date defined by a formula]**.

Leer [in deze sectie](../../sending/using/computing-the-sending-date.md) hoe u de verzenddatum berekent.

De formule moet worden ingevuld met het specifieke beste tijdstip van de specifieke dag waarop de levering de deur uitgaat.

![](assets/do-not-localize/ComputeSendingDate.png)

Voorbeeld van de formule:

```
AddHours([currentDelivery/scheduling/@contactDate],
[cusSendTimeScoreByClickprofile_link/@EMAIL_BEST_TIME_TO_CLICK_WEDNESDAY])
```

![](assets/do-not-localize/SendingDateFormula.png)

>[!NOTE]
>
>Het datamodel kan verschillen, afhankelijk van uw implementatie.

## Voorspellende betrokkenheidsscore {#predictive-scoring}

Met voorspellende scores voor betrokkenheid voorspelt u de waarschijnlijkheid dat een ontvanger een bericht zal ontvangen en de kans dat hij of zij het abonnement zal opzeggen (zal opzeggen) binnen de volgende 7 dagen na het volgende e-mailbericht.

De waarschijnlijkheid wordt verder verdeeld in emmers volgens het voorspelde niveau van betrokkenheid bij uw inhoud: hoog, gemiddeld of laag. Deze modellen bieden de klanten ook de percentiele positie van het niet-abonnementsrisico om te begrijpen waar de rang van een bepaalde klant ten opzichte van anderen is.

Met voorspellende scores voor betrokkenheid kunt u:

* **Een publiek selecteren**: door vraagactiviteit te gebruiken, kunt u het publiek selecteren om met een specifiek bericht in dienst te nemen
* **Een publiek uitsluiten**: door vraagactiviteit te gebruiken, kunt u het publiek verwijderen dat waarschijnlijker is om af te melden
* **Persoonlijk maken**: personaliseer berichten op basis van het betrokkenheidsniveau (zeer betrokken gebruikers krijgen een andere boodschap dan niet-betrokken gebruikers)

Dit model gebruikt meerdere scores om het volgende aan te geven:

* **Betrokkenheidsscore voor openen/Betrokkenheidsscore voor klikken**: deze waarde geeft aan hoe waarschijnlijk het is dat een abonnee iets doet met een bepaald bericht (openen of klikken). Waarden kunnen variëren van 0,0 tot 1,0.
* **Waarschijnlijkheid van afmelding**: deze waarde geeft aan hoe waarschijnlijk het is dat de ontvanger zich voor het e-mailkanaal afmeldt op basis van één geopend bericht. Waarden kunnen variëren van 0,0 tot 1,0.
* **Retentieniveau**: deze waarde rangschikt gebruikers in drie niveaus: laag, gemiddeld en hoog. Bij een hoge waarde blijven gebruikers waarschijnlijk bij het merk, bij een lage waarde melden ze zich waarschijnlijk af.
* **Percentielwaarde voor retentie**: profielrangorde in termen van kans op afmelden. Waarden kunnen variëren van 0,0 tot 1,0. Als de percentielwaarde voor retentie bijvoorbeeld 0,953 is, is er meer kans dat deze ontvanger bij het merk blijft en minder kans dat deze zich afmeldt dan bij 95,3% van alle gebruikers.

>[!NOTE]
>
>Deze voorspellende mogelijkheden gelden alleen voor e-mailleveringen.
>
>Het model heeft minstens één maand aan data nodig om significante resultaten te produceren.

**Modelinvoer**: leveringslogboeken, trackinglogboeken en specifieke profielkenmerken

**Modeluitvoer**: een profielkenmerk dat de score en categorie van het profiel beschrijft

Voor toegang tot deze cijfers moet u het volgende doen:

1. Open een profiel en klik op de knop Edit.

1. Klik op het tabblad **Engagement Scores for Email Channel**.

Door een vraagactiviteit in een werkschema te gebruiken, kunt u de score gebruiken om uw publiek te optimaliseren. Een voorbeeld met de criteria voor **retentieniveau**:

![](assets/do-not-localize/predictive_score_query.png)