---
title: Informatie over de integratie van Campaign-Audience Manager of de People core-service
description: Met de Audience Manager/de de kernde dienstintegratie van Mensen, kunt u publiek of segmenten binnen de verschillende oplossingen van Adobe Experience Cloud delen.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: e8b96c66-82f7-4adb-88b2-b7e0f7c4a96f
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '518'
ht-degree: 7%

---

# Informatie over de integratie van Campaign-Audience Manager of de People core-service{#about-campaign-audience-manager-or-people-core-service-integration}

>[!CAUTION]
>
>Afhankelijk van de uitgewisselde gegevens kunnen er wettelijke beperkingen gelden voor het invoerende publiek in Adobe Campaign.

Met Adobe Campaign kunt u soorten publiek/segmenten uitwisselen en delen met verschillende Adobe Experience Cloud-toepassingen. Integreren **Adobe Campaign** with **Personenkern-service** (ook bekend als **Profielen en publiek kernservice**) of Adobe Audience Manager biedt u de volgende mogelijkheden:

* Importeer soorten publiek/segmenten van verschillende Adobe Experience Cloud-oplossingen naar Adobe Campaign. Soorten publiek kan worden geïmporteerd uit het **[!UICONTROL Audiences]** in Adobe Campaign.
* Exporteer soorten publiek als gedeeld publiek/segmenten. Deze doelgroepen kunnen worden gebruikt in de verschillende Adobe Experience Cloud-oplossingen die u gebruikt. Soorten publiek kunnen worden geëxporteerd nadat activiteiten in een workflow als doel zijn opgegeven. Hierbij wordt gebruikgemaakt van de optie **[!UICONTROL Save audience]** activiteit.

Integratie ondersteunt twee typen Adobe Experience Cloud-id&#39;s:

* **Bezoeker-id**: Met dit type id kunt u Adobe Experience Cloud-bezoekers combineren met Adobe Campaign-profielen. Zodra een verbinding via Adobe IMS is ingeschakeld, wordt de Marketing Cloud Visitor ID Service geactiveerd, die de permanente cookie vervangt die door Adobe Campaign wordt gebruikt. Zo kunt u een bezoeker identificeren en deze vervolgens koppelen aan een profiel.
  <br>Een bezoekersidentiteitskaart wordt verbonden met een profiel zodra het profiel in een e-mail klikt die via Adobe Campaign wordt verzonden:
   * Als het profiel al een bezoeker-id heeft, kunnen Adobe Campaign het profiel met de browsergegevens van het profiel herstellen en automatisch koppelen aan de bezoeker-id.
   * Als er geen bezoeker-id wordt gevonden, wordt een nieuwe id gemaakt. Deze bezoeker-id wordt opgeslagen in de logboeken voor het bijhouden van profielen.

  De id wordt dan herkend door de andere Adobe Marketing Cloud-toepassingen met dezelfde CNAME.

* **Opgegeven id**: met dit type id kunt u elk type gegevens combineren met elementen uit de Adobe Campaign-database. Het wordt in Adobe Campaign vertegenwoordigd als een vooraf gedefinieerde afstemmingssleutel. Bij het uitwisselen van gegevens worden de Adobe Campaign-database-id&#39;s gehashed. Deze hashed-id&#39;s worden vervolgens vergeleken met de hashed-id&#39;s van het Adobe Marketing Cloud-publiek dat betrokken is bij het importeren of exporteren.
  <br>Deze integratie ondersteunt reguliere gedeclareerde id&#39;s, gehashte gedeclareerde id&#39;s en gecodeerde gedeclareerde id&#39;s.

  >[!NOTE]
  >
  >De gegevensbron Declared ID kan nu ook worden gebruikt met de integratie van de People-kernservice.
  >
  >Als u de de dienstintegratie van de Kern van Mensen gebruikt en de integratie van de Audience Manager wilt toevoegen, zult u de hulp van een consultant van Adobe Audience Manager nodig hebben om te vermijden verlies van alle verzamelde syncs van identiteitskaart wanneer het overgaan aan het gebruiken van deze Gedeclareerde gegevensbron van identiteitskaart in een context van Adobe Audience Manager.


  Met codering kunt u gecodeerde gegevens delen in gegevensbronnen (bijvoorbeeld PII) met de gedeclareerde id door het versleutelingsalgoritme op te geven.

  Als u bijvoorbeeld gecodeerde e-mailadressen of SMS-nummers kunt decoderen, kunt u ook getriggerde berichten naar uw gebruikers verzenden, zelfs als hun profiel niet bestaat in de Adobe Campaign-database.

In het volgende diagram wordt beschreven hoe deze integratie werkt. Hier staat AAM voor Adobe Audience Manager en ACS voor Adobe Campaign Standard.

![](assets/aam_diagram.png)
