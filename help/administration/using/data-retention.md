---
title: Gegevensretentie
description: Meer informatie over de standaardwaarden voor behoud van standaardtabellen
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 01cfa2a0-4ff5-4520-a515-11676de82528
source-git-commit: 99c092bc40c9176a25a6ec2a164ee1d3f85d5cbe
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 4%

---

# Gegevensretentie{#data-retention}

>[!NOTE]
>
>Gegevensrapportage is alleen beschikbaar voor de laatste drie jaar. Neem voor meer informatie over bewaartermijnen contact op met Adobe-consultants of uw technische .

De standaard logboeklijsten in Campaign hebben vooraf ingestelde bewaartermijnen op hen die hun gegevensopslagduur beperken, om te vermijden overladend uw systeem.

De configuratie van het behoud van gegevens wordt geplaatst door de technische beheerders van de Adobe tijdens implementatie en de waarden kunnen voor elke implementatie variëren, die op klantenvereisten wordt gebaseerd.

Neem contact op met de consultants of technische Adoben voor meer informatie over bewaartermijnen die van toepassing zijn op uw omgeving, of voor het instellen van aangepaste bewaartermijnen.

Houd er rekening mee dat het met de standaardworkflowfunctionaliteit mogelijk is retentieperiodes in te stellen voor elke aangepaste tabel.

Hieronder vindt u de standaardretentieperioden voor standaardtabellen. Waar mogelijk, en afhankelijk van uw gegevensgebruik, adviseert de Adobe u om zich naar de geadviseerde bewaartermijnen te bewegen om prestaties van uw instantie van de Campagne te verbeteren.

* **Geconsolideerde het volgen**: 6 maanden (geadviseerd: 1 maand)
* **Logboeken van de Levering**: 6 maanden (geadviseerd: 1 maand)
* **het Volgen logboeken**: 6 maanden (geadviseerd: 1 maand)
* **Gebeurtenissen**: 1 maand
* **Statistieken van gebeurtenisverwerking**: 6 maanden (geadviseerd: 1 maand)
* **Gearchiveerde gebeurtenissen**: 6 maanden (geadviseerd: 1 maand)
* **Tijdelijke entiteiten**: 7 dagen
* **Genegeerde pipelinegebeurtenissen**: 1 maand
* **Leveringsmeldingen**: 1 maand
* **de controle van de Uitvoer**: 6 maanden (geadviseerd: 1 maand)

## Bewaartermijn voor leveringen {#deliveries}

Standaard is de retentieperiode voor leveringen onbeperkt.

Nochtans, als er een hoog volume van leveringen op uw instantie is, kunt u de **NmsCleanup_DeliveryPurgeDelay** optie beschikbaar bij **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** menu bijwerken.

Telkens wanneer de **[!UICONTROL Database cleanup]** -workflow wordt uitgevoerd, worden de leveringen die voldoen aan de voorwaarden voor deze optie verwijderd.

Deze actie kan ertoe bijdragen processen zoals het **[!UICONTROL Copy headers from delivery templates]** werkschema te versnellen.

>[!NOTE]
>
>Leer meer op technische werkschema&#39;s in [ deze sectie ](technical-workflows.md).


De standaardwaarde voor **NmsCleanup_DeliveryPurgeDelay** optie is `-1`. In dit geval wordt geen levering verwijderd.

Als u bijvoorbeeld instelt op `180` , worden alle niet-sjabloonleveringen die de laatste 180 dagen niet zijn bijgewerkt, verwijderd wanneer de **[!UICONTROL Database cleanup]** -workflow wordt uitgevoerd.

>[!NOTE]
>
>* Marketing- of transactiemalplaatjes voor levering worden niet verwijderd.
>
>* Voor terugkerende leveringen worden de onderliggende leveringen met een als maand of jaar vastgestelde aggregatieperiode niet verwijderd.

Wanneer het bijwerken van **NmsCleanup_DeliveryPurgeDelay** optie, wordt het geadviseerd om geleidelijk met veelvoudige herhalingen te werk te gaan. U kunt bijvoorbeeld beginnen door de waarde in te stellen op 300 dagen, vervolgens op 180 dagen, daarna op 120 dagen, enzovoort - zorg ervoor dat herhalingen ten minste twee dagen van elkaar verwijderd zijn. Anders kan de **[!UICONTROL Database cleanup]** -workflow veel langer duren vanwege een groot aantal te verwijderen leveringen.

