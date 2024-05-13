---
title: Gegevensretentie
description: Meer informatie over de standaardwaarden voor behoud van standaardtabellen
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 01cfa2a0-4ff5-4520-a515-11676de82528
source-git-commit: 2e81a05b1b647991250d13d7d37f5da275a8db44
workflow-type: tm+mt
source-wordcount: '395'
ht-degree: 5%

---

# Gegevensretentie{#data-retention}

De standaard logboeklijsten in Campaign hebben vooraf ingestelde bewaartermijnen op hen die hun gegevensopslagduur beperken, om te vermijden overladend uw systeem.

De configuratie van het behoud van gegevens wordt geplaatst door de technische beheerders van de Adobe tijdens implementatie en de waarden kunnen voor elke implementatie variëren, die op klantenvereisten wordt gebaseerd.

Neem contact op met de consultants of technische Adoben voor meer informatie over bewaartermijnen die van toepassing zijn op uw omgeving, of voor het instellen van aangepaste bewaartermijnen.

Houd er rekening mee dat het met de standaardworkflowfunctionaliteit mogelijk is retentieperiodes in te stellen voor elke aangepaste tabel.

Hieronder vindt u de standaardretentieperioden voor standaardtabellen. Waar mogelijk, en afhankelijk van uw gegevensgebruik, adviseert de Adobe u om zich naar de geadviseerde bewaartermijnen te bewegen om prestaties van uw instantie van de Campagne te verbeteren.

* **Geconsolideerde tracering**: 6 maanden (aanbevolen: 1 maand)
* **Leveringslogboeken**: 6 maanden (aanbevolen: 1 maand)
* **Logboeken bijhouden**: 6 maanden (aanbevolen: 1 maand)
* **Gebeurtenissen**: 1 maand
* **Statistieken van gebeurtenisverwerking**: 6 maanden (aanbevolen: 1 maand)
* **Gearchiveerde gebeurtenissen**: 6 maanden (aanbevolen: 1 maand)
* **Tijdelijke entiteiten**: 7 dagen
* **Genegeerde pipelinegebeurtenissen**: 1 maand
* **Leveringsmeldingen**: 1 maand
* **Exportcontrole**: 6 maanden (aanbevolen: 1 maand)

## Bewaartermijn voor leveringen {#deliveries}

Standaard is de retentieperiode voor leveringen onbeperkt.

Als er echter een hoog volume aan leveringen op uw exemplaar is, kunt u de **NmsCleanup_DeliveryPurgeDelay** beschikbaar via de **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** -menu.

Elke keer als **[!UICONTROL Database cleanup]** Wanneer de workflow wordt uitgevoerd, worden de leveringen die voldoen aan de voor deze optie ingestelde voorwaarden verwijderd.

Deze actie kan ertoe bijdragen processen zoals **[!UICONTROL Copy headers from delivery templates]** workflow.

>[!NOTE]
>
>Meer informatie over technische workflows vindt u in [deze sectie](technical-workflows.md).


De standaardwaarde voor de **NmsCleanup_DeliveryPurgeDelay** optie is `-1`. In dit geval wordt geen levering verwijderd.

Als u bijvoorbeeld instelt op `180`worden alle niet-sjabloonleveringen die de afgelopen 180 dagen niet zijn bijgewerkt, verwijderd wanneer de **[!UICONTROL Database cleanup]** workflow wordt uitgevoerd.

>[!NOTE]
>
>* Marketing- of transactiemalplaatjes voor levering worden niet verwijderd.
>
>* Voor terugkerende leveringen worden de onderliggende leveringen met een als maand of jaar vastgestelde aggregatieperiode niet verwijderd.

Wanneer u het dialoogvenster **NmsCleanup_DeliveryPurgeDelay** aanbevolen wordt geleidelijk meerdere herhalingen uit te voeren. U kunt bijvoorbeeld beginnen door de waarde in te stellen op 300 dagen, vervolgens op 180 dagen, daarna op 120 dagen, enzovoort - zorg ervoor dat herhalingen ten minste twee dagen van elkaar verwijderd zijn. Anders wordt de **[!UICONTROL Database cleanup]** de workflow kan veel langer duren vanwege een groot aantal te verwijderen leveringen.

