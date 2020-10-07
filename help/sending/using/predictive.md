---
title: Voorspellingsmogelijkheden voor gebruikersbetrokkenheid
description: Leer hoe u voorspellende verzendtijd en betrokkenheidsscores kunt gebruiken.
page-status-flag: never-activated
uuid: c2c13934-9819-4e18-b5c7-60915c907f37
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: ai-powered-emails
discoiquuid: 609355f6-9003-41b9-9981-ea787419fbf5
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '1061'
ht-degree: 100%

---


# Ontwerp en levering optimaliseren met e-mails met AI-mogelijkheden{#journey-ai}

## Aan de slag met e-mails met AI-mogelijkheden{#journey-ai-ovv}

Met Campaign kunt u het ontwerp en de levering van klantjourneys optimaliseren om de betrokkenheidsvoorkeuren van elk individu te voorspellen. Adobe Campaign wordt aangestuurd door Journey AI en kan openingsfrequenties, optimale verzendtijden en waarschijnlijk verloop analyseren en voorspellen op basis van historische betrokkenheidscijfers.

**Modellen voor machine learning**

Adobe Campaign Standard biedt twee nieuwe modellen voor machine learning: **optimalisatie van voorspellende verzendtijd** en **voorspellende betrokkenheidsscores**. Deze twee modellen worden samen Journey AI genoemd, een type modellen voor machine learning die specifiek zijn voor het ontwerpen en leveren van betere klantjourneys.

* **Optimalisatie van voorspellende verzendtijd**: Met optimalisatie van voorspellende verzendtijd wordt voorspeld wat de beste verzendtijd is voor elk ontvangend profiel voor het openen van of klikken op e-mails. Voor elk ontvangend profiel geven de scores aan wat de beste verzendtijd is op elke weekdag en welke weekdag het geschiktst is voor verzending om de beste resultaten te bereiken.

* **Voorspellende betrokkenheidsscore**: Met de voorspellende betrokkenheidsscore wordt voorspeld hoe waarschijnlijk het is dat een ontvanger iets doet met een bericht evenals de kans dat de klant zich binnen 7 dagen na de volgende e-mailverzending afmeldt. De waarschijnlijkheden worden verder onderverdeeld in buckets op basis van het specifieke risico van terugtrekking, middelgroot of laag. Op deze manier geeft het model ook het risicopercentiel aan voor de klanten om te begrijpen welke positie een bepaalde klant inneemt ten opzichte van andere klanten.

>[!CAUTION]
>Deze mogelijkheid is niet rechtstreeks beschikbaar als onderdeel van het product. Voor de implementatie moet Adobe Consulting worden ingeschakeld. Neem contact op met uw Adobe-vertegenwoordiger voor meer informatie.
>
>De functie vereist het gebruik van een Azure-opslaglocatie die door de klant moet worden geleverd.

## Optimalisatie van voorspellende verzendtijd{#predictive-send-time}

### Klikken en openen optimaliseren{#about-predictive-send-time}

Optimalisatie van voorspellende verzendtijd voorspelt de beste verzendtijd voor elk ontvangend profiel voor het openen van en klikken op e-mail. Voor elk ontvangend profiel geven de scores aan wat de beste verzendtijd is op elke weekdag en welke weekdag het geschiktst is voor verzending om de beste resultaten te bereiken.

Binnen het model voor optimalisatie van voorspellende verzendtijd zijn er twee submodellen:
* De voorspelbare verzendtijd voor openen is de beste tijd om een bericht naar de klant te verzenden voor een maximale kans op openen.
* De voorspelbare verzendtijd voor klikken is de beste tijd om een bericht naar de klant te verzenden voor een maximale kans op klikken

**Modelinvoer**: leveringslogboeken, logbestanden bijhouden en profielkenmerken (niet-PII)

**Modeluitvoer**: beste tijd om een bericht te verzenden (voor openen en klikken)


Uitvoerdetails

