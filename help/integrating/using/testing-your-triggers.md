---
title: Uw triggers testen
description: Leer tips voor het oplossen van problemen waarmee u de meest voorkomende problemen kunt oplossen die u tegenkomt bij het gebruik van Triggers met Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 66628f2a-6ed3-4b12-b2ed-9b9eec440dc3
source-git-commit: 602878233e919d01f3972167cb6d3a1acc4cfc02
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 1%

---

# Uw triggers testen{#testing-your-triggers}

De volgende tips voor het oplossen van problemen helpen u de meest voorkomende problemen op te lossen die u kunt tegenkomen bij het gebruik van Triggers met Adobe Campaign:

**Is de functionaliteit geactiveerd?**

Als u wilt controleren of de integratie Triggers - campagne is geactiveerd, klikt u op het Adobe Campaign-logo in de linkerbovenhoek en selecteert u **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]**. U moet de **[!UICONTROL Experience Cloud Triggers]** item.

Ga naar de volgende stap als u deze ziet.

Als dat niet het geval is, neemt u contact op met de Adobe-accountmanager of de professionele servicepartner. Zie [De functionaliteit activeren](../../integrating/using/configuring-triggers-in-experience-cloud.md#activating-the-functionality).

**Probeer een trigger te maken**

Voer de in [Een toegewezen trigger maken in Campagne](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) om een trigger te maken.

Als de trigger is gemaakt, gaat u verder naar de volgende stap. Zo niet, dan betekent dit dat de verbinding met het eindpunt van de trigger is mislukt. Controleer of Triggers is ingericht in Experience Cloud (Activeringsservices). Als dit niet het geval is, neemt u contact op met de manager van uw Adobe-account of de professionele servicepartner. De volgende informatie is vereist:

* Bedrijfsnaam Marketing Cloud
* Organisatie-id
* Login van de Analyse Bedrijf (kan het zelfde zijn als de Naam van het Bedrijf van de Marketing Cloud)

**Probeer de trigger te publiceren**

Voer de in [Een toegewezen trigger maken in Campagne](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) om de trigger te publiceren.

Als de publicatie is gelukt, gaat u verder naar de volgende stap. Als dat niet het geval is, neemt u contact op met Adobe om de instantie opnieuw te starten en probeert u het opnieuw.

**De trigger van de website genereren**

Voer de in [De transactiemalplaatje van het bericht uitgeven](../../integrating/using/using-triggers-in-campaign.md#editing-the-transactional-message-template) om de transactiesjabloon te bewerken en te publiceren. Test vervolgens het genereren van de trigger van de website.

Als de trigger wordt ontvangen door Analytics, gaat u naar de volgende stap. Indien niet, controleer de volgende punten:

* Trigger is ingeschakeld voor Analytics
* De website die MCID en Analytics gebruikt, is ingeschakeld in DTM
* De juiste analytische rapportsuite wordt gebruikt bij het maken van triggers

**Wordt de trigger ontvangen door Campaign?**

Als niet, controleer of de trekker van de pijpleiding wordt ontvangen.

Als niet, contacteer Adobe om de configuratie van de pijpleidingseindpunten te controleren.

Zo ja, volg deze richtsnoeren:

* Controleer het type van verzoeningsidentiteitskaart in de gegevensbron van de Campagne.
* CustomerId-gegevensbron wordt gemaakt via Customer Attributes.
* Controleer de gegevensbron-id.
* Vraag Adobe om de instantie van de Campagne na de configuratie opnieuw te beginnen DataSource.
* Controleer het parseren van de trigger in het triggerrapport.

**Is de trigger in status in behandeling?**

Indien niet, ga naar de volgende stap. Zo ja, volg deze richtsnoeren:

* Controleer of de transactiesjabloon is gepubliceerd.
* Controleer of het profiel niet in lijst van gewezen personen is.
* Controleer de toepassing van typologische regels.
* Controleer de logboeken van het transactiemelding bericht.

**Is het bericht geldig?**

Controleer de volgende items als het bericht niet geldig is:

* Voor de gebieden van de trekkerverrijking die als ongeldig worden gemerkt, bevestig het transactiesjabloon van de bijbehorende inzamelingen eventCusResource.
* De berichtindeling valideren
