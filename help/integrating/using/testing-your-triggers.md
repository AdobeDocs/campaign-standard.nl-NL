---
title: Uw triggers testen
description: null
page-status-flag: never-activated
uuid: b3a6667d-e843-4ad6-817e-d91542b5f2e2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
discoiquuid: f67e69f2-09fb-4f33-b2c3-c67a060743e3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: bd74905985734412b4fb11ad11d70faf9fcc9ca6
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 0%

---


# Uw triggers testen{#testing-your-triggers}

De volgende tips voor het oplossen van problemen helpen u de meest voorkomende problemen op te lossen die u kunt tegenkomen bij het gebruik van Triggers met Adobe Campaign:

**Is de functionaliteit geactiveerd?**

Als u wilt controleren of de integratie Triggers - campagne is geactiveerd, klikt u op het Adobe Campaign-logo in de linkerbovenhoek en selecteert u **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]**. Je moet het **[!UICONTROL Experience Cloud Triggers]** object zien.

Ga naar de volgende stap als u deze ziet.

Als dat niet het geval is, neemt u contact op met uw Adobe-accountmanager of professionele servicepartner. Zie De functionaliteit [activeren](../../integrating/using/configuring-triggers-in-experience-cloud.md#activating-the-functionality).

**Probeer een trigger te maken**

Voer de stappen uit die worden beschreven in [Een toegewezen trigger maken in Campagne](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) om een trigger te maken.

Als de trigger is gemaakt, gaat u verder naar de volgende stap. Zo niet, dan betekent dit dat de verbinding met het eindpunt van de trigger is mislukt. Controleer of Triggers is ingericht in Experience Cloud (Activeringsservices). Als dat niet het geval is, neemt u contact op met de manager of de professionele servicepartner van Adobe. De volgende informatie is vereist:

* Bedrijfsnaam van Marketing Cloud
* IMS Organisatie-id
* Analytics Login Company (kan het zelfde zijn als de Bedrijfsnaam van de Onderneming van de Marketing Cloud)

**Probeer de trigger te publiceren**

Voer de stappen uit die worden beschreven in [Een toegewezen trigger maken in Campagne](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) om de trigger te publiceren.

Als de publicatie is gelukt, gaat u verder naar de volgende stap. Als dat niet het geval is, neemt u contact op met Adobe om de instantie opnieuw te starten en het opnieuw te proberen.

**De trigger van de website genereren**

Voer de stappen uit die worden beschreven in [Het transactiemalplaatje](../../integrating/using/using-triggers-in-campaign.md#editing-the-transactional-message-template) bewerken en publiceren van de transactiesjabloon. Test vervolgens het genereren van de trigger van de website.

Ga naar de volgende stap als de trigger door Analytics is ontvangen. Indien niet, controleer de volgende punten:

* Trigger is ingeschakeld voor Analytics
* De website die MCID en Analytics gebruikt, is ingeschakeld in DTM
* De juiste Analytics-rapportsuite wordt gebruikt bij het maken van triggers

**Wordt de trigger ontvangen door Campaign?**

Als niet, controleer of de trekker van de pijpleiding wordt ontvangen.

Als dat niet het geval is, neemt u contact op met Adobe om de configuratie van de eindpunten van de pijplijn te controleren.

Zo ja, volg de volgende hulplijnen:

* Controleer het type van verzoeningsidentiteitskaart in de gegevensbron van de Campagne.
* CustomerId-gegevensbron wordt gemaakt via Customer Attributes.
* Controleer de gegevensbron-id.
* Vraag Adobe om de instantie van de Campagne na de configuratie opnieuw te beginnen DataSource.
* Controleer het parseren van de trigger in het triggerrapport.

**Is de trigger in status in behandeling?**

Indien niet, ga naar de volgende stap. Zo ja, volg de volgende hulplijnen:

* Controleer of de transactiesjabloon is gepubliceerd.
* Controleer of het profiel zich niet op lijst van afgewezen personen bevindt.
* Controleer de toepassing van typologische regels.
* Controleer de logboeken van het transactiemelding bericht.

**Is het bericht geldig?**

Controleer de volgende items als het bericht niet geldig is:

* Voor de gebieden van de trekkerverrijking die als ongeldig worden gemerkt, bevestig het transactiesjabloon van de bijbehorende inzamelingen eventCusResource.
* De berichtindeling valideren

