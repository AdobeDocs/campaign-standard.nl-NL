---
solution: Campaign Standard
product: campaign
title: Berichten bijhouden en controleren
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
translation-type: tm+mt
source-git-commit: a7300666587362048431d0bafacc317170b317aa
workflow-type: tm+mt
source-wordcount: '410'
ht-degree: 3%

---


# Bijhouden en bewaken {#track-and-monitor}

Hebt u op de knop Verzenden geklikt? Laten we eens kijken wat er gebeurt. Zodra de levering wordt verzonden, laat Adobe Campaign u toe om spoor van de verzonden berichten te houden en te ontdekken hoe uw ontvangers op uw levering reageren. Op deze manier kunt u uw volgende campagnes beter verzenden en optimaliseren.

## Leveringen controleren{#monitoring-deliveries}

Om uw campagnes te controleren, moet u ervoor zorgen dat het bericht inderdaad aan uw ontvangers is geleverd.

**Tips**

* U kunt de status van de berichten in de leveringslogboeken controleren.

* Adobe Campaign biedt een e-mailwaarschuwingssysteem waarmee meldingen worden verzonden om gebruikers op de hoogte te stellen van belangrijke systeemactiviteiten, zodat gebruikers kunnen controleren of de levering is gelukt of mislukt.

* Van het berichtdashboard, kunt u tot verscheidene rapporten voor dit specifieke bericht toegang hebben.

Zie [Levering](../../sending/using/monitoring-a-delivery.md)controleren voor meer informatie.

## Tracking {#tracking-deliveries}

Om beter te weten wat het gedrag van uw doelprofielen is, kunt u bijhouden hoe zij op een levering reageren: ontvangen, openen, klikken op koppelingen, abonnementen enz. Raadpleeg het tabblad **Logboeken** bijhouden van de levering.

**Tip**: Berichten bijhouden is standaard ingeschakeld. Als u URL&#39;s wilt configureren, selecteert u de optie URL&#39;s weergeven in de onderste sectie van de wizard voor levering. Voor elke URL van het bericht kunt u kiezen of u reeksspatiëring wilt activeren.

Raadpleeg voor meer informatie de sectie [Tracking messages](../../sending/using/tracking-messages.md) en de beschrijving van de [trackingindicatoren](../../reporting/using/tracking-indicators.md) .

## Dynamische rapporten {#dyn-reports}

Met dynamische rapporten kunt u volledig aanpasbare en real-time rapporten maken om uw campagnes te controleren. Met Dimension, meetgegevens en visualisaties kunt u de impact en het succes van uw campagnes op ontvangers meten.

**Tip** - De ingebouwde rapporten zijn beschikbaar voor u om uw campagnes te controleren maar deze rapporten kunnen ook worden aangepast door om het even welke metriek of dimensies aan uw rapport te slepen en te laten vallen.

For more on this, refer to the [Reporting guide](../../reporting/using/about-dynamic-reports.md).

## Hot clicks

In het rapport Hot click wordt de berichtinhoud (HTML en/of tekst) weergegeven met het percentage klikken op elke koppeling. Door het percentage van klikken op elke dynamische inhoud weer te geven, kunt u meten welke inhoud het meest geschikt is voor de ontvangers.

Raadpleeg het rapport [Hot](../../reporting/using/hot-clicks.md)click voor meer informatie.

## Tips voor de prestaties van de levering {#performance-tips}

* Bewaar de levering niet in mislukte staat op het geval, aangezien dit tijdelijke lijsten handhaaft en de prestaties beïnvloedt.

* Verwijder leveringen die niet meer nodig zijn en inactieve ontvangers uit de database om de adreskwaliteit te behouden.

* Probeer geen grote leveringen samen te plannen. Houd er rekening mee dat het 5 tot 10 minuten kan duren voordat de laadbewerking gelijkmatig over het systeem is verspreid.

**Verwante onderwerpen:**

* [Waarschuwingen ontvangen wanneer fouten optreden](../../sending/using/receiving-alerts-when-failures-happen.md)
* [Rapporten](../../reporting/using/about-dynamic-reports.md)
