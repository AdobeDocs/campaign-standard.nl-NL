---
title: Aangepaste bronnen voor campagne toewijzen en eigen entiteiten voor dynamiek 365
description: Leer hoe u bronnen en entiteiten in kaart brengt in de context van de integratie tussen Adobe Campaign Standard en Microsoft Dynamics 365.
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e11de4d4482400e62be2db076c88da5ae30d60cc
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 0%

---


# De middelen van de Campagne van de kaart en Dynamica 365 entiteiten

Leer hoe u aangepaste bronnen en aangepaste entiteiten in kaart brengt in het kader van de integratie tussen Adobe Campaign Standard en Microsoft Dynamics 365.

>[!CAUTION]
>
>Deze mogelijkheid is niet beschikbaar buiten de verpakking als onderdeel van het product. Voor de implementatie moet Adobe Consulting worden ingeschakeld. Neem contact op met uw Adobe-vertegenwoordiger voor meer informatie.

## Vereisten

De integratie [van de Dynamica 365-Adobe Campaign Standard van](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md) Microsoft steunt douaneentiteiten, toelatend douaneentiteiten in Dynamiek 365 om aan overeenkomstige douanemiddelen in Campagne worden gesynchroniseerd.

De nieuwe gegevens in de douanemiddelen kunnen voor verscheidene doeleinden, met inbegrip van segmentatie en verpersoonlijking worden gebruikt.

De integratie ondersteunt zowel gekoppelde als niet-gekoppelde tabellen. Koppeling wordt ondersteund tot drie niveaus (niveau1->niveau2->niveau3).

>[!CAUTION]
>
>Als om het even welk dossier van het middel van de Campagne persoonlijke informatie bevat, zijn de specifieke aanbevelingen van toepassing. Meer informatie [in deze sectie](../../integrating/using/notices-and-recommendations-for-acs-and-ms-dynamics.md#privacy-linked-resources).

## Kennisgevingen

Wanneer het vormen van de gegevensstromen van de douaneentiteit, is het belangrijk om zich van het volgende bewust te zijn:

* Het creëren van en het wijzigen van de douanemiddelen van de Campagne zijn gevoelige verrichtingen die door deskundige slechts gebruikers moeten worden uitgevoerd.
* Voor de stromen van de gegevens van de douaneentiteit, verandering het volgen binnen Dynamiek 365 voor gesynchroniseerde douaneentiteiten moet worden toegelaten.
* Als een ouder en verbonden kindverslag dicht bij de zelfde tijd in Dynamiek 365, wegens de parallelle verwerking van de integratie worden gecreeerd, is er een lichte kans dat een nieuw kindverslag aan Campaign vóór zijn ouderverslag zou kunnen worden geschreven.

* Als het bovenliggende en onderliggende item aan de Campagnezijde zijn gekoppeld met de optie **1 cardinaliteit (eenvoudige koppeling** ), blijft de onderliggende record verborgen en ontoegankelijk (via UI of API) totdat de bovenliggende record in Campaign wordt ontvangen.

* (Ervan uitgaande dat **1 cardinaliteit een eenvoudige koppeling** is in Campagne) Als de onderliggende record wordt bijgewerkt of verwijderd in Dynamics 365 en die wijziging wordt geschreven naar Campagne voordat de bovenliggende record wordt weergegeven in Campaign (niet waarschijnlijk, maar een externe mogelijkheid), wordt die update of verwijdering niet verwerkt in Campagne en wordt een fout gegenereerd. In het geval van een update moet de betreffende record opnieuw worden bijgewerkt in Dynamics 365 om de bijgewerkte record te synchroniseren. In geval van schrapping moet de betrokken record afzonderlijk aan de campagnezijde worden vermeld, aangezien er geen record meer is in Dynamics 365 om te verwijderen of bij te werken.

* Als u in een situatie terechtkomt waarin u denkt dat u kindverslagen hebt verborgen en geen manier om tot hen toegang te hebben, kunt u het type van kardinale verbinding in **0 of 1 kardinaliteit eenvoudige verbinding** tijdelijk veranderen om tot die verslagen toegang te hebben.

Een uitgebreider overzicht van aangepaste campagnebronnen vindt u [in deze sectie](../../developing/using/key-steps-to-add-a-resource.md).
