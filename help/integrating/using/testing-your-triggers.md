---
title: Uw triggers testen
description: Leer tips voor het oplossen van problemen waarmee u de meest voorkomende problemen kunt oplossen die u tegenkomt bij het gebruik van Triggers met Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
feature: Triggers
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 66628f2a-6ed3-4b12-b2ed-9b9eec440dc3
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 1%

---

# Uw triggers testen{#testing-your-triggers}

De volgende tips voor het oplossen van problemen helpen u de meest voorkomende problemen op te lossen die u kunt tegenkomen bij het gebruik van Triggers met Adobe Campaign:

**wordt de functionaliteit geactiveerd?**

Als u wilt controleren of de integratie Triggers - campagne is geactiveerd, klikt u op het Adobe Campaign-logo in de linkerbovenhoek en selecteert u **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** . U moet het item **[!UICONTROL Experience Cloud Triggers]** zien.

Ga naar de volgende stap als u deze ziet.

Als dat niet het geval is, neemt u contact op met uw Adobe-accountmanager of professionele servicepartner. Zie [ het Activeren van de functionaliteit ](../../integrating/using/configuring-triggers-in-experience-cloud.md#activating-the-functionality).

**probeer creërend een trekker**

Volg de stappen die in [ worden beschreven Creërend een in kaart gebrachte trekker in Campagne ](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) om een trekker tot stand te brengen.

Als de trigger is gemaakt, gaat u verder naar de volgende stap. Als dat niet het geval is, betekent dit dat de verbinding met het eindpunt van de trigger is mislukt. Controleer of Triggers is ingericht in Experience Cloud (Activeringsservices). Als dit niet het geval is, neemt u contact op met de Adobe-accountmanager of de professionele servicepartner. De volgende informatie is vereist:

* Marketing Cloud Company Name
* Organisatie-ID
* Analytics Login Company (kan het zelfde zijn als de Naam van het Bedrijf van Marketing Cloud)

**probeer het publiceren van de trekker**

Volg de stappen die in [ worden beschreven Creërend een in kaart gebrachte trekker in Campagne ](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) om de trekker te publiceren.

Als de publicatie is gelukt, gaat u verder naar de volgende stap. Als dat niet het geval is, neemt u contact op met Adobe om de instantie opnieuw te starten en probeert u het opnieuw.

**produceer de trekker van de website**

Volg de stappen die in [ worden beschreven het Uitgeven van het transactionele berichtmalplaatje ](../../integrating/using/using-triggers-in-campaign.md#editing-the-transactional-message-template) worden beschreven om het transactiesjabloon uit te geven en te publiceren. Test vervolgens het genereren van de trigger van de website.

Als de trigger wordt ontvangen door Analytics, gaat u naar de volgende stap. Indien niet, controleer de volgende punten:

* Trigger is ingeschakeld voor Analytics
* De website die MCID en Analytics gebruikt, is ingeschakeld in DTM
* De juiste analytische rapportsuite wordt gebruikt bij het maken van triggers

**wordt de trekker ontvangen door Campagne?**

Als niet, controleer of de trekker van de pijpleiding wordt ontvangen.

Als niet, contacteer Adobe om de configuratie van de pijpleidingseindpunten te controleren.

Zo ja, volg deze richtsnoeren:

* Controleer het type van verzoeningsidentiteitskaart in de gegevensbron van de Campagne.
* CustomerId-gegevensbron wordt gemaakt via Customer Attributes.
* Controleer de gegevensbron-id.
* Vraag Adobe om de instantie van de Campagne na de configuratie van Datasource opnieuw te beginnen.
* Controleer het parseren van de trigger in het triggerrapport.

**is de trekker in hangende status?**

Indien niet, ga naar de volgende stap. Zo ja, volg deze richtsnoeren:

* Controleer of de transactiesjabloon is gepubliceerd.
* Controleer of het profiel niet in lijst van gewezen personen is.
* Controleer de toepassing van typologische regels.
* Controleer de logboeken van het transactiemelding bericht.

**is het bericht geldig?**

Controleer de volgende items als het bericht niet geldig is:

* Voor de gebieden van de trekkerverrijking die als ongeldig worden gemerkt, bevestig het transactiesjabloon van de bijbehorende inzamelingen eventCusResource.
* De berichtindeling valideren
