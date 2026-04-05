---
title: Berichten bijhouden en controleren
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: true
description: Leer hoe u met Adobe Campaign de verzonden berichten kunt volgen en kunt ontdekken hoe de ontvangers op uw levering reageren
feature: Deliverability
role: User
level: Intermediate
exl-id: dd3bd672-fb9d-4e82-bdf3-d319f372baaa
source-git-commit: ac925ec5f59f1bb57b56b430fd175a27b08c3bfe
workflow-type: tm+mt
source-wordcount: '433'
ht-degree: 0%

---

# Track en monitor {#track-and-monitor}

Hebt u op de knop Verzenden geklikt? Laten we eens kijken wat er gebeurt. Zodra de levering wordt verzonden, laat Adobe Campaign u toe om spoor van de verzonden berichten te houden en te ontdekken hoe uw ontvangers op uw levering reageren. Op deze manier kunt u uw volgende campagnes beter verzenden en optimaliseren.

## Bewaking van leveringen {#monitoring-deliveries}

Om uw campagnes te controleren, moet u ervoor zorgen dat het bericht inderdaad aan uw ontvangers is geleverd.

**Uiteinden**

* U kunt de status van de berichten in de leveringslogboeken controleren.

* Adobe Campaign biedt een e-mailwaarschuwingssysteem waarmee meldingen worden verzonden om gebruikers op de hoogte te stellen van belangrijke systeemactiviteiten, zodat gebruikers kunnen controleren of de levering is gelukt of mislukt.

* Van het berichtdashboard, kunt u tot verscheidene rapporten voor dit specifieke bericht toegang hebben.

Voor meer dit, zie [ Controle een levering ](../../sending/using/monitoring-a-delivery.md).

## Tracking {#tracking-deliveries}

Als u beter wilt weten wat uw doelprofielen doen, kunt u bijhouden hoe zij op een levering reageren: ontvangst, openen, klikken op koppelingen, abonnementen enzovoort. Verwijs naar het **Volgen logboeken** lusje van de levering.

**Uiteinde**: Het volgen van het bericht wordt toegelaten door gebrek. Als u URL&#39;s wilt configureren, selecteert u de optie URL&#39;s weergeven in de onderste sectie van de wizard voor levering. Voor elke URL van het bericht kunt u kiezen of u reeksspatiëring wilt activeren.

Voor meer op dit, verwijs naar de [ het Volgen berichten ](../../sending/using/tracking-messages.md) sectie en [ het Volgen indicatoren ](../../reporting/using/tracking-indicators.md) beschrijving.

## Dynamische rapporten {#dyn-reports}

Met dynamische rapporten kunt u volledig aanpasbare en real-time rapporten maken om uw campagnes te controleren. Met afmetingen, meetgegevens en visualisaties kunt u de impact en het succes van uw campagnes op ontvangers meten.

**Tip** - de ingebouwde rapporten zijn beschikbaar voor u om uw campagnes te controleren maar deze rapporten kunnen ook worden aangepast door om het even welke metriek of dimensies aan uw rapport te slepen en te laten vallen.

Voor meer op dit, verwijs naar de [ Rapporterende gids ](../../reporting/using/about-dynamic-reports.md).

## Hot kliks

In het rapport Hot click wordt de berichtinhoud (HTML en/of tekst) weergegeven met het percentage klikken op elke koppeling. Door het percentage van klikken op elke dynamische inhoud weer te geven, kunt u meten welke inhoud het meest geschikt is voor de ontvangers.

Voor meer op dit, verwijs naar het [ Hete klik rapport ](../../reporting/using/hot-clicks.md).

## Tips voor prestaties van levering {#performance-tips}

* Bewaar de levering niet in mislukte staat, aangezien dit tijdelijke lijsten handhaaft en de prestaties beïnvloedt.

* Verwijder leveringen die niet meer nodig zijn en inactieve ontvangers uit de database om de adreskwaliteit te behouden.

* Probeer geen grote leveringen samen te plannen. Houd er rekening mee dat het 5 tot 10 minuten kan duren voordat de laadbewerking gelijkmatig over het systeem is verspreid.

**Verwante onderwerpen:**

* [Waarschuwingen ontvangen wanneer fouten optreden](../../sending/using/receiving-alerts-when-failures-happen.md)
* [Rapporten](../../reporting/using/about-dynamic-reports.md)
