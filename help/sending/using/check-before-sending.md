---
solution: Campaign Standard
product: campaign
title: Controleren vóór verzending
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
description: '"Als uw bericht klaar is, leert u hoe u alle controles kunt uitvoeren voordat u het verzendt"'
feature: Deliverability
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 15%

---


# Alle controles uitvoeren voordat {#perform-all-checks} wordt verzonden

Zodra uw bericht klaar is, zorg ervoor zijn inhoud correct, op alle apparaten wordt getoond, en bevat geen fouten zoals verkeerde verpersoonlijking of gebroken verbindingen.

Alvorens uw bericht te verzenden, zorg ook dat de parameters en de configuratie met de levering verenigbaar zijn.

## Waarom validatie belangrijk is {#validation-is-key}

Alvorens een levering te verzenden, moet u ervoor zorgen dat uw ontvangers het bericht zullen ontvangen dat u echt hen wilt verzenden. Hiervoor moet u de inhoud en de leveringsparameters van het bericht valideren.

Met deze stap kunt u mogelijke fouten detecteren en corrigeren voordat u deze aan uw hoofddoel kunt leveren.

De stappen voor het valideren van een levering worden [weergegeven in deze sectie](../../sending/using/get-started-sending-messages.md#prepare-test-send).

## E-mailweergave {#email-rendering}

Controleer of uw bericht optimaal wordt weergegeven op verschillende webclients, in webmails en op apparaten voordat u op de knop **[!UICONTROL Send]** drukt.

Om dit mogelijk te maken, legt Adobe Campaign de weergave vast en stelt deze beschikbaar in een specifiek rapport. Op deze manier kunt u het voorbeeld van het verzonden bericht bekijken in de verschillende contexten waarin het bericht mogelijk wordt ontvangen.

**Tips**:

* U kunt het verzonden bericht bekijken in de verschillende contexten waarin het kan worden ontvangen: webmail, berichtservice, mobiel, enz.

* Rendermogelijkheden via e-mail zijn van cruciaal belang om te bepalen of uw e-mailcampagnes erin slagen de filters van belangrijke ISP&#39;s (Internet Service Providers) en webmailservices te overschrijden. Dergelijke hulpmiddelen verzenden een pre-vlucht exemplaar van een e-mail naar een netwerk van testinboxes, zodat kunt u zien hoe het bericht, over deze diensten zal tonen of teruggeven. Ze kunnen ook rapporten en opties voor codecorrectie bevatten die u helpen snel oplossingen te vinden en te maken die de leesbaarheid verbeteren.

Meer informatie [in deze sectie](../../sending/using/email-rendering.md).

## Proefberichten {#proof-messages}

Door proefdrukken te verzenden, kunt u de koppeling om te weigeren controleren, de pagina spiegelen en andere koppelingen controleren, het bericht valideren, controleren of afbeeldingen worden weergegeven, mogelijke fouten opsporen, enz. Mogelijk wilt u ook uw ontwerp en rendering op verschillende apparaten controleren.

Meer informatie [in deze sectie](../../sending/using/sending-proofs.md).

## A/B-testleveringen instellen {#a-b-testing-deliveries}

Als u meerdere inhoud voor een e-maillevering hebt, kunt u A/B-tests gebruiken om na te gaan welke versie de grootste invloed heeft op de doelpopulatie.

**Tips**:

* Verschillende versies naar sommige ontvangers verzenden

* Selecteer het bestand met de hoogste successnelheid en stuur het naar de rest van het doel

Meer informatie [in deze sectie](../../channels/using/designing-an-a-b-test-email.md).

