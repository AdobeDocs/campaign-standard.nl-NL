---
title: Informatie over de integratie van Campaign-Audience Manager of de People core-service
description: Met de Audience Manager/People core service integration kunt u soorten publiek of segmenten delen binnen de verschillende Adobe Experience Cloud-oplossingen.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
feature: Triggers
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: e8b96c66-82f7-4adb-88b2-b7e0f7c4a96f
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '518'
ht-degree: 3%

---

# Informatie over de integratie van Campaign-Audience Manager of de People core-service{#about-campaign-audience-manager-or-people-core-service-integration}

>[!CAUTION]
>
>Afhankelijk van de uitgewisselde gegevens kunnen er wettelijke beperkingen gelden voor het invoerende publiek in Adobe Campaign.

Met Adobe Campaign kunt u soorten publiek/segmenten uitwisselen en delen met verschillende Adobe Experience Cloud-toepassingen. Het integreren **Adobe Campaign** met **de kerndienst van de Mensen** (ook als **wordt bekend de kerndienst van Profielen &amp; van het publiek**) of Adobe Audience Manager staat u toe:

* Importeer soorten publiek/segmenten van verschillende Adobe Experience Cloud-oplossingen naar Adobe Campaign. Soorten publiek kan worden geïmporteerd vanuit het menu **[!UICONTROL Audiences]** in Adobe Campaign.
* Exporteer soorten publiek als gedeeld publiek/segmenten. Deze doelgroepen kunnen worden gebruikt in de verschillende Adobe Experience Cloud-oplossingen die u gebruikt. Soorten publiek kunnen worden geëxporteerd nadat activiteiten in een werkstroom als doel zijn opgegeven, met behulp van de **[!UICONTROL Save audience]** -activiteit.

Integratie ondersteunt twee typen Adobe Experience Cloud-id&#39;s:

* **identiteitskaart van de Bezoeker**: dit type van identiteitskaart staat u toe om de bezoekers van Adobe Experience Cloud met de profielen van Adobe Campaign te verzoenen. Zodra een verbinding via Adobe IMS is ingeschakeld, wordt de Marketing Cloud Visitor ID Service geactiveerd, die de permanente cookie vervangt die door Adobe Campaign wordt gebruikt. Zo kunt u een bezoeker identificeren en deze vervolgens koppelen aan een profiel.
  <br> Een bezoekersidentiteitskaart wordt verbonden met een profiel zodra het profiel in een e-mail klikt die via Adobe Campaign wordt verzonden:
   * Als het profiel al een bezoeker-id heeft, kunnen Adobe Campaign het profiel met de browsergegevens van het profiel herstellen en automatisch koppelen aan de bezoeker-id.
   * Als er geen bezoeker-id wordt gevonden, wordt een nieuwe id gemaakt. Deze bezoeker-id wordt opgeslagen in de logboeken voor het bijhouden van profielen.

  De id wordt dan herkend door de andere Adobe Marketing Cloud-toepassingen met dezelfde CNAME.

* **Verklaarde identiteitskaart**: dit type van identiteitskaart staat u toe om het even welk type van gegevens met elementen van het gegevensbestand van Adobe Campaign te verzoenen. Het wordt in Adobe Campaign vertegenwoordigd als een vooraf gedefinieerde afstemmingssleutel. Bij het uitwisselen van gegevens worden de Adobe Campaign-database-id&#39;s gehashed. Deze hashed-id&#39;s worden vervolgens vergeleken met de hashed-id&#39;s van het Adobe Marketing Cloud-publiek dat betrokken is bij het importeren of exporteren.
  <br> deze integratie steunt regelmatige gedeclareerde IDs, gehakt verklaarde IDs en gecodeerde verklaarde IDs.

  >[!NOTE]
  >
  >De verklaarde gegevensbron van identiteitskaart kan nu ook met de dienstintegratie van de Kern van Mensen worden gebruikt.
  >
  >Als u de de dienstintegratie van de Kern van Mensen gebruikt en de integratie van Audience Manager wilt toevoegen, zult u de hulp van een consultant van Adobe Audience Manager nodig hebben om te vermijden verlies van alle verzamelde identiteitskaart- syncs wanneer het overgaan aan het gebruiken van deze Gedeclareerde gegevensbron van identiteitskaart in een context van Adobe Audience Manager.


  Met codering kunt u gecodeerde gegevens delen in gegevensbronnen (bijvoorbeeld PII) met de gedeclareerde id door het versleutelingsalgoritme op te geven.

  Als u bijvoorbeeld gecodeerde e-mailadressen of SMS-nummers kunt decoderen, kunt u ook getriggerde berichten naar uw gebruikers verzenden, zelfs als hun profiel niet bestaat in de Adobe Campaign-database.

In het volgende diagram wordt beschreven hoe deze integratie werkt. Hier staat AAM voor Adobe Audience Manager en ACS voor Adobe Campaign Standard.

![](assets/aam_diagram.png)
