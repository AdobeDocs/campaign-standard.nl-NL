---
title: Info over Adobe Experience Platform Data Connector
description: Beheer XDM-schema's om uw standaardgegevens voor campagnes beschikbaar te maken op het Adobe Experience Platform.
page-status-flag: never-activated
uuid: 867b1c4b-4c79-4c52-9d0a-ef71993e50a2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuring-channels
discoiquuid: 406c955a-b2d2-4099-9918-95f5fa966067
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 9388df151eabbc6f63461e854d0276c14d9ef93d

---


# Info over Adobe Experience Platform Data Connector {#about-aep-data-connector}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connector is momenteel in bèta, die vaak zonder kennisgeving kan worden bijgewerkt. Klanten moeten op Azure (momenteel alleen in bèta voor Noord-Amerika) worden gehost om toegang te krijgen tot deze mogelijkheden. Neem contact op met de klantenservice van Adobe als u toegang wilt.

Met de Adobe Experience Platform Data Connector kunnen bestaande klanten hun gegevens beschikbaar maken op het Adobe Experience Platform door XTK-gegevens (gegevens die in Campaign worden opgenomen) toe te wijzen aan Experience Data Model (XDM)-gegevens op het Adobe Experience Platform.

De connector is **eenrichtingsgericht** en verzendt de gegevens van Adobe Campaign Standard naar Adobe Experience Platform. De gegevens worden nooit van het Adobe Experience Platform naar Adobe Campagne Standard verzonden.

De gegevensconnector van het Adobe Experience Platform is bedoeld voor **gegevensengineers** die de aangepaste bronnen van Adobe Campagne Standard begrijpen en begrijpen hoe het algemene gegevensschema van de klant zich in het Adobe Experience Platform moet bevinden.

In de volgende secties worden de belangrijkste stappen beschreven voor het uitvoeren van een gegevenstoewijzing tussen Campaign Standard en Adobe Experience Platform. Dit begint met de verwezenlijking van een schema XDM en een dataset.

Hoe kan ik-video&#39;s zijn ook beschikbaar op [deze pagina](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/administrating/adobe-experience-platform-data-connector/understanding-the-adobe-experience-platform-data-connector.html).

>[!NOTE]
>Zodra de Verbinding van de Gegevens van het Platform van de Ervaring van Adobe wordt gevormd en de gegevens in het Platform van de Ervaring van Adobe met succes worden opgenomen, moet u de dataset toelaten zodat de gegevens in het Profiel van de Klant in real time worden omvat.
>
>Dit kan worden uitgevoerd via de API&#39;s of de interface van het Adobe Experience Platform. Raadpleeg de desbetreffende documentatie voor meer informatie:
>
>* [Een gegevensset inschakelen voor realtime klantprofiel](https://docs.adobe.com/content/help/en/experience-platform/rtcdp/datasets/dataset.html)
>* [Een gegevensset configureren voor realtime profiel en identiteitsservice van klanten met behulp van API&#39;s](https://docs.adobe.com/content/help/en/experience-platform/catalog/api/getting-started.html)


## Belangrijkste concepten {#key-concepts}

* Uit de functie voor het toewijzen van vakken is alleen beschikbaar voor velden die standaard in de campagnestandaard zijn opgenomen. Voor het opnemen van alle douanegebieden en middelen, moet elke klant zijn eigen afbeelding bepalen.

* Adobe Experience Platform Data Connector stuurt profielgegevens regelmatig door het platform. &#x200B; De intervalduur is 15 mn. Deze waarde kan worden gewijzigd met API&#39;s van [Adobe Experience Platform](https://docs.adobe.com/content/help/en/experience-platform/ingestion/home.html).

* De gegevenstechnicus kan de toewijzing publiceren, wijzigen en pauzeren van Campagne aan het Platform van de Ervaring van Adobe.

* Elke doeldimensie kan worden toegewezen. De aanbeveling is één enkele afbeelding te maken voor alle gebieden in één enkele doeldimensie.

* Alle profielupdates, inclusief kanaalopt-ins/opt-outs, maken deel uit van de batchupdate.

* Wijzigingen in Adobe Campaign Standard of XDM-schema moeten handmatig opnieuw worden toegewezen. &#x200B;

* Gegevens van trackinglogbestanden en uitzendingen worden automatisch als Experience Events opgenomen in het Adobe Experience Platform. Deze opname wordt in real-time gestreamd naar het Adobe Experience Platform.

* Experience Cloud ID Service (ECID) is een apparaat-id die standaard wordt verzonden met Experience Events.

   Het is een unieke en permanente id die aan een bezoeker is toegewezen en die door de Platform Identity Service kan worden gebruikt om dezelfde bezoeker en zijn gegevens in verschillende Experience Cloud-oplossingen te identificeren. Raadpleeg de Help bij [de](https://docs.adobe.com/content/help/en/id-service/using/home.html)Experience Cloud Identity Service voor meer informatie.

   >[!NOTE]
   >
   >Houd er rekening mee dat als twee of meer profielen hetzelfde apparaat delen, de ECID hetzelfde is voor deze twee profielen in de Unified Identity-service.

## Beperkingen {#limitations}

* De overdracht van abonnementsgebeurtenissen buiten de box wordt niet ondersteund. Als u abonnementsgebeurtenissen wilt overbrengen, kunt u de bijbehorende XDM en gegevensset maken op het Adobe Experience Platform en vervolgens een aangepaste gegevenstoewijzing voor deze gegevens configureren.

* Met betrekking tot privacyverzoeken (zowel toegangs- als verwijderacties) moeten klanten afzonderlijke aanvragen indienen: één voor Campagne via de integratie van de Privacy Core Service (zie [deze sectie](https://helpx.adobe.com/campaign/kb/acs-privacy.html#righttoaccess)), en één voor het Platform van de Ervaring van Adobe via zijn [Privacy Service](https://helpx.adobe.com/campaign/kb/acs-privacy.html#ccpa). Zie [deze pagina](https://helpx.adobe.com/campaign/kb/acs-privacy.html#righttoaccess)voor meer informatie over aanvragen voor toegang en verwijderen.

* Voor elk XDM-veld moet de DULE-labeling worden uitgevoerd in het Adobe Experience Platform. Dit is de verantwoordelijkheid van de klant om DULE-labels toe te passen.

* Beperkingen op marketingacties worden alleen van toepassing nadat DULE-labels zijn toegepast in het Adobe Experience Platform. Daarvoor zijn alle gegevens beschikbaar voor alle soorten marketingacties.

* Elke 15 minuten wordt de batchtaak uitgevoerd en worden de records geïdentificeerd die zijn gewijzigd sinds de laatste batch. Als alle records tegelijk veranderen, kan een knelpunt in de prestaties de opname van alle profielen beheren
