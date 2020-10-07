---
title: Informatie over de Adobe Experience Platform-gegevensconnector
description: Beheer XDM-schema's om uw Campaign Standard-gegevens beschikbaar te maken op Adobe Experience Platform.
page-status-flag: never-activated
uuid: 867b1c4b-4c79-4c52-9d0a-ef71993e50a2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuring-channels
discoiquuid: 406c955a-b2d2-4099-9918-95f5fa966067
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '760'
ht-degree: 4%

---


# Informatie over de Adobe Experience Platform-gegevensconnector {#about-aep-data-connector}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connector bevindt zich momenteel in bèta, die vaak zonder voorafgaande kennisgeving kan worden bijgewerkt. Klanten moeten op Azure (momenteel alleen in bèta voor Noord-Amerika) worden gehost om toegang te krijgen tot deze mogelijkheden. Neem contact op met de klantenservice van Adobe als u toegang wilt.

Adobe Experience Platform Data Connector helpt bestaande klanten hun gegevens op Adobe Experience Platform beschikbaar te maken door XTK-gegevens (gegevens die in Campaign worden opgenomen) toe te wijzen aan XDM-gegevens (Experience Data Model) op Adobe Experience Platform.

Merk op dat de schakelaar **uni-directioneel** is en de gegevens van Adobe Campaign Standard naar Adobe Experience Platform verzendt. De gegevens worden nooit van de Adobe Experience Platform naar Adobe Campaign Standard verzonden.

Adobe Experience Platform Data Connector is bedoeld voor **gegevensengineers** die de aangepaste bronnen van Adobe Campaign Standard begrijpen en begrijpen hoe het algemene gegevensschema van de klant zich in Adobe Experience Platform moet bevinden.

In de volgende secties worden de belangrijkste stappen beschreven voor het uitvoeren van een gegevenstoewijzing tussen Campaign Standard en Adobe Experience Platform. Dit begint met de verwezenlijking van een schema XDM en een dataset.

Hoe kan ik-video&#39;s zijn ook beschikbaar op [deze pagina](https://docs.adobe.com/content/help/nl-NL/campaign-learn/campaign-standard-tutorials/administrating/adobe-experience-platform-data-connector/understanding-the-adobe-experience-platform-data-connector.html).

>[!NOTE]
>Zodra de Verbinding van Gegevens van Adobe Experience Platform wordt gevormd en de gegevens met succes in Adobe Experience Platform worden opgenomen, moet u de dataset toelaten zodat de gegevens in het Profiel van de Klant in real time worden omvat.
>
>Dit kan worden uitgevoerd via de API&#39;s of de Adobe Experience Platform-interface. Raadpleeg de desbetreffende documentatie voor meer informatie:
>
>* [Een gegevensset inschakelen voor realtime klantprofiel](https://docs.adobe.com/content/help/en/experience-platform/rtcdp/datasets/dataset.html)
>* [Een gegevensset configureren voor realtime profiel en identiteitsservice van klanten met behulp van API&#39;s](https://docs.adobe.com/content/help/en/experience-platform/catalog/api/getting-started.html)


## Belangrijkste concepten {#key-concepts}

* Uit de functie voor het toewijzen van vakken is alleen beschikbaar voor velden die standaard in Campaign Standard zijn opgegeven. Voor het opnemen van alle douanegebieden en middelen, moet elke klant zijn eigen afbeelding bepalen.

* Adobe Experience Platform Data Connector zorgt ervoor dat profielgegevens regelmatig via het platform worden doorgegeven. &#x200B; De intervalduur is 15 mn. Deze waarde kan worden gewijzigd met [Adobe Experience Platform API&#39;s](https://docs.adobe.com/content/help/en/experience-platform/ingestion/home.html).

* Gegevenstechnicus kan de toewijzing publiceren, wijzigen en pauzeren van Campagne naar Adobe Experience Platform.

* Elke doeldimensie kan worden toegewezen. De aanbeveling is één enkele afbeelding te maken voor alle gebieden in één enkele doeldimensie.

* Alle profielupdates, inclusief kanaalopt-ins/opt-outs, maken deel uit van de batchupdate.

* Wijzigingen in Adobe Campaign Standard- of XDM-schema moeten handmatig opnieuw worden toegewezen. &#x200B;

* Gegevens voor bijhouden van logbestanden en uitzending worden automatisch als Experience Events aan Adobe Experience Platform doorgegeven. Deze inname wordt in real-time gestreamd naar Adobe Experience Platform.

* Experience Cloud ID Service (ECID) is een apparaat-id die standaard wordt verzonden met Experience Events.

   Het is een unieke en permanente id die aan een bezoeker is toegewezen en die door de identiteitsdienst van het Platform kan worden gebruikt om dezelfde bezoeker en hun gegevens in verschillende Experience Cloud-oplossingen te identificeren. Raadpleeg de Help bij [de](https://docs.adobe.com/content/help/en/id-service/using/home.html)Experience Cloud Identity Service voor meer informatie.

   >[!NOTE]
   >
   >Houd er rekening mee dat als twee of meer profielen hetzelfde apparaat delen, de ECID hetzelfde is voor deze twee profielen in de Unified Identity-service.

## Beperkingen {#limitations}

* De overdracht van abonnementsgebeurtenissen buiten de box wordt niet ondersteund. Om abonnementsgebeurtenissen over te brengen, kunt u overeenkomstige XDM en dataset op Adobe Experience Platform tot stand brengen, dan een afbeelding van douanegegevens voor deze gegevens vormen.

* Met betrekking tot privacyverzoeken (zowel de Acties van de Toegang als van de Schrapping), moeten de klanten afzonderlijke verzoeken via de Dienst [van de Kern van de](https://docs.adobe.com/content/help/en/experience-platform/privacy/home.html#how-to-use-privacy-service-to-manage-privacy-job-requests)Privacy plaatsen: één voor Campagne en één voor Adobe Experience Platform. Zie [Informatie over privacyverzoeken](https://helpx.adobe.com/campaign/kb/acs-privacy.html#righttoaccess) en Privacyverzoeken [](https://helpx.adobe.com/nl/campaign/kb/acs-privacy.html#ManagingPrivacyRequests) beheren in Campagne voor meer informatie.

* Voor elk XDM gebied, moet het DULE etiketteren in Adobe Experience Platform worden gedaan. Dit is de verantwoordelijkheid van de klant om DULE-labels toe te passen.

* Beperkingen op marketingacties worden pas van toepassing nadat DULE-labels zijn toegepast in Adobe Experience Platform. Daarvoor zijn alle gegevens beschikbaar voor alle soorten marketingacties.

* Elke 15 minuten wordt de batchtaak uitgevoerd en worden de records geïdentificeerd die zijn gewijzigd sinds de laatste batch. Als alle records tegelijk veranderen, kan een knelpunt in de prestaties de opname van alle profielen beheren