* Bereken het beste tijdstip om een e-mail te verzenden voor de 7 dagen van de week met intervallen van 1 uur (bijvoorbeeld: 9:00 uur, 10:00 uur, 11:00 uur)
* Het model geeft de beste dag in de week en het beste tijdstip op die dag aan
* Elke optimale tijd wordt twee keer berekend: één keer om de openingsfrequentie te maximaliseren en één keer om de klikfrequentie te maximaliseren
* Er worden 16 velden weergegeven (14 voor weekdagen en 2 voor de hele week):
   * de beste verzendtijd voor een e-mail om klikken te optimaliseren op maandag - waarden tussen 0 en 23
   * de beste verzendtijd voor een e-mail om openen te optimaliseren op maandag - waarden tussen 0 en 23
   * de beste verzendtijd voor een e-mail om klikken te optimaliseren op dinsdag - waarden tussen 0 en 23
   * ...
   * de beste verzendtijd voor een e-mail om klikken te optimaliseren op zondag - waarden tussen 0 en 23
   * de beste verzendtijd voor een e-mail om openen te optimaliseren op zondag - waarden tussen 0 en 23
   * ...
   * de beste verzenddag voor een e-mail om openen te optimaliseren voor de hele week - van maandag tot en met zondag
   * de beste verzendtijd voor een e-mail om openen te optimaliseren voor de hele week - waarden tussen 0 en 23

>[!NOTE]
>
>Deze voorspellende mogelijkheden gelden alleen voor e-mailleveringen.
>
>Het model heeft minstens één maand aan data nodig om significante resultaten te produceren.


### Profielscores openen{#access-predictive-send-time-scores}

Zodra de mogelijkheden van machine learning zijn geïmplementeerd in Campaign, verrijken ze de profielgegevens met nieuwe tabbladen met de beste scores voor openen/klikken. De cijfers worden berekend door Journey AI en worden aan de hand van technische workflows naar Campaign overgezet.

Voor toegang tot deze cijfers moet u het volgende doen:

1. Open een profiel en klik op de knop Edit.

1. Klik op het tabblad **Send Time Score By Click** of **Send Time Score By Open**.

De profielscores geven standaard het beste tijdstip van de dag voor elke dag van de week aan, en het beste algemene tijdstip voor de hele week.

![](assets/do-not-localize/SendTimeScore.png)

### Berichten verzenden op het beste moment{#use-predictive-send-time}

Als u de e-mails wilt laten verzenden op het optimale tijdstip per profiel, moet de levering worden gepland met de optie **[!UICONTROL Send at a custom date defined by a formula]**.
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

Met voorspellende betrokkenheidsscore kunt u het volgende doen:

* **Een doelgroep selecteren**: met de queryactiviteit kunt u de doelgroep selecteren die u wilt aantrekken met een specifiek bericht
* **Een doelgroep uitsluiten**: met de queryactiviteit kunt u de doelgroep verwijderen voor afmelden
* **Personaliseren**: personaliseer berichten op basis van het betrokkenheidsniveau (sterk betrokken gebruikers krijgen een ander bericht dan niet-betrokken gebruikers)

Dit model gebruikt meerdere scores om het volgende aan te geven:

* **Betrokkenheidsscore voor openen/Betrokkenheidsscore voor klikken**: deze waarde geeft aan hoe waarschijnlijk het is dat een abonnee iets doet met een bepaald bericht (openen of klikken). Waarden kunnen variëren van 0,0 tot 1,0.
* **Waarschijnlijkheid van afmelding**: deze waarde geeft aan hoe waarschijnlijk het is dat de ontvanger zich voor het e-mailkanaal afmeldt op basis van één geopend bericht. Waarden kunnen variëren van 0,0 tot 1,0.
* **Retentieniveau**: met deze waarde worden gebruikers in drie niveaus ingedeeld: laag, gemiddeld en hoog. Bij een hoge waarde blijven gebruikers waarschijnlijk bij het merk, bij een lage waarde melden ze zich waarschijnlijk af.
* **Percentielwaarde voor retentie**: profielrangorde in termen van kans op afmelden. Waarden kunnen variëren van 0,0 tot 1,0. Als de percentielwaarde voor retentie bijvoorbeeld 0,953 is, is er meer kans dat deze ontvanger bij het merk blijft en minder kans dat deze zich afmeldt dan bij 95,3% van alle gebruikers.

>[!NOTE]
>
>Deze voorspellende mogelijkheden gelden alleen voor e-mailleveringen.
>
>Het model heeft minstens één maand aan data nodig om significante resultaten te produceren.


**Modelinvoer**: leveringslogboeken, trackinglogboeken en specifieke profielkenmerken

**Modeluitvoer**: een profielkenmerk dat de score en categorie van het profiel beschrijft


### De betrokkenheidsscore gebruiken voor het e-mailkanaal

Voor toegang tot deze cijfers moet u het volgende doen:

1. Open een profiel en klik op de knop Edit.

1. Klik op het tabblad **Engagement Scores for Email Channel**.

Door een queryactiviteit in een workflow op te nemen kunt u de score gebruiken om uw doelgroep te optimaliseren.

Een voorbeeld met de criteria voor **retentieniveau**:

![](assets/do-not-localize/predictive_score_query.png)























