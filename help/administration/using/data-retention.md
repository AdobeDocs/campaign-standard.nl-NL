---
title: Gegevensretentie
description: Meer informatie over de standaardwaarden voor behoud van standaardtabellen
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 01cfa2a0-4ff5-4520-a515-11676de82528
source-git-commit: bd4b6d0d7d8fae6b14a41dc9001027d8154c9222
workflow-type: tm+mt
source-wordcount: '353'
ht-degree: 5%

---

# Gegevensretentie{#data-retention}

>[!NOTE]
>
>Gegevensrapportage is alleen beschikbaar voor de laatste drie jaar. Neem voor meer informatie over de bewaartermijnen voor gegevens contact op met Adobe-consultants of uw technische beheerders.

De standaard logboeklijsten in Campaign hebben vooraf ingestelde bewaartermijnen op hen die hun gegevensopslagduur beperken, om te vermijden overladend uw systeem.

De configuratie van het behoud van gegevens wordt geplaatst door de technische beheerders van Adobe tijdens implementatie en de waarden kunnen voor elke implementatie variëren, die op klantenvereisten wordt gebaseerd.

Neem contact op met de Adobe-consultants of technische beheerders voor meer informatie over bewaartermijnen die van toepassing zijn op uw omgeving, of voor het instellen van aangepaste bewaartermijnen.

Houd er rekening mee dat het met de standaardworkflowfunctionaliteit mogelijk is retentieperiodes in te stellen voor elke aangepaste tabel.

Hieronder vindt u de standaardretentieperioden voor standaardtabellen. Waar mogelijk, en afhankelijk van uw gegevensgebruik, stelt Adobe u voor om naar de geadviseerde bewaartermijnen te bewegen om prestaties van uw instantie van de Campagne te verbeteren.

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
* **Leveringen**: 2 jaar

## Bewaartermijn voor leveringen {#deliveries}

<!-- By default, the retention period for deliveries is unlimited.-->

Vanaf 1 juni 2025 blijven alleen leveringen van de afgelopen twee jaar beschikbaar in het systeem. Hieronder vindt u meer informatie:

* Leveringen ouder dan twee jaar worden definitief verwijderd en niet langer toegankelijk.
* Deze opschoning omvat alleen verzonden en mislukte leveringen; terugkerende leveringen, conceptleveringen en sjablonen worden niet beïnvloed.
* Wanneer een levering is verwijderd, worden gekoppelde tracerings- of verzendgegevens ook permanent verwijderd.
* Marketing- of transactiemalplaatjes voor levering worden niet verwijderd.
* Voor terugkerende leveringen worden de onderliggende leveringen met een als maand of jaar vastgestelde aggregatieperiode niet verwijderd.

Als u processen zoals de **[!UICONTROL Copy headers from delivery templates]** -workflow wilt versnellen, kan de retentieperiode van de levering worden verkort. Neem hiervoor contact op met uw Adobe-vertegenwoordiger.

<!--

However, if there is a high volume of deliveries on your instance, you can update the **NmsCleanup_DeliveryPurgeDelay** option available from the **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** menu.

Each time the **[!UICONTROL Database cleanup]** workflow is run, the deliveries meeting the conditions set for this option will be deleted.

-->

<!--

When updating the **NmsCleanup_DeliveryPurgeDelay** option, it is recommended to proceed gradually with multiple iterations. For example, you can start by setting the value to 300 days, then 180 days, then 120 days, and so on - making sure iterations are at least 2 days apart. Otherwise, the **[!UICONTROL Database cleanup]** workflow may take much longer because of a large number of deliveries to delete.

This action can help speeding up processes such as the **[!UICONTROL Copy headers from delivery templates]** workflow. Learn more on technical workflows in [this section](technical-workflows.md).

The default value for the **NmsCleanup_DeliveryPurgeDelay** option is `-1`. In this case, no delivery is deleted.

For example, if you set it to `180`, any non-template deliveries that have not been updated in the last 180 days will be deleted when the **[!UICONTROL Database cleanup]** workflow is run.

-->


