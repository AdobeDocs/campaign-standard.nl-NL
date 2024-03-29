---
title: Berichten bijhouden en controleren
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
description: Leer hoe u met Adobe Campaign de verzonden berichten kunt volgen en kunt ontdekken hoe de ontvangers op uw levering reageren
feature: Deliverability
role: User
level: Intermediate
exl-id: dd3bd672-fb9d-4e82-bdf3-d319f372baaa
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '433'
ht-degree: 3%

---

# Track en monitor {#track-and-monitor}

Hebt u op de knop Verzenden geklikt? Laten we eens kijken wat er gebeurt. Zodra de levering wordt verzonden, laat Adobe Campaign u toe om spoor van de verzonden berichten te houden en te ontdekken hoe uw ontvangers op uw levering reageren. Op deze manier kunt u uw volgende campagnes beter verzenden en optimaliseren.

## Bewaking van leveringen {#monitoring-deliveries}

Om uw campagnes te controleren, moet u ervoor zorgen dat het bericht inderdaad aan uw ontvangers is geleverd.

**Tips**

* U kunt de status van de berichten in de leveringslogboeken controleren.

* Adobe Campaign biedt een e-mailwaarschuwingssysteem waarmee meldingen worden verzonden om gebruikers op de hoogte te stellen van belangrijke systeemactiviteiten, zodat gebruikers kunnen controleren of de levering is gelukt of mislukt.

* Van het berichtdashboard, kunt u tot verscheidene rapporten voor dit specifieke bericht toegang hebben.

Zie voor meer informatie [Toezicht op de levering](../../sending/using/monitoring-a-delivery.md).

## Tracking {#tracking-deliveries}

Als u beter wilt weten wat uw doelprofielen doen, kunt u bijhouden hoe zij op een levering reageren: ontvangst, openen, klikken op koppelingen, abonnementen enzovoort. Zie de **Logboeken bijhouden** tabblad van de levering.

**Tip**: Het bijhouden van berichten is standaard ingeschakeld. Als u URL&#39;s wilt configureren, selecteert u de optie URL&#39;s weergeven in de onderste sectie van de wizard voor levering. Voor elke URL van het bericht kunt u kiezen of u reeksspatiëring wilt activeren.

Raadpleeg voor meer informatie de [Berichten bijhouden](../../sending/using/tracking-messages.md) en de [Traceringsindicatoren](../../reporting/using/tracking-indicators.md) beschrijving.

## Dynamische rapporten {#dyn-reports}

Met dynamische rapporten kunt u volledig aanpasbare en real-time rapporten maken om uw campagnes te controleren. Met Dimensionen, meetgegevens en visualisaties kunt u de impact en het succes van uw campagnes op ontvangers meten.

**Tip** - Ingebouwde rapporten zijn beschikbaar voor u om uw campagnes te controleren maar deze rapporten kunnen ook worden aangepast door om het even welke metriek of dimensies aan uw rapport te slepen en te laten vallen.

Raadpleeg voor meer informatie de [Rapportagehandleiding](../../reporting/using/about-dynamic-reports.md).

## Hot clicks

In het rapport Hot click wordt de berichtinhoud (HTML en/of tekst) weergegeven met het percentage klikken op elke koppeling. Door het percentage van klikken op elke dynamische inhoud weer te geven, kunt u meten welke inhoud het meest geschikt is voor de ontvangers.

Raadpleeg voor meer informatie de [Rapport Hot click](../../reporting/using/hot-clicks.md).

## Tips voor prestaties van levering {#performance-tips}

* Bewaar de levering niet in mislukte staat, aangezien dit tijdelijke lijsten handhaaft en de prestaties beïnvloedt.

* Verwijder leveringen die niet meer nodig zijn en inactieve ontvangers uit de database om de adreskwaliteit te behouden.

* Probeer geen grote leveringen samen te plannen. Houd er rekening mee dat het 5 tot 10 minuten kan duren voordat de laadbewerking gelijkmatig over het systeem is verspreid.

**Verwante onderwerpen:**

* [Waarschuwingen ontvangen wanneer fouten optreden](../../sending/using/receiving-alerts-when-failures-happen.md)
* [Rapporten](../../reporting/using/about-dynamic-reports.md)
